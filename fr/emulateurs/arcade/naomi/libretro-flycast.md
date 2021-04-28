---
title: Libretro Flycast
---

# Libretro Flycast

**Libretro Flycast** est un émulateur **Sega Dreamcast multiplate-formes** capable d'émuler les systèmes suivants :

* **NAOMI M1** 
* **NAOMI M2** 
* **NAOMI M4** 

## \*\*\*\*![](./gerald-g-parchment-background-or-border-5.svg)**Licence**

Ce core est sous licence **GPLv2**

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| Core Options | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Rumble | ✔ |
| Disk Control | ✔ |

## ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8XiT7IYKKaiugqvx_V%2F-M8Xmbk84n_wFmAjHuYz%2Ftqfp32.svg?alt=media&token=e16549a1-1f0a-407a-9ac1-016a0c61d9d6)BIOS

###  Liste des bios obligatoires

| Nom de fichier | Description | **MD5** | Fourni |
| :---: | :---: | :---: | :---: |
| naomi.zip | Format MAME à partir du Romset MAME 0.154 | eb4099aeb42ef089cfe94f8fe95e51f6 | ❌ |

### Liste des bios optionnels

| Nom du fichier bios | **Description** | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| airlbios.zip | BIOS Naomi pour le jeu « Airline Pilots Deluxe » de MAME | 3f348c88af99a40fbd11fa435f28c69d | ❌ |
| hod2bios.zip | BIOS Naomi pour le jeu « The House of the Dead 2 » de MAME | 9c755171b222fb1f4e1439d5b709dbf1 | ❌ |

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 📁dc
> > > >
> > > > > 🗒**naomi.zip**
> > > > >
> > > > > 🗒**airlbios.zip**
> > > > >
> > > > > 🗒**hod2bios.zip**

## ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8aCYUVKmyQVmzExaM5%2F-M8aNa4dCTHo4lu4UBan%2From-30098_640.png?alt=media&token=3580fa09-47e6-4c89-b00e-1e655c7ffffe)Roms

Flycast ce base sur le Romset de **Mame**  mais aussi sur des format **nullDC** pour sa partie Naomi.

### Romset Mame

Seul les roms Naomi **issue d'un RomSet MAME 0.135 ou supérieur** sont compatible !   
Nous vous conseillons le dernier Romset 0.230 qui apportera son lot de compatibilité supplémentaire!  
Pour plus d'info sur la version du Romset en cour : [MameDev](https://www.mamedev.org/release.html) .


>**Remarque :**
>
>Les **fichiers dat** afin de trier vos roms arcade sont **disponible** dans le dossier :`/recalbox/share/bios/dc/Naomi_datfiles.zip`
{.is-info}

Vous pouvez aussi le télécharger ci dessous :

{% file src="../../../.gitbook/assets/naomi-0.220\_noclones\_v1.0-barhi.dat" caption="Naomi-0.220\_NoClones" %}

### Romset NullDC

Ces roms sont compatibles avec Flycast mais **moins fiable** que des roms **issue d'un Romset Mame.**


>**Information :**
>
>Les Roms **NullDC** sont en format : _`.bin + .lst`_
{.is-info}

Exemple pour le jeu **`cfield.zip`** :

* `/recalbox/share/roms/naomi/cfield/...`
* `/recalbox/share/roms/naomi/cfield/cfield.bin`
* `/recalbox/share/roms/naomi/cfield/cfield.lst`

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁naomi
> > > >
> > > > > 🗒**fichier.zip**

## ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8aCYUVKmyQVmzExaM5%2F-M8aKPqMCdW7WO3xrn1F%2Fhammer-28636_640.png?alt=media&token=d513c9a6-0bfe-48ec-8bc7-28e0de5a3754)Configuration avancée de l'émulateur


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

* **Github utilisé :** [https://github.com/libretro/flycast/](https://github.com/libretro/flycast)
* **Documentation Libretro :** [https://docs.libretro.com/library/flycast/](https://docs.libretro.com/library/flycast/)
* **Github Officiel :** [https://github.com/flyinghead/flycast/](https://github.com/flyinghead/flycast)

