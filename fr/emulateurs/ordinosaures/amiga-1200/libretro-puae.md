---
title: Libretro PUAE
---

# Libretro PUAE

Basé sur P-UAE 2.6.1, Git Commit: 0186c1b16f7181ffa02d73e6920d3180ce457c46, Crédits à Mustafa 'GnoStiC' TUFAN

Tous les crédits à: Richard Drummond " [http://www.rcdrummond.net/uae/](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&pto=aue&rurl=translate.google.com&sl=auto&sp=nmt4&tl=fr&u=http://www.rcdrummond.net/uae/&usg=ALkJrhig6Wk-oRWU1bN2eefyK62LcfeQ5g) "

E-UAE est basé sur le travail de dizaines de contributeurs, dont Bernd Schmidt \(l'auteur et mainteneur d'origine des UAE\), Bernie Meyer \(l'auteur du compilateur J86 x86\), Toni Wilen \(le mainteneur actuel de WinUAE\), et bien d'autres .

Ce port était basé au départ sur la version PS3 E-UAE 0.8.29-WIP4 version 8 \(donc également à Ole.\)

Et bien sûr pour l'équipe RetroArch / Libretro: " [http://www.libretro.com/](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&pto=aue&rurl=translate.google.com&sl=auto&sp=nmt4&tl=fr&u=http://www.libretro.com/&usg=ALkJrhhhR2tkxXIUWKsRHvKwwMignvG2AQ) "

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/PUAE/blob/master/COPYING).

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/tqfp32.svg) BIOS

### Liste des bios obligatoires

Vous trouverez les bios avec le nom indiqué dans la colonne **Description** qu'il vous faudra renommer avec le nom indiqué dans la colonne **Nom de fichier**.

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| kick40068.A1200.rom | Kickstart v3.1 r40.068 \(1993-12\)\(Commodore\)\(A1200\)\[!\].rom |  | ❌ |
| kick40068.A4000.rom | Kickstart v3.1 r40.068 \(1993-12\)\(Commodore\)\(A4000\)\[!\].rom |  | ❌ |

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒 kick40068.A1200.rom  
┃ ┃ ┃ ┣ 🗒 kick40068.A4000.rom  

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/rom-30098_640.png) Roms

### **Extensions supportées**

La rom doit avoir l'extension :

* .adf
* .adz
* .ipf
* .lha
* .lhz
* .lzx
* .zip
* .rp9
* .dms
* .fdi
* .hdf
* .hdz
* .m3u

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁amiga1200  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.ipf**  


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/hammer-28636_640.png) Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

