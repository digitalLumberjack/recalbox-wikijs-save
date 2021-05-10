---
title: Libretro vice\_xscpu64
---

# Libretro vice\_xscpu64



## ![](/migration-images/emulateurs/ordinosaures/commodore-64/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/vice-libretro/blob/master/COPYING).

## ![](/migration-images/emulateurs/ordinosaures/commodore-64/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ordinosaures/commodore-64/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/ordinosaures/commodore-64/tqfp32.svg) BIOS

### Liste des bios optionnels

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| scpu-dos-1.4.bin | CMD SuperCPU Kernal 1.4 | cda2fcd2e1f0412029383e51dd472095 | ⚠ |
| scpu-dos-2.04.bin | CMD SuperCPU Kernal 2.04 | b2869f8678b8b274227f35aad26ba509 | ⚠ |

⚠ Fourni mais n'est pas le bon bios.

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 📁 vice  
┃ ┃ ┃ ┃ ┣ 📁 SCPU64  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 **scpu-dos-1.4.bin**  
┃ ┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **scpu-dos-2.04.bin**  

## ![](/migration-images/emulateurs/ordinosaures/commodore-64/rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .crt
* .d64
* .d71
* .d81
* .g64
* .nbz
* .nib
* .p00
* .prg
* .t64
* .tap
* .z64
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
┃ ┃ ┃ ┣ 📁c64  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/ordinosaures/commodore-64/hammer-28636_640.png) Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/ordinosaures/commodore-64/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/vice-libretro/](https://github.com/libretro/vice-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/vice/](https://docs.libretro.com/library/vice/)

