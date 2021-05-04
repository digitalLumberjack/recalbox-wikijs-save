---
title: Libretro Mednafen\_NGP
---

# Libretro Mednafen\_NGP

**Libretro Mednafen\_ngp** est un émulateur de système de jeu vidéo SNK Neo Geo Pocket et Neo Geo Pocket Color basé sur NeoPop.

Il a été écrit par :

* neopop\_uk
* Équipe Mednafen

## ![](/migration-images/emulateurs/consoles-portables/neo-geo-pocket/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/beetle-ngp-libretro/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-portables/neo-geo-pocket/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/neo-geo-pocket/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ \(not link-cable emulation\) |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats | ✔ |
| Native Cheats | ✕ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/neo-geo-pocket/tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/neo-geo-pocket/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .ngp
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
┃ ┃ ┃ ┣ 📁ngp  
┃ ┃ ┃ ┃ ┣ 🗒**jeux.zip**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/neo-geo-pocket/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/neo-geo-pocket/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/beetle-ngp-libretro/](https://github.com/libretro/beetle-ngp-libretro)
* **Documentation Libretro :** [https://docs.libretro.com/library/beetle\_neopop/](https://docs.libretro.com/library/beetle_neopop/)
* **Code source Officiel :** [https://mednafen.github.io/releases/](https://mednafen.github.io/releases/)
* **Documentation Officiel :** ​[https://mednafen.github.io/documentation/ngp.html](https://mednafen.github.io/documentation/ngp.html)
* **Site Officiel :**[ ****https://mednafen.github.io/](https://mednafen.github.io)
* **Forum Officiel :** [https://forum.fobby.net/](https://forum.fobby.net/)

