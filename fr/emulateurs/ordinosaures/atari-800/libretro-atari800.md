---
title: Libretro Atari800
---

# Libretro Atari800



## ![](/migration-images/emulateurs/ordinosaures/atari-800/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/atari800/atari800/blob/master/COPYING)**.**

## ![](/migration-images/emulateurs/ordinosaures/atari-800/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ordinosaures/atari-800/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/ordinosaures/atari-800/tqfp32.svg) BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| ATARIBAS.ROM | BASIC interpreter | 0bac0c6a50104045d902df4503a4c30b | ❌ |
| ATARIOSA.ROM | Atari 400/800 PAL | eb1f32f5d9f382db1bbfb8d7f9cb343a | ❌ |
| ATARIOSB.ROM | Atari 400/800 NTSC | a3e8d617c95d08031fe1b20d541434b2 | ❌ |
| ATARIXL.ROM | Atari XL/XE OS | 06daac977823773a3eea3422fd26a703 | ❌ |

### **Emplacement**

Placez les bios comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 🗒**ATARIXL.ROM**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **ATARIBAS.ROM**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **ATARIOSA.ROM**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **ATARIOSB.ROM**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **ATARIXL.ROM**  

## ![](/migration-images/emulateurs/ordinosaures/atari-800/rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .atr
* .atx
* .bin
* .car
* .cas
* .com
* .dcm
* .rom
* .xex
* .xfd
* .zip

Ce système supporte les roms compressées au format .zip. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip ne doit contenir qu'une seule rom compressée.

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁atari800  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/ordinosaures/atari-800/hammer-28636_640.png) Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/ordinosaures/atari-800/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/atari800/atari800/](https://github.com/atari800/atari800/)
* **Doc Libretro** : [https://docs.libretro.com/library/atari800/](https://docs.libretro.com/library/atari800/)

