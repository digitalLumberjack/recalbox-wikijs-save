# Manual IP settings

## Recalbox 4.0​ <a id="recalbox-4-0"></a>

 In order to **select a fixed ip for your recalbox,** you will have to edit the file  `/etc/network/interfaces`.

* ​ [Get a root access from Terminal ](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal)and edit the file with :`nano /etc/network/interfaces`


>**Information:**
>
>For a **permanently solution** you must **edit the**`interfaces.base` file. And before you can edit this file you must remount the file system as rw. So try this commands: `mount -o remount,rw /` `nano /etc/network/interfaces.base`
>{% endhint %}
>
>​
>
>* **Search the line** containing the **interface** you want to modify \(ethX para ethernet, wlanX para wifi\):
>
>```text
>auto eth0
>iface eth0 inet dhcp
>```
>
>### So let us modify eth0 ip. <a id="vamos-mudar-o-endereco-ip-eth-0"></a>
>
>* **Replace** with the **static ip** settings :
>
>```
>auto eth0
>iface eth0 inet static
>address 192.168.1.10
>network 192.168.1.0
>netmask 255.255.255.0
>broadcast 192.168.1.255
>gateway 192.168.1.254
>```
>
>* Neste exemplo, sua: **A rede local** tem como endereço do modem 192.168.1.x. **O endereço da sua placa** é 192.168.1.254. **Sua máscara de rede** é, portanto, 255.255.255.0. E você deseja que **seu endereço** seja **192.168.1.10**
>
>By switching to a static IP address, you will lose the configuration of your DNS server\(s\) in the process. In order to get name resolution working, you will have to create a file names`/etc/resolv.conf`. By default, this files points to an auto-generated file located at `/tmp/resolv.conf`, so in order to do it once and for all, run the following commands:
>
>```text
>rm /etc/resolv.conf
>nano /etc/resolv.conf
>```
>
>Enter the following lines, which corresponds to DNS servers of the OpenDNS project:
>
>```text
>nameserver 208.67.222.222nameserver 208.67.220.220
>```
>
>Save the file.
>
>Now reload the settings with :  
>`ifdown eth0 && ifup eth0`
>
>{% hint style="warning" %}
>THESE EDITS **WILL BE OVERWRITTEN WITH EACH NEW UPDATE** - You will have to repeat these tasks after each update.
>
{.is-info}

## Starting from Recalbox 4.1 <a id="a-partir-de-recalbox-4-1"></a>

[Get a root access from Terminal](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal)

Type `connmanctl services` and note what is returned, for example:

`*AO Wired ethernet_b827eb6462be_cable`

* Then type: `cd`

`nano custom.sh`

```text
#!/bin/bash
/usr/bin/connmanctl config ethernet_b827eb6462be_cable --ipv4 manual 192.168.1.181 255.255.255.0 192.168.1.1
mount -o remount,rw /
echo "nameserver 208.67.222.222" >> /etc/resolv.conf
echo "nameserver 208.67.220.220" >> /etc/resolv.conf
```

Replace ethernet\__\*_ by the **value you've got previously** and the **IP address you want** to give. You might wish to replace the DNS server IPs of the OpenDNS project, with the DNS servers \(if any\) provided by your own ISP.

 hen quit from nano text editor by `Ctrl X`, answer the saving question by typing `Y` and then finally `Enter`.

 After quiting nano and back to terminal shell, type the command `chmod +x custom.sh`, making it executable, then `reboot` to restart your Recalbox.

## Starting from Recalbox 6.1 <a id="a-partir-de-recalbox-4-1"></a>

Since version 6.1, it is possible to edit the IP manually in the recalbox.conf file:

```text
## Wifi - static IP
## if you want a static IP address, you must set all 3 values (ip, gateway, and netmask)
## if any value is missing or all lines are commented out, it will fall back to the
## default of DHCP
;wifi.ip=manual ip address
;wifi.gateway=new gateway
;wifi.netmask=new netmask
```

You need to remove the **`;`**from the front of the last three lines, or the configuration will not work, and fill them in with the information you want, for example:

```text
wifi.ip=192.168.1.10
wifi.gateway=192.168.1.254
wifi.netmask=255.255.255.0
```

