---
title: N64 controllers configuration
---

# N64 controllers configuration

## EDIT:

By default, **/usr/share/mupen64plus** is read-only, so it won't work unless you enable read-write mode using this command `mount -o remount, rw /`​

## EDIT FOR RECALBOX VERSION&gt; V4.1

jstest no longer exists -&gt; use sdl2-jstest

In case your button 0 exits the emulator \(like the hotkey would\), you will need to modify the following file: `~/configs/mupen64/mupen64plus.cfg` =&gt; Change the parameter **Joy Mapping Stop = "J1B0"** to **Joy Mapping Stop = ""**​

## RECALBOX V3.3.0 ONLY

Mupen64plus is not auto-configured by Recalbox like other emulators. So you have to do it manually.

_For information: the button of your **Hotkey** will be automatically assigned to the output function of the emulator._

### A - Add your controller configuration to the system:

​

To configure your controller, you will need information on it. Log in as [root](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal), and use the[ jstest ](https://recalbox.gitbook.io/tutorials/obsolete/test-your-joystick-with-jstest)command:

`jstest /dev/input/js0`

or

`sdl2-jstest -l`

In my case, I get:

```text
Joystick (Broadcom Bluetooth Wireless  Joystick                        ) has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (Trigger, ThumbBtn, ThumbBtn2, TopBtn, TopBtn2, PinkieBtn, BaseBtn, BaseBtn2, BaseBtn3, BaseBtn4, BaseBtn5, BaseBtn6).
```

Once the name of the controller and each button has been identified, you must modify this file:`/usr/share/mupen64plus/InputAutoCfg.ini`

Use this command:

`nano /usr/share/mupen64plus/InputAutoCfg.ini`

Now at the end of the file add the configuration info, like this:

_This model is an example, with information about my own controller \(controller name, button number etc ...\). You will need to adapt it with the information from your own controller._

```text
[Broadcom Bluetooth Wireless  Joystick                        ]
plugged = True
plugin = 2
mouse = False
AnalogDeadzone = 4096,4096
AnalogPeak = 32768,32768
DPad R = hat(0 Right)
DPad L = hat(0 Left)
DPad D = hat(0 Down)
DPad U = hat(0 Up)
Start = button(9)
Z Trig = button(7)
B Button = button(2)
A Button = button(1)
C Button R = axis(3+)
C Button L = axis(3-)
C Button D = axis(2+)
C Button U = axis(2-)
R Trig = button(5)
L Trig = button(4)
Mempak switch = button(6)
Rumblepak switch = 
X Axis = axis(0-,0+)
Y Axis = axis(1-,1+)
```

Once your configuration is correct, do `Ctrl + x` to quit nano, agree to overwrite the file with `y`, and press `Enter` to quit. You can now start an N64 game, and test your configuration.

Your configuration is correct, do you like it? Great ^^ But there is a "problem". When you update your Recalbox, all of these configuration files are also updated. They will therefore be reset. If you don't want to do this after each update, make a backup of your `InputAutoCfg.ini` file. You can also add your configuration to Recalbox. You should consult this point, and post your own configuration in comment.

We will then add it to the system during a future update of Recalbox \(no longer necessary because a configgen is integrated since version 4.0.0 of Recalbox\).

### B - Add special commands

Mupen64plus does not support button combinations, like Retroarch emulators, to launch a special command. But you can assign unused buttons to a specific command, like save / load a savestate, change save locations, etc...

To do this, as a first step, you must identify all the unused buttons in your configuration. So as seen before, go to [root access](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal) and use the[ jstest command](https://recalbox.gitbook.io/tutorials/obsolete/test-your-joystick-with-jstest), then write down the code number of your unused buttons.

Now, still in root access, edit your `mupen64plus.cfg` file with this command:

`nano /recalbox/configs/mupen64/mupen64plus.cfg`

Then go to the section called `[CoreEvents]`. The correct section is this:

```text
# Joystick event string for stopping the emulator
Joy Mapping Stop = ""
# Joystick event string for switching between fullscreen/windowed modes
Joy Mapping Fullscreen = ""
# Joystick event string for saving the emulator state
Joy Mapping Save State = ""
# Joystick event string for loading the emulator state
Joy Mapping Load State = ""
# Joystick event string for advancing the save state slot
Joy Mapping Increment Slot = ""
# Joystick event string for taking a screenshot
Joy Mapping Screenshot = ""
# Joystick event string for pausing the emulator
Joy Mapping Pause = ""
# Joystick event string for muting/unmuting the sound
Joy Mapping Mute = ""
# Joystick event string for increasing the volume
Joy Mapping Increase Volume = ""
# Joystick event string for decreasing the volume
Joy Mapping Decrease Volume = ""
# Joystick event string for fast-forward
Joy Mapping Fast Forward = ""
# Joystick event string for pressing the game shark button
Joy Mapping Gameshark = ""
```

Keep in mind that Mupen64plus identifies `player 1` as `J0`, `player 2` as `J1` etc...  
So for example, if you want to add button number 10 of player 1 to the "save savestates" command, you must edit your file like this: `Joy Mapping Save State = "J0B10"`

And if you want to add button 5 of player 2 to the "load savestates" command, you have to edit your file like this: `Joy Mapping Load State = "J1B5"`

Once your configuration is correct, do ****`Ctrl + x` ****to quit nano, agree to overwrite the file with `y`, and press `Enter` to quit.

