---
title: Libretro MAME2003
---

# Libretro MAME2003

**Libretro MAME2003** est un émulateur plus récent que imame4all. Beaucoup plus de jeux sont fonctionnels.

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**MAME non-commerciale**](https://github.com/libretro/mame2003-libretro/blob/master/LICENSE.md).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Sauvegardes | ✔ |
| States | game-dependent |
| Rembobinage | ✔ |
| Netplay | ✔ |
| Native Cheats | ✔ |
| Controllers | ✔ |
| Multi-Mouse | ✔ |

## ![](./tqfp32.svg) BIOS

Les Romsets BIOS ne sont pas nécessaires lorsque vous utilisez des Romsets d'arcade "Full Non-Merged". Pour les roms "Split" et "Non-Merged", placez les BIOS nécessaires dans le même répertoire que la Romset du jeu.


>**Remarque :  
>Placer les bios** dans le répertoire : `/recalbox/share/roms/mame/`   
>ou dans **son sous-répertoire** si vous utiliser plusieurs cores de Mame, par exemple :`/recalbox/share/roms/mame/Mame 2003/`
{.is-warning}

## \*\*\*\*![](./rom-30098_640.png) **Roms**

* Basé sur le romset : MAME 0.78 \(Décembre 2003\)
* Taille : 28gb
* Romsets émulés : 4 721 \(incluant les clones, etc...\)
* Active Sets : 4721
* Parents : 1042
* Clones : 2039
* Others : 1624
* BIOS : 16
* Fichier dat : [mame2003.dat](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/mame2003/mame2003.dat)

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

**Vous pouvez aussi opter pour un sous répertoire \(utile si vous voulez avoir un set mame pour un autre core\)**

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁**mame**
> > > >
> > > > > 📁Mame 2003
> > > > >
> > > > > > 🗒**fichier.zip**

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur



## \*\*\*\*![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes**

* **Progettosnaps :** [https://www.progettosnaps.net/](https://www.progettosnaps.net/)
* **Github :** [https://github.com/libretro/mame2003-libretro/](https://github.com/libretro/mame2003-libretro)
* **Doc Libretro** : [https://docs.libretro.com/library/mame\_2003/](https://docs.libretro.com/library/mame_2003/)
* **Site Officiel :** 
* **Wiki du core :** 

