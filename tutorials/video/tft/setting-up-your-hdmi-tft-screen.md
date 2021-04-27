---
description: 'Recalbox versions concerned: All'
---

# Setting up your HDMI TFT screen

## Configuring your 5" TFT HDMI screen


>You can find this screen at the following address: [http://www.banggood.com/5-Inch-800-x-480-HDMI-TFT-LCD-Touch-Screen-For-Raspberry-PI-2-Model-B-B-A-B-p-1023438.html](http://www.banggood.com/5-Inch-800-x-480-HDMI-TFT-LCD-Touch-Screen-For-Raspberry-PI-2-Model-B-B-A-B-p-1023438.html).
>
>This is the equivalent of the Adafruit device: [https://learn.adafruit.com/adafruit-5-800x480-tft-hdmi-monitor-touchscreen-backpack/overview](https://learn.adafruit.com/adafruit-5-800x480-tft-hdmi-monitor-touchscreen-backpack/overview).
{.is-success}

You can make it work on Recalbox by configuring the /boot/config.txt file.

Don't forget that the TFP401 driver does not have a video scaler! If you do not feed it exactly 800×480 pixels, the image will not stretch/shrink to fit!

So we have to configure the resolution in the config.txt file Connect to your Pi \(either in SSH or on a local TTY\).

Make /boot writable to modify the required :

```text
mount -o remount, rw /boot
```

Edit the /boot/config.txt file with nano or vim and add :

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

The line `max_usb_current=1` increases the max output USB current of Pi. This way, your Pi will provide enough power to your screen. Make sure that the main power supply is powerful enough for all your devices.

If the image doesn't have the right resolution when emulating, you will have to modify the recalbox.conf file and change the `global.videomode` variable :

```text
global.videomode=default
```

to use the default configuration in the config.txt file.

Check this post to see this with images: [https://forum.recalbox.com/topic/4539/how-to-config-portable-5-inch-screen-pics-inside](https://forum.recalbox.com/topic/4539/how-to-config-portable-5-inch-screen-pics-inside)

## Configuring your 7" TFT HDMI screen

You can find them for a fair price:

* [https://www.waveshare.com/7inch-HDMI-LCD-C.htm](https://www.waveshare.com/7inch-HDMI-LCD-C.htm)
* [https://www.waveshare.com/wiki/7inch\_HDMI\_LCD\_\(C](https://www.waveshare.com/wiki/7inch_HDMI_LCD_%28C)\)

You can make it work on Recalbox by configuring the `/boot/config.txt` file.

Don't forget that the TFP401 driver does not have a video scaler ! If you do not feed it exactly 800×480 pixels, the image will not stretch/shrink to fit ! So we need to configure the resolution in the config.txt file. 

Connect to your Pi \(either in SSH or on a local TTY\).  
Make /boot writable to modify the required :

```text
mount -o remount, rw /boot
```

Edit the `/boot/config.txt` file with nano or vim and add :

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

The line `max_usb_current=1` increases the max USB output current of Pi if your display is powered by USB. Use `hdmi_max_current=1` if the display is powered by HDMI. This way, your Pi will provide enough power to your display. Make sure that the main power supply is powerful enough for all your devices \(5V-3A\). For a larger screen \(10" and up\), make sure you use an external power supply.

If the image does not have the right resolution during emulation, you will have to modify the recalbox.conf file and change the `global.videomode` variable :

```text
global.videomode=default
```

You can set the custom mode with the help provided on this page : [https://www.raspberrypi.org/documentation/configuration/config-txt/video.md](https://www.raspberrypi.org/documentation/configuration/config-txt/video.md)

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

