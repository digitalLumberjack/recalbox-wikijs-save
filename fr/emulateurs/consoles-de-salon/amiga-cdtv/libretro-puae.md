---
title: Libretro PUAE
---

# Libretro PUAE

Basé sur P-UAE 2.6.1, Git Commit: 0186c1b16f7181ffa02d73e6920d3180ce457c46, Crédits à Mustafa 'GnoStiC' TUFAN

Tous les crédits à: Richard Drummond " [http://www.rcdrummond.net/uae/](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&pto=aue&rurl=translate.google.com&sl=auto&sp=nmt4&tl=fr&u=http://www.rcdrummond.net/uae/&usg=ALkJrhig6Wk-oRWU1bN2eefyK62LcfeQ5g) "

E-UAE est basé sur le travail de dizaines de contributeurs, dont Bernd Schmidt \(l'auteur et mainteneur d'origine des UAE\), Bernie Meyer \(l'auteur du compilateur J86 x86\), Toni Wilen \(le mainteneur actuel de WinUAE\), et bien d'autres .

Ce port était basé au départ sur la version PS3 E-UAE 0.8.29-WIP4 version 8 \(donc également à Ole.\)

Et bien sûr pour l'équipe RetroArch / Libretro: " [http://www.libretro.com/](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&pto=aue&rurl=translate.google.com&sl=auto&sp=nmt4&tl=fr&u=http://www.libretro.com/&usg=ALkJrhhhR2tkxXIUWKsRHvKwwMignvG2AQ) "

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cdtv/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/PUAE/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cdtv/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅🐌 | ✅ | ✅ |

🐌 Basses performances mais jouable

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cdtv/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Core Options | ✔ |
| Controls | ✔ |
| Remapping | ✔ |
| Multi-Mouse | ✔ |
| Disk Control | ✔ |
| LEDs | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cdtv/tqfp32.svg) BIOS

### Liste des bios obligatoires

Vous trouverez les bios avec le nom indiqué dans la colonne **Description** qu'il vous faudra renommer avec le nom indiqué dans la colonne **Nom de fichier**.

<table>
  <thead>
    <tr>
      <th style="text-align:center"><b>Nom de fichier</b>
      </th>
      <th style="text-align:center">Description</th>
      <th style="text-align:center">MD5</th>
      <th style="text-align:center">Fourni</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">kick34005.CDTV.rom</td>
      <td style="text-align:center">
        <p></p>
        <p>CDTV Extended-ROM v1.0 (1991)(Commodore)(CDTV)[!].rom</p>
      </td>
      <td style="text-align:center">89da1838a24460e4b93f4f0c5d92d48d</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
  </tbody>
</table>

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒 **kick34005.CDTV.rom**  

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cdtv/rom-30098_640.png) Roms

### Extensions supportées

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .iso
* .mds/.mdf
* .img/.ccd
* .nrg
* .chd
* .m3u
* .uae

### Emplacement

Placez les isos comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 roms  
┃ ┃ ┃ ┣ 📁 cd32  
┃ ┃ ┃ ┃ ┣ 🗒 **fichier.cue**  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **fichier.bin**  


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cdtv/hammer-28636_640.png) Configuration avancée de l'émulateur


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

## ![](/migration-images/emulateurs/consoles-de-salon/amiga-cdtv/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/puae/](https://github.com/libretro/puae/)
* **Doc** : [https://docs.libretro.com/library/puae/](https://docs.libretro.com/library/puae/)

