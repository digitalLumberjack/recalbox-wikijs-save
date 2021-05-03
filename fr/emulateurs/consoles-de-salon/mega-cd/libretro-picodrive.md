---
title: Libretro PicoDrive
---

# Libretro PicoDrive

**Libretro PicoDrive** est un émulateur open-source Sega [**8**](/fr/emulateurs/consoles-de-salon/master-system)/[**16**](/fr/emulateurs/consoles-de-salon/megadrive) bit et ****[**32X**](/fr/emulateurs/consoles-de-salon/32x). Il a été réfléchi pour les appareils portable sur l'architecture [**ARM**](https://fr.wikipedia.org/wiki/Architecture_ARM).

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**non-commerciale**](https://github.com/libretro/picodrive/blob/master/COPYING)**.**

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
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Disk Control | ✔ |

## ![](./tqfp32.svg) BIOS

### Liste des bios optionnels

<table>
  <thead>
    <tr>
      <th style="text-align:center">Nom de fichier</th>
      <th style="text-align:center">Description</th>
      <th style="text-align:center">MD5</th>
      <th style="text-align:center">Fourni</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">bios_CD_E.sms</td>
      <td style="text-align:center">BIOS EU MegaCD (bootrom)</td>
      <td style="text-align:center">e66fa1dc5820d254611fdcdba0662372</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">bios_CD_U.sms</td>
      <td style="text-align:center">BIOS US SegaCD (bootrom)</td>
      <td style="text-align:center">2efd74e3232ff260e371b99f84024f7f</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">bios_CD_J.sms</td>
      <td style="text-align:center">BIOS JP MegaCD (bootrom)</td>
      <td style="text-align:center">
        <p>278a9397d192149e84e820ac621a8ed</p>
        <p>bdeb4c47da613946d422d97d98b21cda</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
  </tbody>
</table>

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 🗒 **bios\_CD\_E.sms**
> > > >
> > > > 🗒 **bios\_CD\_U.sms**
> > > >
> > > > 🗒 **bios\_CD\_J.sms**

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .iso

### **Emplacement**

Placez les isos comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁segacd
> > > >
> > > > > 🗒**fichier.zip**


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

* **Github utilisé** : [https://github.com/libretro/picodrive/](https://github.com/libretro/picodrive/)
* **Doc Libretro** : [https://docs.libretro.com/library/picodrive/](https://docs.libretro.com/library/picodrive/)

