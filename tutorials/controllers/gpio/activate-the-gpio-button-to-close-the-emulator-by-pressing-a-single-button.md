# Activate the GPIO button to close the emulator by pressing a single button

This python script for Raspberry Pi allows a button to be used to close the emulator by pressing a single GPIO button. It is compatible with any other function or script previously assigned to the buttons.

The button selected by default is the **Start button on Player 1;** can be changed during installation by anyone else, because it does not remove any previous functions. The emulator closes after pressing the button for at least 0.5 s. The button activation time can also be changed.

## Required:

* A Recalbox on the Raspberry Pi that uses GPIO commands \(it is not necessary to have a free button\).
* The Raspberry Pi must have access to the Internet:
  * You can activate and configure the wifi and host name, obtain the IP recalbox, the SSID of your network and the network key with a keyboard. Once validated, wifi is activated. There is a known bug that does not allow you to enter all the characters required for the SSID or key. You can configure it directly from your wifi using [recalbox.conf.](/basic-manual/getting-started/the-recalbox.conf-file)
* A computer on which you can perform root SSH access on the Rapsberry \(on Windows or Mac, a program such as PuTTY may be required\).

## Installation:

* Open an ssh session from your computer to the Raspberry.
* Once logged in, copy and paste this command into the ssh session:

`wget --quiet --show-progress -O /recalbox/share/system/exit-emu-1b https://gist.githubusercontent.com/DjLeChuck/446cd415575f03c927627e378979027d/raw/9ebe3a5e178ff047b536220afd513981095fb41d/exit-emu-1b-installer && chmod 755 /recalbox/share/system/exit-emu-1b && /recalbox/share/system/exit-emu-1b install`

The installer will display a list of possible GPIO port maps corresponding to the GPIO map for Recalbox, corresponding to the following image:

![GPIO port mapping](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M1pg9d9WjOYChpb5hus%2F-M1pzARovpy60-nqM0ZG%2FgaU6t.png?alt=media&token=89aed639-da21-4c6c-afe6-590fe47e423e)

* After selecting the button port to which you want to assign the script, the installer will request the delay to exit the emulator, you will need to enter the desired delay in seconds. \(It is important to answer both questions, otherwise the installer will fail\)
* After a few seconds, if the result is a message on the screen saying "Start button", everything went well and now we have the button script installed and working.

## Installed files:

* [/recalbox/scripts/rpi-exit-emu-1b.py](https://gist.github.com/DjLeChuck/445ce3d37f41f12d5bf8cb9482db4027)
* [/etc/init.d/S98exit-emu-1b](https://gist.github.com/DjLeChuck/5f798b0d4af4071a92111bf61703aeb1)
* [/recalbox/share/system/exit-emu-1b](https://gist.github.com/DjLeChuck/446cd415575f03c927627e378979027d)

## Uninstall:

* Start a [ssh session](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal)
* type `/recalbox/share/system/exit-emu-1b uninstall`


>**Warning:**
>
>In the Retroarch's default configuration, the script terminates the emulators by brute force, using a killall command which, depending on the core used, can cause the loss of some changes to the emulator configuration made during the game. For example, this happens with Mame2003.
>
>To avoid this, I implemented the closing of the emulator through a network command for Retroarch. Now Retroarch will close correctly and you will not lose any configuration changes in the emulators.
>{% endhint %}
>
>{% hint style="info" %}
>**Note:**
>
>This change is only for Retroarch, although it covers most of the emulators in the system, emulators like **Fb2x, scummvm or mupen64plus** are still disabled by brute force, until you find another way to apply it.
>
{.is-danger}

## Tips and tricks:

* If at any time you need to assign the emulator close function to another button, just restart the installer with the command `/recalbox/share/system/exit-emu-1b install`

  and put in the installation the new port number you want.

* If you change your emulator's configuration and exit with the button assigned at installation, those changes will be lost. Make sure they are in the file:`/recalbox/share/system/configs/retroarch/retroarchcustom.cfg` Or in the Retroarch custom configuration file where you use the `Network_cmd_enable` parameter to `= "true"`.
* If, for some reason, the script stops working and the button loses the function of closing the emulator, you can make it work again with the command: `/etc/init.d/S98exit-emu-1b restart` you will need to insert it in an [SSH session](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal).

