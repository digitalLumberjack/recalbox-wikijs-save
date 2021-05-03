---
title: Libretro blueMSX
---

# Libretro blueMSX



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/blueMSX-libretro/blob/master/license.txt).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| pesadelo.rom | Forte II Games - Pesadelo | ba53d700ec25bcb08020ce693319cd28 | ✅ |
| cbios\_logo\_msx1.rom | MSX - C-BIOS | 25b5cdea5040883a206b89845cdf55f1 | ✅ |
| cbios\_main\_msx1.rom | MSX - C-BIOS | 87b27f48cc25e2b6f749c019587d5f23 | ✅ |
| sf7000.rom | SEGA - SF-7000 | 561b362f9aa4cbcb240461abf83c2e0d | ✅ |
| ARAB1.ROM | - | 7fa0558bcec9dba310579521623d9f6a | ✅ |
| ARABIC.rom | - | 20c4b5d1d9469c201b145f082ec32658 | ✅ |
| BEERIDE.ROM | - | b32279f2700652a5ce0a809318626763 | ✅ |
| FMPAC.rom | - | 6f69cc8b5ed761b03afd78000dfb0e19 | ✅ |
| GCVMX80.ROM | - | fd0b8f1766dc6dcc03a43d9c79dc4e37 | ✅ |
| HANGUL.rom | - | 9baf17b190f631405b6b0eeeeb162b87 | ✅ |
| KANJI.rom | - | acf53887c2d2783dc059a9b442c86b90 | ✅ |
| MICROSOLDISK.ROM | - | 02e8b1f96049f09d6d3a735647cbbb2a | ✅ |
| MOONSOUND.rom | - | 42af93619160ef2116416f74a6cb12f2 | ✅ |
| MSX.rom | - | 364a1a579fe5cb8dba54519bcfcdac0d | ✅ |
| MSXAR.ROM | - | 793e3b833c33be7aaf834beacb8fb926 | ✅ |
| MSXBR.rom | - | d13c1fc9ad4897c322f51aab3ad3b30d | ✅ |
| MSXDOS23.ROM | - | 56bf5b02fed377b7bb9d91f914965431 | ✅ |
| MSXFR.rom | - | 6f43d28ac4a69182c860c2db0e18ee6d | ✅ |
| MSXG.rom | - | 4655329d3f37bf1a655d05f2abd1aa62 | ✅ |
| MSXHAN.rom | - | 394efbc50fb7df1151130d8c162f85c3 | ✅ |
| MSXJ.rom | - | f005e55c680ba6e7b19f6d4dc8f73ce5 | ✅ |
| MSXKANJI.rom | - | 9dfdebfaa6b547222a40aab8bb2e29f8 | ✅ |
| MSXKR.rom | - | c84f362c44192659273d45ae97462362 | ✅ |
| MSXR.rom | - | 0db9592930488259fc1a5c127215e784 | ✅ |
| MSXR2.ROM | - | 704bdd980fa56c6be5c680358458eeeb | ✅ |
| MSXSE.ROM | - | 161cb768c52a13f5b38ba46e721b68c1 | ✅ |
| MSXSP.rom | - | 51af5b19aeccf94eb8e03bce0b5d33c4 | ✅ |
| NATIONALDISK.rom | - | 86269da485e852d9f581ac27f4ba32ff | ✅ |
| NOVAXIS.rom | - | 20989124671593ab04eeb01d52a1e25c | ✅ |
| PAINT.rom | - | 41db0d7b37be479296ffd59fcd6775f0 | ✅ |
| PANASONICDISK.rom | - | 00aa02b6077de40a0b51d71a3c3e1d5f | ✅ |
| PHILIPSDISK.rom | - | 01dd1d72ed9bb6afe8a9b441c198a1cd | ✅ |
| RS232.ROM | - | 55cca200bbbdd0a1ec5c9d70966c05c0 | ✅ |
| SUNRISEIDE.rom | - | 7b564497beb2c0de0847f107dec00ddf | ✅ |
| SWP.rom | - | 490db04e2a3c1c993a2a9d3611949c76 | ✅ |
| XBASIC2.rom | - | 0b6120f289336538bc564548109f97c6 | ✅ |
| nowindDos1.rom | - | 8c294a75f14fc30fce0c8642d28ccec1 | ✅ |
| nowindDos2.rom | - | 1847398c014384b833868c64f149f338 | ✅ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 📁 Machines
> > > >
> > > > > 📁 Forte II Games - Pesadelo
> > > > >
> > > > > > 🗒 pesadelo.rom
> > > > >
> > > > > 📁 MSX2 - C-BIOS
> > > > >
> > > > > > 🗒 cbios\_logo\_msx.rom
> > > > > >
> > > > > > 🗒 cbios\_main\_msx.rom
> > > > > >
> > > > > > 🗒 cbios\_sub.rom
> > > > >
> > > > > 📁 SEGA - SF7000
> > > > >
> > > > > > 🗒 sf7000.rom
> > > > >
> > > > > 📁 Shared Roms
> > > > >
> > > > > > 🗒 ARAB1.ROM
> > > > > >
> > > > > > 🗒 ARABIC.rom
> > > > > >
> > > > > > 🗒 BEERIDE.ROM
> > > > > >
> > > > > > 🗒 FMPAC.rom
> > > > > >
> > > > > > 🗒 GCVMX80.ROM
> > > > > >
> > > > > > 🗒 HANGUL.rom
> > > > > >
> > > > > > 🗒 KANJI.rom
> > > > > >
> > > > > > 🗒 MICROSOLDISK.ROM
> > > > > >
> > > > > > 🗒 MOONSOUND.rom
> > > > > >
> > > > > > 🗒 MSX.rom
> > > > > >
> > > > > > 🗒 MSXAR.ROM
> > > > > >
> > > > > > 🗒 MSXBR.rom
> > > > > >
> > > > > > 🗒 MSXDOS23.ROM
> > > > > >
> > > > > > 🗒 MSXFR.rom
> > > > > >
> > > > > > 🗒 MSXG.rom
> > > > > >
> > > > > > 🗒 MSXHAN.rom
> > > > > >
> > > > > > 🗒 MSXJ.rom
> > > > > >
> > > > > > 🗒 MSXKANJI.rom
> > > > > >
> > > > > > 🗒 MSXKR.rom
> > > > > >
> > > > > > 🗒 MSXR.rom
> > > > > >
> > > > > > 🗒 MSXR2.ROM
> > > > > >
> > > > > > 🗒 MSXSE.rom
> > > > > >
> > > > > > 🗒 MSXSP.rom
> > > > > >
> > > > > > 🗒 NATIONALDISK.rom
> > > > > >
> > > > > > 🗒 NOVAXIS.rom
> > > > > >
> > > > > > 🗒 PAINT.rom
> > > > > >
> > > > > > 🗒 PANASONICDISK.rom
> > > > > >
> > > > > > 🗒 PHILIPSDISK.rom
> > > > > >
> > > > > > 🗒 RS232.ROM
> > > > > >
> > > > > > 🗒 SUNRISEIDE.rom
> > > > > >
> > > > > > 🗒 SWP.rom
> > > > > >
> > > > > > 🗒 XBASIC2.rom
> > > > > >
> > > > > > 🗒 nowindDos1.rom
> > > > > >
> > > > > > 🗒 nowindDos2.rom

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .cas
* .dsk
* .mx1
* .rom
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
> > > > 📁msx1
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur



## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/blueMSX-libretro/](https://github.com/libretro/blueMSX-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/bluemsx/](https://docs.libretro.com/library/bluemsx/)

