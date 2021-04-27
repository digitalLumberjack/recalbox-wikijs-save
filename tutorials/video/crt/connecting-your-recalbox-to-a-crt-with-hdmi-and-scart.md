# Connecting your Recalbox to a CRT with HDMI and SCART

## Principles

### Cabling

First, you will need to create the super-cable to convert VGA to Scart. Thanks to @ian57 for this post by the way !

[https://forum.recalbox.com/topic/3475/recalbox-sur-tv-crt-en-rgb/745](https://forum.recalbox.com/topic/3475/recalbox-sur-tv-crt-en-rgb/745)

![](https://s3-eu-west-1.amazonaws.com/forums.recalbox.com/ac9ba3d3-29fc-4ff2-8644-aee71b62f043.png)



I used this \(HDMI VGA scart cable\) on a terminal with a 36 cm Tv and a Recalbox 6.1.1, there were no particular problems.

Here is the schematic of my wiring at the output of the VGA converter.

Then for the configurations, it's very different from the VGA666/pi2scart/rgbPi \(they all 3 use DPI in 18 bits mode \(6 bits/color\) :

In the config.txt file, we configure as if we had a 1920x240 screen:

```text
hdmi_cvt=1920 240 60 1 1 0 0
hdmi_disable_edid=0xa5000080 #Enables the ignoring of EDID/display data if your display doesn't have an accurate EDID.

hdmi_pixel_encoding=2 #Force the pixel encoding mode. By default it will use the mode requested from edid so shouldn't need changing. 
avoid_safe_mode=1
disable_overscan=0 #oversan enabled
hdmi_drive=2
hdmi_group=1
hdmi_mode=6
hdmi_force=1
```

In the recalbox.conf file, we force EmulationStation to be displayed in 480 interlaced \(it stings a bit\); otherwise we use CEA 8 HDMI un 240 non-interlaced, but we will need a theme adapted to this low resolution.

```text
system.es.videomode=CEA 6 HDMI
 
#global.videomode=CEA 4 HDMI
global.videomode=DMT 87 HDMI
```

Then, you have to tell libretro for each emulator to use only part of the 1920x240 window.  
To do this, you have to create a config file for each emulator : cf [https://forum.recalbox.com/topic/18927/recalbox-6-1-sur-écran-crt/9](https://forum.recalbox.com/topic/18927/recalbox-6-1-sur-écran-crt/9) to be placed in `/share/system/configs/retroarch`

For example, my `megadrive.cfg`

```text
aspect_ratio_index = "23"
custom_viewport_width = "1792"
custom_viewport_height = "224"
custom_viewport_x = "104"
custom_viewport_y = "16"
```

The last 4 lines have to be adapted to the screen geometry. The values can be found by adjusting from the Retroarch menu.

If this is not done, the emulator image will be completely overwritten in the middle of the screen.

## Useful links for retroarch kernel configuration

This link allows you to simply generate the configuration files for the retroarch from a web interface.

[https://surchargeur-ra-rb.netlify.com/](https://surchargeur-ra-rb.netlify.com/)

More coming soon =\)

