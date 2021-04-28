---
title: Deuxième miniTFT pour les scrapes et les vidéos \(boîtier OGST / petits écrans tft Raspeberry Pi 1/
---

# Deuxième miniTFT pour les scrapes et les vidéos \(boîtier OGST / petits écrans tft Raspeberry Pi 1/

Cette page vous montrera comment configurer votre second écran TFT pour afficher les scrapes et vidéos.

## Introduction

La dernière version de Recalbox supporte quasi nativement l'affichage des vidéos et scrapes des systèmes émulés, les images et vidéos des jeux installés \(quand ils sont scrapés\) sur un second écran connecté sur le port GPIO \(SPI/DPI, l'écran OGST d'Odroid\).

## Que fait ce script ?

L'opération de l'affichage procède comme ceci : 

* Quand l'interface est sur le carousel des systèmes disponibles, une vidéo de boot de la console / du système est visible si elle existe, sinon une vidéo par défaut est visible.
* Quand l'interface est sur la liste de jeux : 
  * Dans le cas de jeux scrapés, l'image du jeu apparaît sur l'écran TFT.
  * Dans le cas où les vidéos et les images des jeux ont été scrapés, l'écran TFT affichera l'image du jeu pour 1 seconde et la vidéo du jeu sera affichée en boucle. 
* Quand le jeu est lancé : 
  * Dans le cas de jeux scrapés, l'image du jeu apparaît sur l'écran TFT. 
  * Dans le cas où les vidéos et les images des jeux ont été scrapés, l'écran TFT affichera la vidéo du jeu puis affichera l'image du jeu.
* Quand Recalbox affiche l'écran de veille, l'écran TFT est éteint, et une fois sorti de l'écran de veille, est allumée de nouveau. Ceci est utilisable sur les écrans SPI sur les Raspberry Pi.

## Installation d'un écran 2.8" TFT SPI 

Un écran tel sur [Module de port série de module d'affichage LCD 2.8 pouces 240x320 SPI TFT avec PCB ILI9341 5V / 3.3V](https://www.amazon.fr/dp/B07MXH92RL/) ira très bien.

Ce genre d'écran ne coûte pas cher \(&lt; 15€\). Le branchement sur le port GPIO est le suivant :

![2.8 TFT Screen for arduino](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MIPB5avhsBjQ4pk4VGw%2F-MIPUHztymq0KpEGJlvR%2Fimage.png?alt=media&token=1aca874b-cb50-4cb9-8f02-109128e13694)

### Tableau de câblage

|  Module **TFT** |  **Raspberry Pi** |
| :--- | :--- |
|  VCC |  +3,3V \(pin 1\) |
|  GND |  GND \(pin 6\) |
|  CS |  SPI0 CE0 \(pin 24\) |
|  RESET |  GPIO 25 \(pin 22\) |
|  DC |  GPIO 24 \(pin 18\) |
|  SDA |  SPI0 MOSI \(pin 19\) |
|  SCL |  SPI0 SCLK \(pin 23\) |
|  LED |  GPIO 18 \(pin 12\) |
|  SDO |  SPI0 MISO \(pin 21\) |

### Schéma de câblage

![Wiring schematic](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MIPB5avhsBjQ4pk4VGw%2F-MIPUgzrHYim25zIAqto%2Fimage.png?alt=media&token=a411d6b8-c860-46c2-a94a-9ff77099caee)



### Configuration

Le support du deuxième mini écran TFT est intégré dans recalbox 7.0. Il est toujours nécessaire de configurer le mini écran TFT Arduino spécifiquement. Pour cela, vous devez modifier le fichier `/boot/config.txt` comme indiqué ci-dessous pour ajouter le support de l'écran via un overlay. Il faut en premier lieu monter les partitions en écriture :

```text
mount -o remount, rw /boot 
mount -o remount, rw /
```

Modifiez le fichier et ajoutez les lignes suivantes à la fin avec l'éditeur nano :

```text
dtparam=spi=on
#small tft spi 2.8 adafruit type (for arduino)
dtoverlay=rpi-display,reset=25,dc=24,led=18,rotate=90,speed=48000000
```

Le support du bus SPI est activé et l'affichage est configuré via l'overlay approprié. Vous avez plus qu'à configurer le fichier recalbox.conf pour activer le support de l'écran. Pour cela, configurez les options comme ceci :

```text
#Second miniTFT screen as marquee to display scrapes and videos
#Enable it with system.secondMiniTFT.enabled=1, disable with system.secondMiniTFT.enabled=0
 
system.secondminitft.enabled=1
 
#Type of mini TFT : OGST, unknown
#for Support of XU4 OGSTCase mini screen, just configure it secondminitft.type=ogst
#Most of spi tft screen are enabled thanks to overlays in /boot/config.txt
#please check the specific configuration of your screen
#Some examples are available on the page .....
# values are :
# - overlay : screen configured through overlays in /boot/config.txt
# - ogst : screen of the XU4 OGST case. Supported out of the box
# - default : the rest of the world
 
system.secondminitft.type=overlay
 
#Choose the resolution of your screen
#miniTFT resolution  320x240 -> 240p, 480x320 -> 320p
 
system.secondminitft.resolution=240p

#Scraped image aspect on tft screen : fbv display option
# options available : stretch, ignore-aspect, enlarge.
# stretch : Strech (using a simple resizing routine) the image to fit onto screen if necessary
# alpha : use the alpha channel (if applicable)
# ignore-aspect : Ignore the image aspect while resizing
# enlarge : Enlarge the image to fit the whole screen if necessary

# 1 = enabled, 0 = disabled

system.secondminitft.imagestretchenabled=1
system.secondminitft.imageenlargeenabled=0
system.secondminitft.imagealphaenabled=1
system.secondminitft.imageignoreaspectenabled=1

#When activating the second TFT screen, you may want to display
#game scraped video only on the second screen. This variable
#allows you to disable scraped video playing in ES during game browsing
#system.secondminitft.disablevideoines=1 disable video playing in ES
#system.secondminitft.disablevideoines=0 enable video playing in ES

system.secondminitft.disablevideoines=1

#if the backlight of your your screen can be manage by PWM, 
#indicates the  GPIO value of your PWM control
#WiringPi and its gpio program will be used to control the backlight
#when RB goes in SLEEP mode, and when it wakes up.
#On raspberry pi, PWMs cannot be used simultaneously with Jack sound output.
#If your are using HDMI or a Audio hat you can use backlight PWM control for the second screen
#If you are using Jack output please leave commented.
#The Screen will be switch down in Sleep mode, and switch on when it wakes up.
#On OGST, only this mode is available.

;system.secondminitft.backlightcontrol=18
```

Normalement, tout est OK, redémarrez et votre écran doit afficher les images et vidéos des jeux scrapés.

Voici les tests de développement sur un Pi3 :

{% embed url="https://www.youtube.com/watch?v=vX4hZjsDEVY" caption="Deuxième mini écran TFT sur Pi3" %}

Ici, vous pouvez voir la façon dont GameMakers utilise cette fonctionnalité sur une de leur création : une mini New Astro City.

{% embed url="https://www.youtube.com/watch?v=Axzaw6IRtcI" %}

## Waveshare TFT Screen 3.5" RevA et Rev B

Cet écran se trouve [ici](https://fr.aliexpress.com/item/32284958830.html).

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MISqDnif6eiqwftued5%2F-MISq_9Sbid5Ky8CWuBH%2Fimage.png?alt=media&token=fc013d5c-691c-4baf-8054-1a2df52c712d)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MISqDnif6eiqwftued5%2F-MISqjBJ4Dfh7pPot6fE%2Fimage.png?alt=media&token=6d7ebb29-10f9-4e55-99f2-a76e373d028c)

### **Tableau de câblage**

|  PIN NO. |  SYMBOLE |  DESCRIPTION |
| :--- | :--- | :--- |
|  1, 17 |  3.3V |  Power positive \(3.3V power input\) |
|  2, 4 |  5V |  Power positive \(5V power input\) |
|  3, 5, 7, 8, 10, 12, 13, 15, 16 |  NC |  NC |
|  6, 9, 14, 20, 25 |  GND |  Ground |
|  11 |  TP\_IRQ |  Touch Panel interrupt, low level while the Touch Panel detects touching |
|  18 |  LCD\_RS |  Command/data register selection |
|  19 |  LCD\_SI / TP\_SI |  LCD display/SPI data input of Touch Panel |
|  21 |  TP\_SO |  SPI data output of Touch Panel |
|  22 |  RST |  Reset |
|  23 |  LCD\_SCK / TP\_SCK |  LCD display/SPI clock of Touch Panel |
|  24 |  LCD\_CS |  LCD chip selection, low active |
|  26 |  TP\_CS |  Touch Panel chip selection, low active |

### Configuration

La procédure de configuration est identique à l'écran 2.8" Arduino mais les paramètres sont différents.

Le support du deuxième mini écran TFT est intégré dans recalbox 7.0. Il est toujours nécessaire de configurer le mini écran TFT Waveshare \(rev A/B\) spécifiquement. Pour cela, vous devez modifier le fichier `/boot/config.txt` comme indiqué ci-dessous pour ajouter le support de l'écran via un overlay. Il faut en premier lieu monter les partitions en écriture :

```text
mount -o remount, rw /boot 
mount -o remount, rw /
```

Modifiez le fichier et ajoutez les lignes suivantes à la fin avec l'éditeur nano :

```text
#minitft 3.5 waveshare
dtparam=spi=on
dtoverlay=waveshare35a:rotate=270,speed=27000000 #for revA
dtoverlay=waveshare35b:rotate=270,speed=27000000 #for revB
```

Le support du bus SPI est activé et l'affichage est configuré via l'overlay approprié. Vous avez plus qu'à configurer le fichier recalbox.conf pour activer le support de l'écran. Pour cela, configurez les options comme ceci :

```text
#Second miniTFT screen as marquee to display scrapes and videos
#Enable it with system.secondMiniTFT.enabled=1, disable with system.secondMiniTFT.enabled=0
 
system.secondminitft.enabled=1
 
#Type of mini TFT : OGST, unknown
#for Support of XU4 OGSTCase mini screen, just configure it secondminitft.type=ogst
#Most of spi tft screen are enabled thanks to overlays in /boot/config.txt
#please check the specific configuration of your screen
#Some examples are available on the page .....
# values are :
# - overlay : screen configured through overlays in /boot/config.txt
# - ogst : screen of the XU4 OGST case. Supported out of the box
# - default : the rest of the world
 
system.secondminitft.type=overlay
 
#Choose the resolution of your screen
#miniTFT resolution  320x240 -> 240p, 480x320 -> 320p
 
system.secondminitft.resolution=320p

#Scraped image aspect on tft screen : fbv display option
# options available : stretch, ignore-aspect, enlarge.
# stretch : Strech (using a simple resizing routine) the image to fit onto screen if necessary
# alpha : use the alpha channel (if applicable)
# ignore-aspect : Ignore the image aspect while resizing
# enlarge : Enlarge the image to fit the whole screen if necessary

# 1 = enabled, 0 = disabled

system.secondminitft.imagestretchenabled=1
system.secondminitft.imageenlargeenabled=0
system.secondminitft.imagealphaenabled=1
system.secondminitft.imageignoreaspectenabled=1

#When activating the second TFT screen, you may want to display
#game scraped video only on the second screen. This variable
#allows you to disable scraped video playing in ES during game browsing
#system.secondminitft.disablevideoines=1 disable video playing in ES
#system.secondminitft.disablevideoines=0 enable video playing in ES

system.secondminitft.disablevideoines=1

#if the backlight of your your screen can be manage by PWM, 
#indicates the  GPIO value of your PWM control
#WiringPi and its gpio program will be used to control the backlight
#when RB goes in SLEEP mode, and when it wakes up.
#On raspberry pi, PWMs cannot be used simultaneously with Jack sound output.
#If your are using HDMI or a Audio hat you can use backlight PWM control for the second screen
#If you are using Jack output please leave commented.
#The Screen will be switch down in Sleep mode, and switch on when it wakes up.
#On OGST, only this mode is available.

;system.secondminitft.backlightcontrol=18
```

Normalement, tout est OK, redémarrez et votre écran doit afficher les images et vidéos des jeux scrapés.

## Adafruit TFT Screen 3.5"

Vous pouvez obtenir cet écran [ici](https://www.adafruit.com/product/2097) et il est plutôt cher.

![Adafruit 3.5 tft screen front](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MISozPtXpm0P1-gNYgL%2F-MISpyDwzlmdvrCwNlgz%2Fimage.png?alt=media&token=fbc20f9f-d414-49b1-9884-cd31492ca5db)

![Adafruit 3.5 tft screen back](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MISozPtXpm0P1-gNYgL%2F-MISq3rzzgZNCubfSQQs%2Fimage.png?alt=media&token=f8a32a07-736e-45fb-8765-fe82be5ffb29)

### Tableau de câblage

{% embed url="https://pinout.xyz/pinout/pitft\_plus\_35\#" caption="Wiring chart \(online\)" %}

![Screen wiring chart](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MIPZj5OZECb40Brr61n%2F-MIP_mfBEuBFThwm_2GN%2Fimage.png?alt=media&token=fb6dccc4-ecae-4a3f-a0f5-9ae7e5c04276)

### Configuration

La procédure de configuration est identique à l'écran 2.8" Arduino mais les paramètres sont différents.

Le support du deuxième mini écran TFT est intégré dans recalbox 7.0. Il est toujours nécessaire de configurer le mini écran TFT Adafruit spécifiquement. Pour cela, vous devez modifier le fichier `/boot/config.txt` comme indiqué ci-dessous pour ajouter le support de l'écran via un overlay. Il faut en premier lieu monter les partitions en écriture :

```text
mount -o remount, rw /boot 
mount -o remount, rw /
```

Modifiez le fichier et ajoutez les lignes suivantes à la fin avec l'éditeur nano :

```text
#minitft 3.5 adafruit
dtparam=spi=on
dtoverlay=pitft35-resistive,rotate=270,fps=30
```

Le support du bus SPI est activé et l'affichage est configuré via l'overlay approprié. Vous avez plus qu'à configurer le fichier recalbox.conf pour activer le support de l'écran. Pour cela, configurez les options comme ceci :

```text
#Second miniTFT screen as marquee to display scrapes and videos
#Enable it with system.secondMiniTFT.enabled=1, disable with system.secondMiniTFT.enabled=0
 
system.secondminitft.enabled=1
 
#Type of mini TFT : OGST, unknown
#for Support of XU4 OGSTCase mini screen, just configure it secondminitft.type=ogst
#Most of spi tft screen are enabled thanks to overlays in /boot/config.txt
#please check the specific configuration of your screen
#Some examples are available on the page .....
# values are :
# - overlay : screen configured through overlays in /boot/config.txt
# - ogst : screen of the XU4 OGST case. Supported out of the box
# - default : the rest of the world
 
system.secondminitft.type=overlay
 
#Choose the resolution of your screen
#miniTFT resolution  320x240 -> 240p, 480x320 -> 320p
 
system.secondminitft.resolution=320p

#Scraped image aspect on tft screen : fbv display option
# options available : stretch, ignore-aspect, enlarge.
# stretch : Strech (using a simple resizing routine) the image to fit onto screen if necessary
# alpha : use the alpha channel (if applicable)
# ignore-aspect : Ignore the image aspect while resizing
# enlarge : Enlarge the image to fit the whole screen if necessary

# 1 = enabled, 0 = disabled

system.secondminitft.imagestretchenabled=1
system.secondminitft.imageenlargeenabled=0
system.secondminitft.imagealphaenabled=1
system.secondminitft.imageignoreaspectenabled=1

#When activating the second TFT screen, you may want to display
#game scraped video only on the second screen. This variable
#allows you to disable scraped video playing in ES during game browsing
#system.secondminitft.disablevideoines=1 disable video playing in ES
#system.secondminitft.disablevideoines=0 enable video playing in ES

system.secondminitft.disablevideoines=1

#if the backlight of your your screen can be manage by PWM, 
#indicates the  GPIO value of your PWM control
#WiringPi and its gpio program will be used to control the backlight
#when RB goes in SLEEP mode, and when it wakes up.
#On raspberry pi, PWMs cannot be used simultaneously with Jack sound output.
#If your are using HDMI or a Audio hat you can use backlight PWM control for the second screen
#If you are using Jack output please leave commented.
#The Screen will be switch down in Sleep mode, and switch on when it wakes up.
#On OGST, only this mode is available.

;system.secondminitft.backlightcontrol=18
```

Normalement, tout est OK, redémarrez et votre écran doit afficher les images et vidéos des jeux scrapés

## **ODROID Game Station Turbo \(OGST XU4\)**

### Qu'est-ce que l'écran TFT OGST ?

{% embed url="https://www.hardkernel.com/shop/ogst-gaming-console-kit-for-xu4/" %}

## 

Avec le boitier OGST, seule la configuration du fichier recalbox.conf est nécessaire. La configuration de l'écran est automatique une fois configuré.



### Configuration

Pour cette configuration, il n'est pas nécessaire d'utiliser SSH. Une simple modification du fichier recalbox.conf doit être effectuée et ceci est possible en accédant à la carte SD depuis Windows.

La configuration est effectuée avec les lignes suivantes :

```text
#Second miniTFT screen as marquee to display scrapes and videos
#Enable it with system.secondMiniTFT.enabled=1, disable with system.secondMiniTFT.enabled=0

#this configuration is REQUIRED 
system.secondminitft.enabled=1
 
#Type of mini TFT : OGST, unknown
#for Support of XU4 OGSTCase mini screen, just configure it secondminitft.type=ogst
#Most of spi tft screen are enabled thanks to overlays in /boot/config.txt
#please check the specific configuration of your screen
#Some examples are available on the page .....
# values are :
# - overlay : screen configured through overlays in /boot/config.txt
# - ogst : screen of the XU4 OGST case. Supported out of the box
# - default : the rest of the world

#this configuration is REQUIRED if system.secondminitft.enabled=1 
system.secondminitft.type=ogst
 
#Choose the resolution of your screen
#miniTFT resolution  320x240 -> 240p, 480x320 -> 320p

#this configuration is REQUIRED if system.secondminitft.enabled=1 
system.secondminitft.resolution=240p

#Scraped image aspect on tft screen : fbv display option
# options available : stretch, ignore-aspect, enlarge.
# stretch : Strech (using a simple resizing routine) the image to fit onto screen if necessary
# alpha : use the alpha channel (if applicable)
# ignore-aspect : Ignore the image aspect while resizing
# enlarge : Enlarge the image to fit the whole screen if necessary

# 1 = enabled, 0 = disabled

#this configuration is REQUIRED if system.secondminitft.enabled=1
system.secondminitft.imagestretchenabled=1
system.secondminitft.imageenlargeenabled=0
system.secondminitft.imagealphaenabled=1
system.secondminitft.imageignoreaspectenabled=1

#When activating the second TFT screen, you may want to display
#game scraped video only on the second screen. This variable
#allows you to disable scraped video playing in ES during game browsing
#system.secondminitft.disablevideoines=1 disable video playing in ES
#system.secondminitft.disablevideoines=0 enable video playing in ES

#this configuration is OPTIONAL if system.secondminitft.enabled=1
system.secondminitft.disablevideoines=1

#if the backlight of your your screen can be manage by PWM, 
#indicates the  GPIO value of your PWM control
#WiringPi and its gpio program will be used to control the backlight
#when RB goes in SLEEP mode, and when it wakes up.
#On raspberry pi, PWMs cannot be used simultaneously with Jack sound output.
#If your are using HDMI or a Audio hat you can use backlight PWM control for the second screen
#If you are using Jack output please leave commented.
#The Screen will be switch down in Sleep mode, and switch on when it wakes up.
#On OGST, only this mode is available.

#this configuration is OPTIONAL if system.secondminitft.enabled=1
;system.secondminitft.backlightcontrol=18

```

Après avoir enregistré le fichier, redémarrez le système.

## Personnalisation

Il est possible de personnaliser les vidéos affichées des systèmes / consoles, la vidéo de démarrage et d'extinction. Pour cela, vous devez modifier le fichier `system/configs/minitftscreen/miniTFTVideosCfg.sh`

```text
#some useful video constants
LogoFolder='/recalbox/share_init/system/tft_logos'
DefaultLogo='RBvideos/introRecalboxWinners.mp4'
DefaultStartLogo='RBvideos/recalboxHologram.mp4'
DefaultStopLogo='RBvideos/recalboxIntroExplode.mp4'
DefaultImage='noimage.png'
LogoFile=""

#loop system video : -1 = loop forever, 0 = no loop, 1 = loop once, 2 = loop twice, etc...
Loop=-1
#loop default system video
DefaultLogoLoop=-1

#change to your own videos by modifying each "LogoFile" variable.
#for example

# Nintendo
    snes)           LogoFile='myownvideoSNES.mp4' && Loop=-1  ;;
    nes)            LogoFile='myownvideoNES.mp4' && Loop=-1  ;;
```

Il n'est actuellement pas possible de modifier le mode opératoire lors de la sélection de jeux.

