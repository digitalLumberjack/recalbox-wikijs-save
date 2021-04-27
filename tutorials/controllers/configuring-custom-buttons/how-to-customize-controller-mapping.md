# How to customize controller mapping

For those who want to change the button mapping of the retroarch's core emulators.

* **Start a game** from that emulator
* **In the retroarch menu** \(hotkey + b\), go to "**Settings**" and then "**Input user 1 keys**"
* **Reconfigure the keys**, remember to **have a keyboard available**, because while you are remapping the control, it may be unresponsive, in this case, **you use the keyboard** \("w" and "x" to validate and return\)
* Then **go to** "**Insert Hotkeys**" and reconfigure the keys as desired
* **Go back to the first retroarch menu** and choose **"Save new configuration**" \(usually the name of the configuration is **core\_name.cfg**, for example **catsfc.cfg** if you are on **snes + catsfc**\)
* **Connect via ssh** to Recalbox, and **modify the name of the configuration file** to get something more meaningful.

Example for the **neogeo emulator:**

`mv /recalbox/share/system/configs/retroarch/catsfc.cfg /recalbox/share/system/configs/retroarch/inputs/neogeocustom.cfg`​

* **Modify** the **recalbox.conf** file by **adding the following line** to take into account the new configuration:`neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeocustom.cfg`


>Warning:
>
>All other settings are the **default,** so **no shader, cheat, or whatever.**
{.is-danger}

