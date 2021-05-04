---
title: Dolphin
---

# Dolphin

**Dolphin** est un émulateur pour deux récentes consoles de jeu de Nintendo : la GameCube et la Wii. Il permet aux joueurs sur PC d'apprécier les jeux réalisés pour ces deux consoles en **full HD** \(1080p\) avec différentes améliorations : compatibilité avec tous les contrôleurs de PC, vitesse turbo, jeu en ligne en réseau, et bien plus encore !

Plus de 200 personnes ont travaillé dur depuis des années pour créer Dolphin. La liste des contributeurs peut être trouvée [sur GitHub](https://github.com/dolphin-emu/dolphin/graphs/contributors).

## ![](/migration-images/emulateurs/consoles-de-salon/gamecube/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/dolphin-emu/dolphin/blob/master/license.txt).

## ![](/migration-images/emulateurs/consoles-de-salon/gamecube/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC X86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |

## ![](/migration-images/emulateurs/consoles-de-salon/gamecube/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/consoles-de-salon/gamecube/tqfp32.svg) BIOS

Bien que purement facultatives, il existe tout de même des bios Gamecube par zone géographique, à savoir Europe \(EUR\), États-Unis \(USA\) et Japon \(JAP\).

### Liste des bios optionnels

| Non de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| IPL.bin | BIOS GameCube EUR | 0cdda509e2da83c85bfe423dd87346cc | ⚠ |
| IPL.bin | BIOS GameCube JAP | fc924a7c879b661abc37cec4f018fdf3 | ⚠ |
| IPL.bin | BIOS GameCube USA | 339848a0b7c2124cf155276c1e79cbd0 | ⚠ |

⚠Fourni mais n'a pas la bonne signature MD5.

### **Emplacement**

Placez les bios comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 📁 gamecube  
┃ ┃ ┃ ┃ ┣ 📁 EUR  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 **IPL.bin**  
┃ ┃ ┃ ┃ ┣ 📁 JAP  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 **IPL.bin**  
┃ ┃ ┃ ┃ ┣ 📁 USA  
┃ ┃ ┃ ┃ ┃ ┣ 🗒 **IPL.bin**  

## ![](/migration-images/emulateurs/consoles-de-salon/gamecube/rom-30098_640.png) Roms

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .iso
* .gcz
* .rvz

### **Emplacement**

Placez les isos comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁gamecube  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.iso**  


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/gamecube/hammer-28636_640.png) Configuration avancées de l’émulateur

### Options de Dolphin

-

### **Jouer avec de véritables manettes Gamecube** 


>Un adaptateur USB pour manette Gamecube est nécessaire pour cette fonction !
{.is-danger}

* Branchez votre adaptateur Gamecube a votre Recalbox 
* Ouvrez le fichier : `/recalbox/share/system/recalbox.conf`
  * Dans la section contrôleurs, cherchez la ligne suivante :
    * `gamecube.realgamecubepads=0`  
  * puis modifiez par ceci :
    * `gamecube.realgamecubepads=1` 
* Voila votre manette Gamecube fonctionne maintenant dans Dolphin.

### Packs de textures personnalisées

Dolphin permet, en plus de faire tourner les jeux Gamecube, d'améliorer les textures ou encore pour certain les vidéos en HD, crée par des passionnés \(merci à eux\) pour encore plus embellir vos jeux préférés.

Pour l’instant il existe des packs textures pour les jeux suivants :

* Mario Kart Double Dash
* Luigi’s Mansion
* Zelda Ocarina of Time
* Resident Evil 2
* Resident Evil 3 Nemesis

_Cette liste n’est pas exhaustive, d’autres sont sûrement en préparation ou sont déjà sortis lorsque vous lirez ces lignes._

Ils sont disponible sur le [forum de Dolphin](https://forums.dolphin-emu.org/Forum-custom-texture-projects). Les formats supportés sont :

* BC7
* DDS

Placez vos pack de textures dans le dossier suivant :

* `/recalbox/share/saves/dolphin-emu/Load/Textures/`

Toutes les textures doivent se trouver dans un dossier avec l'ID du jeu pour lequel vous installez le pack ou l'équivalent de 3 lettres sans région.

* `GM4`: id sans région
* `GM4P01`: id complet 

![Exemple pour Mario Kart Double Dash \(Europe\)](/migration-images/emulateurs/consoles-de-salon/gamecube/textures-packs.png)

On peut trouve cette information sous Dolphin Pour ce faire :

* Lancez n’importe quel jeu GameCube.
* Une fois le jeu démarre, appuyez simultanément sur `Hotkey+B` 
* Le menu Dolphin apparaît avec une liste de vos jeux
* Recherchez le jeu dont vous avez besoin de connaître l’ID, cette dernière est indiquée sur la quatrième colonne et elle est composée d’une combinaison de 6 lettres et chiffres.


>Si les textures ne se trouvent pas dans un dossier nommé correctement, alors le pack ne fonctionnera pas !
{.is-danger}

## ![](/migration-images/emulateurs/consoles-de-salon/gamecube/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/dolphin-emu/dolphin](https://github.com/dolphin-emu/dolphin)
* **Site officiel** : [https://www.dolphin-emu.org/](https://www.dolphin-emu.org/)

