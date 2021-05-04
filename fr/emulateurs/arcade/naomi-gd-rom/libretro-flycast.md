---
title: Libretro Flycast
---

# Libretro Flycast

**Libretro Flycast** est un émulateur **Sega Dreamcast multiplate-formes** capable d'émuler la **Naomi GD-ROM.**

## \*\*\*\*![](/migration-images/emulateurs/arcade/naomi-gd-rom/gerald-g-parchment-background-or-border-5.svg)**Licence**

Ce core est sous licence **GPLv2**

## ![](/migration-images/emulateurs/arcade/naomi-gd-rom/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/arcade/naomi-gd-rom/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| Netplay | ✕ |
| Core Options | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Rumble | ✔ |
| Disk Control | ✔ |

## ![](/migration-images/emulateurs/arcade/naomi-gd-rom/tqfp32.svg) BIOS

### Liste des bios **obligatoires**

| Nom de fichier | Description | **MD5** | Fourni |
| :---: | :---: | :---: | :---: |
| naomi.zip | Format MAME a partir du Romset 0.154 | eb4099aeb42ef089cfe94f8fe95e51f6 | ❌ |

### Liste des bios **optionnels**

| Nom de fichier | **Description** | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| airlbios.zip | Naomi Airline Pilots deluxe Bios from MAME | 3f348c88af99a40fbd11fa435f28c69d | ❌ |
| hod2bios.zip | Naomi The House of the Dead 2 Bios from MAME | 9c755171b222fb1f4e1439d5b709dbf1 | ❌ |

### **Emplacement**

Placez les bios comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 📁dc  
┃ ┃ ┃ ┃ ┣ 🗒**naomi.zip**  
┃ ┃ ┃ ┃ ┣ 🗒**airlbios.zip**  
┃ ┃ ┃ ┃ ┣ 🗒**hod2bios.zip**  

## ![](/migration-images/emulateurs/arcade/naomi-gd-rom/rom-30098_640.png) Roms

Flycast se base sur le romset de **Mame**.

### Romset Mame

Seuls les roms Naomi **issue d'un romset MAME 0.135 ou supérieur** sont compatible !   
Nous vous conseillons le dernier r**omset Mame 0.230** qui apportera son lot de compatibilité supplémentaire !  
Pour plus d'info sur la version du romset en cour : [MameDev](https://www.mamedev.org/release.html) .

Sur Naomi GD-Rom certaines roms nécessitent un fichier `.chd` issu aussi du romset MAME :


>**Remarque :**
>Les **fichiers dat** afin de trier vos roms arcade sont **disponible** dans le dossier :`/recalbox/share/bios/dc/`
{.is-info}

Vous pouvez aussi le télécharger ci dessous :

{% file src="../../../.gitbook/assets/naomigd-0.220\_noclones\_v1.0-barhi.dat" caption="NaomiGd-0.220\_NoClones" %}


>**Informations :**
>Les jeux **Naomi GD-ROMS**  sont en format `.zip + .chd` 
{.is-info}

Exemple pour le jeu **`cfield.zip`** :  
Placez le fichier du jeu a la racine du dossier NaomiGD   
`/recalbox/share/roms/naomigd/cfield.zip`

Placez le\(s\) fichier\(s\) .chd nécessaire dans un dossier du même nom que le jeu zip

`/recalbox/share/roms/naomigd/cfield/gdl-0025.chd`

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁naomigd  
┃ ┃ ┃ ┃ ┣ 🗒**jeu1.zip**  
┃ ┃ ┃ ┃ ┣ 📁 **jeu1**  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 **jeu1.chd**  

## ![](/migration-images/emulateurs/arcade/naomi-gd-rom/hammer-28636_640.png) Configuration avancée de l'émulateur


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

## \*\*\*\*![](/migration-images/emulateurs/arcade/naomi-gd-rom/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes**

* **Github utilisé :** [https://github.com/libretro/flycast](https://github.com/libretro/flycast)
* **Documentation Libretro :** [https://docs.libretro.com/library/flycast/](https://docs.libretro.com/library/flycast/)
* **Github Officiel :** [https://github.com/flyinghead/flycast](https://github.com/flyinghead/flycast)

