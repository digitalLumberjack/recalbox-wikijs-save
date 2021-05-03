---
title: Libretro gpSP
---

# Libretro gpSP

**Libretro gpSP** est un émulateur basé sur le fork de notaz de gpSP pour la Game Boy Advance avec des améliorations supplémentaires de la base de code.

## ![](./gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/gpsp/blob/master/COPYING).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| RetroAchievements | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](./tqfp32.svg)BIOS

### Liste des bios optionnels

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| gba\_bios.bin | BIOS Game Boy Advance | a860e8c0b6d573d191e4ec7db1b1e4f6 | ❌ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒**gba\_bios.bin**

## \*\*\*\*![](./rom-30098_640.png)**Roms**

### **Extensions supporté**

La rom doit avoir l'extension :

* **.gba**
* **.bin**

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁gba
> > > >
> > > > > 🗒**jeux.gba**


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

* **Code source utilisé :** [https://github.com/libretro/gpsp](https://github.com/libretro/gpsp)\*\*\*\*
* **Documentation Libretro :** ​[https://docs.libretro.com/library/gpsp](https://docs.libretro.com/library/gpsp/)
* **Code source Officiel :** [https://github.com/notaz/gpsp](https://github.com/notaz/gpsp)
* **Site Officiel :** [https://notaz.gp2x.de/other.php](https://notaz.gp2x.de/other.php)
* **Forum Officiel :** 
* **Documentation Officiel :** ​

