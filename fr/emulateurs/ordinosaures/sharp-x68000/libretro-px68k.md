---
title: Libretro PX68k
---

# Libretro PX68k



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/px68k-libretro/blob/master/COPYING).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| iplrom.dat | BIOS X68000 | 7fd4caabac1d9169e289f0f7bbf71d8e | ✅ |
| cgrom.dat | Fichier police | cb0a5cfcf7247a7eab74bb2716260269 | ✅ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 📁 keropi
> > > >
> > > > > 🗒 iplrom.dat
> > > > >
> > > > > 🗒 cgrom.dat

### Liste des bios optionnels

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| iplrom30.dat | BIOS X68000 \#2 | f373003710ab4322642f527f567e020a | ⚠ |
| iplromco.dat | BIOS X68000 \#3 | cc78d4f4900f622bd6de1aed7f52592f | ⚠ |
| iplromxv.dat | BIOS X68000 \#4 | 0617321daa182c3f3d6f41fd02fb3275 | ⚠ |

⚠ Fourni mais n'est pas le bon bios.

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 📁 keropi
> > > >
> > > > > 🗒 iplrom30.dat
> > > > >
> > > > > 🗒 iplromco.dat
> > > > >
> > > > > 🗒 iplromxv.dat

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .dim
* .img
* .d88
* .88d
* .hdm
* .dup
* .2hd
* .xdf
* .hdf
* .cmd
* .m3u
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
> > > > 📁x68000
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur



## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/px68k-libretro/](https://github.com/libretro/px68k-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/px68k/](https://docs.libretro.com/library/px68k/)

