---
title: Libretro melonDS
---

# Libretro melonDS

**Libretro melonDS** est un émulateur Nintendo DS/DSI prometteur développer en C et C++.

L'émulateur **melonDS** vise à fournir une émulation Nintendo DS rapide et précise. Bien qu'il s'agisse encore d'un travail en cours, il possède un ensemble assez solide de fonctionnalités:

* Cœur presque complet \(CPU, vidéo, audio, ...\)
* Recompilateur JIT pour une émulation rapide
* Rendu OpenGL, conversion ascendante 3D
* RTC, microphone, couvercle fermé / ouvert
* Prise en charge du joystick
* Savestates
* Différents modes d'affichage / dimensionnement / rotation
* \(WIP\) Wifi: multijoueur local, connectivité en ligne
* Émulation DSi \(WIP\)
* DLDI
* \(WIP\) Modules complémentaires d’emplacement GBA
* et plus sont prévus!

Il a été écrit par **Arisotura \(**connu sous le nom de StapleButter\), un ancien contributeur à DeSmuME.

## ![](/migration-images/emulateurs/consoles-portables/nintendo-ds/gerald-g-parchment-background-or-border-5.svg)Licence

 ****Cet émulateur est sous licence [**GPLv3**](https://github.com/libretro/melonDS/blob/master/LICENSE).

## ![](/migration-images/emulateurs/consoles-portables/nintendo-ds/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/nintendo-ds/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/nintendo-ds/tqfp32.svg)BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| bios7.bin | BIOS ARM7 | df692a80a5b1bc90728bc3dfc76cd948 | ❌ |
| bios9.bin | BIOS ARM9 | a392174eb3e572fed6447e956bde4b25 | ❌ |
| firmware.bin | Firmware NDS | 145eaef5bd3037cbc247c213bb3da1b3 e45033d9b0fa6b0de071292bba7c9d13 3ad72b2c9a736b24953f2d391da4bfcc | ❌ |

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 🗒 **bios7.bin**
> > > >
> > > > \*\*\*\*🗒 **bios9.bin**
> > > >
> > > > \*\*\*\*🗒 **firmware.bin**

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/nintendo-ds/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .nds
* .zip
* .7z

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁ds
> > > >
> > > > > 🗒**jeux.zip**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/nintendo-ds/hammer-28636_640.png)Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
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

## ![](/migration-images/emulateurs/consoles-portables/nintendo-ds/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/melonds](https://github.com/libretro/melonds)\*\*\*\*
* **Documentation Libretro :** ​[https://docs.libretro.com/library/melonds/](https://docs.libretro.com/library/melonds/)
* **Code source Officiel :** [https://github.com/Arisotura/melonDS](https://github.com/Arisotura/melonDS)
* **Documentation Officiel :** N/A
* **Site Officiel :** [http://melonds.kuribo64.net/](http://melonds.kuribo64.net/)
* **Forum Officiel :** [http://melonds.kuribo64.net/board/](http://melonds.kuribo64.net/board/)

