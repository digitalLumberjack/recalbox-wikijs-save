# Connecting your Recalbox to a DVI monitor

You need to **connect your Recalbox to a DVI screen** but you get a **black screen or a pink line** on the edge of the screen?

Then edit the config.txt file, and **comment the following line** with a \# : `#hdmi_drive=2`


>**Warning :**
>
>Since recalbox v4.0.0, the /boot partition is read-only. So, before you can edit the config.txt file, you need to mount the /boot partition with read-write permissions.
{.is-danger}

* **Connect with root**, 
* Then enter the following command:  `mount -o remount, rw /boot`

