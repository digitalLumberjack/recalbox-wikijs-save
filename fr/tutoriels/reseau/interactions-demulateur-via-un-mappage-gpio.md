---
title: Interactions d'émulateur via un mappage GPIO
---

# Interactions d'émulateur via un mappage GPIO

Les commandes réseau sont utilisées pour contrôler certaines parties de RetroArch. Pour ce faire, les commandes sont envoyées à RetroArch via UDP \(User Datagram Protocol\).

Habituellement dans la **Recalbox**, ces commandes sont transmises par la fonction **Hotkey** du contrôleur. Par exemple, pour réinitialiser le jeu, vous appuyez sur les touches de **Hotkey + A** ou pour sauvegarder le jeu, vous appuyez sur les touches de **Hotkey + Y**.

Rappelez-vous que cela ne fonctionne qu'avec **RetroArch** / les **émulateurs qui font partie de libretro**.

## Activer

Mais ces commandes peuvent également être envoyées à RetroArch via une ligne de commande ou des broches GPIO. Pour cela, vous devez activer l'option **commandes réseau** dans le menu RetroArch ou modifier la ligne suivante dans `retroarch.cfg` :

* `network_cmd_enable = «true»`

## Envoyer une commande via GPIO

#### Exemples d'application :

Vous utilisez un boîtier existant de console de jeu rétro \(NES, N64, etc.\) et vous voulez utiliser le bouton de réinitialisation d'origine pour réinitialiser le jeu auquel vous jouez actuellement et non pas pour réinitialiser tout le matériel \(Raspberry Pi, etc.\). Le script suivant montre comment envoyer la commande réseau **RESET** à RetroArch via les broches GPIO 5 et 6 pour réinitialiser le jeu en cours.

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

Avec ce script, il est non seulement possible de **RESET** les émulateurs, mais vous pouvez également utiliser la commande nécessaire à partir de diverses commandes. Vous pouvez **QUITTER** les émulateurs \(retour à EmulationStation\), **CHARGER** ou **SAUVEGARDER** un état de jeu, **PAUSER** la partie, etc. Pour cela, il suffit de remplacer la commande **RESET** de la **COMMAND = RESET** par une commande de votre choix.


>**ATTENTION :**
>
>_Ce script peut ne pas fonctionner avec toutes les commandes réseau de RetroArch. Pour certains, il fonctionne, mais pour d'autres, il nécessite plus de travail pour le faire fonctionner \(par exemple, FASTFORWARD\_HOLD\)._
{.is-danger}

Vous pouvez également remapper les broches Raspberry Pi.

Et **n'oubliez pas** : **Recalbox** dispose déjà d'options intégrées pour réinitialiser, démarrer et arrêter le matériel que vous utilisez [via des boutons et GPIO](/v/francais/tutoriels/autres/ajouter-un-bouton-on-off-a-votre-recalbox).

## Commandes

Les commandes suivantes sont prises en charge par RetroArch :

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

## Envoyer une commande via la ligne de commande

Vous pouvez également envoyer des commandes réseau via la ligne de commande sous Linux. Voici comment procéder :

*  `echo -n "QUIT" | nc -u -w1 127.0.0.1 55355`

RetroArch est à l'écoute du **port 55355** par défaut.

