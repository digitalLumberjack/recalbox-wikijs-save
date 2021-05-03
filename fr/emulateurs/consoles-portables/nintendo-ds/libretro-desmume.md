---
title: Libretro DeSmuME
---

# Libretro DeSmuME

**Libretro DeSmuME** est un émulateur pour le système de jeu Nintendo DS développer en C et C++.

Il est écrit par :

* YopYop156
* Zeromus

## ![](./gerald-g-parchment-background-or-border-5.svg)Licence

 ****Ce core est sous licence [**GPLv2**](https://github.com/libretro/desmume/blob/master/license.txt).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ \(Not Download Play, Link-Cable or Wi-Fi emulation\) |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Username | ✔ |

## ![](./tqfp32.svg)BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| bios7.bin | BIOS ARM7 | df692a80a5b1bc90728bc3dfc76cd948 | ❌ |
| bios9.bin | BIOS ARM9 | a392174eb3e572fed6447e956bde4b25 | ❌ |
| firmware.bin | Firmware NDS | 145eaef5bd3037cbc247c213bb3da1b3 e45033d9b0fa6b0de071292bba7c9d13 3ad72b2c9a736b24953f2d391da4bfcc | ❌ |

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 🗒 **bios7.bin**
> > > >
> > > > \*\*\*\*🗒 **bios9.bin**
> > > >
> > > > \*\*\*\*🗒 **firmware.bin**

## \*\*\*\*![](./rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .nds
* .bin
* .zip
* .7z

Ce système supporte les roms compressées au format .zip/.7z. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip/.7z doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip/.7z ne doit contenir qu'une seule rom compressée.

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁ds
> > > >
> > > > > 🗒**jeux.nds**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/desmume](https://github.com/libretro/desmume)
* **Documentation Libretro :** [https://docs.libretro.com/library/desmume/](https://docs.libretro.com/library/desmume/)
* **Code source Officiel :** [https://github.com/TASVideos/desmume](https://github.com/TASVideos/desmume)\*\*\*\*
* **Documentation Officiel :** ​[https://desmume.org/documentation/](https://desmume.org/documentation/)
* **Site Officiel :** [https://desmume.org/](https://desmume.org/)
* **Forum Officiel :** [http://forums.desmume.org/](http://forums.desmume.org/)

