---
title: Libretro Gambatte
---

# Libretro Gambatte

**Libretro Gambatte** est un émulateur Game Boy Color multiplateforme, open source et axé sur la précision, écrit en C++.   
Il est basé sur des centaines de tests matériels de cas d'angle, ainsi que sur une documentation antérieure et des efforts d'ingénierie inverse.

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/gambatte-libretro/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| [Softpatching](https://docs.libretro.com/guides/softpatching/) | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/tqfp32.svg)BIOS

### Liste des bios optionnels

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| gbc\_bios.bin | BIOS Game Boy Color | dbfce9db9deaa2567f6a84fde55f9680 | ❌ |

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒**gbc\_bios.bin**  

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/game-boy-color/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .bin
* .gbc
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
┃ ┃ ┃ ┣ 📁gbc  
┃ ┃ ┃ ┃ ┣ 🗒**jeux.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/gambatte-libretro/](https://github.com/libretro/gambatte-libretro)
* **Documentation Libretro** : [https://docs.libretro.com/library/gambatte/](https://docs.libretro.com/library/gambatte/)
* **Code source officiel :** [https://github.com/sinamas/gambatte](https://github.com/sinamas/gambatte)
* **Ancien code source standalone :** [https://sourceforge.net/projects/gambatte/files/gambatte/](https://sourceforge.net/projects/gambatte/files/gambatte/)

