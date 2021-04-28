---
title: Configurez votre petit écran TFT sur le bus SPI
description: Méthode de mise à jour pour les versions de Recalbox après 4.1.
---

# Configurez votre petit écran TFT sur le bus SPI

## Configurez votre écran TFT Adafruit 2,8" capacitif/résistif

Cet écran se trouve sur [ce site](https://www.adafruit.com/product/1601). Comme les overlays existent déjà pour cet écran dans le répertoire `/boot/overlays`, il sera pris en charge avec une configuration simple.

```text
pitft28-capacitive.dtbo
pitft28-resistive.dtbo
```

Vérifiez si vous avez la version capacitive ou résistive de l'écran et ajustez la ligne dt-overlay line dans`/boot/config.txt`.

Cet écran utilise le bus SPI pour être piloté. Sa faible résolution nous permet d'obtenir une bonne fréquence d'images dans les fréquences d'émulation. Pas vraiment à 60fps, mais plus que le minimum de 30 fps grâce au programme modifié `fcbp` \(voir [ici](/v/francais/tutoriels/video/tft/fbcp-utilisation-de-fbcp-pour-les-petits-ecrans-tft)\).

Pour cela, vous devez obtenir un accès en écriture sur le système :

```text
mount -o remount, rw /boot
mount -o remount, rw /
```

### Modification du fichier /boot/config.txt pour correspondre à la résolution de l'écran

Pour que cet écran fonctionne, vous devez avoir ces lignes dans le fichier `/boot/config.txt` :

```text
#overclocking extreme
arm_freq=1100
core_freq=550
sdram_freq=600
over_voltage=8
over_voltage_sdram=6
force_turbo=1

dtparam=spi=on
dtparam=i2c1=on
dtparam=i2c_arm=on
#forcing HDMI output at TFT screen resolution to be able to make the FB copy
#resolution configuration
hdmi_force_hotplug=1
hdmi_cvt=320 240 60 1 0 0 0
hdmi_group=2
hdmi_mode=87
# working config for speed
# 900 Mhz -> 48000000
# 1Ghz -> 35000000
#modification of the speed   
dtoverlay=pitft28-resistive,rotate=90,speed=22000000,fps=60
```

La partie overclocking n'est pas nécessaire et elle est configurée pour un Pi1.

La vitesse du bus SPI doit être ajustée si vous overclockez votre Raspberry Pi pour obtenir une bonne image. Ces réglages ont été testés sur un Raspberry P1 à 1,1Ghz.

Pour commencer, vous pouvez essayer avec ceci :

```text
dtoverlay=pitft28-resistive,rotate=90,speed=32000000,fps=20
```

Dans le cas d'un écran capacitif, il suffit de remplacer par ceci :

```text
dtoverlay=pitft28-capacitive,rotate=90,speed=32000000,fps=20
```

Lors du redémarrage, l'écran doit commencer par un écran blanc et, après quelques secondes, il doit devenir noir. C'est le signe que l'écran est maintenant pris en charge. Mais vous n'obtiendrez aucune image tant que vous ne lancerez pas `fbcp`.

Vous devez maintenant utiliser une connexion SSH sur votre Raspberry Pi pour effectuer/vérifier les étapes suivantes \(voir [ici](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal)\).

### Activation de fbcp dans le fichier recalbox.conf

Dans recalbox.conf, il suffit d'activer le support `fbcp` et de redémarrer.


>**Attention :**
>
>Assurez-vous de désactiver les contrôleurs GPIO
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

Ou modifiez la configuration des broches GPIO en utilisant la fiche 4 ou 5 pour régler la broche utilisée, en évitant les broches utilisées par votre écran. Voir [ici](/v/francais/tutoriels/controleurs/gpio/les-controleurs-gpio) pour plus de détails.

```text
## fbcp FrameBuffer Copy Program
## For small TFT screen on GPIO and SPI
## See https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29 for details
## Needed for Waveshare 3.2" 3.5" TFT screen, 2.8" Adafruit screen
## See https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29
## for support and configuration details needed by /boot/config.txt
system.fbcp.enabled=1
```

Modifiez le fichier recalbox.conf comme ceci :

```text
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=4/3
```

Sauvegardez le fichier et redémarrez. L'écran devrait maintenant fonctionner parfaitement. Si vous rencontrez des problèmes, vérifiez d'abord que le programme `fbcp` fonctionne avec :

```text
ps aux | grep fbcp
```

Cet écran de 2,8" fonctionne bien mais peut être trop petit et trop cher \(35€\) en ce qui concerne les clones chinois. Configurons donc maintenant un écran TFT 3,2" de Waveshare que l'on trouve sur Banggood pour un prix inférieur à 15€.

##  Configurez votre écran TFT Waveshare 3,2" capacitif/résistif

L'écran est le suivant : un module d'affichage TFT LCD de 3,2 pouces à écran tactile pour le Raspberry Pi B+, B, A+. Sa résolution est la même que celle du 2,8" : 320x240. Il s'agit en fait d'un [écran Waveshare](https://www.waveshare.com/3.2inch-rpi-lcd-b.htm).

Cet écran n'est pas pris en charge par défaut par les systèmes de fichier du noyau. Nous devrons en ajouter d'autres pour que l'écran fonctionne. Ces fichiers peuvent se trouver [ici](https://github.com/swkim01/waveshare-dtoverlays).

Obtenez les fichiers `waveshare35a-overlay.dtb` et `waveshare32b-overlay.dtb` respectivement pour l'écran WaveShare 3,2" 320x240 et l'écran WaveShare 3,5" 320x480. Pour les nouveaux noyaux de la version 4.4, nous devons renommer les fichiers dtb en fichiers dtbo pour qu'ils correspondent au nouveau nom de l'arbre de superposition. Renommez `waveshare35a-overlay.dtb` en `waveshare35a.dtbo` et `waveshare32b-overlay.dtb` en `waveshare32b.dtbo` et copiez-les dans le répertoire **/boot/overlays**

Nous modifions maintenant le fichier `/boot/config.txt` pour prendre en charge le nouvel écran :

```text
#tft screen

#Waveshare 3.2 TFT Screen
#same resolution for hdmi and tft
hdmi_force_hotplug=1
hdmi_cvt=320 240 60 1 0 0 0
hdmi_group=2                
hdmi_mode=1                 
hdmi_mode=87                

dtparam=spi=on              
dtoverlay=waveshare32b:rotate=270,speed=82000000
```

### Activation de fbcp dans le fichier recalbox.conf

Dans **recalbox.conf**, il suffit d'activer le support `fbcp` et de redémarrer.


>**Attention :**
>
>Assurez-vous de désactiver les contrôleurs GPIO
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

ou modifiez la configuration des broches GPIO en utilisant la fiche 4 ou 5 pour affiner la broche utilisée, en évitant les broches utilisées par votre écran. Voir [ici](/v/francais/tutoriels/controleurs/gpio/les-controleurs-gpio) pour plus de détails.

```text
## fbcp FrameBuffer Copy Program
## For small TFT screen on GPIO and SPI
## See https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29 for details
## Needed for Waveshare 3.2" 3.5" TFT screen, 2.8" Adafruit screen
## See https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29
## for support and configuration details needed by /boot/config.txt
system.fbcp.enabled=1
```

Modifiez le fichier **recalbox.conf** comme ceci :

```text
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=4/3
```

Sauvegardez le fichier, et redémarrez. L'écran devrait maintenant fonctionner parfaitement. Si vous rencontrez des problèmes, vérifiez d'abord que le programme `fbcp` fonctionne avec cette ligne de commande :

```text
ps aux | grep fbcp
```

Un écran fonctionnel en vidéo :

![Waveshare 3,2&quot; resistif TFT](https://camo.githubusercontent.com/a797d270ad2e8165e81a52ac2c3570291f09cd3c/687474703a2f2f696d672e796f75747562652e636f6d2f76692f6863466b5f766a514c566f2f302e6a7067)

[https://youtu.be/hcFk\_vjQLVo](https://youtu.be/hcFk_vjQLVo)

## Pourquoi l'écran TFT capacitif/résistif de 3,5" de Waveshare n'est-il pas utilisable avec Recalbox ?

Cet écran ne peut pas être utilisé pour les jeux d'arcade avec Recalbox. Le bus SPI ne dispose pas d'une bande passante suffisante pour traiter cette résolution supérieure de 480x320. Si vous augmentez la vitesse du bus, l'affichage devient instable \(couleurs, clignotement\). Pendant mes tests, je n'ai pu obtenir que 20-25 FPS. Cet écran est utilisable avec un serveur X avec une fréquence d'images lente mais pas en mode arcade qui nécessite une fréquence d'images plus élevée.

Comme décrit sur [ce site](https://learn.adafruit.com/), il n'est pas recommandé d'utiliser cet écran pour jouer. &lt;&lt; Avec deux fois plus de pixels à pousser sur l'écran, le PiTFT 3,5" est sensiblement plus lent que ses frères plus compacts et nous le déconseillons fortement pour les jeux &gt;&gt;. Maintenant, vous savez !

Mais si vous voulez faire en sorte que cela fonctionne, vous pouvez procéder comme suit :

### Modification du fichier /boot/config.txt pour correspondre à la résolution de l'écran

Obtenez les fichiers `waveshare35a-overlay.dtb` et `waveshare32b-overlay.dtb` respectivement pour l'écran WaveShare 3,2" 320x240 et l'écran WaveShare 3,5" 320x480. Pour les nouveaux noyaux de la version 4.4, nous devons renommer les fichiers dtb en fichiers dtbo pour qu'ils correspondent au nouveau nom de l'arbre de superposition. Renommez `waveshare35a-overlay.dtb` en `waveshare35a.dtbo` et `waveshare32b-overlay.dtb` en `waveshare32b.dtbo` et copiez-les dans le répertoire **/boot/overlays**

Nous modifions maintenant le fichier `/boot/config.txt` pour prendre en charge le nouvel écran :

```text
#tft screen
#Waveshare 3.5 TFT Screen
#same resolution for hdmi and tft
hdmi_force_hotplug=1
hdmi_cvt=480 320 60 1 0 0 0
hdmi_group=2
hdmi_mode=1
hdmi_mode=87

dtparam=spi=on
dtoverlay=waveshare35a:rotate=270,speed=27000000
# speed=41000000,fps=60 for better FPS, but the colors will look a little weird.
```

### Activation de fbcp dans le fichier recalbox.conf

Dans **recalbox.conf**, il suffit d'activer le support `fbcp`et de redémarrer.


>**Attention :** assurez-vous de désactiver les contrôleurs GPIO !
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

ou modifiez la configuration des broches GPIO en utilisant la fiche 4 ou 5 pour régler la broche utilisée en évitant les broches utilisées par votre écran. Voir [ici](/v/francais/tutoriels/controleurs/gpio/les-controleurs-gpio) pour plus de détails.

```text
fbcp FrameBuffer Copy Program
## For small TFT screen on GPIO and SPI
## See https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29 for details
## Needed for Waveshare 3.2" 3.5" TFT screen, 2.8" Adafruit screen
## See https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29
## for support and configuration details needed by /boot/config.txt
system.fbcp.enabled=1
```

Modifiez le fichier **recalbox.conf** comme ceci :

```text
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=3/2
```

Sauvegardez le fichier, et redémarrez. L'écran devrait maintenant fonctionner parfaitement. Si vous rencontrez des problèmes, vérifiez d'abord que le programme `fbcp` fonctionne avec cette ligne de commande :

```text
ps aux | grep fbcp
```

Un écran fonctionnel de 3,5 pouces avec des problèmes de FPS en vidéo :

![Waveshare 3,5&quot; resistif TFT](https://camo.githubusercontent.com/addc8d2219dc02a03897a7dd3439b006f2440611/687474703a2f2f696d672e796f75747562652e636f6d2f76692f484a585141456156684b452f302e6a7067)

[https://youtu.be/HJXQAEaVhKE](https://youtu.be/HJXQAEaVhKE)

Fonctionnant avec une vitesse=41000000,fps=60 ; c'est clairement risqué, certains écrans donneront des résultats étranges... Cela fonctionnera sur certains écrans en fonction du contrôleur de la puce intégrée.

Selon mon humble avis, si vous avez le [LCD 3,5" \(C\) pour Raspberry Pi \(480x320 ; 125Mhz\)](https://www.waveshare.com/3.5inch-RPi-LCD-C.htm), il devrait fonctionner, mais avec le [LCD 3,5" \(B\) pour Raspberry Pi \(480x320 ; IPS\)](https://www.waveshare.com/3.5inch-RPi-LCD-B.htm), vous ne pourrez pas obtenir 60fps !

![Recalbox 3.5 TFT LCD Raspberry Pi 3 B ](https://camo.githubusercontent.com/194c0f4efcfdf3779ea6b948e230a582bd3d7824/687474703a2f2f69332e7974696d672e636f6d2f76692f63677a6e4f6376525271512f6d617872657364656661756c742e6a7067)

[https://www.youtube.com/watch?v=cgznOcvRRqQ](https://www.youtube.com/watch?v=cgznOcvRRqQ)

## Faites fonctionner votre écran TFT 3,5" résistif Waveshare à fond !

Bientôt disponible.  
Ceci est à destination des courageux : [https://github.com/juj/fbcp-ili9341](https://github.com/juj/fbcp-ili9341)

