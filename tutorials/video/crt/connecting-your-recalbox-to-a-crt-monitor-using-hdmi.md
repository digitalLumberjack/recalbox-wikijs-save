# Connecting your recalbox to a CRT monitor using HDMI


>**WARNING**
>
>It is **IMPERATIVE** to have version **4.1 STABLE of Recalbox** for these modifications to work.  
>  
>**To play your Recalbox on a CRT screen connected in HDMI**, several choices are possible, depending on the connections of your screen
>
>* Connection via the HDMI socket using an **HDMI / VGA adapter ==&gt; VGA / BNC**
>* Connection via HDMI jack using an **HDMI / VGA adapter ==&gt; VGA / SCART**
{.is-danger}

## Hardware

### Connect your Recalbox to a CRT monitor with RGB input in BNC, via HDMI.

Many professional CRT monitors have RGB inputs in BNC, as in this picture in Line 3 \(Input\).

* So we will have 3 wires for the 3 colors \(Red, Green, Blue\), as well as 2 wires for the synchronization \(vertical and horizontal\).

![](http://www.auschoice.com/images/ebay_images/garage_sale_images_dv/sonytrini-1387169360-8160.jpg)

#### ​Connectors <a id="connectiques"></a>

You'll need an adapter like this:

​ [https://www.amazon.fr/UGREEN-Adaptateur-Rasberry-Chromebook-Ordinateur/dp/B00NBUTHJG/ref=sr\_1\_5?ie=UTF8&qid=1489225116&sr=8-5&keywords=vga+hdmi](https://www.amazon.fr/UGREEN-Adaptateur-Rasberry-Chromebook-Ordinateur/dp/B00NBUTHJG/ref=sr_1_5?ie=UTF8&qid=1489225116&sr=8-5&keywords=vga+hdmi)​

![HDMI-VGA Adapter](http://i.imgur.com/WTRfCo6.png)

* Once connected to the HDMI port of your Recalbox, you will have a VGA output jack, and an audio jack.


>You will need an external micro-usb power supply, 1A should be sufficient.
{.is-danger}

* Then you will need a VGA ==&gt; BNC adapter like this one:

​ [https://www.amazon.fr/gp/product/B0033AF5Y0/ref=oh\_aui\_detailpage\_o01\_s00?ie=UTF8&psc=1](https://www.amazon.fr/gp/product/B0033AF5Y0/ref=oh_aui_detailpage_o01_s00?ie=UTF8&psc=1)​

![VGA-BNC Adapter](http://i.imgur.com/UAuajvZ.png)

* Not having found a VGA-BNC adapter with female BNC output, I had to use 5 male-male BNC connectors, found in specialized electronics store.

![BNC male-male connector](http://i.imgur.com/UEXCmCR.png)

## Software <a id="software"></a>

### ​Recalbox boot configuration

The resolutions accepted by this type of screen are different, depending on the model ; but in general you will want :

* **480i for EmulationStation** \(my screen doesn't support 480p, and the texts are unreadable in 240p\)
* **240p for gaming** \(output resolution for almost all consoles of that era\)

This is what your file should look like `/boot/config.txt`

```text
#Définition de la résolution du mode custom DMT 87 HDMI pour la résolution des jeux
hdmi_cvt=1920 240 60 1 1 0 0

#Ignore le EDID de votre TV (le CRT peut envoyer de mauvaises informations)
hdmi_ignore_edid=0xa5000080

#Force le mode d'encodage des pixels, 2 correspond à Full RGB
hdmi_pixel_encoding=2

#Désactive le safe mode au boot du raspberry pi
avoid_safe_mode=1

#Ne pas désactiver l'overscan
disable_overscan=0

#Evite les interférences de l'adaptateur en boostant le signal HDMI
config_hdmi_boost=4

#Force le son sur HDMI
hdmi_drive=2

#Selectionne le groupe HDMI CEA
hdmi_group=1

#Résolution CEA 6 = 480
interlacedhdmi_mode=6​

#Kernel utilisé
kernel=zImage

#Utiliser le mode HDMI même si aucun câble n'est connecté
hdmi_force_hotplug=1

#paramètres mémoire
gpu_mem_256=128
gpu_mem_512=256
gpu_mem_1024=512​

#Paramètre lié à l'audio
dtparam=audio=on

#Permet de temporiser le boot
boot_delay=3
```


>* To edit this file, you have to make the boot partition writable by following this tutorial : [https://recalbox.gitbook.io/tutorials/access/accessing-a-partition-in-write-mode](https://recalbox.gitbook.io/tutorials/access/accessing-a-partition-in-write-mode) 
>* To access it via Winscp, follow this tutorial : ​[https://recalbox.gitbook.io/tutorials/access/network-access-via-winscp](https://recalbox.gitbook.io/tutorials/access/network-access-via-winscp)
{.is-info}

Some explanations : The Raspberry pi will start in hdmi\_group=1 hdmi\_mode=6, which corresponds to 480i \(interlaced\). If the boot is done directly in 240p, the texts of the menus and games would be unreadable.

The line `hdmi_cvt=1920 240 60 1 1 0 0` specifies a resolution of 1920 x 240 x 60 Hz, which will not be used for booting, but will be registered as DMT 87 HDMI mode, which we will use later for launching games. Here's a little more explanation on this line:

```text
hdmi_cvt=<width> <height> <framerate> <aspect> <margins> <interlace> <rb>
width        width in pixels
height       height in pixels
framerate    framerate in Hz
aspect       aspect ratio 1=4:3, 2=14:9, 3=16:9, 4=5:4, 5=16:10, 6=15:9
margins      0=margins disabled, 1=margins enabled
interlace    0=progressive, 1=interlaced
rb           0=normal, 1=reduced blanking
```

### ​Configuration of the recalbox.conf file

Although the **Raspberry Pi boots in CEA 6 video mode** \(via config.txt\) I preferred to force this configuration for EmulationStation:

```text
system.es.videomode=CEA 6 HDMI
```

* We must then specify the boot resolution for our emulators, in a global way:

```text
global.videomode=DMT 87 HDMI
```

All emulators will therefore be launched in DMT 87 HDMI mode \("custom" mode\) containing via the hdmi\_cvt of the config.txt file, the resolution 1920 x 240x 60Hz.


>**Small explanation for the 1920 pixels wide** : To make it short, a CRT monitor only needs a vertical number of pixels \(240 here\) and a vertical refresh rate \(60 Hz here\).
>
>So we specify 1920 pixels wide, because 1920 is a multiple of 160, 320, 384... which are often encountered resolutions.   
>  
>For the other resolutions, we will calculate the overscan with retroarch, i.e. the necessary black bands around the screen to keep the original ratio.
{.is-info}

Everything goes fine for me in this resolution. But you can specify a different resolution per console, with the following line:

```text
dreamcast.videomode=hdmi_cvt 320 240 60 1 1 0 0
```

### ​Retroarch viewport configuration \(keep the original aspect ratio and set the image on its screen\)

#### Configuration per system

When starting a game, it must therefore start with a resolution of 320 x 240 x 60 Hz pixels. We can specify for each system, the actual display size and the offset if needed.

These configuration files are to be created in your shared folder : `/system/configs/retroarch/` They should contain the name of the system \(the same as in the roms folder\), for example : `nes.cfg`, or `mastersystem.cfg`.

Here is the content of my nes.cfg file

```text
aspect_ratio_index = "22"
video_smooth = "false"
video_scale_integer = "false"
video_threaded = "false"
custom_viewport_width = "1680"
custom_viewport_height = "224"
custom_viewport_x = "118"
custom_viewport_y = "17"
```

* To adjust the screen positioning, simply change the **custom\_viewport\_x and y values** directly in game via the retroarch menu \(**Hotkey + B**\), then copy these values into the system _\*.cfg_ file.
* Here are the **viewports width and height** that I configured for my CRT :

```text
nes.cfg
custom_viewport_width = "1680"
custom_viewport_height = "224"
        
snes.cfg
custom_viewport_width = "1792"
custom_viewport_height = "224"

gb.cfg gbc.cfg gamegear.cfg
custom_viewport_width = "960"
custom_viewport_height = "144"

gba.cfg
custom_viewport_width = "1440"
custom_viewport_height = "160"

megadrive.cfg neogeo.cfg segacd.cfg sega32x.cfg fba_libretro.cfg
custom_viewport_width = "1920"
custom_viewport_height = "224"

mastersystem.cfg
custom_viewport_width = "1536"
custom_viewport_height = "192"

psx.cfg n64.cfg
custom_viewport_width = "1920"
custom_viewport_height = "240"

pcenginecd.cfg
custom_viewport_width = "1760"
custom_viewport_height = "240"
```

#### Configuration per game <a id="configuration-par-jeux"></a>

**​**For the **arcade**, I use **fba\_libretro**. Since almost every game has a different resolution, I defined one file per game \(to keep the original ratio\). Same manipulation as per system, except that the files are located in your shared folder : `/system/configs/retroarch/fba_libretro/` 

The content of the file is identical to the system configuration. The filename must be in the form _rom.zip.cfg_ So for example: _1944.zip.cfg_

### Special Cases <a id="cas-particuliers"></a>

#### Nintendo 64 <a id="nintendo-64"></a>

​To **handle viewports** on the **Nintendo 64** emulator, we need to **select the core** retroarch `glupen64`. Then, just like on other systems, the configuration will be in a `n64.cfg` file.

#### AdvanceMame <a id="advancemame"></a>

For **Mame** arcade games, the **AdvanceMame** core has the particularity to **automatically calculate the resolution of each game**, adapting it to your screen resolution.

This way, **we don't need to do a configuration per game** \(as it is the case for fba\_libretro\).

## _This part to be completed !_ <a id="cette-partie-reste-a-completer"></a>

### ​Emulation Station Themes

The theme must be realized in **4/3** to have a well-framed image

I propose you a theme created by Supernature2K: [https://forum.recalbox.com/topic/6580/release-wip-theme-recalbox-multi-help-needed](https://forum.recalbox.com/topic/6580/release-wip-theme-recalbox-multi-help-needed)

This theme is configurable, and adapts perfectly to CRTs.

![Recalbox Multi Theme](http://i.imgur.com/6hQFlPO.png)

