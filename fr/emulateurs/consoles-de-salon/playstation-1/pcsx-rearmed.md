---
title: PCSX-ReARMed
---

# PCSX-ReARMed



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/notaz/pcsx_rearmed/blob/master/COPYING).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC x86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ 🐌 | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

🐌 Basses performances mais jouable

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

Bien que certains jeux puissent démarrer sans bios sous _PCSX-ReARMed,_ il est fortement conseillé d'ajouter ces fichiers dans le répertoire des bios afin d'améliorer les performances de l'émulateur et la gestions des sauvegardes sur les cartes mémoires "virtuelles".

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
      <td style="text-align:center">scph101.bin</td>
      <td style="text-align:center">Version 4.4 03/24/00 A</td>
      <td style="text-align:center">6e3735ff4c7dc899ee98981385f6f3d0</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">scph7001.bin</td>
      <td style="text-align:center">Version 4.1 12/16/97 A</td>
      <td style="text-align:center">1e68c231d0896b7eadcad1d7d8e76129</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">scph5501.bin</td>
      <td style="text-align:center">Version 3.0 11/18/96 A</td>
      <td style="text-align:center">490f666e1afb15b7362b406ed1cea246</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">scph1001.bin</td>
      <td style="text-align:center">Version 2.0 05/07/95 A</td>
      <td style="text-align:center">
        <p>dc2b9bf8da62ec93e868cfd29f0d067d</p>
        <p>924e392ed05558ffdb115408c263dccf</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
  </tbody>
</table>

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 **scph101.bin**
> > > >
> > > > \*\*\*\*🗒 **scph7001.bin**
> > > >
> > > > \*\*\*\*🗒 **scph5501.bin**
> > > >
> > > > \*\*\*\*🗒 **scph1001.bin**

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .img/.ccd/.sub
* .mdf/.mts
* .pbp
* .bin/.toc
* .cbn

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


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur



## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/notaz/pcsx\_rearmed/](https://github.com/notaz/pcsx_rearmed/)

