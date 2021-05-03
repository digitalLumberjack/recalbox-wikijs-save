---
title: Codeur rotatif via GPIO \(Contrôle du volume numérique\)
---

# Codeur rotatif via GPIO \(Contrôle du volume numérique\)

\(Ce bref guide et ce script python est adapté du [projet de Savetheclocktower](https://gist.github.com/savetheclocktower/9b5f67c20f6c04e65ed88f2e594d43c1) \[anglais\] trouvé sur GitHub\).

## But

Ce script est destiné à ceux qui veulent un bouton de volume physique sur un projet Recalbox, comme les machines d'arcade. Ce script est utile pour les bornes d'arcade avec des haut-parleurs qui n'ont pas leur propre bouton de volume physique, ou qui auraient des difficultés à déplacer le bouton de contrôle du haut-parleur près de l'utilisateur.

Ce script utilise un codeur rotatif standard à 5 broches et a été testé sur le codeur d'Adafruit. Cinq fils sont nécessaires pour ce codeur rotatif : trois pour la partie bouton \(A, B et terre\), et deux pour la partie touche \(commun et terre\). Voici une référence pour les broches GPIO de Raspberry Pi.

| Description | BCM \# | Board \# |
| :--- | :--- | :--- |
| bouton A | GPIO 26 | 37 |
| bouton B | GPIO 19 | 35 |
| bouton de la terre | pin de la terre en-dessous du GPIO 26 | 39 |
| touche commun | GPIO 13 | 33 |
| touche de la terre | pin de la terre opposé au GPIO 13 | 34 |

Vous pouvez utiliser les broches que vous voulez ; il suffit de mettre à jour le script `volume-monitor.sh` si vous les modifiez. Si vous n'avez pas de bouton poussoir dans votre codeur rotatif, laissez les broches inoccupées. N'importe quelle broche de terre peut être utilisée, ces broches sont juste suggérées à cause de leur proximité.

### Volume daemon

Le script ci-dessous fonctionne comme suit : il utilise les broches spécifiées, et lorsque le bouton est tourné d'une manière ou d'une autre, il utilise les états des broches A et B pour savoir si le bouton a été tourné vers la gauche ou vers la droite. Ainsi, il sait s'il faut augmenter ou diminuer le volume du système en réponse, ce qu'il fait avec le programme de ligne de commande **Amixer**.

1. Pour installer le script dans votre Recalbox : vous devez d'abord vous [connecter à votre Recalbox via ssh](/fr/tutoriels/systeme/acces/acces-root-via-terminal). 
2. Remonter la partition en lecture-écriture : `mount -o remount, rw /` 
3. Créez/éditez votre script **volume-monitor.py** dans **/recalbox/scripts** via nano : `nano /recalbox/scripts/volume-monitor.py` 
4. Copiez et collez le script du bas dans le fichier, puis enregistrez le fichier par la commande Ctrl+X :  
   _****_

   ```python
   #!/usr/bin/env python2

   """
   The daemon responsible for changing the volume in response to a turn or press
   of the volume knob.
   The volume knob is a rotary encoder. It turns infinitely in either direction.
   Turning it to the right will increase the volume; turning it to the left will
   decrease the volume. The knob can also be pressed like a button in order to
   turn muting on or off.
   The knob uses two GPIO pins and we need some extra logic to decode it. The
   button we can just treat like an ordinary button. Rather than poll
   constantly, we use threads and interrupts to listen on all three pins in one
   script.
   """

   import os
   import signal
   import subprocess
   import sys
   import threading

   from RPi import GPIO
   from multiprocessing import Queue

   DEBUG = False

   # SETTINGS
   # ========

   # The two pins that the encoder uses (BCM numbering).
   GPIO_A = 26   
   GPIO_B = 19

   # The pin that the knob's button is hooked up to. If you have no button, set
   # this to None.
   GPIO_BUTTON = 13 

   # The minimum and maximum volumes, as percentages.
   #
   # The default max is less than 100 to prevent distortion. The default min is
   # greater than zero because if your system is like mine, sound gets
   # completely inaudible _long_ before 0%. If you've got a hardware amp or
   # serious speakers or something, your results will vary.
   VOLUME_MIN = 60
   VOLUME_MAX = 96

   # The amount you want one click of the knob to increase or decrease the
   # volume. I don't think that non-integer values work here, but you're welcome
   # to try.
   VOLUME_INCREMENT = 1

   # (END SETTINGS)
   # 


   # When the knob is turned, the callback happens in a separate thread. If
   # those turn callbacks fire erratically or out of order, we'll get confused
   # about which direction the knob is being turned, so we'll use a queue to
   # enforce FIFO. The callback will push onto a queue, and all the actual
   # volume-changing will happen in the main thread.
   QUEUE = Queue()

   # When we put something in the queue, we'll use an event to signal to the
   # main thread that there's something in there. Then the main thread will
   # process the queue and reset the event. If the knob is turned very quickly,
   # this event loop will fall behind, but that's OK because it consumes the
   # queue completely each time through the loop, so it's guaranteed to catch up.
   EVENT = threading.Event()

   def debug(str):
     if not DEBUG:
       return
     print(str)

   class RotaryEncoder:
     """
     A class to decode mechanical rotary encoder pulses.
     Ported to RPi.GPIO from the pigpio sample here: 
     http://abyz.co.uk/rpi/pigpio/examples.html
     """

     def __init__(self, gpioA, gpioB, callback=None, buttonPin=None, buttonCallback=None):
       """
       Instantiate the class. Takes three arguments: the two pin numbers to
       which the rotary encoder is connected, plus a callback to run when the
       switch is turned.

       The callback receives one argument: a `delta` that will be either 1 or -1.
       One of them means that the dial is being turned to the right; the other
       means that the dial is being turned to the left. I'll be damned if I know
       yet which one is which.
       """

       self.lastGpio = None
       self.gpioA    = gpioA
       self.gpioB    = gpioB
       self.callback = callback

       self.gpioButton     = buttonPin
       self.buttonCallback = buttonCallback

       self.levA = 0
       self.levB = 0

       GPIO.setmode(GPIO.BCM)
       GPIO.setup(self.gpioA, GPIO.IN, pull_up_down=GPIO.PUD_UP)
       GPIO.setup(self.gpioB, GPIO.IN, pull_up_down=GPIO.PUD_UP)

       GPIO.add_event_detect(self.gpioA, GPIO.BOTH, self._callback)
       GPIO.add_event_detect(self.gpioB, GPIO.BOTH, self._callback)

       if self.gpioButton:
         GPIO.setup(self.gpioButton, GPIO.IN, pull_up_down=GPIO.PUD_UP)
         GPIO.add_event_detect(self.gpioButton, GPIO.FALLING, self._buttonCallback, bouncetime=500)


     def destroy(self):
       GPIO.remove_event_detect(self.gpioA)
       GPIO.remove_event_detect(self.gpioB)
       GPIO.cleanup()

     def _buttonCallback(self, channel):
       self.buttonCallback(GPIO.input(channel))

     def _callback(self, channel):
       level = GPIO.input(channel)
       if channel == self.gpioA:
         self.levA = level
       else:
         self.levB = level

       # Debounce.
       if channel == self.lastGpio:
         return

       # When both inputs are at 1, we'll fire a callback. If A was the most
       # recent pin set high, it'll be forward, and if B was the most recent pin
       # set high, it'll be reverse.
       self.lastGpio = channel
       if channel == self.gpioA and level == 1:
         if self.levB == 1:
           self.callback(1)
       elif channel == self.gpioB and level == 1:
         if self.levA == 1:
           self.callback(-1)

   class VolumeError(Exception):
     pass

   class Volume:
     """
     A wrapper API for interacting with the volume settings on the RPi.
     """
     MIN = VOLUME_MIN
     MAX = VOLUME_MAX
     INCREMENT = VOLUME_INCREMENT

     def __init__(self):
       # Set an initial value for last_volume in case we're muted when we start.
       self.last_volume = self.MIN
       self._sync()

     def up(self):
       """
       Increases the volume by one increment.
       """
       return self.change(self.INCREMENT)

     def down(self):
       """
       Decreases the volume by one increment.
       """
       return self.change(-self.INCREMENT)

     def change(self, delta):
       v = self.volume + delta
       v = self._constrain(v)
       return self.set_volume(v)

     def set_volume(self, v):
       """
       Sets volume to a specific value.
       """
       self.volume = self._constrain(v)
       output = self.amixer("set 'PCM' unmute {}%".format(v))
       self._sync(output)
       return self.volume

     def toggle(self):
       """
       Toggles muting between on and off.
       """
       if self.is_muted:
         output = self.amixer("set 'PCM' unmute")
       else:
         # We're about to mute ourselves, so we should remember the last volume
         # value we had because we'll want to restore it later.
         self.last_volume = self.volume
         output = self.amixer("set 'PCM' mute")

       self._sync(output)
       if not self.is_muted:
         # If we just unmuted ourselves, we should restore whatever volume we
         # had previously.
         self.set_volume(self.last_volume)
       return self.is_muted

     def status(self):
       if self.is_muted:
         return "{}% (muted)".format(self.volume)
       return "{}%".format(self.volume)

     # Read the output of `amixer` to get the system volume and mute state.
     #
     # This is designed not to do much work because it'll get called with every
     # click of the knob in either direction, which is why we're doing simple
     # string scanning and not regular expressions.
     def _sync(self, output=None):
       if output is None:
         output = self.amixer("get 'PCM'")

       lines = output.readlines()
       if DEBUG:
         strings = [line.decode('utf8') for line in lines]
         debug("OUTPUT:")
         debug("".join(strings))
       last = lines[-1].decode('utf-8')

       # The last line of output will have two values in square brackets. The
       # first will be the volume (e.g., "[95%]") and the second will be the
       # mute state ("[off]" or "[on]").
       i1 = last.rindex('[') + 1
       i2 = last.rindex(']')

       self.is_muted = last[i1:i2] == 'off'

       i1 = last.index('[') + 1
       i2 = last.index('%')
       # In between these two will be the percentage value.
       pct = last[i1:i2]

       self.volume = int(pct)

     # Ensures the volume value is between our minimum and maximum.
     def _constrain(self, v):
       if v < self.MIN:
         return self.MIN
       if v > self.MAX:
         return self.MAX
       return v

     def amixer(self, cmd):
       p = subprocess.Popen("amixer {}".format(cmd), shell=True, stdout=subprocess.PIPE)
       code = p.wait()
       if code != 0:
         raise VolumeError("Unknown error")
         sys.exit(0)

       return p.stdout


   if __name__ == "__main__":

     gpioA = GPIO_A
     gpioB = GPIO_B
     gpioButton = GPIO_BUTTON

     v = Volume()

     def on_press(value):
       v.toggle()
       print("Toggled mute to: {}".format(v.is_muted))
       EVENT.set()

     # This callback runs in the background thread. All it does is put turn
     # events into a queue and flag the main thread to process them. The
     # queueing ensures that we won't miss anything if the knob is turned
     # extremely quickly.
     def on_turn(delta):
       QUEUE.put(delta)
       EVENT.set()

     def consume_queue():
       while not QUEUE.empty():
         delta = QUEUE.get()
         handle_delta(delta)

     def handle_delta(delta):
       if v.is_muted:
         debug("Unmuting")
         v.toggle()
       if delta == 1:
         vol = v.up()
       else:
         vol = v.down()
       print("Set volume to: {}".format(vol))

     def on_exit(a, b):
       print("Exiting...")
       encoder.destroy()
       sys.exit(0)

     debug("Volume knob using pins {} and {}".format(gpioA, gpioB))

     if gpioButton != None:
       debug("Volume button using pin {}".format(gpioButton))

     debug("Initial volume: {}".format(v.volume))

     encoder = RotaryEncoder(GPIO_A, GPIO_B, callback=on_turn, buttonPin=GPIO_BUTTON, buttonCallback=on_press)
     signal.signal(signal.SIGINT, on_exit)

     while True:
       # This is the best way I could come up with to ensure that this script
       # runs indefinitely without wasting CPU by polling. The main thread will
       # block quietly while waiting for the event to get flagged. When the knob
       # is turned we're able to respond immediately, but when it's not being
       # turned we're not looping at all.
       # 
       # The 1200-second (20 minute) timeout is a hack; for some reason, if I
       # don't specify a timeout, I'm unable to get the SIGINT handler above to
       # work properly. But if there is a timeout set, even if it's a very long
       # timeout, then Ctrl-C works as intended. No idea why.
       EVENT.wait(1200)
       consume_queue()
   EVENT.clear()
   ```

5. _Marquer le script comme un fichier exécutable :_ `chmod +x /recalbox/scripts/volume-monitor.py` __
6. _Pour que le script de contrôle du volume démarre avec votre système, procédez comme suit :_`touch ~/custom.sh && chmod u+x ~/custom.sh` __
7. Ouvrez le script **custom.sh** dans l'éditeur nano :`nano ~/custom.sh` __
8. _Enfin, copiez et collez ce qui suit dans le fichier **custom.sh** et enregistrez avec Ctrl+X :_`python /recalbox/scripts/volume-monitor.py` __
9. _Redémarrez votre Recalbox en utilisant la commande de redémarrage :_ `reboot` __
10. _Profitez du nouveau contrôle de volume de votre matériel._

### Modifications du script

_Ces modifications se trouvent toutes sous la rubrique "Settings" du script **Volume-monitor.py**_


>ASTUCE !   
>_****_Veuillez patienter 3 secondes après l'apparition du menu d'Emulationstation AVANT de toucher le codeur rotatif. Tourner le codeur plus tôt peut bloquer le script et rendre le codeur insensible.
{.is-success}

_Si vous souhaitez modifier les deux broches par défaut utilisées par le codeur, modifiez les lignes suivantes dans le script. Veillez à utiliser les codes de numérotation BCM._

![](/migration-images/tutoriels/audio/image%20%28249%29.png)

`GPIO_A = 26`

`GPIO_B = 19`

_Si vous voulez changer la broche à laquelle le bouton poussoir est accroché, alors modifiez la ligne correspondante dans le script ci-dessous. Veillez à utiliser les codes de numérotation BCM. Si vous n'avez pas de bouton, réglez ce paramètre sur Aucun._

`GPIO_BUTTON = 13`

_Si vous souhaitez modifier la plage \(c'est-à-dire : min & max\) que le script module le volume du Raspberry Pi, alors éditez la ligne correspondante dans le script ci-dessous. Les chiffres sont exprimés en pourcentage. Le max par défaut est inférieur à 100 pour éviter toute distorsion. Le min par défaut est supérieur à zéro car si votre système est comme le mien, le son devient complètement inaudible bien avant 0%. Si vous avez un amplificateur matériel ou des haut-parleurs de qualité ou autre, vos résultats varieront._

`VOLUME_MIN = 60`

`VOLUME_MAX = 96`

_Si vous souhaitez que le volume de votre système change plus rapidement et soit plus sensible, modifiez la ligne correspondante dans le script ci-dessous. Le paramètre par défaut est 1, passez à 2 pour doubler le taux de changement de volume._

`VOLUME_INCREMENT = 1`

### Comment désinstaller le script

_Répétez les étapes 7 et 8 ci-dessus, mais en supprimant la ligne ajoutée à l'étape 8 ou en la commentant par l'ajout d'un hachage, par exemple la ligne se lit comme suit :_

`#python /recalbox/scripts/volume-monitor.py`

## Crédits

Je tiens à remercier _Substring_ pour l'aide qu'il nous a apporté en rendant possible ce guide et la modification de Recalbox.  
J'aimerais également remercier les autres développeurs de Recalbox pour avoir rendu ce merveilleux projet disponible.  
Et je voudrais remercier _savetheclocktower_ pour le code du projet original et pour son aide dans la conversion en Python2.

