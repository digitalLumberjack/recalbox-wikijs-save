---
title: Libretro BK
---

# Libretro BK



## ![](/migration-images/emulateurs/ordinosaures/elektronika-bk/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**personnalisé**](https://github.com/libretro/bk-emulator/blob/master/COPYING).

## ![](/migration-images/emulateurs/ordinosaures/elektronika-bk/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅  | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ordinosaures/elektronika-bk/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/ordinosaures/elektronika-bk/tqfp32.svg) BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | **MD5** | Fourni |
| :---: | :---: | :---: | :---: |
| B11M\_BOS.ROM | Requis | fe4627d1e3a1535874085050733263e7 | ❌ |
| B11M\_EXT.ROM | Requis | dc52f365d56fa1951f5d35b1101b9e3f | ❌ |
| BAS11M\_0.ROM | Requis | 946f6f23ded03c0e26187f0b3ca75993 | ❌ |
| BAS11M\_1.ROM | Requis | 1e6637f32aa7d1de03510030cac40bcf | ❌ |
| DISK\_327.ROM | Requis | 5015228eeeb238e65da8edcd1b6dfac7 | ❌ |
| FOCAL10.ROM | Requis | 5737f972e8638831ab71e9139abae052 | ❌ |
| MONIT10.ROM | Requis | 95f8c41c6abf7640e35a6a03cecebd01 | ❌ |

### **Emplacement**

Placez les **bios** comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 📁 bk  
┃ ┃ ┃ ┃ ┣ 🗒 **B11M\_BOS.ROM**  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **B11M\_EXT.ROM**  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **BAS11M\_0.ROM**  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **BAS11M\_1.ROM**  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **DISK\_327.ROM**  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **FOCAL10.ROM**  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **MONIT10.ROM**  

## ![](/migration-images/emulateurs/ordinosaures/elektronika-bk/rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .bin
* .zip

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁bk  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/ordinosaures/elektronika-bk/hammer-28636_640.png) Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/ordinosaures/elektronika-bk/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/bk-emulator/](https://github.com/libretro/bk-emulator/)
* **Doc Libretro** : 

