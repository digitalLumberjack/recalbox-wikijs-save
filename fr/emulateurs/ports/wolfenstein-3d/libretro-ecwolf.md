---
title: Libretro ECWolf
---

# Libretro ECWolf

**Libretro ECWolf** est un moteur de jeu de port source pour Wolfenstein 3D. This port is courtesy of phcoder.

ECWolf est un portage du moteur Wolfenstein 3D basé sur Wolf4SDL. Il combine le moteur original Wolfenstein 3D avec l'expérience utilisateur de ZDoom pour créer le port source Wolf3D le plus convivial pour les utilisateurs et les modificateurs.

Comme ZDoom, ECWolf vise à prendre en charge tous les jeux qui utilisent le moteur Wolfenstein 3D, y compris Blake Stone \(à venir dans ECWolf 3.0\), Corridor 7, Operation Body Count, Rise of the Triad et Super 3D Noah's Ark. ECWolf supportera également Macintosh Wolfenstein 3D avec toutes ses missions créées par l'utilisateur \(à venir dans ECWolf 2.0\).

* Un binaire unique exécute tous les jeux pris en charge. \(Wolfenstein 3D, Spear of Destiny, ...\)
* Prise en charge complète des modes haute résolution avec correction du rapport d'aspect, y compris la prise en charge d'un écran large.
* Schémas de contrôle modernes \(WASD + souris\).
* Automap de style Mac Wolf / S3DNA / ROTT.
* Emplacements de sauvegarde illimités.
* Ceci est en fait basé sur le moteur Wolf3D au lieu d'une recréation ou de forcer dans un moteur plus moderne.

  * Logiciel rendu à l'aide de la même diffusion de rayons 8 bits.

ECWolf peut exécuter le contenu suivant:

* Wolfenstein 3D
* Spear of Destiny
* Arche de Noé Super 3D

## ![](/migration-images/emulateurs/ports/wolfenstein-3d/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/ecwolf/blob/master/docs/license-gpl.txt).

## ![](/migration-images/emulateurs/ports/wolfenstein-3d/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ports/wolfenstein-3d/cogwheel-145804_640.png)Fonctionnalités



## ![](/migration-images/emulateurs/ports/wolfenstein-3d/tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](/migration-images/emulateurs/ports/wolfenstein-3d/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .zip
* .pk3

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁ports  
┃ ┃ ┃ ┃ ┣ 📁Wolfenstein 3D  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 **ecwolf.pk3**  

## ![](/migration-images/emulateurs/ports/wolfenstein-3d/hammer-28636_640.png)Configuration avancée de l'émulateur



## Création de mods

* Créez des mods sans travailler avec le code source !
  * Les mods fonctionnent avec toutes les plates-formes prises en charge, y compris Windows, macOS et Linux.
* Support de texture arbitraire haute résolution, plat et sprite.
* Pushwalls mobiles simultanés illimités.
* Des choses illimitées.
* Taille de la carte illimitée. \(Bien que les limites techniques limitent le format GAMEMAPS à 181x181.\)
* Utilise des formats de script et des formats de données similaires à ceux de ZDoom.
  * Les utilitaires d'édition Doom fonctionnent avec ECWolf \(sauf pour les niveaux\).

Notez que jusqu'à ECWolf 2.0, bien que des changements radicaux ne soient pas exclus, la rétrocompatibilité des mods ne sera pas nécessairement conservée. Consultez [le wiki](http://maniacsvault.net/ecwolf/wiki/Version_compatibility) pour plus d'informations.

## ![](/migration-images/emulateurs/ports/wolfenstein-3d/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/ecwolf/](https://github.com/libretro/ecwolf)
* **Code source Officiel :** 
* **Site Officiel :** [http://maniacsvault.net/ecwolf/](http://maniacsvault.net/ecwolf/)
* **Forum Officiel :** [https://forum.drdteam.org/viewforum.php?f=174](https://forum.drdteam.org/viewforum.php?f=174)
* **Documentation Officiel :** [http://maniacsvault.net/ecwolf/wiki/Main\_Page](http://maniacsvault.net/ecwolf/wiki/Main_Page)​

