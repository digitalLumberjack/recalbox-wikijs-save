---
title: Libretro Stella
---

# Libretro Stella

**Libretro Stella** est un émulateur Atari multiplateforme.

## ![](/migration-images/emulateurs/consoles-de-salon/atari-2600/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/stella-emu/stella/blob/master/License.txt).

## ![](/migration-images/emulateurs/consoles-de-salon/atari-2600/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-de-salon/atari-2600/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ |
| RetroAchievements | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/atari-2600/tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](/migration-images/emulateurs/consoles-de-salon/atari-2600/rom-30098_640.png)**Roms**

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .a26
* .bin
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
┃ ┃ ┃ ┣ 📁atari2600  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/atari-2600/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-de-salon/atari-2600/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github utilisé :** [https://github.com/libretro/stella/](https://github.com/libretro/stella/)
* **Doc Libretro :** [https://docs.libretro.com/library/stella/](https://docs.libretro.com/library/stella/)

