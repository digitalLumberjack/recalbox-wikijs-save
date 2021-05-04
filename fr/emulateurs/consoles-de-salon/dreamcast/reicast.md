---
title: Reicast
---

# Reicast

**Reicast** est un émulateur capable d'émuler la **Dreamcast**.

## ![](/migration-images/emulateurs/consoles-de-salon/dreamcast/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**BSD-3**](https://github.com/reicast/reicast-emulator/blob/alpha/LICENSE).

## ![](/migration-images/emulateurs/consoles-de-salon/dreamcast/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌  | ❌  | ✅  | ✅  | ✅  | ✅  | ❌ | ✅  | ✅  |

## ![](/migration-images/emulateurs/consoles-de-salon/dreamcast/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
|  |  |

## ![](/migration-images/emulateurs/consoles-de-salon/dreamcast/tqfp32.svg) BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| dc\_boot.bin | BIOS Dreamcast | e10c53c2f8b90bab96ead2d368858623 | ❌  |
| dc\_flash.bin | Date / Heure / Langue | 0a93f7940c455905bea6e392dfde92a4 | ❌  |

### **Emplacement**

Placez les bios comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 🗒 **dc\_boot.bin**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **dc\_flash.bin**  

## \*\*\*\*![](/migration-images/emulateurs/consoles-de-salon/dreamcast/rom-30098_640.png) **Roms**

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .cdi
* .gdi
* .chd

### **Emplacement**

Placez les isos comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁dreamcast  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.cue**  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **fichier.bin**  


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/dreamcast/hammer-28636_640.png) Configuration avancée des émulateurs

### \*\*\*\*

## \*\*\*\*![](/migration-images/emulateurs/consoles-de-salon/dreamcast/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes**

* **Github utilisé :** [https://github.com/reicast/reicast-emulator/](https://github.com/reicast/reicast-emulator/)
* **Doc** : [https://reicast.com/guide/](https://reicast.com/guide/)

