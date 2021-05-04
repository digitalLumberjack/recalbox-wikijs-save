---
title: Libretro ParaLLEl\_n64
---

# Libretro ParaLLEl\_n64

Émulateur Nintendo 64 _optimisé réécrit_ spécialement conçu pour Libretro. Initialement basé sur Mupen64 Plus.

## ![](/migration-images/emulateurs/consoles-de-salon/nintendo-64-dd/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv3**](https://github.com/libretro/mupen64plus-libretro/blob/master/LICENSE).

## ![](/migration-images/emulateurs/consoles-de-salon/nintendo-64-dd/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC X86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ |

## ![](/migration-images/emulateurs/consoles-de-salon/nintendo-64-dd/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/consoles-de-salon/nintendo-64-dd/tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| 64DD\_IPL.bin | BIOS N64DD - obligatoire | 8d3d9f294b6e174bc7b1d2fd1c727530 | ❌ |

### Emplacement

Placez le BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒 **64DD\_IPL.bin**  

## \*\*\*\*![](/migration-images/emulateurs/consoles-de-salon/nintendo-64-dd/rom-30098_640.png) **Roms**

### Extensions supportées

Les roms doivent avoir l'extension suivante :

* .ndd

### Emplacement

Placez les roms comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 roms  
┃ ┃ ┃ ┣ 📁 64dd  
┃ ┃ ┃ ┃ ┣ 🗒 **fichier.ndd**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/nintendo-64-dd/hammer-28636_640.png) Configuration avancée de l'émulateur


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

## \*\*\*\*![](/migration-images/emulateurs/consoles-de-salon/nintendo-64-dd/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes**

* **Github utilisé :** [https://github.com/libretro/parallel-n64](https://github.com/libretro/parallel-n64)

