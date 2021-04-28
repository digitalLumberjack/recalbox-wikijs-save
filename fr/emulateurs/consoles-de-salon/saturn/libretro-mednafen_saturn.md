---
title: Libretro Mednafen\_Saturn
---

# Libretro Mednafen\_Saturn

**Libretro Mednafen\_Saturn** est un port de l'émulateur **Mednafen Saturn** \(standalone\) à Libretro prennant en charge la Sega Saturn.

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/beetle-saturn-libretro/blob/master/COPYING).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalités | Supporté |
| :--- | :--- |
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
| Multi-Mouse | ✔ |

## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| sega\_101.bin | BIOS Saturn JP - Requis pour les jeux JAP | 85ec9ca47d8f6807718151cbcca8b964 | ❌ |
| mpr-17933.bin | BIOS Saturn US.mdEU - Requis pour les jeux EUR/USA | 3240872c70984b6cbfda1586cab68dbe | ❌ |
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
> > > > 🗒 **sega\_101.bin**
> > > >
> > > > \*\*\*\*🗒 **mpr-17933.bin**
> > > >
> > > > \*\*\*\*🗒 **mpr-18811-mx.ic1**
> > > >
> > > > \*\*\*\*🗒 **mpr-19367-mx.ic1**

## ![](./rom-30098_640.png) Roms

### Extensions supportées

Les isos doivent avoir les extensions suivantes :

* .cue
* .m3u
* .img/.ccd
* .iso
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
> > > > > 🗒 **fichier.cue**


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/v/francais/usage-avance/surcharge-de-configuration).
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

* **Github utilisé** : [https://github.com/libretro/beetle-saturn-libretro/](https://github.com/libretro/beetle-saturn-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/beetle\_saturn/](https://docs.libretro.com/library/beetle_saturn/)

