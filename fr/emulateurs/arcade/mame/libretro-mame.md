---
title: Libretro MAME
---

# Libretro MAME



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence **MAME non-commerciale**.

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

Les Romsets BIOS ne sont pas nécessaires lorsque vous utilisez des Romsets d'arcade "Full Non-Merged". Pour les roms "Split" et "Non-Merged", placez les BIOS nécessaires dans le même répertoire que la Romset du jeu.


>**Remarque :  
>Placer les bios** dans le répertoire : `/recalbox/share/roms/mame/`   
>ou dans **son sous-répertoire** si vous utiliser plusieurs cores de Mame, par exemple :`/recalbox/share/roms/mame/Mame/`
{.is-warning}

## ![](./rom-30098_640.png) Roms

Libretro-MAME est basé sur les dernières versions de l'émulateur MAME et le catalogue de jeu est étoffé.

[Cliquez ici](https://www.mamedev.org/) pour obtenir plus d'info sur le développement de Mame .

* Basé sur le romset : MAME 0.230
* Taille : 261gb
* Romsets émulés :  \(incluant les clones, etc...\)
* Active Sets : 
* Parents :
* Clones : 
* Others : 
* BIOS : 
* DatFile :  [http://www.progettosnaps.net/dats/MAME/](http://www.progettosnaps.net/dats/MAME/)
* Fichier dat :

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .zip
* .chd

Les fichiers CHD sont nécessaires que pour certaines roms. Si il n'existe aucun fichier CHD pour une rom, la rom fonctionnera.

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁**mame**
> > > >
> > > > > 🗒**fichier.zip**
> > > > >
> > > > > 🗒**chd.zip**

**Vous pouvez aussi opter pour un sous répertoire \(utile si vous voulez avoir un set mame pour un autre core\)**

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁**mame**
> > > >
> > > > > 📁Mame
> > > > >
> > > > > > 🗒**fichier.zip**
> > > > > >
> > > > > > 🗒**chd.zip**

{% file src="../../../.gitbook/assets/mame-0.220\_noclones\_v1.0-barhi \(1\).dat" caption="Mame-0.220\_NoClones" %}

## \*\*\*\*![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes** <a id="liens-exterieur"></a>

* **Progettosnaps :** [https://www.progettosnaps.net/](https://www.progettosnaps.net/)**​**
* **Site Officiel :** [https://github.com/libretro/mame/](https://github.com/libretro/mame)

