---
title: Réinstallation propre
---

# Réinstallation propre

## **Que dois je faire avant une réinstallation propre du système ?**

### _**1. Je ne dispose pas de support amovible, uniquement la microsd**_

* Toujours avoir une copie de ses roms, scaps, bios sur son PC ou sur un disque de sauvegarde.
* Faire une sauvegarde du dossier Recalbox contenant les roms, bios, saves sur votre PC.
* Télécharger et réinstaller la [dernière version de Recalbox](https://archive.recalbox.com/) sur votre microsd avec etcher.
* C'est peut être le moment de penser à un support amovible non ?

#### Les bios

* Vérifier la signature de vos bios dans recalbox manager via votre connexion internet et navigateur web sur votre PC.
* Recalbox ajoute de nouveaux émulateurs qui ont parfois besoin de bios.



### _**2. Je dispose d'un support amovible \(clé usb/disque dur externe usb\)**_

* Le format exfat est conseillé pour les disques durs de grosses capacités mais le fat32 peut aller aussi
* Brancher le disque dur externe ou la clé USB sur votre PC, puis
  * renommer le dossier recalbox en recalbox.old
* Télécharger et installer [la dernière version de Recalbox](https://download.recalbox.com/fr/) sur votre microsd avec Etcher.
* Brancher votre disque dur externe ou clé usb sur votre Rpi/Odroid.
* Choisir votre support amovible pour votre support.
* L'arborescence du dossier Recalbox sera de nouveau créé sur votre périphérique externe.
* Éteindre votre recalbox.
* Brancher votre disque dur externe ou clé usb sur votre PC.
* Déplacer UNIQUEMENT LES ROMS, BIOS ET SAVE.
* **NE PAS déplacer les gamelist/scrap, custom theme et OVERLAYS**. \(Responsable de nombreux bugs\)
* Tester votre recalbox avec les paramètres par défaut.
* Si tout va bien, vous pouvez commencer à customiser vos réglages, progressivement.



## R**éinstallation propre du système**

Suivez le guide [Téléchargement et Installation de Recalbox.](/fr/usage-basique/preparation-et-installation)

