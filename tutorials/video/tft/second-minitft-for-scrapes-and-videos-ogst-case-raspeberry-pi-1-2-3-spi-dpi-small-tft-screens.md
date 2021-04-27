# Second miniTFT for scrapes and videos \(OGST case/Raspeberry Pi 1/2/3 SPI/DPI small tft screens\)

This page will show you how to configure your second small TFT screen to display scrapes and videos

## Introduction

The latest version of recalbox almost natively supports the display of videos of emulated systems, images/videos of installed games \(when they have been scrapped\) on a second screen connected to the GPIO \(SPI/DPI, screen of the OGST Odroid box\).

## What does the scripts do

The operation of the display is as follows: 

* When the interface is on the system carousel, a boot video of the console/system is displayed if it exists, otherwise a default video is displayed 
* When the interface is on the games selection :  
  * in case the images of the games have been scrapped, the image of the game appears on the tft mini screen. 
  * in case the game videos and images have been scrapped, the tft screen displays the game image for 1 second and then the game video is played in a loop. 
* when the game is launched :  
  * in case the game images have been scrapped, the game image appears on the tft mini screen.  
  * in case the videos and images of the games have been scratched, the tft screen displays the video and then displays the game image
* when Recalbox goes in sleep mode, OGST screen is turned off, and back on, on wake up. This feature is usable to on raspberry SPI tft screen.

## Installation on a 2.8" TFT SPI screen 

Such a 2.8" TFT SPI with 240 × 320 SPI TFT LCD CI ILI9341 3.3V 5V can be found at [https://www.amazon.fr/gp/product/B07QS6BCGK/ref=ppx\_yo\_dt\_b\_asin\_title\_o00\_s00?ie=UTF8&psc=1](https://www.amazon.fr/gp/product/B07QS6BCGK/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)

It is very cheap \(&lt; 15€\). The wiring on the GPIO is the following :

![2.8 TFT Screen for arduino](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MIPB5avhsBjQ4pk4VGw%2F-MIPUHztymq0KpEGJlvR%2Fimage.png?alt=media&token=1aca874b-cb50-4cb9-8f02-109128e13694)

### Wiring chart

|  **TFT module** |  **Raspberry Pi** |
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

### Wiring schematic

![Wiring schematic](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MIPB5avhsBjQ4pk4VGw%2F-MIPUgzrHYim25zIAqto%2Fimage.png?alt=media&token=a411d6b8-c860-46c2-a94a-9ff77099caee)



### Configuration

The support of the second mini TFT is integrated in the recalbox 7.0 distribution. It is still necessary to configure the arduino mini TFT screen specifically. To do so you need to modify the `/boot/config.txt` file as follows to add support for our screen via an overlay. To do this we pass the partitions to write :

```text
mount -o remount, rw /boot 
mount -o remount, rw /
```

then edit the file and add at the end of the file using nano :

```text
dtparam=spi=on
#small tft spi 2.8 adafruit type (for arduino)
dtoverlay=rpi-display,reset=25,dc=24,led=18,rotate=90,speed=48000000
```

The SPI bus support is activated and the display is configured via the appropriate overlay. Then you just have to configure the recalbox.conf file to activate the screen support. To do this, configure as follows:

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

Normally everything is ok, just reboot and your screen should display the images and videos of your "scraped" games.

Here are the development tests on a Pi3 :

{% embed url="https://youtu.be/vX4hZjsDEVY" caption="Second mini tft screen support on Pi3" %}



Here is how our friends from GameMakers used the feature on one of their creation: a mini New Astro City.

{% embed url="https://youtu.be/Axzaw6IRtcI" %}



## Waveshare TFT Screen 3.5" RevA and Rev B

The screen can be found here [https://fr.aliexpress.com/item/32284958830.html](https://fr.aliexpress.com/item/32284958830.html)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MISqDnif6eiqwftued5%2F-MISq_9Sbid5Ky8CWuBH%2Fimage.png?alt=media&token=fc013d5c-691c-4baf-8054-1a2df52c712d)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MISqDnif6eiqwftued5%2F-MISqjBJ4Dfh7pPot6fE%2Fimage.png?alt=media&token=6d7ebb29-10f9-4e55-99f2-a76e373d028c)

### **Wiring chart**

|  PIN NO. |  SYMBOL |  DESCRIPTION |
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

The configuration procedure is identical to screen 2.8 arduino but the parameters are different.

The support of the second mini TFT is integrated in the recalbox 7.0 distribution. It is still necessary to configure the waveshare \(revA/B\)/chinise clone mini TFT screen specifically. To do so you need to modify the `/boot/config.txt` file as follows to add support for our screen via an overlay. To do this we pass the partitions to write :

```text
mount -o remount, rw /boot 
mount -o remount, rw /
```

then edit the file and add at the end of the file using nano :

```text
#minitft 3.5 waveshare
dtparam=spi=on
dtoverlay=waveshare35a:rotate=270,speed=27000000 #for revA
dtoverlay=waveshare35b:rotate=270,speed=27000000 #for revB
```

The SPI bus support is activated and the display is configured via the appropriate overlay. Then you just have to configure the recalbox.conf file to activate the screen support. To do this, configure as follows:

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

Normally everything is ok, just reboot and your screen should display the images and videos of your "scraped" games.

## Adafruit TFT Screen 3.5"

This screen can be found here [https://www.adafruit.com/product/2097](https://www.adafruit.com/product/2097) but it is not very cheap.

![Adafruit 3.5 tft screen front](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MISozPtXpm0P1-gNYgL%2F-MISpyDwzlmdvrCwNlgz%2Fimage.png?alt=media&token=fbc20f9f-d414-49b1-9884-cd31492ca5db)

![Adafruit 3.5 tft screen back](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MISozPtXpm0P1-gNYgL%2F-MISq3rzzgZNCubfSQQs%2Fimage.png?alt=media&token=f8a32a07-736e-45fb-8765-fe82be5ffb29)

### Wiring chart

{% embed url="https://pinout.xyz/pinout/pitft\_plus\_35\#" caption="Wiring chart \(online\)" %}

![Screen wiring chart](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MIPZj5OZECb40Brr61n%2F-MIP_mfBEuBFThwm_2GN%2Fimage.png?alt=media&token=fb6dccc4-ecae-4a3f-a0f5-9ae7e5c04276)

### Configuration

The configuration procedure is identical to screen 2.8 arduino but the parameters are different.

The support of the second mini TFT is integrated in the recalbox 7.0 distribution. It is still necessary to configure the adafruit mini TFT screen specifically. To do so you need to modify the `/boot/config.txt` file as follows to add support for our screen via an overlay. To do this we pass the partitions to write :

```text
mount -o remount, rw /boot 
mount -o remount, rw /
```

then edit the file and add at the end of the file using nano :

```text
#minitft 3.5 adafruit
dtparam=spi=on
dtoverlay=pitft35-resistive,rotate=270,fps=30
```

The SPI bus support is activated and the display is configured via the appropriate overlay. Then you just have to configure the recalbox.conf file to activate the screen support. To do this, configure as follows:

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

Normally everything is ok, just reboot and your screen should display the images and videos of your "scraped" games.

## **ODROID Game Station Turbo \(OGST XU4\)**

### What is an OGST TFT screen?

{% embed url="https://www.hardkernel.com/shop/ogst-gaming-console-kit-for-xu4/" %}

## 

On the OGST box only the configuration of the recalbox.conf file is necessary. The configuration of the screen is automatic once configured.

{% embed url="https://youtu.be/qMSSzsTE3Us" caption="Activated feature on the OGST case" %}

### Configuration

For this configuration it is not necessary to use SSH. A simple modification of the recalbox.conf file has to be done and it is possible to do this by accessing your SD card through a Windows workstation.

The configuration is done in the following lines:

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

After saving the file, simply restart the system.

## Customization

It is possible to customize the displayed videos of the systems/console, startup video and shutdown video. To do this you need to edit the `system/configs/minitftscreen/miniTFTVideosCfg.sh`

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

It is currently not possible to change the operating mode when selecting games.

