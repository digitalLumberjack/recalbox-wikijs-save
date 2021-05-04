---
title: Libretro GenesisPlusGX
---

# Libretro GenesisPlusGX

**Libretro Genesis Plus GX** est un émulateur Sega 8/16 bits open-source axé sur la précision et la portabilité.  
Le code source, basé à l'origine sur Genesis Plus 1.3 de Charles MacDonald, a été fortement modifié et amélioré, en ce qui concerne les objectifs et la conception initiaux, afin d'améliorer la précision de l'émulation, la mise en œuvre de nouvelles fonctionnalités et l'ajout de la prise en charge de périphériques supplémentaires, de cartouches et le matériel des systèmes.

Genesis Plus GX est compatible à 100% avec les logiciels Genesis / Mega Drive, Sega / Mega CD, Master System, Game Gear, SG-1000 et Pico \(y compris tous les dumps connus sans licence ou pirate\), émulant également les modes de compatibilité descendante lorsqu'ils sont disponibles.

## ![](/migration-images/emulateurs/consoles-portables/game-gear/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**non-commerciale**](https://github.com/libretro/Genesis-Plus-GX/blob/master/LICENSE.txt).

## 🔧 ****Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/game-gear/cogwheel-145804_640.png)Fonctionnalités

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

## ![](/migration-images/emulateurs/consoles-portables/game-gear/tqfp32.svg)BIOS

### Liste des bios optionnels

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| bios.gg | BIOS GameGear \(bootrom\) | 672e104c3be3a238301aceffc3b23fd6 | ⚠ |

⚠ Fourni mais n'est pas le bon bios.

### **Emplacement**

Placez les bios comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 🗒 **bios.gg**  

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/game-gear/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .gg
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
┃ ┃ ┃ ┣ 📁gamegear  
┃ ┃ ┃ ┃ ┣ 🗒**jeux.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/game-gear/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/game-gear/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/Genesis-Plus-GX](https://github.com/libretro/Genesis-Plus-GX)
* **Documentation Libretro** : [https://docs.libretro.com/library/genesis\_plus\_gx/](https://docs.libretro.com/library/genesis_plus_gx/)
* **Code source Officiel :** [https://github.com/ekeeke/Genesis-Plus-GX](https://github.com/ekeeke/Genesis-Plus-GX)

