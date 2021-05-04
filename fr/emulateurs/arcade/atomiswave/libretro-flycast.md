---
title: Libretro Flycast
---

# Libretro Flycast

**Libretro Flycast** est un émulateur **Sega Dreamcast multi-plateformes** capable d'émuler le **Sammy Atomiswave.**

## ![](/migration-images/emulateurs/arcade/atomiswave/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence **GPLv2.**

## ![](/migration-images/emulateurs/arcade/atomiswave/compatibility.png) **Compatibilité**

| **RPI0/RPI1** | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ 🐌 | ✅ | ✅ |

🐌 Basses performances mais jouable

## ![](/migration-images/emulateurs/arcade/atomiswave/cogwheel-145804_640.png)Fonctionnalités

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

## ![](/migration-images/emulateurs/arcade/atomiswave/tqfp32.svg)BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| awbios.zip | Bios « Atomiswave » de Mame | 0ec5ae5b5a5c4959fa8b43fcf8687f7c | ❌ |

### **Emplacement**

Placez les bios comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 📁dc  
┃ ┃ ┃ ┃ ┣ 🗒**awbios.zip**  

## \*\*\*\*![](/migration-images/emulateurs/arcade/atomiswave/rom-30098_640.png)**Roms**

Libretro Flycast se base sur le Romset de **MAME** mais aussi sur des formats **NullDC** pour sa partie Atomiswave.

### Extensions supportées

Les roms doivent avoir les extensions suivantes :

* .zip
* .7z
* .bin/.lst
* .dat

## Romset Mame

Seules les roms Atomiswave **issues d'un RomSet MAME 0.135 ou supérieur** sont compatibles.  
Nous vous conseillons le **RomSet Mame 0.220** qui apportera son lot de compatibilités supplémentaires.  
Pour plus d'informations sur la version du Romset en cours, consultez la page [MameDev](https://www.mamedev.org/release.html).


>**Remarque :**
>Afin de trier vos roms arcade, les **fichiers dat** sont disponibles dans le dossier :`/recalbox/share/bios/dc/Atomiswawe_datfiles.zip`
{.is-info}

Vous pouvez aussi le télécharger ci dessous :

{% file src="../../../.gitbook/assets/atomiswave-0.220\_noclones\_v1.0-barhi.dat" %}

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁atomiswave  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  

## Romset NullDC

Ces roms sont compatibles avec Flycast mais **moins fiables** que des roms **issues d'un set MAME.**


>**Information :**
>Les Roms **NullDC** sont au format : _`.bin + .lst`_
{.is-info}

### **Emplacement**

Placez les roms comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁atomiswave  
┃ ┃ ┃ ┃ ┣ 📁**jeux**  
┃ ┃ ┃ ┃ ┃ ┣ 🗒**jeux.bin**  
┃ ┃ ┃ ┃ ┃ ┣ 🗒**jeux.lst**  

## ![](/migration-images/emulateurs/arcade/atomiswave/hammer-28636_640.png)Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder aux options

Vous pouvez configurer diverses options de deux façons différentes.

* Via le Menu RetroArch :

┣ 📁Menu RetroArch  
┃ ┣ 📁Options du core  
┃ ┃ ┣ 🧩Name\_option  

* Via le fichier `retroarch-core-options.cfg`:

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁system  
┃ ┃ ┃ ┣ 📁configs  
┃ ┃ ┃ ┃ ┣ 📁retroarch  
┃ ┃ ┃ ┃ ┃ ┣ 📁cores  
┃ ┃ ┃ ┃ ┃ ┃ ┣ 🧩**retroarch-core-options.cfg**  

### Options du core

## ![](/migration-images/emulateurs/arcade/atomiswave/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github utilisé :** [https://github.com/libretro/flycast](https://github.com/libretro/flycast)
* **Doc Libretro :** [https://docs.libretro.com/library/flycast/](https://docs.libretro.com/library/flycast/)
* **Github Officiel :** [https://github.com/flyinghead/flycast](https://github.com/flyinghead/flycast)

