---
title: Libretro Mednafen\_PCFX
---

# Libretro Mednafen\_PCFX

**Libretro Mednafen\_PCFX** est un port de l'émulateur Mednafen PC-FX pour le NEC PC-FX.

## ![](/migration-images/emulateurs/consoles-de-salon/pc-fx/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/beetle-pcfx-libretro/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-de-salon/pc-fx/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-de-salon/pc-fx/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Crop Overscan | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/pc-fx/tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| pcfx.rom | BIOS PC-FX v1.00 - 2 Sep 1994 | 08e36edbea28a017f79f8d4f7ff9b6d7 | ❌  |

### Emplacement

Placez le BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒**pcfx.rom**

## ![](/migration-images/emulateurs/consoles-de-salon/pc-fx/rom-30098_640.png) Roms

### Extensions supportées

Les isos doivent avoir l'extension suivante :

* .cue
* .ccd
* .toc
* .chd

### Emplacement

Placez les isos comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 roms
> > >
> > > > 📁 pcfx
> > > >
> > > > > 🗒 **fichier.cue**


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/pc-fx/hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder aux options

Vous pouvez configurer diverses options de deux façons différentes.

* Via le Menu RetroArch :

> 📁Menu RetroArch
>
> > 📁Options du core
> >
> > > 🧩Name\_option

* Via le fichier `retroarch-core-options.cfg`:

> 📁recalbox
>
> > 📁share
> >
> > > 📁system
> > >
> > > > 📁configs
> > > >
> > > > > 📁retroarch
> > > > >
> > > > > > 📁cores
> > > > > >
> > > > > > > 🧩**retroarch-core-options.cfg**

### Options du core

## ![](/migration-images/emulateurs/consoles-de-salon/pc-fx/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/beetle-pcfx-libretro/](https://github.com/libretro/beetle-pcfx-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/beetle\_pc\_fx/](https://docs.libretro.com/library/beetle_pc_fx/)

