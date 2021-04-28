---
title: Libretro Mesen\_S
---

# Libretro Mesen\_S

**Libretro Mesen-S** est un émulateur SNES multiplateforme pour Windows et Linux construit en C ++ et C \#.

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv3**](https://github.com/SourMesen/Mesen-S/blob/master/README.md).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalités | Supporté |
| :---: | :---: |
| Restart | ✔ |
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
| Multi-Mouse | ✔ |
| [Softpatching](https://docs.libretro.com/guides/softpatching/) | ✔ |
| Crop Overscan | ✔ |

## ![](./tqfp32.svg) BIOS

### Liste des bios optionnels

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| cgb\_bios.bin | BIOS Game Boy Color | b560efd759d87634a03b243f22bba27a | ❌ |
| sgb\_bios.bin | BIOS Super Game Boy | d574d4f9c12f305074798f54c091a8b4 | ❌ |
| sgb2\_boot.bin | BIOS Super Game Boy 2 | b4331a9e612b4738867a30af9c96df52 | ❌ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒**cgb\_bios.bin**
> > > >
> > > > \*\*\*\*🗒 **sgb\_bios.bin**
> > > >
> > > > \*\*\*\*🗒 **sgb2\_boot.bin**

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

La rom doit avoir l'extension :

* .gbc
* .sgb
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
> > > > 📁gbc
> > > >
> > > > > 🗒**jeux.zip**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
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

* **Code source utilisé** : [https://github.com/SourMesen/Mesen-S/](https://github.com/SourMesen/Mesen-S/)
* **Documentation Libretro** : [https://docs.libretro.com/library/mesen-s/](https://docs.libretro.com/library/mesen-s/)

