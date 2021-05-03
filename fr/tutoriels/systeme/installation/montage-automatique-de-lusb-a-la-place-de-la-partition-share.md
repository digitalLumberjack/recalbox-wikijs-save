---
title: Montage automatique de l'USB à la place de la partition share
---

# Montage automatique de l'USB à la place de la partition share

Il est possible **d'utiliser un disque externe** en tant que **partition SHARE.**


>Cela permet de stocker toutes vos roms, vos médias et vos fichiers personnels sur un support plus gros, comme une clé USB ou un disque dur externe.
{.is-info}

* Vous allez **avoir besoi**n d'un [accès root](/fr/tutoriels/systeme/acces/acces-root-via-terminal) ainsi que d'un **support formaté en FAT32.** 
* Utilisez **la commande** `mount` pour **voir les volumes montés :**

```text
rootfs on / type rootfs (rw)
/dev/root on / type ext4 (rw,relatime,data=ordered)
devtmpfs on /dev type devtmpfs (rw,relatime,size=242096k,nr_inodes=60524,mode=75 5)
proc on /proc type proc (rw,relatime)
devpts on /dev/pts type devpts (rw,relatime,gid=5,mode=620,ptmxmode=000)
tmpfs on /dev/shm type tmpfs (rw,relatime,mode=777)
tmpfs on /tmp type tmpfs (rw,relatime)
sysfs on /sys type sysfs (rw,relatime)
/dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
/dev/mmcblk0p5 on /boot type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
/dev/sda1 on /media/usb0 type vfat rw,sync,nodev,noexec,noatime,nodiratime,fmas=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro _
```

* **Repérer la ligne** décrivant le montage de votre **support externe**. Elle devrait **ressemble**r à ceci :

`/dev/sda1 on /media/usb0 type vfat` **&lt;-----**

* **Copiez** toutes les données depuis **la partition SHARE** vers **votre support** :

`cp -rv /recalbox/share/* /media/usb0/`


>L'opération peut prendre du temps, en fonction de la taille de votre collection de roms.
{.is-info}

* Maintenant, **éditez le point de montage** dans le fichier **/etc/fstab :**

`vi /etc/fstab`

* **Appuyez** sur **"i"** pour **éditer** 
* **Ajoutez** un **"\#"** pour **commenter la ligne suivante :**

```text
/dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
```

Comme **ceci :**

```text
#/dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
```



* Et **ajoutez la nouvelle ligne** que votre appareil montera sur **/recalbox/share** :

`/dev/sda1 /recalbox/share vfat defaults,rw 0 0` 

* **Appuyez** maintenant sur **"Echap"**, sur **":"**, sur **"wq"**, et finalement sur **"Entrée"** pour **sauvegarder les modifications et quitter.** 
* Vous pouvez maintenant **redémarrer**.


>**Depuis Recalbox 4.0.0,** le système de stockage sur support amovible est **géré directement dans EmulationStation**.  
>  
>Pour plus d'informations, vous pouvez consulter [ce tutoriel](/fr/tutoriels/systeme/installation/utiliser-un-peripherique-usb-de-stockage-sur-recalbox).
{.is-info}

