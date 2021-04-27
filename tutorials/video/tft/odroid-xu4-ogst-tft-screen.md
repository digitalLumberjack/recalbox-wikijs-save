---
description: >-
  This integration method is temporary, pending OGST support in Recalbox. Many
  thanks to littlebalup for its work.
---

# Odroid XU4 : OGST TFT screen

## What is an OGST TFT screen?

{% embed url="https://www.hardkernel.com/shop/ogst-gaming-console-kit-for-xu4/" %}

## The following part is obsolete, OGST support is now native in Recalbox.

**See** [https://recalbox.gitbook.io/documentation/tutorials/video/tft/second-minitft-for-scrapes-and-videos-ogst-case-raspeberry-pi-1-2-3-spi-dpi-small-tft-screens\#odroid-game-station-turbo-ogst-xu-4](/tutorials/video/tft/second-minitft-for-scrapes-and-videos-ogst-case-raspeberry-pi-1-2-3-spi-dpi-small-tft-screens#odroid-game-station-turbo-ogst-xu-4)

## Installation

Prerequisite :

* An ODROID XU4\(Q\) with the OGST game console kit.
* Recalbox installed \(tested on stable version 18.07.13, 2018 christmas beta, v6 0 and v6.1\)
* Recalbox connected to the Internet.

The installation script will run as follows :

* Download the package
* Install the script `/recalbox/share/system/custom.sh`
* Extract the logo package to `/recalbox/share/system/tft_logos`
* Replace the `/usr/bin/ffmpeg` binary with a new one \( the existing one is too old and buggy for video looping operations \)
* Modify and recompile `/usr/lib/python2.7/site-packages/configgen/emulatorlauncher.py`
* Reboot the system

Installation Procedure :

* Getting root access to the terminal
* Copy and paste to your terminal and execute the following command line for **Recalbox 2018** :

```text
wget https://www.dropbox.com/s/jp85fh6j4lkoz8m/install.sh && chmod +x install.sh && ./install.sh
```

* Make a copy/paste on your terminal and execute the following command line for **Recalbox v6.0** :

```text
wget https://www.dropbox.com/s/1c63n1kakkpylbw/install_6x.sh && chmod +x install_6x.sh && ./install_6x.sh
```

* Make a copy/paste on your terminal and execute the following command line for **Recalbox v6.1** :

```text
curl -sL https://www.dropbox.com/s/9bhrq0bta8aah8o/install_6.1.sh | bash
```

That's all folks ! Enjoy !


>**Note**
>
>After updating the Recalbox system, you may need to reinstall it. If you have made changes \(see the "Customization" section\), make a backup of your custom.sh file and your tft\_logos folder before. Then restore them after installation.
>
>The `custom.sh` script has been updated for v6.1. If you made a `custom.sh` script for an old version, you will have to recreate it based on the new "official" script, to use it on v6.1.
{.is-info}

## Some information on how it works

* At system startup, the `/recalbox/share/system/custom.sh` script is executed \(via the `/etc/init.d/S99custom` startup script with the boot parameter to initialize the TFT screen and display the default logo\).
* When a game \(or Kodi\) is launched, the modified emulator launcher `/usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc` runs the `custom.sh` script with the name of the emulator launched as argument, displaying the corresponding logo on the TFT screen.
* The `custom.sh` script continues to run silently in the background while the emulator is running \(while the python / emulatorlauncher process exists\), waiting and monitoring the process shutdown.
* Once the emulator is stopped, the `custom.sh` script displays the default logo again.

## Customization

* All logos \(static images or video clips\) are stored in `/recalbox/share/system/tft_logos`.
* You can add, modify, delete, etc... logos as you wish but you may need to modify the `/recalbox/share/system/custom.sh` script accordingly for some changes to take effect \(the path of the logo files is stored there as well as the loop parameter if you want to loop a video clip\). Make sure you keep the integrity of the script structure.
* If you have accidentally corrupted the `custom.sh` script, make a backup of your _tft\_logos_ folder if you have made any changes, redo the installation procedure, then restore your _tft\_logos_ folder if necessary.
* To be displayed correctly, all images or video clips of the logos must be 320 x 240 pixels \(the resolution of the TFT screen\).
* Works with _.mp4, .jpg, .png_ and _.gif_ files. All files supported by ffmpeg should work. Just try !

## Contributions

### Some tests with introduction videos specific to Recalbox

[Related topic on the Recalbox forum \(French\)](https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case)

{% embed url="https://youtu.be/ZXZSbX--2xg" caption="TFT OGST screen support on Recalbox " %}

### Some videos in 320x240 format

Download this archive, and replace the default value by the one you want :\) [https://mega.nz/\#!Kp8BkYoD!SAeq9xcDUX4po\_Xmhed\_KypmycQ8iQRS1SZI9vBRb3Q](https://mega.nz/#!Kp8BkYoD!SAeq9xcDUX4po_Xmhed_KypmycQ8iQRS1SZI9vBRb3Q)

### Complete video package with all systems

Coming from [https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case/97](https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case/97) thanks to @kevinnash  
Just download the package here : [https://uptobox.com/gsic8c6h72fq](https://uptobox.com/gsic8c6h72fq)

