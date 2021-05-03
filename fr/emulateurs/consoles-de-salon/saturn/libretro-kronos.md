---
title: Libretro Kronos
---

# Libretro Kronos

**Libretro Kronos** est un port de l'émulateur **Yabause** pour Libretro prennant en charge la Sega Saturn.

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/yabause/blob/master/yabause/COPYING).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| saturn\_bios.bin | BIOS Saturn | af5828fdff51384f99b3c4926be27762 | ❌ |
| stvbios.zip | ⁉ | 2b99d9dcecde22db4371580b6bb33f32 53a094ad3a188f86de4e64624fe9b3ca 17116d2aea72454096b3f80ab714bfba 2b99d9dcecde22db4371580b6bb33f32 4cb34733b741ada074f11e3abcdc56d8 6b6d422a6c392eaec178b64b92987e99 88b9da6cda268ba1d9e37dd82d038801 8c34608cc140e1bfbf9c945a12fed0e8 b876d86e244d00b336980b4e26e9413 | ❌ |
| mpr-18811-mx.ic1 | The King of Fighters '95 - Requis pour ce jeu | 255113ba943c92a54facd25a10fd780c | ❌ |
| mpr-19367-mx.ic1 | Ultraman: Hikari no Kyojin Densetsu - Requis pour ce jeu | 1cd19988d1d72a3e7caa0b73234c96b4 | ❌ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 saturn\_bios.bin
> > > >
> > > > 🗒 stvbios.zip
> > > >
> > > > 🗒 mpr-18811-mx.ic1
> > > >
> > > > 🗒 mpr-19367-mx.ic1

## ![](./rom-30098_640.png) Roms

### Extensions supportées

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .m3u
* .img/.ccd
* .chd

### Emplacement

Placez les isos comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 roms
> > >
> > > > 📁 saturn
> > > >
> > > > > 🗒 fichier.cue


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
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

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/yabause/](https://github.com/libretro/yabause/)

