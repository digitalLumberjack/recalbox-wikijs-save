---
title: Libretro PicoDrive
---

# Libretro PicoDrive

**Libretro PicoDrive** est un émulateur open-source Sega [**8**](/fr/emulateurs/consoles-de-salon/master-system)/[**16**](/fr/emulateurs/consoles-de-salon/megadrive) bit et ****[**32X**](/fr/emulateurs/consoles-de-salon/32x). Il a été réfléchi pour les appareils portable sur l'architecture [**ARM**](https://fr.wikipedia.org/wiki/Architecture_ARM).

## ![](/migration-images/emulateurs/consoles-de-salon/megadrive/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**non-commerciale**](https://github.com/libretro/picodrive/blob/master/COPYING)**.**

## ![](/migration-images/emulateurs/consoles-de-salon/megadrive/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-de-salon/megadrive/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Disk Control | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/megadrive/tqfp32.svg) BIOS


>**Aucun bios n'est requis.**
{.is-success}

## ![](/migration-images/emulateurs/consoles-de-salon/megadrive/rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .bin
* .en
* .md
* .smd
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
┃ ┃ ┃ ┣ 📁megadrive  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/megadrive/hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
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

## ![](/migration-images/emulateurs/consoles-de-salon/megadrive/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/picodrive/](https://github.com/libretro/picodrive/)
* **Doc Libretro** : [https://docs.libretro.com/library/picodrive/](https://docs.libretro.com/library/picodrive/)

