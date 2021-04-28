---
title: Attribuer jusqu'à 4 fonctions sur chaque port GPIO
description: En cours de test !
---

# Attribuer jusqu'à 4 fonctions sur chaque port GPIO

\*\*\*\*⚠ **Pour Raspberry Pi uniquement**

Si vous voulez construire votre borne d'arcade, vous pouvez ajouter des boutons supplémentaires et les affecter à des fonctions spéciales. Voici comment cela fonctionne.

## À propos des ports GPIO Raspberry Pi

Sur un Raspberry Pi, vous disposez de plusieurs ports GPIO, du GPIO2 au GPIO26 :

![GPIO](https://webofthings.org/wp-content/uploads/2016/10/pi-gpio.png)

Lorsque vous voulez connecter un bouton, vous devez le brancher entre un port GPIOxx et un port GND. Veuillez noter que les **numéros GPIO** sont utilisés, et non pas les **numéros PIN \(1 à 40\)** !

## Comment l'installer sur Recalbox

1. Ajoutez ceci dans `/recalbox/share/system/recalbox.conf`:

   ```text
   # Uncomment to enable custom GPIO script feature
   system.rpi.gpio=enable
   ```

2. Éditez`/recalbox/share/system/configs/retroarch/retroarchcustom.cfg` et ajouter cette ligne : `network_cmd_enable = true`
3. Configurez`/recalbox/share/system/configs/rpi-gpio.ini` \(voir les commandes disponibles ci-dessous\)
4. Redémarrez Recalbox et profitez-en !

## Syntaxe du ficher rpi-gpio.ini

Vous devez commencer par \[GPIOxx\] et remplacer `xx` par le numéro GPIO en question.  
Ajoutez ensuite ces 4 lignes :

```text
quick=
standard=
hold=
release=
```

`quick` est une action qui sera exécutée si vous appuyez et relâchez rapidement le bouton.`standard` est une action qui sera exécutée si vous maintenez et relâchez le bouton pendant environ 1 seconde.  
`hold` est une action qui sera exécutée si vous maintenez le bouton enfoncé pendant une longue période \(plus de 2 secondes\). `release` est une action qui sera exécutée si vous relâchez le bouton après un événement `hold`.

Toutes les actions sont facultatives. Si vous ne souhaitez pas attribuer de fonction, laissez simplement un blanc après `=`

Exemple :

```text
[GPIO26]
quick=VOLUP
standard=VOLDOWN
hold=VOLMUTE
release=
[GPIO16]
quick=RESET
standard=QUIT
hold=
release=
```

## Actions disponibles

### Actions globales

* VOLUP : Augmenter le volume
* VOLDOWN : Diminuer le volume
* VOLMUTE : Volume muet / non muet
* QUIT : Quitter l'émulateur actuel et retourner à EmulationStation

### Actions spécifiques aux émulateurs RetroArch

* RESET
* FAST\_FORWARD  
* FAST\_FORWARD\_HOLD  
* LOAD\_STATE  
* SAVE\_STATE  
* FULLSCREEN\_TOGGLE    
* STATE\_SLOT\_PLUS  
* STATE\_SLOT\_MINUS  
* REWIND  
* MOVIE\_RECORD\_TOGGLE  
* PAUSE\_TOGGLE  
* FRAMEADVANCE    
* SHADER\_NEXT  
* SHADER\_PREV  
* CHEAT\_INDEX\_PLUS  
* CHEAT\_INDEX\_MINUS  
* CHEAT\_TOGGLE  
* SCREENSHOT   
* NETPLAY\_FLIP  
* SLOWMOTION   
* OVERLAY\_NEXT  
* DISK\_EJECT\_TOGGLE  
* DISK\_NEXT  
* DISK\_PREV  
* GRAB\_MOUSE\_TOGGLE  
* MENU\_TOGGLE  

