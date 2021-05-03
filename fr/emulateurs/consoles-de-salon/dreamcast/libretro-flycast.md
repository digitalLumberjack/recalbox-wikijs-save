---
title: Libretro Flycast
---

# Libretro Flycast

**Libretro Flycast** est un émulateur **Sega Dreamcast multiplate-formes** capable d'émuler la **Dreamcast.**

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence **GPLv2.**

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌  | ❌  | ✅  | ✅  | ✅  | ✅  | ✅ | ✅  | ✅  |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| Core Options | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Rumble | ✔ |
| Disk Control | ✔ |

## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| dc\_boot.bin | BIOS Dreamcast | e10c53c2f8b90bab96ead2d368858623 | ❌  |
| dc\_flash.bin | Date / Heure / Langue | 0a93f7940c455905bea6e392dfde92a4 | ❌  |

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 📁 dc
> > > >
> > > > > 🗒 **dc\_boot.bin**
> > > > >
> > > > > \*\*\*\*🗒 **dc\_flash.bin**

## \*\*\*\*![](./rom-30098_640.png) **Roms**

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .cdi
* .gdi
* .chd
* .iso
* .elf
* .m3u

### **Emplacement**

Placez les isos comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁dreamcast
> > > >
> > > > > 🗒**fichier.cue**
> > > > >
> > > > > \*\*\*\*🗒 **fichier.bin**


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

## \*\*\*\*![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes**

* **Github utilisé :** [https://github.com/libretro/flycast](https://github.com/libretro/flycast)
* **Doc Libretro :** [https://docs.libretro.com/library/flycast/](https://docs.libretro.com/library/flycast/)
* **Github Officiel :** [https://github.com/flyinghead/flycast](https://github.com/flyinghead/flycast)

