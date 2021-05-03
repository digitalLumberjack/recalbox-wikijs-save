---
title: Libretro Mednafen\_Lynx
---

# Libretro Mednafen\_Lynx

**Libretro Mednafen\_lynx** est un émulateur de système de jeu vidéo Atari Lynx.  
Plus précisément, c'est un port de Mednafen Lynx qui est un fork de Handy.

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**zlib**](https://github.com/libretro/beetle-lynx-libretro/blob/master/mednafen/lynx/license.txt) et [**GPLv2**](https://github.com/libretro/beetle-lynx-libretro/blob/master/COPYING)\*\*\*\*

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/atari-lynx/compatibility.png) ****Compatibilité

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
| Netplay | ✔ \(pas d'émulation de câble de liaison\) |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| Cheats \(Cheats menu\) | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| [Softpatching](https://docs.libretro.com/guides/softpatching/) | ✔ |
| Crop Overscan | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/tqfp32.svg)BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| lynxboot.img | Image Boot Lynx | fcd403db69f54290b51035d82f835e7b | ❌  |

### Emplacement

Placez le BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒**lynxboot.img**

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

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁lynx
> > > >
> > > > > 🗒**jeux.lnx**


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

## ![](/migration-images/emulateurs/consoles-portables/atari-lynx/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/beetle-lynx-libretro](https://github.com/libretro/beetle-lynx-libretro)
* **Documentation Officiel :** [https://docs.libretro.com/library/beetle\_lynx/](https://docs.libretro.com/library/beetle_lynx/)
* **Code source Officiel :** [https://mednafen.github.io/releases/](https://mednafen.github.io/releases/)
* **Site Officiel :** [https://mednafen.github.io/](https://mednafen.github.io/)

