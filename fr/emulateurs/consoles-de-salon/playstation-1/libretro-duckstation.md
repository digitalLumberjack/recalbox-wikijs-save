---
title: Libretro - Duckstation
---

# Libretro - Duckstation

 

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv3**](https://github.com/libretro/duckstation/blob/master/LICENSE).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC x86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
|  |  |

## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| scph5500.bin | BIOS PS1 japonais - requis pour les jeux japonais | 8dd7d5296a650fac7319bce665a6a53c | ❌ |
| scph5501.bin | BIOS PS1 américain - requis pour les jeux américains | 490f666e1afb15b7362b406ed1cea246 | ❌ |
| scph5502.bin | BIOS PS1 européen - requis pour les jeux européens | 32736f17079d0b2b7024407c39bd3050 | ❌ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 **scph5500.bin**
> > > >
> > > > \*\*\*\*🗒 **scph5501.bin**
> > > >
> > > > \*\*\*\*🗒 **scph5502.bin**

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .bin/.toc
* .m3u
* .img/.ccd/.sub
* .exe
* .pbp
* .chd

### Emplacement

Placez les isos comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 roms
> > >
> > > > 📁 psx
> > > >
> > > > > 🗒 **fichier.cue**
> > > > >
> > > > > \*\*\*\*🗒 **fichier.bin**


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./cogwheel-145804_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/v/francais/usage-avance/surcharge-de-configuration).
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

* **Github utilisé** : [https://github.com/libretro/duckstation/](https://github.com/libretro/duckstation/)
* **Doc Libretro** : -
