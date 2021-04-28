---
title: Clonez votre carte SD
---

# Clonez votre carte SD


>Attention si tu veux **cloner vers une autre carte SD!** Deux cartes SD de **fabricants différents,** sensées être de **même capacité**, ne feront pas exactement la **même taille**. Tu risques donc de ne **pas pouvoir restaurer** ta sauvegarde sur une c**arte SD de marque différente**, sauf si celle-ci a une taille supérieure à celle de départ.
{.is-danger}

* **Pour cloner** ta carte SD et avoir un backup complet de ta recalbox tu peux utiliser ces logiciels :

  * **Windows** : [Win32 Disk Imager](http://sourceforge.net/projects/win32diskimager/) avec la fonction READ
  * **MacOS X** : ApplePi-Baker
  * **Linux** : Utilise la commande DD dans un terminal \(plus d'informations plus loin\)

* Branche ta carte SD dans votre PC utilisant linux. Déterminer quel périphérique est ta carte SD

`sudo fdisk -l`

* Une fois dans ton dossier de sauvegarde \(backup\), extrait et compresse ta carte SD avec cette commande :

`sudo dd if=/dev/sdX | gzip -9 > ./recalbox-20150411-sdb.img.gz`   
\(la lettre X doit être remplacée par la lettre déterminée à la première étape.\)

* **Pour restaurer** ta sauvegarde, branche ta carte SD formatée en FAT32 dans votre PC et utilise cette commande :

`gunzip ./recalbox-20150411-sdb.img.gz | sudo dd of=/dev/sdX`   
\(où /dev/sdX est ta carte SD\)   
_Pour suivre l'avancée du processus_ `dd`_, ouvrez un nouveau terminal et tapez la commande suivante_ `watch -n 5 sudo pkill -USR1 -n -x dd`

