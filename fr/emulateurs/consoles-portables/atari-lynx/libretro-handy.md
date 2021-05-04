---
title: Libretro Handy
---

# Libretro Handy

**Libretro Handy** est un émulateur de système de jeu vidéo Atari Lynx qui peut être utilisé comme noyau de libretro.  
Handy était le nom original du projet Lynx qui a été lancé chez Epyx puis terminé par Atari.

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/gerald-g-parchment-background-or-border-5.svg)Licen**c**e

Ce core est sous licence [**zlib**](https://sourceforge.net/projects/handy/).

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay \(State based\) | ✔ \(not link-cable emulation\) |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/tqfp32.svg)BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| lynxboot.img | Image Boot Lynx | fcd403db69f54290b51035d82f835e7b | ❌  |

### Emplacement

Placez le BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒**lynxboot.img**  

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/atari-lynx/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .lnx
* .o
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
┃ ┃ ┃ ┣ 📁lynx  
┃ ┃ ┃ ┃ ┣ 🗒**jeux.lnx**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/libretro-handy](https://github.com/libretro/libretro-handy)
* **Documentation Libretro :** [https://docs.libretro.com/library/handy/](https://docs.libretro.com/library/handy/)
* **Code source Officiel :** [http://handy.sourceforge.net/download.htm](http://handy.sourceforge.net/download.htm)
* **Site Officiel :**  [http://handy.sourceforge.net/](http://handy.sourceforge.net/)

