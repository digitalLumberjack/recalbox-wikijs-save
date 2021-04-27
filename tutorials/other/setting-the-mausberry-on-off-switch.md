# Setting the Mausberry ON/OFF Switch

## Introduction <a id="introduction"></a>

Mausberry circuits manage the activation and deactivation of the Raspberry Pi using an ON / OFF switch. This type of circuit can be used to use the on / off switch of an NES and its RESET button for example.


>**Note:**  
>This wiki is dedicated to version v4 on Raspberry Pi 2/3 of Recalbox
>
{.is-info}


>**WARNING!**
>
>If you are using a version newer than v4.0.0 beta 3, follow the instructions for version V4B3.
>
>If you are using a version older than v4.0.0 beta 3, follow the instructions for version V4B2.
>
{.is-danger}

## ​Tuto V4B3​

### Connections and wiring

For connections on the Pi, use GPIO ports 23 and 24 \(pin 16 and 18\). The Mausberry is operational with the GPIO23 = OUT / IN = GPIO24. You will find the figure in the Attachments.

### Procedure

#### Prerequisite

1. Your Raspberry Pi must be connected to the network
2. You must know the IP address of your Raspberry Pi. This can be accessed from the Recalbox menu. The IP address should look like: 192.168.0.49 You can also follow this link: \([https://recalbox.gitbook.io/tutorials/ip/discover-your-ip-on-the-network](https://recalbox.gitbook.io/tutorials/ip/discover-your-ip-on-the-network)\)

### Steps

Go to the Recalbox web interface from your internet browser example: [http://192.168.0.49](http://192.168.0.49) Click on Read and edit the Recalbox configuration file In the section: A - System Options uncommented to obtain:

Save!

###  <a id="procedure"></a>

1. Votre Raspberry Pi doit être connecté au réseau
2. Vous devez connaître l'adresse IP de votre Raspberry Pi. Celle-ci est accessible depuis le menu Recalbox. L'adresse IP doit ressembler à : `192.168.0.49` Vous pouvez également suivre ce lien : \([https://recalbox.gitbook.io/tutorials/ip/discover-your-ip-on-the-network](https://recalbox.gitbook.io/tutorials/ip/discover-your-ip-on-the-network)\)

#### Étapes <a id="etapes-1"></a>

1. Go to the Recalbox web interface from your internet browser example: `http://192.168.0.49`
2. Click on `Read and edit the Recalbox configuration file`
3. In the section : `A - System Options` uncommented to obtain:

`# ------------ A - System Options ----------- #` `# Uncomment the system.power.switch you use` `system.power.switch=MAUSBERRY # http://mausberry-circuits.myshopify.com/pages/setup`

Save!

## Tuto V4B2​ <a id="tuto-v-4-b2"></a>

### Connections and wiring <a id="connections-and-wiring-2"></a>

For connections on the Pi, use GPIO ports 20 and 21. The Mausberry is operational with GPIO20 = OUT / IN = GPIO21. You will find the figure in the Attachments.

### ​Procedure​

#### Prerequisite

1. Your Raspberry Pi must be connected to the network
2. You must know the IP address of your Raspberry Pi. This can be accessed from the Recalbox menu. The IP address should look like: 192.168.0.49 You can also follow this link: \([https://recalbox.gitbook.io/tutorials/v/francais/reseau/ip/connaitre-lip-sur-son-reseau](https://recalbox.gitbook.io/tutorials/v/francais/reseau/ip/connaitre-lip-sur-son-reseau)\)
3. You must be able to connect to your Recalbox via SSH. On Windows, you can use software such as [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) or [Kitty](https://www.fosshub.com/KiTTY.html)​

### ​Steps <a id="undefined-2"></a>

1. Connect via [SSH](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal) to your Recalbox
2. Go to the system directory &gt; `cd /recalbox/share/system/`
3. Create a setup.sh &gt; `nano setup.sh`
4. Copy the contents of the setup.sh Attachments
5. Save with this shortcut&gt; `Ctrl + X`
6. Create a file S99maus &gt; `nano S99maus`
7. Copy the contents of the Attachments **Script: S99maus** &gt; `nano S99maus`
8. Save with this shortcut &gt; `Ctrl + X`
9. You need to temporarily switch the system that is in read-only mode to read / write mode. To do this, run the following command: `mount -o remount, rw /`  The system will revert to read-only mode on the next reboot
10. Run the script setup.sh&gt; `bash setup.sh`
11. Find the new script&gt; `nano /recalbox/scripts/mausberry.sh`
12. Copy the S99maus file to the /etc/init.d/ directory &gt; `cp /recalbox/share/system/S99maus /etc/init.d/`
13. Give execution rights to the script &gt; `chmod 775 /etc/init.d/S99maus`
14. Run the script &gt; `/etc/init.d/S99maus start`
15. You will get an error message like this, but the Mausberry will be functional: `bad -o argument ‘command'`

​

## Attachments

### Connections and wiring

![](http://www.windtopik.fr/wp-content/uploads/2014/11/RPI-GPIO-N-.png)

### Script : setup.sh <a id="script-setup-sh"></a>

```text
echo '#!/bin/bash

#C'est la broche GPIO connectée au fil de l'interrupteur marqué OUT
GPIOpin1=20

#C'est la broche GPIO connectée au fil de l'interrupteur marqué IN
GPIOpin2=21

echo "$GPIOpin1" > /sys/class/gpio/export
echo "in" > /sys/class/gpio/gpio$GPIOpin1/direction
echo "$GPIOpin2" > /sys/class/gpio/export
echo "out" > /sys/class/gpio/gpio$GPIOpin2/direction
echo "1" > /sys/class/gpio/gpio$GPIOpin2/value
while [ 1 = 1 ]; do
power=$(cat /sys/class/gpio/gpio$GPIOpin1/value)
if [ $power = 0 ]; then
sleep 1
else
poweroff
fi
done' > /recalbox/scripts/mausberry.sh
chmod 777 /recalbox/scripts/mausberry.sh
```

​

### Script : S99maus <a id="script-s-99-maus"></a>

```text
#!/bin/bash
### BEGIN INIT INFO
# Provides: mausberry.sh
# Required-Start: $network $local_fs $remote_fs
# Required-Stop: $network $local_fs $remote_fs
# Default-Start: 2 3 4 5
# Default-Stop: 0 1 6
# Short-Description: switch mausberry init script.
# Description: Starts and stops SwitchDaemon service.
### END INIT INFO

#VAR
RUN="/recalbox/scripts/mausberry.sh"
BTD_PID=$(ps -eo pid,command | grep "/bin/bash $RUN" | grep -v grep | awk '{print $1}')

serviceStatus() {
   if [ ! -z "$BTD_PID" ]; then
      echo -e '33[0mservice mausberry.sh ['$BTD_PID'] [33[33;32m OK 33[0m]'
   else
      echo -e '33[0mservice mausberry.sh [33[33;31m KO 33[0m]'
   fi
}

# Carry out specific functions when asked to by the system
case "$1" in
   start)
      echo "Starting script $RUN ..."
      if [ -z "$BTD_PID" ]; then
         nice -n 19 $RUN&

         if [ $? -eq 0 ]; then
            echo -e "33[0mscript $RUN [33[33;32m STARTED 33[0m]"
         fi
      else
         echo "script $RUN already started ['$BTD_PID']!"
      fi
      #serviceStatus
   ;;
   stop)
      echo "Stopping script $RUN ..."
      if [ ! -z "$BTD_PID" ]; then
         kill $BTD_PID

         if [ $? -eq 0 ]; then
            echo -e "33[0mscript $RUN [33[33;31m STOPPED 33[0m]"
         fi
      fi
      #serviceStatus
   ;;
   status)
      serviceStatus
   ;;
   *)
      echo "Usage: /etc/init.d/S99maus {start | stop | status}"
      exit 1
   ;;
esac

exit 0
```

