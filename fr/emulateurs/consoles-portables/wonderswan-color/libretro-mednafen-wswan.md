---
title: Libretro Mednafen\_wswan
---

# Libretro Mednafen\_wswan

**Libretro beetle-wswan** est un émulateur pour les consoles de jeux portables Wonderswan, Wonderswan Color et Pocket Challenge V2 développé en C et C++.

Il est un port autonome de Mednafen WonderSwan vers Libretro, lui-même un fork de Cygne.

## ![](/migration-images/emulateurs/consoles-portables/wonderswan-color/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/beetle-wswan-libretro/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-portables/wonderswan-color/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/wonderswan-color/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ \(not link-cable emulation\) |
| Controls | ✔ |
| Remapping | ✔ |
| [Softpatching](https://docs.libretro.com/guides/softpatching/) | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/wonderswan-color/tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/wonderswan-color/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .wsc
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
┃ ┃ ┃ ┣ 📁wsc  
┃ ┃ ┃ ┃ ┣ 🗒**jeux.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/wonderswan-color/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/wonderswan-color/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/beetle-wswan-libretro](https://github.com/libretro/beetle-wswan-libretro)
* **Documentation Libretro :** [https://docs.libretro.com/library/beetle\_cygne/](https://docs.libretro.com/library/beetle_cygne/)
* **Code source Officiel :** [https://mednafen.github.io/releases/](https://mednafen.github.io/releases/)
* **Site Officiel :** [https://mednafen.github.io](https://mednafen.github.io)
* **Forum Officiel :** [https://forum.fobby.net/](https://forum.fobby.net/)
* **Documentation Officiel :** ​[https://mednafen.github.io/documentation/wswan.html](https://mednafen.github.io/documentation/wswan.html)

