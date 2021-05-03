---
title: Amiberry
---

# Amiberry

**Amiberry** est un core pour ARM optimisé pour Amiga.

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cd32/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv3**](https://github.com/midwan/amiberry/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cd32/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅🐌  | ❌ | ❌ |

🐌 Basses performances mais jouable

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cd32/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cd32/tqfp32.svg) BIOS

### Liste des bios obligatoires

Vous trouverez les bios avec le nom indiqué dans la colonne **Description** qu'il vous faudra renommer avec le nom indiqué dans la colonne **Nom de fichier**.

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
      <td style="text-align:center">kick40060.CD32.rom</td>
      <td style="text-align:center">
        <p></p>
        <p>Kickstart v3.1 r40.060 (1993-05)(Commodore)(CD32)[!].rom</p>
      </td>
      <td style="text-align:center">
        <p>f2f241bf094168cfb9e7805dc2856433</p>
        <p>5f8924d013dd57a89cf349f4cdedc6b1</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">kick40060.CD32.ext.rom</td>
      <td style="text-align:center">
        <p></p>
        <p>CD32 Extended-ROM r40.60 (1993)(Commodore)(CD32).rom</p>
      </td>
      <td style="text-align:center">bb72565701b1b6faece07d68ea5da639</td>
      <td style="text-align:center">&#x26A0;</td>
    </tr>
  </tbody>
</table>

⚠ Fourni mais n'a pas la bonne signature MD5.

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 **kick40060.CD32.rom**
> > > >
> > > > 🗒 **kick40060.CD32.ext.rom**

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cd32/rom-30098_640.png) Roms

### Extensions supportées

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .iso
* .mds/.mdf
* .img/.ccd

### Emplacement

Placez les isos comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 roms
> > >
> > > > 📁 cd32
> > > >
> > > > > 🗒 **fichier.cue**
> > > > >
> > > > > 🗒 **fichier.bin**


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cd32/hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
{.is-danger}



## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cd32/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/midwan/amiberry/](https://github.com/midwan/amiberry/)
* **Doc** : [https://blitterstudio.com/amiberry/](https://blitterstudio.com/amiberry/)

