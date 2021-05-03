---
title: Libretro PokeMini
---

# Libretro PokeMini

**Libretro PokeMini** est un émulateur pour la console portable Nintendo Pokémon Mini développé en C et C++.

Il est écrit par **JustBurn**.

## ![](/migration-images/emulateurs/consoles-portables/pokemini/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv3**](https://github.com/libretro/PokeMini/blob/master/LICENSE).

## ![](/migration-images/emulateurs/consoles-portables/pokemini/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/pokemini/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Core Options | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Rumble | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/pokemini/tqfp32.svg)BIOS

### Liste des bios optionnels

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| bios.min | BIOS Pokémon Mini | 1e4fb124a3a886865acb574f388c803d | ⚠ |

⚠ Fourni mais n'est pass le bon bios.

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 🗒 **bios.min**

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/pokemini/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .min
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
> > > > 📁pokemini
> > > >
> > > > > 🗒**jeux.min**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/pokemini/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/pokemini/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source Utilisé :** [https://github.com/libretro/PokeMini](https://github.com/libretro/PokeMini)
* **Documentation Libretro :** [https://docs.libretro.com/library/pokemini/](https://docs.libretro.com/library/pokemini/)
* **Code source Officiel :** [https://sourceforge.net/projects/pokemini/](https://sourceforge.net/projects/pokemini/)
* **Documentation officiel :** [https://sourceforge.net/p/pokemini/wiki/Home/](https://sourceforge.net/p/pokemini/wiki/Home/)

