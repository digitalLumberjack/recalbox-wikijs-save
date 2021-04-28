---
title: Configure an external display \(x86/x86\_64\)
---

# Configure an external display \(x86/x86\_64\)

## Configuration

Since version 7.0, the configuration of external screens has been done from[ recalbox.conf](/basic-manual/getting-started/the-recalbox.conf-file)

open the recalbox.conf file located in the folder:  
`/recalbox/share/system` 

## Know the video outputs available

* Connected to your recalbox in [ssh](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal)
* In your **ssh** terminal type: `xrandr`

Which gives you as a result **the available video outputs and their resolutions.**  
Example:

```text
eDP-1 connected primary 1366x768+0+0 (normal left inverted right x axis y axis) 344mm x 193mm
   1366x768      60.06*+
   1360x768      59.80    59.96  
   1280x720      60.00    59.99    59.86    59.74  
   1024x768      60.04    60.00  
   960x720       60.00  
   928x696       60.05  
   896x672       60.01  
   1024x576      59.95    59.96    59.90    59.82  
   960x600       59.93    60.00   
VGA-1 disconnected (normal left inverted right x axis y axis)
HDMI-1 disconnected (normal left inverted right x axis y axis)
DP-1 disconnected (normal left inverted right x axis y axis)
```

Once the output has been selected, enter it in this part of the recalbox.conf:

```text
## Prefered external screen retrieved from ssh : xrandr
system.externalscreen.prefered=HDMI-1
## Force selected external screen to resolution ex : 1920x1080
system.externalscreen.forceresolution=1920x1080
```

## More info

[https://doc.ubuntu-fr.org/xrandr](https://doc.ubuntu-fr.org/xrandr)

