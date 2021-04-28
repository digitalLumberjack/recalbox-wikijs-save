---
title: Commandes réseau pour RetroArch
---

# Commandes réseau pour RetroArch


>Les commandes réseau sont utilisées pour contrôler certaines parties de RetroArch. Pour ce faire, les commandes sont envoyées à RetroArch via UDP \(_User Datagram Protocol_\). En général, ces commandes sont envoyées via la fonction **Hotkey** du contrôleur. Par exemple, pour restaurer le jeu, vous appuyez sur les touches **Hotkey + A** ou pour sauvegarder le jeu, vous appuyez sur les touches **Hotkey + Y**.
{.is-info}

## Activer <a id="enable"></a>

Mais ces commandes peuvent également être envoyées à RetroArch via la ligne de commande ou les broches GPIO. Pour cela, vous devez activer l'option **commandes réseau** dans le menu RetroArch ou modifier la ligne suivante dans `retroarch.cfg` :

* `network_cmd_enable = "true"`

## Transmettre une commande via la ligne de commande <a id="send-a-command-via-the-command-line"></a>

Ce qui suit montre comment envoyer une commande réseau via la ligne de commande sous Linux :

* `echo -n "QUIT" | nc -u -w1 127.0.0.1 55355`

RetroArch est à l'écoute du port 55355 par défaut.

## Transmettre une commande via GPIO <a id="send-a-command-via-gpio"></a>

### Exemple d'application : <a id="application-example"></a>

Vous utilisez un boîtier de console de jeu rétro existant \(NES, N64, etc.\) et vous souhaitez utiliser le bouton de réinitialisation d'origine pour réinitialiser le jeu auquel vous jouez actuellement et non pas pour réinitialiser l'ensemble du matériel \(Raspberry Pi, etc.\).

Le script suivant montre comment envoyer la commande réseau **RESET** à RetroArch via les broches GPIO 5 et 6 pour réinitialiser le jeu en cours. :

```text
import RPi.GPIO as GPIO  
import time  
import socket  
# addressing information of target  
IPADDR = "127.0.0.1"  
PORTNUM = 55355  
# enter the data content of the UDP packet  
COMMAND = "RESET"  
# initialize a socket, think of it as a cable  
# SOCK_DGRAM specifies that this is UDP  
try:  
    s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)  
except socket.error:  
    print 'Failed to create socket'  
    sys.exit()  
GPIO.setmode(GPIO.BCM)  
GPIO.setup(3, GPIO.IN, pull_up_down=GPIO.PUD_UP)  
def exitEmulator(channel):  
    s.sendto(COMMAND, (IPADDR, PORTNUM))  
GPIO.add_event_detect(3, GPIO.FALLING, callback=exitEmulator, bouncetime=500)  
while True:  
    time.sleep(10)  
```

## Commandes <a id="commands"></a>

Les commandes suivantes sont prises en charge :

* FAST\_FORWARD
* FAST\_FORWARD\_HOLD
* LOAD\_STATE
* SAVE\_STATE
* FULLSCREEN\_TOGGLE
* QUIT
* STATE\_SLOT\_PLUS
* STATE\_SLOT\_MINUS
* REWIND
* MOVIE\_RECORD\_TOGGLE
* PAUSE\_TOGGLE
* FRAMEADVANCE
* RESET
* SHADER\_NEXT
* SHADER\_PREV
* CHEAT\_INDEX\_PLUS
* CHEAT\_INDEX\_MINUS
* CHEAT\_TOGGLE
* SCREENSHOT
* MUTE
* NETPLAY\_FLIP
* SLOWMOTION
* VOLUME\_UP
* VOLUME\_DOWN
* OVERLAY\_NEXT
* DISK\_EJECT\_TOGGLE
* DISK\_NEXT
* DISK\_PREV
* GRAB\_MOUSE\_TOGGLE
* MENU\_TOGGLE

