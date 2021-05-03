---
title: Libretro Fceumm
---

# Libretro Fceumm



## ![](/migration-images/emulateurs/consoles-de-salon/family-computer-disk-system/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/libretro-fceumm/blob/master/Copying).

## ![](/migration-images/emulateurs/consoles-de-salon/family-computer-disk-system/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-de-salon/family-computer-disk-system/cogwheel-145804_640.png) Fonctionnalités

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
| RetroArch Cheats | ✔ |
| Native Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| [Softpatching](https://docs.libretro.com/guides/softpatching/) | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/family-computer-disk-system/tqfp32.svg) BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| disksys.rom | BIOS Family Computer Disk System | ca30b50f880eb660a320674ed365ef7a | ❌  |

### Emplacement

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 🗒 **disksys.rom**

## ![](/migration-images/emulateurs/consoles-de-salon/family-computer-disk-system/rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .fds
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
> > > > 📁fds
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/family-computer-disk-system/hammer-28636_640.png) Configuration avancée de l'émulateur


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


>**Mettre la face B de disquette**  
>Les touches L1 et R1 associées à la touche Hotkey permettent pour l'une d'éjecter le disk et pour l'autre de changer la face.  
>****Donc il faut faire la combinaison Hotkey/R1 + Hotkey/L1 + Hotkey/R1 ou Hotkey/L1 + Hotkey/R1 + Hotkey/L1 pour changer la face.
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/family-computer-disk-system/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/libretro-fceumm](https://github.com/libretro/libretro-fceumm)
* **Doc Libretro** : [https://docs.libretro.com/library/fceumm/](https://docs.libretro.com/library/fceumm/)

