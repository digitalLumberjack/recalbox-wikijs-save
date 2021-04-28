---
title: Blacklist wifi intégré du RPI 3
---

# Blacklist wifi intégré du RPI 3

Déçu par le **débit du wifi intégré** du raspberry pi 3, tu souhaites le **désactiver**.

Voici comment faire :

* **Connecte toi** en [ssh via putty ou winscp](/v/francais/tutoriels/systeme/acces/acces-reseau-via-winscp) ​
* **Monter** la partition en écriture :  `mount -o remount,rw /`  
* **Éditer** le fichier suivant : `nano /etc/modprobe.d/blacklist.conf`   
* **Ajouter** cette ligne : `blacklist brcmfmac`  
* **Enregistre** `ctrl+x` + **`Y` puis** `reboot`  
* **Branche** ton dongle wifi et **teste**.

