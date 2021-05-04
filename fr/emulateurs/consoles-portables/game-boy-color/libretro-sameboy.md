---
title: Libretro SameBoy
---

# Libretro SameBoy

**Libretro SameBoy** est un émulateur open source Gameboy \(DMG\) et Gameboy Color \(CGB\) extrêmement précis, écrit en C.

* Prend en charge l'émulation Game Boy \(DMG\); Game Boy Color \(CGB\) et GBC-Mode; Game Boy Advance \(AGB\)
* Prend en charge l'émulation précise de haut niveau de Super Game Boy \(SGB; NTSC et PAL\) et Super Game Boy 2 \(SGB2\)
* Vous permet de choisir le modèle que vous souhaitez émuler quelle que soit la ROM
* Audio 96 kHz de haute qualité
* Prise en charge de l'économie de batterie
* Enregistrer les états
* Inclut des ROM de démarrage open source pour tous les modèles émulés:
  * Prise en charge complète \(et documentation de\) toutes les palettes spécifiques au jeu dans la ROM de démarrage CGB / AGB, pour une émulation précise des jeux Game Boy sur une Game Boy Color
  * Prend en charge la sélection manuelle de palette avec des combinaisons de touches, avec 4 nouvelles palettes supplémentaires \(direction A + B +\)
  * Prend en charge la sélection de palette dans un jeu CGB, le forçant à fonctionner en mode DMG «palettisé», si la ROM le permet
  * Prise en charge des jeux avec un logo non Nintendo dans l'en-tête
  * Pas de longue animation dans la ROM de démarrage DMG
* Quatre paramètres de correction des couleurs
* Trois réglages de filtres audio passe-haut
* Émulation d'horloge en temps réel
* Modes turbo, rembobinage et ralenti
* Précision extrêmement élevée
* Émulation de câble de liaison

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**MIT**](https://github.com/libretro/SameBoy/blob/master/LICENSE).

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/game-boy-color/compatibility.png) ****Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/cogwheel-145804_640.png)Fonctionnalités

| **Fonctionnalité** | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ |
| Core Options | ✔ |
| RetroAchievements | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Rumble | ✔ |
| Subsystem | ✔ |

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/tqfp32.svg)BIOS

### Liste des bios optionnels

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| cgb\_bios.bin | BIOS Game Boy Color | b560efd759d87634a03b243f22bba27a | ❌ |

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒**cgb\_bios.bin**  

## \*\*\*\*![](/migration-images/emulateurs/consoles-portables/game-boy-color/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .bin
* .gbc
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
┃ ┃ ┃ ┣ 📁gbc  
┃ ┃ ┃ ┃ ┣ 🗒**jeux.gb**  


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/hammer-28636_640.png)Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-portables/game-boy-color/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Code source utilisé :** [https://github.com/libretro/SameBoy/](https://github.com/libretro/SameBoy)
* **Documentation Libretro** : [https://docs.libretro.com/library/sameboy/](https://docs.libretro.com/library/sameboy/)
* **Code source officiel :** [https://github.com/LIJI32/SameBoy](https://github.com/LIJI32/SameBoy)
* **Site officiel :** [https://sameboy.github.io](https://sameboy.github.io)

