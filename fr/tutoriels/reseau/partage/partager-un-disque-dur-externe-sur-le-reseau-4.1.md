---
title: Partager un disque dur externe sur le réseau \(4.1\)
---

# Partager un disque dur externe sur le réseau \(4.1\)


>**But:**   
>_Faire **apparaître un disque dur supplémentaire** \(non utilisé pour les roms, en supplément du SHARE utilisant par exemple la SD\) **branché en USB sur la recalbox** **sur le réseau windows** \(SAMBA\) aux coté du **\SHARE** comme le ferait **un NAS**._
{.is-info}


>**Sur Windows** vous pouvez utilisez **Putty en ligne de commande** ou [WinSCP](http://winscp.net/), beaucoup plus pratique, car compile **console**, **gestionnaire de fichier** et **éditeur de texte**, trois fonctions utilisées dans cette manipulation.
{.is-warning}

**La manip a été testé sur la 4.1**, les versions précédentes demandaient plus de modifications, telles que le montage du disque dans le FSTAB.

* Se connecter classiquement à la recalbox url: **recalbox** login: **root** mdp: **recalboxroot** 
* Lancez la commande **mount -o remount,rw /** afin de **déverrouiller la protection en écriture** des fichiers système \(le **slash** à la fin est important, le déverrouillage durera jusqu'au reboot\). 
* Modifiez **/etc/samba/smb.cfg** et rajouter à la fin :

```text
[usb]
comment = usb
path = /media/usb0
writeable = yes
guest ok = yes
create mask = 0644
directory mask = 0755
force user = root
```

* **Sauvegarder et redémarrer la recalbox**, la modification sera **valable jusqu'à la prochaine mise à jour.**

