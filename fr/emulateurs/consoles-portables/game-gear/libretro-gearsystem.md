---
title: Libretro Gearsystem
description: libretro-super
---

# Libretro Gearsystem

**Libretro Gearsystem** est un émulateur open source, multi-plateforme, Sega Master System / Game Gear / SG-1000 écrit en C ++.

* Noyau Z80 très précis, comprenant des opcodes et des comportements non documentés tels que les registres R et MEMPTR.
* Prise en charge de Multi-Mapper: cartouches SEGA, Codemasters, SG-1000 et ROM uniquement.
* Détection automatique de région: NTSC-JAP, NTSC-USA, PAL-EUR.
* Base de données interne pour la détection des rom
* Émulation VDP très précise, y compris la synchronisation et la prise en charge du mode SMS2 uniquement.
* Émulation audio à l'aide de SDL Audio et de la bibliothèque Sms\_Snd\_Emu.
* Prise en charge des économies de RAM alimentées par batterie.
* Enregistrer les états.
* Support de triche Game Genie et Pro Action Replay.
* Fonctionne sous Windows, Linux, Mac OS X, Raspberry Pi, iOS et en tant que noyau libretro \(RetroArch\).

Le core Libretro Gearsystem a été créé parIgnacio Sanchez

## ![](/migration-images/emulateurs/consoles-portables/game-gear/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**GPLv3**](https://github.com/drhelius/Gearsystem/blob/master/LICENSE).

## 🔧 ****Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/game-gear/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats - Game Genie | ✔ |
| RetroArch Cheats - Pro Acion Replay | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| [Softpatching](https://docs.libretro.com/guides/softpatching/) | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/game-gear/tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/game-gear/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .gg
* .zip
* .7z

Ce système supporte les roms compressées au format .zip/.7z. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip/.7z doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip/.7z ne doit contenir qu'une seule rom compressée.

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁gamegear  
┃ ┃ ┃ ┃ ┣ 🗒**jeux.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/game-gear/hammer-28636_640.png)Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder aux options

Vous pouvez configurer diverses options de deux façons différentes.

* Via le Menu RetroArch :

┣ 📁Menu RetroArch  
┃ ┣ 📁Options du core  
┃ ┃ ┣ 🧩Name\_option  

* Via le fichier `retroarch-core-options.cfg`:

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁system  
┃ ┃ ┃ ┣ 📁configs  
┃ ┃ ┃ ┃ ┣ 📁retroarch  
┃ ┃ ┃ ┃ ┃ ┣ 📁cores  
┃ ┃ ┃ ┃ ┃ ┃ ┣ 🧩**retroarch-core-options.cfg**  

### Options du core

## ![](/migration-images/emulateurs/consoles-portables/game-gear/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/Gearboy/](https://github.com/libretro/Gearboy)
* **Documentation Libretro** : [https://docs.libretro.com/library/gearsystem/](https://docs.libretro.com/library/gearsystem/)
* **Code source Officiel :** [https://github.com/drhelius/Gearsystem/](https://github.com/drhelius/Gearsystem)

