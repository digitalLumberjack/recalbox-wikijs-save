---
title: Libretro mGBA
---

# Libretro mGBA

Libretro **mGBA**  est un émulateur qui permet d'exécuter des jeux Game Boy Advance.  
Il vise à être plus rapide et plus précis que de nombreux émulateurs Game Boy Advance existants, ainsi qu'à ajouter des fonctionnalités qui manquent aux autres émulateurs. Il prend également en charge les jeux Game Boy et Game Boy Color.

## ![](/migration-images/emulateurs/consoles-portables/game-boy-advance/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**MPLv2.0**](https://github.com/libretro/mgba/blob/master/LICENSE).

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/game-boy-advance/compatibility.png) ****Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/game-boy-advance/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Rumble | ✔ |
| [Softpatching](https://docs.libretro.com/guides/softpatching/) | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/game-boy-advance/tqfp32.svg)BIOS

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

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/game-boy-advance/rom-30098_640.png)**Roms**

### **Extensions supporté**

La rom doit avoir l'extension :

* **.gba**

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

## ![](/migration-images/emulateurs/consoles-portables/game-boy-advance/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/game-boy-advance/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/mgba](https://github.com/libretro/mgba)
* **Documentation Libretro :** ​[https://docs.libretro.com/library/mgba/](https://docs.libretro.com/library/mgba/)
* **Code source Officiel :** [https://github.com/mgba-emu/mgba](https://github.com/mgba-emu/mgba)
* **Documentation Officiel :** ​[https://docs.libretro.com/library/mgba/](https://docs.libretro.com/library/mgba/)
* **Site Officiel :** [https://mgba.io/](https://mgba.io/)
* **Forum Officiel :** 



