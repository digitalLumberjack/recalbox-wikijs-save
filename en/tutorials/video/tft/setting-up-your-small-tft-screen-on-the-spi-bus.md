---
title: Setting up your small TFT screen on the SPI bus
---

# Setting up your small TFT screen on the SPI bus

## Configure your capacitive/resistive TFT screen Adafruit 2,8"

You can get this screen on [this website](https://www.adafruit.com/product/1601). As overlays already exist for this screen in `/boot/overlays`, it will be taken into account with an easy configuration.

```text
pitft28-capacitive.dtbo
pitft28-resistive.dtbo
```

Check if you have the resistive or capacitive version of the screen and adjust the dt-overlay line into`/boot/config.txt`.

This screen uses a SPI bus to be driven. Its low resolution allows to gain a correct frames per seconds for emulation. It doesn't reach 60fps, but more than the minimum 30fps with `fcbp` \(see [here](/fr/tutoriels/video/tft/fbcp-utilisation-de-fbcp-pour-les-petits-ecrans-tft)\).

To do this, you need to gain write access to the system:

```text
mount -o remount, rw /boot
mount -o remount, rw /
```

### Edit the /boot/config.txt file to correspond to the screen resolution

To have this working, you need to have those lines into the `/boot/config.txt` file:

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

The overclocking part is not mandatory and is configured for a Pi1.

The SPI bus speed needs to be adjusted if you overclocked your Raspberry Pi to get a correct image. Those settings have been tested on a Raspberry P1 running at 1,1Ghz.

To start, you can try with this:

```text
dtoverlay=pitft28-resistive,rotate=90,speed=32000000,fps=20
```

In the case your screen is a capacitive screen, you need to replace by this:

```text
dtoverlay=pitft28-capacitive,rotate=90,speed=32000000,fps=20
```

On reboot, the screen should display a white screen first and, after a few seconds, should be black. It's a sign that the screen is taken into account. But you won't get any display until you use `fbcp`.

You should have a SSH connection on your Raspberry Pi to execute/verify the following steps \(see [here](/tutorials/system/access/root-access-via-terminal)\).

### Activation of fbcp into recalbox.conf file

In recalbox.conf file, you just need to enable `fbcp` support and to restart.


>**Attention:**
>
>Be sure to disable GPIO controllers!
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

Or edit the GPIO pins configuration by using pins 4 or 5 to define the used pin, and avoid the pins used by the screen. See [ici](/fr/tutoriels/controleurs/gpio/les-controleurs-gpio) \(french\) for more details.

```text
## fbcp FrameBuffer Copy Program
## For small TFT screen on GPIO and SPI
## See https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29 for details
## Needed for Waveshare 3.2" 3.5" TFT screen, 2.8" Adafruit screen
## See https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29
## for support and configuration details needed by /boot/config.txt
system.fbcp.enabled=1
```

Edit the recalbox.conf file as is:

```text
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=4/3
```

Save the file and restart. The screen should now work perfectly. If you got any issue, check first that `fbcp` is running :

```text
ps aux | grep fbcp
```

This 2,8" screen works fine but can be too small and too expensive \($35\) for a chinese clone. In the next part of this tutorial, we'll see how to configure a 3,2" TFT screen from Waveshare that we can find for less than $25.

##  Configurez votre ??cran TFT Waveshare 3,2" capacitif/r??sistif

L'??cran est le suivant : un module d'affichage TFT LCD de 3,2 pouces ?? ??cran tactile pour le Raspberry Pi B+, B, A+. Sa r??solution est la m??me que celle du 2,8" : 320x240. Il s'agit en fait d'un [??cran Waveshare](https://www.waveshare.com/3.2inch-rpi-lcd-b.htm).

Cet ??cran n'est pas pris en charge par d??faut par les syst??mes de fichier du noyau. Nous devrons en ajouter d'autres pour que l'??cran fonctionne. Ces fichiers peuvent se trouver [ici](https://github.com/swkim01/waveshare-dtoverlays).

Obtenez les fichiers `waveshare35a-overlay.dtb` et `waveshare32b-overlay.dtb` respectivement pour l'??cran WaveShare 3,2" 320x240 et l'??cran WaveShare 3,5" 320x480. Pour les nouveaux noyaux de la version 4.4, nous devons renommer les fichiers dtb en fichiers dtbo pour qu'ils correspondent au nouveau nom de l'arbre de superposition. Renommez `waveshare35a-overlay.dtb` en `waveshare35a.dtbo` et `waveshare32b-overlay.dtb` en `waveshare32b.dtbo` et copiez-les dans le r??pertoire **/boot/overlays**

Nous modifions maintenant le fichier `/boot/config.txt` pour prendre en charge le nouvel ??cran :

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

Dans **recalbox.conf**, il suffit d'activer le support `fbcp` et de red??marrer.


>**Attention :**
>
>Assurez-vous de d??sactiver les contr??leurs GPIO
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

ou modifiez la configuration des broches GPIO en utilisant la fiche 4 ou 5 pour affiner la broche utilis??e, en ??vitant les broches utilis??es par votre ??cran. Voir [ici](/fr/tutoriels/controleurs/gpio/les-controleurs-gpio) pour plus de d??tails.

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

Sauvegardez le fichier, et red??marrez. L'??cran devrait maintenant fonctionner parfaitement. Si vous rencontrez des probl??mes, v??rifiez d'abord que le programme `fbcp` fonctionne avec cette ligne de commande :

```text
ps aux | grep fbcp
```

Un ??cran fonctionnel en vid??o :

![Waveshare 3,2&quot; resistif TFT](https://camo.githubusercontent.com/a797d270ad2e8165e81a52ac2c3570291f09cd3c/687474703a2f2f696d672e796f75747562652e636f6d2f76692f6863466b5f766a514c566f2f302e6a7067)

[https://youtu.be/hcFk\_vjQLVo](https://youtu.be/hcFk_vjQLVo)

## Pourquoi l'??cran TFT capacitif/r??sistif de 3,5" de Waveshare n'est-il pas utilisable avec Recalbox ?

Cet ??cran ne peut pas ??tre utilis?? pour les jeux d'arcade avec Recalbox. Le bus SPI ne dispose pas d'une bande passante suffisante pour traiter cette r??solution sup??rieure de 480x320. Si vous augmentez la vitesse du bus, l'affichage devient instable \(couleurs, clignotement\). Pendant mes tests, je n'ai pu obtenir que 20-25 FPS. Cet ??cran est utilisable avec un serveur X avec une fr??quence d'images lente mais pas en mode arcade qui n??cessite une fr??quence d'images plus ??lev??e.

Comme d??crit sur [ce site](https://learn.adafruit.com/), il n'est pas recommand?? d'utiliser cet ??cran pour jouer. &lt;&lt; Avec deux fois plus de pixels ?? pousser sur l'??cran, le PiTFT 3,5" est sensiblement plus lent que ses fr??res plus compacts et nous le d??conseillons fortement pour les jeux &gt;&gt;. Maintenant, vous savez !

Mais si vous voulez faire en sorte que cela fonctionne, vous pouvez proc??der comme suit :

### Modification du fichier /boot/config.txt pour correspondre ?? la r??solution de l'??cran

Obtenez les fichiers `waveshare35a-overlay.dtb` et `waveshare32b-overlay.dtb` respectivement pour l'??cran WaveShare 3,2" 320x240 et l'??cran WaveShare 3,5" 320x480. Pour les nouveaux noyaux de la version 4.4, nous devons renommer les fichiers dtb en fichiers dtbo pour qu'ils correspondent au nouveau nom de l'arbre de superposition. Renommez `waveshare35a-overlay.dtb` en `waveshare35a.dtbo` et `waveshare32b-overlay.dtb` en `waveshare32b.dtbo` et copiez-les dans le r??pertoire **/boot/overlays**

Nous modifions maintenant le fichier `/boot/config.txt` pour prendre en charge le nouvel ??cran :

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

Dans **recalbox.conf**, il suffit d'activer le support `fbcp`et de red??marrer.


>**Attention :** assurez-vous de d??sactiver les contr??leurs GPIO !
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

ou modifiez la configuration des broches GPIO en utilisant la fiche 4 ou 5 pour r??gler la broche utilis??e en ??vitant les broches utilis??es par votre ??cran. Voir [ici](/fr/tutoriels/controleurs/gpio/les-controleurs-gpio) pour plus de d??tails.

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

Sauvegardez le fichier, et red??marrez. L'??cran devrait maintenant fonctionner parfaitement. Si vous rencontrez des probl??mes, v??rifiez d'abord que le programme `fbcp` fonctionne avec cette ligne de commande :

```text
ps aux | grep fbcp
```

Un ??cran fonctionnel de 3,5 pouces avec des probl??mes de FPS en vid??o :

![Waveshare 3,5&quot; resistif TFT](https://camo.githubusercontent.com/addc8d2219dc02a03897a7dd3439b006f2440611/687474703a2f2f696d672e796f75747562652e636f6d2f76692f484a585141456156684b452f302e6a7067)

[https://youtu.be/HJXQAEaVhKE](https://youtu.be/HJXQAEaVhKE)

Fonctionnant avec une vitesse=41000000,fps=60 ; c'est clairement risqu??, certains ??crans donneront des r??sultats ??tranges... Cela fonctionnera sur certains ??crans en fonction du contr??leur de la puce int??gr??e.

Selon mon humble avis, si vous avez le [LCD 3,5" \(C\) pour Raspberry Pi \(480x320 ; 125Mhz\)](https://www.waveshare.com/3.5inch-RPi-LCD-C.htm), il devrait fonctionner, mais avec le [LCD 3,5" \(B\) pour Raspberry Pi \(480x320 ; IPS\)](https://www.waveshare.com/3.5inch-RPi-LCD-B.htm), vous ne pourrez pas obtenir 60fps !

![Recalbox 3.5 TFT LCD Raspberry Pi 3 B ](https://camo.githubusercontent.com/194c0f4efcfdf3779ea6b948e230a582bd3d7824/687474703a2f2f69332e7974696d672e636f6d2f76692f63677a6e4f6376525271512f6d617872657364656661756c742e6a7067)

[https://www.youtube.com/watch?v=cgznOcvRRqQ](https://www.youtube.com/watch?v=cgznOcvRRqQ)

## Faites fonctionner votre ??cran TFT 3,5" r??sistif Waveshare ?? fond !

Bient??t disponible.  
Ceci est ?? destination des courageux : [https://github.com/juj/fbcp-ili9341](https://github.com/juj/fbcp-ili9341)

