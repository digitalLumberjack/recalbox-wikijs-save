---
title: Libretro PCSX-ReARMed
---

# Libretro PCSX-ReARMed

[Libretro PCSX-ReARMed](https://github.com/libretro/pcsx_rearmed) est un fork de [PCSX-ReARMed](https://github.com/notaz/pcsx_rearmed) basé sur le projet PCSX-Reloaded.  
Cette version est orientée pour une architecture ARM et a été créé pour d'améliorer les performances sur l'ordinateur de poche Pandora.  
Cet émulateur a ensuite été porté sur d'autres appareils comme le Raspberry Pi.

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/pcsx_rearmed/blob/master/COPYING).

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC x86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Redémarrage | ✔ |
| Sauvegardes | ✔ |
| Sauvegarde d'état | ✔ |
| Options du core | ✔ |
| Cheats RetroArch | ✔ |
| Contrôles | ✔ |
| Remapping | ✔ |
| Vibration | ✔ |
| Contrôle de disque | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/tqfp32.svg) BIOS

### Liste des bios obligatoires

Bien que certains jeux puissent démarrer sans bios sous _PCSX-ReARMed,_ il est fortement conseillé d'ajouter ces fichiers dans le répertoire des bios afin d'améliorer les performances de l'émulateur et la gestions des sauvegardes sur les cartes mémoires "virtuelles".

<table>
  <thead>
    <tr>
      <th style="text-align:center"><b>Nom de fichier</b>
      </th>
      <th style="text-align:left">Description</th>
      <th style="text-align:center">MD5</th>
      <th style="text-align:center">Fourni</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">scph101.bin</td>
      <td style="text-align:left">Version 4.4 03/24/00 A</td>
      <td style="text-align:center">6e3735ff4c7dc899ee98981385f6f3d0</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">scph7001.bin</td>
      <td style="text-align:left">Version 4.1 12/16/97 A</td>
      <td style="text-align:center">1e68c231d0896b7eadcad1d7d8e76129</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">scph5501.bin</td>
      <td style="text-align:left">Version 3.0 11/18/96 A</td>
      <td style="text-align:center">490f666e1afb15b7362b406ed1cea246</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">scph1001.bin</td>
      <td style="text-align:left">Version 2.0 05/07/95 A</td>
      <td style="text-align:center">
        <p>dc2b9bf8da62ec93e868cfd29f0d067d</p>
        <p>924e392ed05558ffdb115408c263dccf</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
  </tbody>
</table>

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒 **scph101.bin**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **scph7001.bin**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **scph5501.bin**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **scph1001.bin**  

## \*\*\*\*![](/migration-images/emulateurs/consoles-de-salon/playstation-1/rom-30098_640.png) **Roms**

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .img/.ccd/.sub
* .mdf/.mts
* .pbp
* .bin/.toc
* .cbn
* .m3u

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

### Extension `.bin` : cas particulier

Les fichiers roms avec l'extension `.bin` sont également supportés mais nécessitent un fichier `.cue` pour être démarrés.

### Extension `.cue` : comment ça marche ?

Un fichier `.cue` est, tout simplement, un fichier texte dont l'extension a été transformée de `.txt` à `.cue` . Il doit porter le même nom que le fichier `.bin` qu'il accompagne et il contient les informations nécessaires au lancement du fichier `.bin` .

#### Exemple avec un jeu "simple" `.bin`

Le jeu suivant est composé de 1 fichier `.bin` et `.cue` :  
  
`Tony Hawk's Pro Skater 2 (France).bin  
Tony Hawk's Pro Skater 2 (France).cue`

Le fichier `Tony Hawk's Pro Skater 2 (France).cue` contient les informations suivantes :  
  
`FILE "Tony Hawk's Pro Skater 2 (France).bin" BINARY  
    TRACK 01 MODE2/2352  
        INDEX 01 00:00:00`

#### Exemple avec un jeu "multi" `.bin`

Le jeu suivant est composé de plusieurs fichiers `.bin` et d'un fichier `.cue` :  
  
`Tomb Raider II - Starring Lara Croft (France) (Track 01).bin  
Tomb Raider II - Starring Lara Croft (France) (Track 02).bin  
Tomb Raider II - Starring Lara Croft (France) (Track 03).bin  
Tomb Raider II - Starring Lara Croft (France).cue`

Le fichier `Tomb Raider II - Starring Lara Croft (France).cue` contient les informations suivantes :  
  
`FILE "Tomb Raider II - Starring Lara Croft (France) (Track 01).bin" BINARY  
    TRACK 01 MODE2/2352  
        INDEX 01 00:00:00  
FILE "Tomb Raider II - Starring Lara Croft (France) (Track 02).bin" BINARY  
    TRACK 02 AUDIO INDEX 00 00:00:00  
        INDEX 01 00:02:00  
FILE "Tomb Raider II - Starring Lara Croft (France) (Track 03).bin" BINARY  
    TRACK 03 AUDIO INDEX 00 00:00:00   
        INDEX 01 00:02:00`

#### Je n'ai pas le fichier `.cue`, comment je fais ?

 Si vous n'avez qu'un fichier `.bin`et aucun fichier .`cue`, vous pouvez le générer de plusieurs manière :

* En ligne : [http://nielsbuus.dk/pg/psx\_cue\_maker/](http://nielsbuus.dk/pg/psx_cue_maker/)
* Avec ce logiciel freeware : [CueMaker](https://github.com/thorst/CueMaker/releases/)

Vous pouvez aussi l'obtenir [auprès de Redump](http://redump.org/cues/psx/).

### Extension `.m3u` : gérer les jeux multi-CD

Plusieurs CD d'un même jeu peuvent être chargés simultanément depuis EmulationStation dans RetroArch en créant un fichier "liste de lecture" `.m3u` \(texte brut `.txt` avec une extension `.m3u`\).


>Une liste de lecture .m3u peut être utilisé uniquement avec des jeux qui ont **un fichier `.cue` et un seul `.bin` par disque**.
>Tous jeu multi-disques qui a plusieurs fichiers `.bin` pour un seul disque ne fonctionnera pas \(Il est conseillé de convertir ces disques pour obtenir un fichier `.bin` unique\).
{.is-danger}

1.  Renommer les fichiers `.cue` de chaque disque du jeu avec l'extension appropriée `.CD1`, `.CD2`, etc... afin que EmulationStation ne liste que les fichiers `.m3u`et non tous les disques individuels.  
  
   Exemple avec Final Fantasy VII :  
  
   `Final Fantasy VII (France) (Disc 1).bin  
   Final Fantasy VII (France) (Disc 1).cue --┣ Final Fantasy VII (France) (Disc 1).cd1`

   `Final Fantasy VII (France) (Disc 2).bin  
   Final Fantasy VII (France) (Disc 2).cue --┣ Final Fantasy VII (France) (Disc 2).cd2`

   `Final Fantasy VII (France) (Disc 3).bin  
   Final Fantasy VII (France) (Disc 3).cue --┣ Final Fantasy VII (France) (Disc 3).cd3`  
   

2. Créer un nouveau fichier texte que l'on nomme `Final Fantasy VII (France).m3u` et qui contient les informations suivantes :  `Final Fantasy VII (France) (Disc 1).cd1 Final Fantasy VII (France) (Disc 2).cd2 Final Fantasy VII (France) (Disc 3).cd3`


>Cette manipulation fonctionne aussi avec les jeux multi-CD composés de fichiers `.chd` \(il n'y a pas de `.cue` dans ce cas\).  
┣    
>Exemple :  
┣    
>`Final Fantasy VII (France) (Disc 1).chd --┣ Final Fantasy VII (France) (Disc 1).cd1  
>Final Fantasy VII (France) (Disc 2).chd --┣ Final Fantasy VII (France) (Disc 2).cd2  
>Final Fantasy VII (France) (Disc 3).chd --┣ Final Fantasy VII (France) (Disc 3).cd3  
┣    
>Final Fantasy VII (France).m3u`  
┣    
>Le fichier `Final Fantasy VII (France).m3u` sera identique à l'exemple précédent.
{.is-info}

Avec cette configuration, EmulationStation lancera automatiquement le CD1 à chaque lancement du jeu.

#### Changer de disque en cours de partie

Si l'on a besoin de changer de disque lorsque le jeu est lancé, il faut réaliser les actions suivantes :

1. Ouvrir le tiroir CD "virtuel" : `Touche HK + Joystick Gauche (Direction Haut)`
2. Changer de disque : `Touche HK + Joystick Gauche (Direction Droite ou Gauche)`
3. Fermer le tiroir CD "virtuel" : `Touche HK + Joystick Gauche (Direction Haut)`

### **Emplacement**

Placer vos roms Playstation dans le dossier : `/recalbox/share/roms/psx`

## ![](/migration-images/emulateurs/consoles-de-salon/playstation-1/hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour., nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
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

## \*\*\*\*![](/migration-images/emulateurs/consoles-de-salon/playstation-1/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes**

* **Github utilisé** : [https://github.com/libretro/pcsx\_rearmed/](https://github.com/libretro/pcsx_rearmed/)
* **Doc Libretro** : [https://docs.libretro.com/library/pcsx\_rearmed/](https://docs.libretro.com/library/pcsx_rearmed/)

