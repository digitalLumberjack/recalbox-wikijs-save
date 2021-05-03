---
title: Configurer votre écran TFT HDMI
description: 'Version de Recalbox concernées : Toutes'
---

# Configurer votre écran TFT HDMI

## Configurez votre écran TFT HDMI 5"


>**Vous pouvez trouver cet écran** [**ici**](https://www.banggood.com/5-Inch-800-x-480-HD-TFT-LCD-Touch-Screen-For-Raspberry-PI-2-Model-B-or-B+-or-A+-or-B-p-1023438.html)**.**
>
>C'est l'équivalent du [dispositif Adafruit](https://learn.adafruit.com/adafruit-5-800x480-tft-hdmi-monitor-touchscreen-backpack/overview).
{.is-info}

Vous pouvez le faire fonctionner sur Recalbox en configurant le fichier `/boot/config.txt`

N'oubliez pas que le pilote du TFP401 n'a pas de scaler vidéo ! Si vous ne l'alimentez pas exactement en 800×480 pixels, l'image ne s'étirera pas et rétrécira pour s'adapter ! Nous devons donc configurer la résolution dans le fichier config.txt.

Connectez-vous à votre Pi \(soit [en SSH](/fr/tutoriels/systeme/acces/acces-root-via-terminal) ou sur un TTY local\).

Rendre `/boot` accessible en écriture pour modifier le fichier requis :

```text
mount -o remount, rw /boot
```

Éditez le fichier `/boot/config.txt` avec nano ou vim et ajoutez :

```text
# uncomment if hdmi display is not detected and composite is being output
hdmi_force_hotplug=1
 
# uncomment to force a specific HDMI mode (here we are forcing 800x480!)
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
hdmi_cvt=800 480 60 6 0 0 0
 
max_usb_current=1
```

La ligne `max_usb_current=1` augmente le courant USB de sortie max du Pi. De cette façon, votre Pi fournira suffisamment de puissance à votre écran. Assurez-vous que l'alimentation principale est suffisamment puissante pour tous vos appareils.

Si l'image n'a pas la bonne résolution lors de l'émulation, vous devrez modifier le fichier `recalbox.conf` et changer la variable `global.videomode` :

```text
global.videomode=default
```

Pour utiliser la configuration par défaut du fichier `config.txt`.

Consultez [ce message](https://forum.recalbox.com/topic/4539/how-to-config-portable-5-inch-screen-pics-inside) pour voir cela avec des images.

## Configurez votre écran TFT HDMI 7"

Vous pouvez en trouver pour un prix correct [ici](https://www.waveshare.com/7inch-HDMI-LCD-C.htm) ou [là](https://www.waveshare.com/wiki/7inch_HDMI_LCD_%28C%29).

Vous pouvez le faire fonctionner sur Recalbox en configurant le fichier `/boot/config.txt`.

N'oubliez pas que le pilote du TFP401 n'a pas de scaler vidéo ! Si vous ne l'alimentez pas exactement en 800×480 pixels, l'image ne s'étirera pas et rétrécira pour s'adapter ! Nous devons donc configurer la résolution dans le fichier config.txt.

Connectez-vous à votre Pi \(soit [en SSH](/fr/tutoriels/systeme/acces/acces-root-via-terminal) ou sur un TTY local\).

Rendre `/boot` accessible en écriture pour modifier le fichier requis :

```text
mount -o remount, rw /boot
```

Éditez le fichier `/boot/config.txt` avec nano ou vim et ajoutez :

```text
# uncomment if hdmi display is not detected and composite is being output
hdmi_force_hotplug=1
config_hdmi_boost=7
hdmi_max_current=1
# uncomment to force a specific HDMI mode (here we are forcing 2014x600!)
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
hdmi_cvt=1024 600 60 6 0 0 0
display_rotate=0
max_usb_current=1
hdmi_drive=1
hdmi_ignore_edid=0xa5000080
```

La ligne `max_usb_current=1` augmente le courant USB de sortie max du Pi si votre écran est alimenté en USB. Utilisez `hdmi_max_current=1` si l'écran est alimenté par HDMI. De cette façon, votre Pi fournira suffisamment de puissance à votre écran. Assurez-vous que l'alimentation principale est suffisamment puissante pour tous vos appareils \(5V-3A\). Pour un écran plus grand \(10" et plus\), assurez-vous d'utiliser une alimentation externe.

Si l'image n'a pas la bonne résolution lors de l'émulation, vous devrez modifier le fichier `recalbox.conf` et changer la variable `global.videomode` :

```text
global.videomode=default
```

Vous pouvez régler le mode personnalisé grâce à [cette page](https://www.raspberrypi.org/documentation/configuration/config-txt/video.md).

```text
hdmi_cvt=<width> <height> <framerate> <aspect> <margins> <interlace> <rb>

Value 	Default 	Description
width 	(required) 	width in pixels
height 	(required) 	height in pixels
framerate 	(required) 	framerate in Hz
aspect 	3 	aspect ratio 1=4:3, 2=14:9, 3=16:9, 4=5:4, 5=16:10, 6=15:9
margins 	0 	0=margins disabled, 1=margins enabled
interlace 	0 	0=progressive, 1=interlaced
rb 	0 	0=normal, 1=reduced blanking
```

