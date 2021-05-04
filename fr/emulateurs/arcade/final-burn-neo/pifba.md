---
title: PiFBA
---

# PiFBA

**PiFBA** est Final Burn Alpha 2x pour le Raspberry Pi porté par Squid.  
__Cela émule les anciens jeux d'arcade en utilisant des roms basés sur MAME pour CPS1, CPS2, Neogeo, Toaplan et de nombreux autres jeux.

Il devrait prendre en charge les versions les plus récentes des versions MAME de ces ROMs, mais malheureusement, il n'y a pas de version définitive à utiliser. Une liste complète des jeux pris en charge se trouve dans le programme frontal.

Un certain nombre de jeux ne fonctionneront pas correctement, certains sont si volumineux qu'ils semblent manquer de mémoire.


>**Remarque :**
>A n'utiliser que si vous avez un Pi0/1 ou si vous voulez améliorez les performances d'un jeu particulier ramant sur FbNeo.
>piFBA est le mieux optimisé des émulateurs FBA sur la RecalBox pour le Pi0/1 mais est compatible avec beaucoup moins de jeux que FbNeo.
{.is-warning}

## ![](/migration-images/emulateurs/arcade/final-burn-neo/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence **GPLv2**

## ![](/migration-images/emulateurs/arcade/final-burn-neo/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

## ![](/migration-images/emulateurs/arcade/final-burn-neo/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Saves | ✔ |
| States |  |
| Rewind |  |
| Netplay | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats |  |
| Native Cheats |  |
| Controllers |  |
| Multi-Mouse |  |
| Rumble |  |
| Sensors |  |
| Camera |  |
| Location |  |
| Subsystem |  |

## ![](/migration-images/emulateurs/arcade/final-burn-neo/tqfp32.svg)Bios

### Liste des bios

En fonction des jeux, certains bios seront nécessaires et seront à placer dans le même répertoire que les jeux.

### **Emplacement**

Placez les **bios** comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁 fba  
┃ ┃ ┃ ┃ ┣ 🗒 bios.zip  

## ![](/migration-images/emulateurs/arcade/final-burn-neo/rom-30098_640.png)**Roms**

* Basé sur le RomSet MAME : **FBA 0.2.96.71** \(Avril 2007\) lui-même basé sur le set MAME 0.114
* Poids : 3.62GB
* Romsets émulés : 684 \(Pas de clone dans ce set\)
* Liste de compatibilité : [/recalbox/share/roms/fba/clrmamepro/piFBA\_gamelist.txt](https://gitlab.com/recalbox/recalbox/-/raw/master/board/recalbox/fsoverlay/recalbox/share_init/bios/fba/piFBA_gamelist.txt)
* Fichier Dat : [/recalbox/share/roms/fba/clrmamepro/fba\_029671\_od\_release\_10\_working\_roms.dat](https://gitlab.com/recalbox/recalbox/-/raw/master/board/recalbox/fsoverlay/recalbox/share_init/bios/fba/fba_029671_od_release_10_working_roms.dat)

Certaines ROMs importantes peuvent nécessiter une conversion au format '.fba' avant de fonctionner.  
FBACache\_windows.zip est inclus pour ce faire, qui fonctionne sous Windows uniquement.

Un fichier DAT clrmamepro / romcenter est inclus 'fba\_029671\_clrmame\_dat.zip' qui prend en charge la plupart des ROMs qui fonctionnent et peuvent générer des ROMs compatibles à partir des versions récentes de MAME.

## ![](/migration-images/emulateurs/arcade/final-burn-neo/hammer-28636_640.png)Configuration avancée des émulateurs


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

## ![](/migration-images/emulateurs/arcade/final-burn-neo/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github :** [https://github.com/recalbox/pifba](https://github.com/recalbox/pifba) Le code a été déplacé vers github : [https://github.com/squidrpi/pifba](https://github.com/squidrpi/pifba)
* **Site Officiel :** 
* **Wiki du core :** 

