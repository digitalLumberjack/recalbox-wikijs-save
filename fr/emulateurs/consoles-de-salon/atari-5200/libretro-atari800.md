---
title: Libretro Atari800
---

# Libretro Atari800

\*\*\*\*

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/atari800/atari800/blob/master/COPYING)**.**

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Screenshots | ✔ |
| Saves | - |
| States | - |
| Core Options | ✔ |
| Native Cheats | - |
| Controls | ✔ |
| Remapping | ✔ |

## ![](./tqfp32.svg)BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| 5200.rom | 5200 - Requis | 281f20ea4320404ec820fb7ec0693b38 | ❌ |

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 🗒**5200.rom**

## \*\*\*\*![](./rom-30098_640.png)**Roms**

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .a52
* .atr
* .bas
* .bin
* .car
* .cdm
* .xex
* .xfd
* .atr.gz
* .xfd.gz
* .zip

Ce système supporte les roms compressées au format .zip. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip ne doit contenir qu'une seule rom compressée.

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁atari5200
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png)Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/v/francais/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder au**x** options

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

[https://docs.libretro.com/library/atari800/\#core-options](https://docs.libretro.com/library/atari800/#core-options)

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github utilisé :** [https://github.com/libretro/libretro-atari800/](https://github.com/libretro/libretro-atari800/)
* **Doc Libretro :** [https://docs.libretro.com/library/atari800/](https://docs.libretro.com/library/atari800/)

