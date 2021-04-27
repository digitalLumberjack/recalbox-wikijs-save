# Security

As of version 4.0.0, the Recalbox is not secure against attacks in its default configuration. As a general rule:


>* Do not connect your Recalbox directly to the Internet
>* Do not store any sensitive data on your Recalbox
>* Make backups
>* Turn off your Recalbox between sessions
{.is-danger}

## Root password <a id="root-password"></a>

The Recalbox comes with a default root password. Up to version 4.0.0 it is possible to change the root password by doing the following, from a command prompt:

* Remount the / partition in read-write mode

  `mount -o remount,rw /`

* Change the root password

  `passwd`


>Please note that you will have to redo this operation after every update, as updating will cause the Recalbox to overwrite files and reset the root password to its default value. Version 4.1 and above should get rid of the default password.​
{.is-info}

## Network services <a id="network-services"></a>

The Recalbox enables several services by default. While convenient, these are easy entry points for attackers. It is a good practice to disable any service you are not using by editing the 'Network' section of [recalbox.conf](getting-started/the-recalbox.conf-file.md) \(2\)

\(2\) To edit this file, two options:

* Open a command prompt, and once connected, type:

  nano recalbox.conf

* Or, from your computer, open a web browser at: http://\/ in order to access recalbox manager and edit the configuration from the corresponding page.

### - Wifi <a id="wifi"></a>

If you don't need any network connection or if you use a network cable, turn wifi off:

```text
wifi.enabled=0
```

Please note that Recalbox stores your wifi password in clear text in the field wifi.key, so make sure to clear this field when turning wifi off. Version 4.1 shall not store the wifi password in clear text anymore.

### - Samba <a id="samba"></a>

Samba is useful for file transfer from another computer. If you don't use this service, turn it off by using:

```text
system.samba.enabled=0
```

Version 4.1 should support password-protected Samba shares.

### - Virtual Gamepads <a id="virtual-gamepads"></a>

Virtual gamepads enables you to use your phone or tablet as a gamepad. If you don't use these, turn off the service by typing:

```text
system.virtual-gamepads.enabled=0
```



## Recalbox Manager <a id="recalbox-manager"></a>

Recalbox comes with a built-in webserver, running on port 80. This server lets you drag and drop files such as roms from your desktop to your recalbox and change the configuration. However, it's also a golden path for an attacker to own your box. So if you don't use the Recalbox manager \(for example, because you're fine with your config and set of roms, or if you use the samba share for rom upload\), you can turn it off in the following way:

```text
system.manager.enabled=0
```

These steps should make your box \(and by consequence all devices connected to the same network\) a little bit more secure.

