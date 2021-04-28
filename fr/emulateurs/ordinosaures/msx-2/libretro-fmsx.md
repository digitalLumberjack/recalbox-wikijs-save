---
title: Libretro FMSX
---

# Libretro FMSX



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**non commerciale**](https://github.com/libretro/fmsx-libretro/blob/master/LICENSE).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| CARTS.SHA | - | d6dedca1112ddfda94cc9b2e426b818b | ✅ |
| CYRILLIC.FNT | - | 85b38e4128bbc300e675f55b278683a8 | ✅ |
| DISK.ROM | DiskROM/BDOS | 80dcd1ad1a4cf65d64b7ba10504e8190 | ✅ |
| FMPAC16.ROM | - | af8537262df8df267072f359399a7635 | ✅ |
| FMPAC.ROM | FMPAC BIOS | 6f69cc8b5ed761b03afd78000dfb0e19 | ✅ |
| ITALIC.FNT | - | c83e50e9f33b8dd893c414691822740d | ✅ |
| KANJI.ROM | Kanji Font | febe8782b466d7c3b16de6d104826b34 | ✅ |
| MSX2EXT.ROM | MSX2 ExtROM | 2183c2aff17cf4297bdb496de78c2e8a | ✅ |
| MSX2PEXT.ROM | MSX2+ ExtROM | 7c8243c71d8f143b2531f01afa6a05dc | ✅ |
| MSX2P.ROM | MSX2+ BIOS | 6d8c0ca64e726c82a4b726e9b01cdf1e | ✅ |
| MSX2.ROM | BIOS MSX2 | ec3a01c91f24fbddcbcab0ad301bc9ef | ✅ |
| MSXDOS2.ROM | MSX-DOS 2 | 6418d091cd6907bbcf940324339e43bb | ✅ |
| MSX.ROM | BIOS MSX | aa95aea2563cd5ec0a0919b44cc17d47 | ✅ |
| PAINTER.ROM | Yamaha Painter | 403cdea1cbd2bb24fae506941f8f655e | ✅ |
| RS232.ROM | - | 279efd1eae0d358eecd4edc7d9adedf3 | ✅ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 CARTS.SHA
> > > >
> > > > 🗒 CYRILLIC.FNT
> > > >
> > > > 🗒 DISK.ROM
> > > >
> > > > 🗒 FMPAC16.ROM
> > > >
> > > > 🗒 FMPAC.ROM
> > > >
> > > > 🗒 ITALIC.FNT
> > > >
> > > > 🗒 KANJI.ROM
> > > >
> > > > 🗒 MSX2EXT.ROM
> > > >
> > > > 🗒 MSX2PEXT.ROM
> > > >
> > > > 🗒 MSX2P.ROM
> > > >
> > > > 🗒 MSX2.ROM
> > > >
> > > > 🗒 MSXDOS2.ROM
> > > >
> > > > 🗒 MSX.ROM
> > > >
> > > > 🗒 PAINTER.ROM
> > > >
> > > > 🗒 RS232.ROM

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes 

* .rom
* .mx1
* .mx2
* .dsk
* .cas
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
> > > > 📁msx2
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur



## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/fmsx-libretro/](https://github.com/libretro/fmsx-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/fmsx/](https://docs.libretro.com/library/fmsx/)

