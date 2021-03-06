---
title: Libretro Mednafen\_SuperGrafx
---

# Libretro Mednafen\_SuperGrafx

**Libretro Mednafen\_SuperGrafx** est un port standalone de Mednafen PCE Fast pour libretro.

## ![](/migration-images/emulateurs/consoles-de-salon/pc-engine/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/beetle-supergrafx-libretro/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-de-salon/pc-engine/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-de-salon/pc-engine/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :--- |
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
| Multi-Mouse | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/pc-engine/tqfp32.svg) BIOS

### Liste des bios optionnels

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| gexpress.pce | Game Express CD Card | 6d2cb14fc3e1f65ceb135633d1694122 | ⚠ |

⚠ Fourni mais n'a pas la bonne signature MD5.

### Emplacement

Placez le BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒 **gexpress.pce**  

## ![](/migration-images/emulateurs/consoles-de-salon/pc-engine/rom-30098_640.png) Roms

### Extensions supportées

Les roms doivent avoir l'extension suivante :

* .pce/.sgx
* .zip
* .7z

Ce système supporte les roms compressées au format .zip/.7z. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip/.7z doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip/.7z ne doit contenir qu'une seule rom compressée.

### Emplacement

Placez les roms comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 roms  
┃ ┃ ┃ ┣ 📁 pcengine  
┃ ┃ ┃ ┃ ┣ 🗒 **fichier.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/pc-engine/hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder au options

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

## ![](/migration-images/emulateurs/consoles-de-salon/pc-engine/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/beetle-supergrafx-libretro/](https://github.com/libretro/beetle-supergrafx-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/beetle\_sgx/](https://docs.libretro.com/library/beetle_sgx/)

