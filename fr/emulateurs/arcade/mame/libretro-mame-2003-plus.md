---
title: Libretro MAME2003\_Plus
---

# Libretro MAME2003\_Plus

**Libretro MAME2003\_Plus** \(également appelé MAME 2003+ et mame2003-plus\) est un noyau d'émulateur de système arcade **Libretro** qui met l'accent sur des performances élevées et une compatibilité étendue avec les périphériques mobiles, les ordinateurs à carte unique, les systèmes intégrés et autres plates-formes similaires.

Afin de tirer parti des performances et des exigences matérielles moindres d'une architecture MAME antérieure, MAME 2003-Plus a commencé avec le code base de MAME 2003, lui-même dérivé de mame 0.78.

Sur cette base, les contributeurs de MAME 2003-Plus ont rétro porté le support de plusieurs centaines de jeux supplémentaires, ainsi que d’autres fonctionnalités non présentes à l’origine dans MAME 0.78.

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**MAME non-commerciale**](https://github.com/libretro/mame2003-plus-libretro/blob/master/LICENSE.md).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Saves | ✔ |
| States | game-dependent |
| Rewind | ✔ |
| Netplay | ✔ |
| Native Cheats | ✔ |
| Controllers | ✔ |
| Multi-Mouse | ✔ |

## ![](./tqfp32.svg) BIOS

Les Romsets BIOS ne sont pas nécessaires lorsque vous utilisez des Romsets d'arcade "Full Non-Merged". Pour les roms "Split" et "Non-Merged", placez le BIOS dans le même répertoire que la Romset du jeu.


>**Remarque :  
>Placer les bios** dans le répertoire : `/recalbox/share/roms/mame/`   
>ou dans **son sous-répertoire** si vous utiliser plusieurs cores de Mame :`/recalbox/share/roms/mame/Mame 2003-Plus/`
{.is-warning}

## \*\*\*\*![](./rom-30098_640.png) **Roms**

* Basé sur le romset : 0.78-0.188 \(MAME 0.78 en tant que ligne de base avec d'autres ROMs basées sur des jeux de roms MAME ultérieurs\)
* Taille : 32gb
* Romsets émulés : 4941 \(incluant les clones, etc...\)
* Active Sets: 4941
* Parents : 1089
* Clones : 2123
* BIOS : 16
* CHDs : 30
* Samples : 66 + 6 Optional "Soundtrack Samples"
* Fichier dat : [ MAME 2003-Plus XML DAT File](https://github.com/libretro/mame2003-plus-libretro/blob/master/metadata/mame2003-plus.xml)

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
> > > > > 📁Mame 2003-Plus
> > > > >
> > > > > > 🗒**fichier.zip**

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur



## \*\*\*\*![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes**

* **Progettosnaps :** [https://www.progettosnaps.net/](https://www.progettosnaps.net/)
* **Github :** [https://github.com/libretro/mame2003-plus-libretro/](https://github.com/libretro/mame2003-plus-libretro)
* **Doc Libretro :** [https://docs.libretro.com/library/mame2003\_plus/](https://docs.libretro.com/library/mame2003_plus/)
* **Site Officiel :** 
* **Wiki du core :** 

