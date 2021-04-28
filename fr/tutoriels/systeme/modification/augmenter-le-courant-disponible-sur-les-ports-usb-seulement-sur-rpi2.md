---
title: Augmenter le courant disponible sur les ports USB \(seulement sur RPi2\)
---

# Augmenter le courant disponible sur les ports USB \(seulement sur RPi2\)

Avec les **réglages par défaut**, le Raspberry **Pi 2** limite le courant à **600mA pour l'ensemble des 4 ports USB.** La modification logicielle qui est proposée ici **va étendre cette limite à 1200mA.**


>**Notes importantes :**
>
>* Cette modification **n'est pas uniquement** destinée à Recalbox.
>* Cette modification est **réversible.**
>* L'utilisation d'une alimentation de **2000mA est toujours préconisée**, quelque soit l'usage du Raspberry **Pi 2.**
>* Le **courant maximal** admissible par le Raspberry **Pi 2** est de **2000mA.**
{.is-warning}

## Raison d'effectuer cette modification : <a id="raison-deffectuer-cette-modification"></a>

**Avoir besoin de connecter**, sans utiliser un concentrateur USB auto-alimenté, de périphériques USB gourmands, sans dépasser la nouveau courant maximal de 1200mA sur les 4 ports USB.  
   
**Par exemple :** Un disque dur 2.5 pouces USB auto-alimenté.

## Exemple d'utilisation : <a id="exemple-dutilisation"></a>

* Utilisation d'un **disque SSD USB auto-alimenté** afin de stocker l'ensemble des roms, des bios et des sauvegardes.
* **Clé USB Wifi gourmande**
* Recharger/Utiliser **plusieurs manettes USB simultanément**

## Comment faire : <a id="comment-faire"></a>

* [​Editer le fichier config.txt](/v/francais/tutoriels/systeme/modification/editer-le-fichier-config.txt)_\*\*\*\*_
* **Rechercher** la présence éventuelle de la ligne "`max_usb_current=...`"
* **Ajouter la ligne** suivante "`max_usb_current=1`" ou **modifier sa valeur à 1** si elle existe déjà.
* **Enregistrer** le fichier **config.txt**
* **Redémarrer** le Raspberry Pi 2


>**Note :**
>
>Cette astuce fonctionne aussi sur le Raspberry Pi 3, mais la ligne `max_usb_current=...` n'existe pas dans le fichier config.txt .  
>Il faudra donc l'ajouter manuellement.
{.is-info}

