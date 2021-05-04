---
title: Libretro GenesisPlusGX
---

# Libretro GenesisPlusGX

**Libretro GenesisPlusGX** est un émulateur Sega 8/16 bits open-source axé sur la précision et la portabilité.

## ![](/migration-images/emulateurs/consoles-de-salon/master-system/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**non-commerciale**](https://github.com/libretro/Genesis-Plus-GX/blob/master/LICENSE.txt).

## ![](/migration-images/emulateurs/consoles-de-salon/master-system/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-de-salon/master-system/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Multi-Mouse | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/master-system/tqfp32.svg) BIOS

### Liste des bios optionnels

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| bios\_E.sms | BIOS EU MasterSystem \(bootrom\) | 840481177270d5642a14ca71ee72844c 4187d96beaf36385e681a3cf3bd1663d e8b26871629b938887757a64798df6dc 02cbb2e348945c9ac41e37502a58ca76 5cd8f62cd8786af0226e6d2248279338 08b81aa6be18b92daef1b875deecf824 bdb34f2c471e5d0c358eeec621f9d029 | ⚠\* |
| bios\_U.sms | BIOS US MasterSystem \(bootrom\) | 840481177270d5642a14ca71ee72844c b264bef9bda264ffe83afcebac21b81f e8b26871629b938887757a64798df6dc 02cbb2e348945c9ac41e37502a58ca76 5cd8f62cd8786af0226e6d2248279338 08b81aa6be18b92daef1b875deecf824 | ⚠\* |
| bios\_J.sms | BIOS JP MasterSystem \(bootrom\) | 24a519c53f67b00640d0048ef7089105 | ⚠\* |

\* Fourni mais n'est pas le bon bios.

### **Emplacement**

Placez les bios comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 🗒 bios\_E.sms  
┃ ┃ ┃ ┣ 🗒 bios\_U.sms  
┃ ┃ ┃ ┣ 🗒 bios\_J.sms  

## ![](/migration-images/emulateurs/consoles-de-salon/master-system/rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .sms
* .zip
* .7z

Ce système supporte les roms compressées au format .zip/.7z. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip/.7z doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip/.7z ne doit contenir qu'une seule rom compressée.

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁mastersystem  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  

## ![](/migration-images/emulateurs/consoles-de-salon/master-system/hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
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

## ![](/migration-images/emulateurs/consoles-de-salon/master-system/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* Github utilisé : [https://github.com/libretro/Genesis-Plus-GX/](https://github.com/libretro/Genesis-Plus-GX/)
* Doc Libretro : [https://docs.libretro.com/library/genesis\_plus\_gx/](https://docs.libretro.com/library/genesis_plus_gx/)

