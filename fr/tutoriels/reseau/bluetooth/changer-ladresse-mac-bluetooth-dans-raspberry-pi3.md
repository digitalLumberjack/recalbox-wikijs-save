---
title: Changer l'adresse MAC bluetooth dans Raspberry Pi3
---

# Changer l'adresse MAC bluetooth dans Raspberry Pi3

## Why?

In my case I have a malfunctioning raspberry pi3 that none of the USB ports works, so it's impossible for my PS3 wireless controls to pair. Changing the Bluetooth mac address I can sync the controllers with other raspberry and then just clone the mac :\)

## Prerequisites

You will need to add files to your system partition, you can do it by mounting the sd-card or by SSH \(I do recommend [FileZilla](https://filezilla-project.org/) for that\) and a [SSH terminal.](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal)

## Install bdaddr

Fist you need the bdaddr tool installed, you could [compile it](http://www.petrilopia.net/wordpress/wp-content/uploads/bdaddrtar.bz2) using a Raspibian image or just download the pre-compiled binary at [https://www.tbit.com.br/files/static/bdaddr.gz](https://www.tbit.com.br/files/static/bdaddr.gz) extract it to the `/bin` folder of your recalbox and then make it executable by:

```text
chmod +x /bin/bdaddr
```

Remember to make your system partition writable first by `mount -o remount,rw /`

## Change your mac

Ok now you can change the Bluetooth mac address by \(example\):

```text
bdaddr -i hci0 -r B8:27:EB:00:00:00
hciconfig hci0 reset
```

## Change at boot time

Edit or create the initialize script `recalbox\share\system\custom.sh`:

```text
#!/bin/sh
sleep 2
/bin/bdaddr -i hci0 -r B8:27:EB:00:00:00
hciconfig hci0 reset
```

