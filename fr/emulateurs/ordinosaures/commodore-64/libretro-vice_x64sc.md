---
title: Libretro vice\_x64sc
---

# Libretro vice\_x64sc



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
| JiffyDOS\_C64.bin | JiffyDOS C64 Kernal | be09394f0576cf81fa8bacf634daf9a2 | ⚠ |
| JiffyDOS\_C128.bin | JiffyDOS C128 Kernal | cbbd1bbcb5e4fd8046b6030ab71fc021 | ⚠ |
| JiffyDOS\_C1541-II.bin | JiffyDOS 1541 drive BIOS | 1b1e985ea5325a1f46eb7fd9681707bf | ⚠ |
| JiffyDOS\_1571\_repl310654.bin | JiffyDOS 1571 drive BIOS | 41c6cc528e9515ffd0ed9b180f8467c0 | ⚠ |
| JiffyDOS\_1581.bin | JiffyDOS 1581 drive BIOS | 20b6885c6dc2d42c38754a365b043d71 | ⚠ |

⚠ Fourni mais n'est pas le bon bios.

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 📁 vice  
┃ ┃ ┃ ┃ ┣ 🗒 JiffyDOS\_C64.bin  
┃ ┃ ┃ ┃ ┣ 🗒 JiffyDOS\_C128.bin  
┃ ┃ ┃ ┃ ┣ 🗒 JiffyDOS\_C1541-II.bin  
┃ ┃ ┃ ┃ ┣ 🗒 JiffyDOS\_1571\_repl310654.bin  
┃ ┃ ┃ ┃ ┣ 🗒 JiffyDOS\_1581.bin  

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



## ![](/migration-images/emulateurs/ordinosaures/commodore-64/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/vice-libretro/](https://github.com/libretro/vice-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/vice/](https://docs.libretro.com/library/vice/)

