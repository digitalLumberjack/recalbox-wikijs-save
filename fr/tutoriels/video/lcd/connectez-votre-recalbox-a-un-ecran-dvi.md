---
title: Connectez votre Recalbox à un écran DVI
---

# Connectez votre Recalbox à un écran DVI

Vous devez **connecter votre Recalbox sur un écran DVI** mais vous obtenez **un écran noir** ou **une ligne rose sur le bord de l'écran ?**

* Alors éditez le [fichier config.txt](/v/francais/tutoriels/systeme/modification/editer-le-fichier-config.txt), et **commentez la ligne :** `hdmi_drive=2` avec un \# : `#hdmi_drive=2`


>**Attention :**
>
>La partition /boot est en lecture seule.  
>Donc, **avant de pouvoir modifier** le fichier **config.txt**, vous devez monter la partition **/boot** avec des droits de _lecture-écriture_**.**
{.is-danger}

* **Connectez-vous** [en accès root](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal) via SSH puis **saisissez la commande** suivante :  `mount -o remount, rw /boot`

