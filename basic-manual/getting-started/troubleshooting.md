# Troubleshooting

## Controllers

* The PS3 controller is blinking but does not associate
  * Plug a controller on the recalbox and wait 10 seconds. You can now unplug the controller and press the Home button.
* The PS3 controller seems dead
  * You must reset the controller by pressing a little button behind the controller in a little hole, with a paperclip.

## Other

* Black border, image too big
  * Use your tv remote to find the image menu, and set the image size to _1:1 pixel_ or _full_.

    If it doesn't work, try to activate the overscan in the recalbox menu **System Settings**.

    See \[\[Overscan settings\|Overscan-settings-\(EN\)\]\] for more information.
* Black screen on PC monitor
  * If you have a black screen on PC monitor \(hdmi or dvi\) edit the config.txt file \(MAJ at start\) and remove the line hdmi\_drive=2

    More info in \[\[Mini HowTo - Connect your recalbox to a DVI screen\|Connect-your-recalbox-to-a-DVI-screen-\(EN\)\]\]

## Hard reset

* If you want to reset the system, plug an usb keyboard and press Shift at startup. You can reinstall recalboxOS from here. All your data will be erased.

## Root access

* Use the username `root` and the password `recalboxroot`
* You can connect through ssh to the recalbox.
* You can access a terminal by quitting emulationstation with F4 and then press ALT+F2.

More info in \[\[Mini HowTo - Root access on terminal\|Root-access-on-terminal-\(EN\)\]\]

