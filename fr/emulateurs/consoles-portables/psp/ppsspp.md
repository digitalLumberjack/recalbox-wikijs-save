---
title: PPSSPP
---

# PPSSPP

**PPSSPP** est un émulateur libre pour la console portable PSP développer en C++.  
Il est disponible sur de nombreuses plate-formes, dont Android, Windows, iOS et GNU/Linux.

Il est écrit par **Henrik Hrydgard**.

## Exigences

* OpenGL / Open GL ES 2.0 ou supérieur pour le moteur de rendu OpenGL.
* Vulkan pour le moteur de rendu Vulkan.
* Direct3D 11 pour le moteur de rendu Direct3D 11.

## ![](/migration-images/emulateurs/consoles-portables/psp/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/hrydgard/ppsspp/blob/master/LICENSE.TXT).

## ![](/migration-images/emulateurs/consoles-portables/psp/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/psp/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Saves | ✔ |
| States | ✔ |
| Core Options | ✔ |
| Native Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Username | ✔ |
| Language | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/psp/tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/psp/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .elf
* .iso
* .cso
* .prx
* .pbp

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁psp    
┃ ┃ ┃ ┃ ┣ 🗒**jeux.**i**so**  


>Les isos au format **Redump** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/psp/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/psp/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source Utilisé/Officiel :** [https://github.com/hrydgard/ppsspp](https://github.com/hrydgard/ppsspp)
* **Documentation Libretro :** [https://docs.libretro.com/library/ppsspp/](https://docs.libretro.com/library/ppsspp/)
* **Site Officiel :** [http://www.ppsspp.org/](http://www.ppsspp.org/)
* **Forum Officiel :** [https://forums.ppsspp.org/](https://forums.ppsspp.org/)
* **Documentation Officiel :** ​[http://www.ppsspp.org/guides.html](http://www.ppsspp.org/guides.html)

