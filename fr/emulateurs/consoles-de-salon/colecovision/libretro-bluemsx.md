---
title: Libretro blueMSX
---

# Libretro blueMSX



## ![](/migration-images/emulateurs/consoles-de-salon/colecovision/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/blueMSX-libretro/blob/master/license.txt).

## ![](/migration-images/emulateurs/consoles-de-salon/colecovision/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-de-salon/colecovision/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Disk Control | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/colecovision/tqfp32.svg) BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| czz50-1.rom | Requis | 1de922acdd742d31349c2801e9768c35 | ✅  |
| czz50-2.rom | Requis | 72b089dc55b7fe7ffb5028f365e8c045 | ✅  |
| coleco.rom | Requis | 2c66f5911e5b42b8ebe113403548eee7 | ✅  |
| coleco.rom | Requis | 2c66f5911e5b42b8ebe113403548eee7 | ✅  |
| SVI603.ROM | Requis | c60a2e85572c0ccb69505a7646d5c1b6 | ✅  |

### **Emplacement**

Placez les bios comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 📁 Machines  
┃ ┃ ┃ ┃ ┣ 📁 COL - Bit Corporation Dina  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 czz50-1.rom  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 czz50-2.rom  
┃ ┃ ┃ ┃ ┣ 📁 COL - ColecoVision with Opcode Memory Extension  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 coleco.rom  
┃ ┃ ┃ ┃ ┣ 📁 COL - ColecoVision  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 coleco.rom  
┃ ┃ ┃ ┃ ┣ 📁 COL - Spectravideo SVI-603 Coleco  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 SVI603.ROM  

## ![](/migration-images/emulateurs/consoles-de-salon/colecovision/rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .col

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁colecovision  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.col**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/colecovision/hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder au**x** options

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

## ![](/migration-images/emulateurs/consoles-de-salon/colecovision/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/blueMSX-libretro/](https://github.com/libretro/blueMSX-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/bluemsx/](https://docs.libretro.com/library/bluemsx/)

