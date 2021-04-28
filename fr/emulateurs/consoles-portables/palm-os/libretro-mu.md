---
title: Libretro Mu
---

# Libretro Mu

**Libretro Mu** est un émulateur de Palm Os développé en C et C++.

La continuation du Core est dédiée à Emily \(1998-2020\)

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**Creative Commons Attribution-NonCommercial 3.0 United States**](https://github.com/libretro/Mu#license).

## ![](./compatibility.png) ****Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png)Fonctionnalités



## ![](./tqfp32.svg)BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| palmos41-en-m515.rom | BIOS Palm OS 4.1 | 9da101cd2317830649a31f8fa46debec | ❌ |

### Liste des bios optionnels

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| bootloader-dbvz.rom | Palm Bootloader | 9da101cd2317830649a31f8fa46debec | ⚠ |

⚠ Fourni mais n'est pas le bon bios.

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 🗒 **palmos41-en-m515.rom**
> > > >
> > > > \*\*\*\*🗒 **bootloader-dbvz.rom**

## \*\*\*\*![](./rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .prc
* .pdb
* .pqa
* .img

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁palm
> > > >
> > > > > 🗒**jeux.prc**


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png)Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/v/francais/usage-avance/surcharge-de-configuration).
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

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/Mu](https://github.com/libretro/Mu)
* **Code source Officiel :** [https://github.com/meepingsnesroms/Mu](https://github.com/meepingsnesroms/Mu)
* **Site Officiel :** [https://meepingsnesroms.github.io/](https://meepingsnesroms.github.io/)

