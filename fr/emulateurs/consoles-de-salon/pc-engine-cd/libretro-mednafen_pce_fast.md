---
title: Libretro Mednafen\_PCE\_FAST
---

# Libretro Mednafen\_PCE\_FAST

**Libretro Mednafen\_PCE\_FAST** est un port libretro de Mednafen PCE Fast avec le module PC Engine SuperGrafx retiré.

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/beetle-pce-fast-libretro/blob/master/COPYING).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

<table>
  <thead>
    <tr>
      <th style="text-align:center"><b>Nom de fichier</b>
      </th>
      <th style="text-align:center">Description</th>
      <th style="text-align:center">MD5</th>
      <th style="text-align:center">Fourni</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">syscard3.pce</td>
      <td style="text-align:center">Super CD-ROM2 System V3.xx</td>
      <td style="text-align:center">
        <p>ff1a674273fe3540ccef576376407d1d</p>
        <p>1e47a1780aaa7e277a3896c1ba00e317</p>
        <p>38179df8f4ac870017db21ebcbf53114</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
  </tbody>
</table>

### Liste des bios optionnels

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| syscard1.pce | CD-ROM System V2.xx | 9f770275393b8627cf9d24e5c56d2ab9 | ⚠ |
| syscard2.pce | CD-ROM System V1.xx | 424f1d6bf93259bf255afa7d1dc9f721 | ⚠ |
| gexpress.pce | Game Express CD Card | 6d2cb14fc3e1f65ceb135633d1694122 | ⚠ |

⚠ Fourni mais n'a pas la bonne signature MD5.

### Emplacement

Placez le BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 **syscard1.pce**
> > > >
> > > > \*\*\*\*🗒 **syscard2.pce**
> > > >
> > > > \*\*\*\*🗒 **syscard3.pce**
> > > >
> > > > \*\*\*\*🗒 **gexpress.pce**

## ![](./rom-30098_640.png) Roms

### Extensions supportées

Les isos doivent avoir l'extension suivante :

* .cue/.bin
* .ccd/.img
* .chd

### Emplacement

Placez les isos comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 roms
> > >
> > > > 📁 pcenginecd
> > > >
> > > > > 🗒 **fichier.cue**
> > > > >
> > > > > \*\*\*\*🗒 **fichier.bin**


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
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

* **Github utilisé** : [https://github.com/libretro/beetle-pce-fast-libretro/](https://github.com/libretro/beetle-pce-fast-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/beetle\_pce\_fast/](https://docs.libretro.com/library/beetle_pce_fast/)

