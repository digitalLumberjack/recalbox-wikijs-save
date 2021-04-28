---
title: Complete guide on video configuration
---

# Complete guide on video configuration

These are the best recommendations for configuring the video to fit your screen. There are three levels of configuration: system, emulator default video mode, and emulator specific video mode. Keep in mind that screen resolution can have a significant impact on frame rate, especially with CPU-intensive emulators \(N64, PSX, and others\). Most of this guide will focus on the HDMI output and expose the 3 cases as often as possible: Pure HDMI, HDMI to DVI, HDMI to VGA.

## What are the possible video modes?

First of all, you should understand the basics of screen resolution : a number of pixels in width by a number of pixels in height with a given refresh rate in Hertz. For example: 1280x1024@60 which is a common screen resolution of 4x3 for 19" monitors. Today's TVs all display Full HD at 1080p \(and more\), such as 1920x1080@60Hz. We're not going to go through interlaced or progressive modes, that's beside the point. Please refer to the manufacturer's manual of your display for its native resolution.

There are two groups of video modes : CEA and DMT. All these modes are listed [here ](http://elinux.org/RPiconfig)or [there](https://www.raspberrypi.org/documentation/configuration/config-txt/README.md). Make sure the mode is compatible with your native screen resolution. A simple basic rule : CEA is for TV mode, DMT is for all other modes.

The most common modes are :

* DMT 4 : 640x480@60
* DMT 9 : 800x600@60
* DMT 16 : 1024x768@60
* DMT 35 : 1280x1024@60
* DMT 57 : 1680x1050@60
* 720p : CEA 4
* 1080p : CEA 16

In this tutorial, we will cover 3 cases :

* A normal 1080p television. Let's call it 1080pTV
* a 720p VGA monitor connected with HDMI to VGA. Nickname: 720pVGA
* a good old 17" DVI capable of displaying 1280x1024@60. Name it ... DVIboy. Don't forget to consult the Tutorial for DVI displays [https://recalbox.gitbook.io/tutorials/lcd/connecting-your-recalbox-to-a-dvi-monitor](https://recalbox.gitbook.io/tutorials/lcd/connecting-your-recalbox-to-a-dvi-monitor)

With what you already know about screen modes, these are the most common settings:

* 1080pTV corresponds to CEA 16
* 720pVGA corresponds to CEA 4
* DVIboy corresponds to DMT 35

## Your system boots

At startup, the Pi will ask your monitor for its preferred screen resolution. Your monitor sends its EDID \(Extended Display Identification Data\) and the Raspberry selects the screen resolution noted as "preferred". This is where the very first problem occurs:

* most - if not all - native HDMI displays \(TVs, monitors\) should send the correct EDID
* HDMI to DVI should work as well
* HDMI to VGA adapters can be a bit tricky and provide an inaccurate EDID ...

Now that you know a little more about what can happen, here are some examples:

* The 1080pTV is a good boy and will get his 1080p right away,
* The 720pVGA has a crappy HDMI to VGA that matches "DMT 16" as preferred mode,
* The DVIboy adjusts its DMT 35 perfectly.

Since the screen detected at startup is the one that displays EmulationStation with its preferred resolution, the 720pVGA will have an awful display. Fortunately, this can be corrected by editing the `/boot/config.txt` file.

Here are the lines you need to edit :

```text
#hdmi_group=1
#hdmi_mode=1
```

**hdmi\_group** : 1 for CEA, 2 for DMT

**hdmi\_mode** : refer to the lines above; so for our 720pVGA, here's how we publish `/boot/config.txt` :

```text
hdmi_group=1
hdmi_mode=4
```


>**Please note :**
>
>* The "\#" sign is deleted, the technical term for this is "uncommented". A line beginning with a \# is a comment, not a command.
>* hdmi\_group=1 means CEA
>* hdmi\_mode=4 means 720p
{.is-info}

Now that we're done, all three of our screens are set up.

Let's keep moving!

## Global video mode for emulators

Now that EmulationStation is running in full screen, your hand is eager to test a game ... The main thing you need to know here is that the screen resolution is changed before running an emulator. But to which resolution ? Check your `recalbox.conf` and read the `global.videomode` setting. Its default value is `CEA 4 HDMI`. This means that the screen resolution will be changed to 720p just before launching the emulator.

Time to check some examples :

* 1080pTV can display 720p like a charm
* 720pVGA can display the 720p without a scratch
* DVIboy is... mmh... well, it can't display 720p. So just edit `recalbox.conf` and set `global.videomode` to its native video mode: `global.videomode=DMT 35 HDMI`


>**Tip**
>
>Feeling lucky, want to save yourself a change in screen resolution? Then set `global.videomode=default` : Recalbox will not change the screen resolution before running an emulator. But warning : this can have a considerable impact on performance.  
>Extending an image from the native resolution of the emulator to 1080p can be very demanding on the CPU and slow down the emulation. I do not recommend the default setting if your monitor can display a resolution higher than CEA 4.
{.is-info}

## Video mode by emulator

Finally, the video mode can be set specifically for the emulator of your choice. For example, if you read the `recalbox.conf` file, you will notice that `n64.videomode=DMT 4 HDMI` means that we are replacing the global.videomode file for the N64 emulation.

I hope this guide helped you understanding how the screen resolution is handled on Pi and Recalbox.

Feel free to ask your questions on the [forum ](https://forum.recalbox.com/)or on [Discord](https://discord.gg/NbQFbGM).

## Practical advice

### tvservice

tvservice is an excellent tool to diagnose your output :

```text
# tvservice --help
Utilisation : tvservice [OPTIONS]...
  -p, --preferred                   Allumer le HDMI avec les paramètres préférés
  -e, --explicit="GROUP MODE DRIVE" Mise en route de l'HDMI avec GROUPE explicite (CEA, DMT, CEA_3D_SBS, CEA_3D_TB, CEA_3D_FP, CEA_3D_FS)
                                      MODE (voir --modes) et DRIVE (HDMI, DVI)
  -t, --ntsc                        Utiliser la fréquence NTSC pour le mode HDMI (par exemple 59,94Hz au lieu de 60Hz)
  -c, --sdtvon="MODE ASPECT"        Mise en route de la SDTV avec MODE (PAL ou NTSC) et ASPECT (4:3, 14:9 ou 16:9)
  -o, --off                         Éteindre l'écran
  -m, --modes=GROUP                 Obtenir les modes GROUPE supportés (CEA, DMT)
  -M, --monitor                     Suivre les événements HDMI
  -s, --status                      Obtenir le statut HDMI
  -a, --audio                       Obtenir des informations sur le support audio
  -d, --dumpedid <filename>         Vider les informations EDID dans le fichier
  -j, --json                        Utiliser le format JSON pour les modes de sortie
  -n, --name                        Afficher l'ID de l'appareil à partir de l'EDID
  -h, --help                        Afficher cette information
```

The most commonly used switches :

* `tvservice -s` provides current display information
* `tvservice -m CEA` or `tvservice -m DMT` : list of supported CEA or DMT modes

