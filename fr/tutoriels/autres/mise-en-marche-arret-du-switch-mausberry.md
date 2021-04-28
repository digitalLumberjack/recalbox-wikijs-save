---
title: Mise en marche/arrêt du Switch Mausberry
---

# Mise en marche/arrêt du Switch Mausberry

## Introduction

Les circuits Mausberry gèrent l'activation et la désactivation du Raspberry Pi à l'aide d'un interrupteur ON/OFF.  
Ce type de circuit peut être utilisé pour utiliser l'interrupteur marche/arrêt d'une NES et son bouton de RESET par exemple.


>**Note :**
>
>Ce wiki est dédié à la version v4 sur Raspberry Pi 2/3 de Recalbox
{.is-info}


>**ATTENTION !**
>
>Si vous utilisez une version plus récente que la v4.0.0 beta 3, suivez les instructions de la version V4B3.
>
>Si vous utilisez une version plus ancienne que la v4.0.0 beta 3, suivez les instructions de la version V4B2.
{.is-danger}

## Tuto V4B3

### Connexions et câblage

Pour les connexions sur le Pi, utilisez les ports GPIO 23 et 24 \(broche 16 et 18\).  
Le Mausberry est opérationnel avec le GPIO23 = OUT / IN = GPIO24 . Vous trouverez en annexe la figure.

### Procédure

#### Prérequis

1. Votre Raspberry Pi doit être connecté au réseau
2. Vous devez connaître l'adresse IP de votre Raspberry Pi. Celle-ci est accessible depuis le menu Recalbox. L'adresse IP doit ressembler à : `192.168.0.49` Vous pouvez également [consulter ce tutoriel](/v/francais/tutoriels/reseau/ip/connaitre-lip-sur-son-reseau). 

#### Étapes

1. Allez sur l'interface web Recalbox à partir de votre navigateur internet exemple : `http://192.168.0.49`
2. Cliquez sur `Lire et éditer le fichier de configuration du Recalbox`
3. Dans la rubrique : `A - System Options` dé-commenté pour obtenir :

`# ------------ A - System Options ----------- #` `# Uncomment the system.power.switch you use` `system.power.switch=MAUSBERRY # http://mausberry-circuits.myshopify.com/pages/setup`

Sauvegardez !

## Tuto V4B2

### Connexions et câblage

Pour les connexions sur le Pi, utilisez les ports GPIO 20 et 21.  
Le Mausberry est opérationnel avec le GPIO20 = OUT / IN = GPIO21 . Vous trouverez en annexe la figure.



### Procédure

#### Prérequis

1. Votre Raspberry Pi doit être connecté au réseau
2. Vous devez connaître l'adresse IP de votre Raspberry Pi. Celle-ci est accessible depuis le menu Recalbox. L'adresse IP doit ressembler à : `192.168.0.49` Vous pouvez également consulter ce tutoriel.
3. Vous devez pouvoir vous connecter à votre Recalbox via SSH. Sous Windows, vous pouvez utiliser des logiciels tels que [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) ou [Kitty](https://www.fosshub.com/KiTTY.html)

### 

### Étapes

1. Connectez-vous via SSH sur votre Recalbox
2. Accéder au répertoire système &gt; `cd /recalbox/share/system/`
3. Créer un fichier setup.sh &gt; `nano setup.sh`
4. Copier le contenu de l'annexe setup.sh
5. Sauvez par ce raccourci &gt; `Ctrl + X`
6. Créer un fichier S99maus &gt; `nano S99maus`
7. Copier le contenu de l'annexe **Script: S99maus** &gt; `nano S99maus`
8. Sauvez par ce raccourci &gt; `Ctrl + X`
9. Vous devez faire passer temporairement le système qui est en mode lecture seule en mode lecture/écriture. Pour cela, exécutez la commande suivante : `mount -o remount, rw /`  Le système reviendra en mode lecture seule au prochain redémarrage
10. Lancez le script setup.sh &gt; `bash setup.sh`
11. Recherchez le nouveau script &gt; `nano /recalbox/scripts/mausberry.sh`
12. Copiez le fichier S99maus dans le répertoire /etc/init.d/ &gt; `cp /recalbox/share/system/S99maus /etc/init.d/`
13. Donner des droits d'exécution au script &gt; `chmod 775 /etc/init.d/S99maus`
14. Lancez le script &gt; `/etc/init.d/S99maus start`
15. Vous obtiendrez un message d'erreur comme celui-ci, mais le Mausberry sera fonctionnel : `bad -o argument ‘command'`

## Annexes <a id="annexes"></a>

### Branchements et câblage <a id="branchements-et-cablage-2"></a>

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

