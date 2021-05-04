---
title: Libretro Mednafen\_PSX
---

# Libretro Mednafen\_PSX

[Beetle PSX](https://github.com/libretro/beetle-psx-libretro)  est un fork du module PSX de [Mednafen](https://mednafen.github.io/) pour Libretro, il fonctionne actuellement sous Linux, macOS et Windows.

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/beetle-psx-libretro/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC x86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ✅ 🐌  | ✅ | ❌ | ✅ | ✅ | ✅ |

🐌 Basses performances mais jouable

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Redémarrage | ✔ |
| Capture d'écran | ✔ |
| Sauvegardes | ✔ |
| Sauvegardes d'état | ✔ |
| Options du core | ✔ |
| RetroAchievements | ✔ |
| Cheats RetroArch | ✔ |
| Contrôles | ✔ |
| Remapping | ✔ |
| Multi-Mouse | ✔ |
| Vibration | ✔ |
| Contrôle de disque | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| scph5500.bin | BIOS PS1 japonais - requis pour les jeux japonais | 8dd7d5296a650fac7319bce665a6a53c | ❌ |
| scph5501.bin | BIOS PS1 américain - requis pour les jeux américains | 490f666e1afb15b7362b406ed1cea246 | ❌ |
| scph5502.bin | BIOS PS1 européen - requis pour les jeux européens | 32736f17079d0b2b7024407c39bd3050 | ❌ |

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒 **scph5500.bin**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **scph5501.bin**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **scph5502.bin**  

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/rom-30098_640.png) Roms

### Extensions supportées

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .bin/.toc
* .m3u
* .img/.ccd/.sub
* .exe
* .pbp
* .chd

### Emplacement

Placez les isos comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 roms  
┃ ┃ ┃ ┣ 📁 psx  
┃ ┃ ┃ ┃ ┣ 🗒 **fichier.cue**  


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/hammer-28636_640.png) Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/beetle-psx-libretro/](https://github.com/libretro/beetle-psx-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/beetle\_psx/](https://docs.libretro.com/library/beetle_psx/)

