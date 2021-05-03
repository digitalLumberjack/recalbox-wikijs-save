---
title: Surcharge de configuration
description: >-
  Description des surcharges locales de configurations appliquées à des jeux en
  particulier ou a des repertoires complets.
---

# Surcharge de configuration


>**Recalbox 7.0 et supérieur!**
{.is-warning}

## Aperçu des possibilités

A partir de Recalbox 7.0, vous pouvez surcharger les configuration d'un jeu ou d'un répertoire complet.

Ça signifie qu'en ajoutant des fichiers particuliers dans vos répertoires de roms, vous allez pouvoir modifier le comportement de Recalbox, de Retroarch ou de l'émulateur pour un jeu particulier ou pour tous les jeux d'un répertoire.

Concrètement, vous allez pouvoir agir sur:

* La configuration de Recalbox
* La configuration générale de Retroarch
* La configuration des cores Retroarch

Accessoirement, vous aurez également la possibilité de surcharger les images et les descriptions des répertoires de roms tels qu'ils sont affichés dans EmulationStation, nous verrons pourquoi un peu plus loin.

Pêle-mêle, on va pouvoir, pour un jeu ou un ensemble de jeux:

* Définir un émulateur ou un core particulier
* Définir une résolution vidéo particulière
* Modifier la configuration vidéo de Retroarch
* Modifier les options des cores
* etc.

## Généralités

Les surcharges vont s'appliquer sur un fichier de base. Ces fichiers sont les fichiers qui sont chargés en tout premier lieu par le lanceur python \(appelé **configgen**\) lorsqu'on lance un jeu:

| Cible | Fichier de configuration |
| :--- | :--- |
| **Recalbox** | `/recalbox/share/system/recalbox.conf` |
| **Retroarch** | `/recalbox/share/system/configs/retroarch/retroarchcustom.cfg.origin` |
| **Cores** | `/recalbox/share/system/configs/retroarch/cores/retroarch-core-options.cfg` |

Tous les fichiers de configuration que l'on peut surcharger sont des fichiers de type clefs/valeurs.  
On va donc pouvoir modifier la valeur d'une clefs de la configuration de base, ou définir une clef inexistante.

Nous pourrons même surcharger les surcharges! En effet le système permet de définir une surcharge par niveau de répertoires.  
  
Il va donc commencer par charger la configuration de base, puis appliquer successivement tous les fichiers de surcharge qu'il trouvera dans les répertoires, en commençant à la racine. Puis au final, il tentera d'appliquer la surcharge du jeu, si elle existe.



Prenons un exemple, si on lance le jeu `/recalbox/share/roms/snes/platform/Aladdin (France).zip`, le **configgen** cherchera à surcharger la configuration retroarch, en chargeant dans l'ordre:

1. `Base: /recalbox/share/system/configs/retroarch/retroarchcustom.cfg`
2. `Path: /.retroarch.cfg`
3. `Path: /recalbox/.retroarch.cfg`
4. `Path: /recalbox/share/.retroarch.cfg`
5. `Path: /recalbox/share/roms/.retroarch.cfg`
6. `Path: /recalbox/share/roms/snes/.retroarch.cfg`
7. `Path: /recalbox/share/roms/snes/platform/.retroarch.cfg`
8.    `File: /recalbox/share/roms/snes/platform/Aladdin (France).zip.retroarch.cfg`

Bien entendu, il n'est pas vraiment conseillé de surcharger les configuration avant d'atteindre au minimum le répertoire d'un système.

Vous remarquerez que pour surcharger un répertoire, les fichiers de surcharge doivent se trouver **à l’intérieur** du répertoire, et commencer par un point \(.\), ce qui les rend invisible pour le système linux.  
  
A contrario, la surcharge d'un jeu, doit être nommé exactement comme le jeu, **extension de fichier comprise**, suivit du suffixe de surcharge, `.retroarch.cfg` dans l'exemple au dessus


>Étant donné que les fichiers de surcharges se trouvent à l’intérieur de vos répertoires de roms, ils ne craignent pas un plantage de Recalbox, une mise à jour qui se serait mal passé, ou un crash de votre SD \(à condition d'utiliser un support externe bien entendu
>
>Ils sont en outre transportables : Prenez votre clef USB avec vous pour jouer chez un ami, votre configuration s'appliquera sans rien devoir toucher !
{.is-info}

## Surcharger Recalbox

Surcharger la configuration Recalbox présente deux intérêts immédiats :

* Pouvoir sélectionner un mode vidéo particulier pour un jeu ou un ensemble de jeux. Les aficionados du pixel perfect en arcade seront ravis.
* Pouvoir choisir un core ou un émulateur standalone pour un jeu ou un ensemble de jeux.

Il existe d'autres possibilité, et nul doute que vous en trouverez 😉 


>Surcharger des clefs qui ne sont pas utilisées par le **configgen** n'a aucun effet ! N’espérez pas modifier le comportement d'EmulationStation \(en surchargeant les tris par exemple\).
{.is-danger}


>Rappel:  
>Surcharge répertoire: **`/path/to/your/roms/.recalbox.conf`**  
>Surcharge rom: **`/path/to/your/roms/file.zip.recalbox.conf`**
{.is-warning}



### Exemple 1: Multiple versions de MAME

Pourquoi se contenter d'une seule version de MAME alors que nous pourrions toutes les avoir.

Par exemple, vous pourriez avoir MAME 2003 Plus et MAME 2010, chaque romset dans son propre répertoire:  
  
`/recalbox/share/roms/mame/  
 ├── MAME2003Plus  
 └── MAME2010`



Il suffit alors d'ajouter le fichier :

{% code title="/recalbox/share/roms/mame/MAME2003Plus/.recalbox.conf" %}
```text
mame.emulator=libretro
mame.core=mame2003_plus
```
{% endcode %}



Et le fichier :

{% code title="/recalbox/share/roms/mame/MAME2010/.recalbox.conf" %}
```text
mame.emulator=libretro
mame.core=mame2010
```
{% endcode %}


>Et voilà! C'est tout. Désormais, tous les jeux du répertoire MAME2003Plus se lanceront avec le core mame2003\_plus-libretro, et ceux du repertoire MAME2010 avec le core mame2010-libretro!
{.is-success}



### Exemple 2: Affecter un core particulier à un jeu

Mon jeu `/recalbox/share/pcengine/1943 Kai (Japan).zip` fonctionne mieux avec le core `mednafen_pce_fast_libretro` qu'avec le core `mednafen_supergrafx_libretro` par défaut \(hypothèse totalement arbitraire pour l'exemple\).

Jusqu'à présent, il était possible de le faire via EmulationStation, en éditant les metadata du jeu. L'information est alors stockée dans le fichier `gamelist.xml`. Une erreur d'écriture du fichier, un scrappe malencontreux, et c'est toute la configuration qui est perdue.

Ici il suffit d'ajouter le fichier:

{% code title="/recalbox/share/roms/pcengine/1943Kai\(Japan\).zip.recalbox.conf" %}
```text
global.emulator=libretro
global.core=mednafen_pce_fast
```
{% endcode %}


>Cette fois, pas de risque de perte de la configuration !  
>Bien entendu, éditer les metadata via EmulationStation fonctionne toujours. En revanche, un fichier de surcharge sera prioritaire sur ce qui est stocké dans le `gamelist.xml`.
{.is-success}



### Exemple 3: Modifier le mode vidéo pour un jeu

Sur mon Raspberry Pi2, le mode vidéo par défaut est CEA 4 HDMI. Mais sur le jeu **`Blazing Stars`** sur **FinalBurn Neo**, tourne un peu lentement. Le passer en 240p aiderait certainement, en plus d'être pixel-perfect ! \(encore une fois, hypothèse tout à fait hypothétique, juste pour l'exemple\)

{% code title="/recalbox/share/roms/fba\_libretro/blazstar.zip.recalbox.conf" %}
```text
global.videomode=CEA 8 HDMI
```
{% endcode %}


>Et voilà ! Lorsque je lance ce jeux là, ma TV commute en 240p, et je peux pleinement profiter de Blazing Stars.
{.is-success}

## Surcharger Retroarch

Les configurations Retroarch concernent Retroarch lui même \(et les options de configurations sont très nombreuses !\) ainsi que les différents cores, qui ont chacun des options particulières en fonction des machines qu'ils émulent.


>Il existe déjà des mécanismes propres à Recalbox et à Retroarch pour surcharger soit la ligne de commande qui lance l’émulateur \(via Recalbox.conf\), soit directement les configurations Retroarch/Cores \(via les menus de Retroarch\)
>
>Mais aucun de ces systèmes ne permettait d'appliquer les surcharges à des répertoires entiers et/ou de conserver ces configurations spécifiques au même endroit que les roms. Ce qui est particulièrement intéressant pour les gens qui utilisent des partages réseaux pour alimenter en roms plusieurs Recalbox !
{.is-info}



### Configuration de Retroarch

La configuration Retroarch elle même est extrêmement riche, et couvre énormément de domaines différents.

Il est inutile de s’étendre sur la question, le mieux est d'aller voir directement dans le fichier de RetroArch, qui est particulièrement bien documenté : [https://github.com/libretro/RetroArch/blob/master/retroarch.cfg](https://github.com/libretro/RetroArch/blob/master/retroarch.cfg)

Les possibilités offertes par les surcharges locales sont énormes, parmi lesquelles on peut compter :

* Configuration vidéo : Ratio, Échelle, Anti-alias, rotation d'écran, ou même sélections de shaders, etc.
* Tuning de l'audio pour certains jeux difficiles
* Overlays
* Certaines options concernant les inputs : sélection souris, sensibilité, etc.
* Forcer des configurations NetPlay particulières
* Changer les répertoires Retroarch \(sauvegarde par exemple\)
* Régler divers options : Rembobinage, Avance rapide, etc.
* ...

A l'instar des surcharges de configuration Recalbox, on va pouvoir créer des fichiers `.retroarch.cfg` pour les répertoires et pour les roms.


>**Rappel :**  
>Surcharge répertoire: **`/path/to/your/roms/.retroarch.cfg`**  
>Surcharge rom: **`/path/to/your/roms/file.zip.retroarch.cfg`**
{.is-warning}

#### Exemple 1: Forcer une configuration vidéo

#### Exemple 2: Forcer une shader pour un répertoire complet



### Configuration des Cores

Surcharger les options des cores offre d'énormes possibilités, _**parmi lesquelles une fonctionnalité très attendues des fans "d'ordinausaures": La possibilité de définir un répertoire par sous système !**_


>Les surcharges de cores sont ajoutées au fichier _share/system/configs/retroarch/cores/retroarch-core-options.cfg_ au lancement du jeu concerné, cela implique que, une fois le jeu fermé, **elles seront sauvegardées dans ce même fichier**, pour éviter toute mauvaise surprise, nous recommandons de surcharger les clés dans le dossier avec des valeurs par défaut \(par exemple `fbneo-frameskip = "0"`\) si vous tenez à surcharger un jeu en particulier avec des valeurs spécifiques \(par exemple `fbneo-frameskip = "2"`\), ainsi vous conserverez vos valeurs "de base" pour les fichiers n'ayant pas de surcharges personnalisées.
{.is-danger}

C'est particulièrement intéressants pour les cores multi-machines, comme:

* **theodore**, qui couvre les Thomson MO5, MO6 et TO7 jusqu'au TO9+ 
* **atari800**, qui couvre tous les Atari 8bits, de la première serie 800, jusqu'aux XE, en passant par les XL. 
* **vice**, qui émule maintenant le C64, le PET, le Vic20, le CBM2, ... 
* **hatari**, qui émule du premier 520ST aux derniers Falcons 
* et d'autres encore...


>**Rappel :**  
>Surcharge répertoire: **`/path/to/your/roms/.core.cfg`**  
>Surcharge rom: **`/path/to/your/roms/file.zip.core.cfg`**
{.is-warning}



#### Exemple 1: Configurer des sous-systèmes Thomson

Les Thomson, ordinateurs français 8bits des années 80, se sont scindés en 2 séries : 

* Les MO, qui ont donné le premier MO5, puis plus tard le MO6 avec son clavier mécanique et son lecteur de cassette intégré 
* Les TO, qui ont donné les premiers TO7 et TO7-70, puis plus tard les TO8 et TO8D, avec lecteurs de disquettes, et la série des TO9 et TO9+, ordinateurs aux looks plus professionnels

Les jeux MO et TO ne sont pas du tout compatibles. Au sein d'une même série, il y a compatibilité ascendante : Un MO6 fera tourner \(en général\) les jeux du MO5.  
  
Bien entendu, on cherchera à émuler chaque jeu avec la machine la plus proche de la machine pour laquelle il a été conçu à l'origine, afin d’éviter tout problème et maximiser les chance d'avoir une émulation parfaite.

Si l'on prend les packs TOSEC \([http://www.tosec.org](https://www.tosecdev.org/)\), les jeux Thomson on été répartis en 4 sous-systèmes :

* MO5
* MO6
* TO7 \(TO7-70\)
* TO8, TO8D, TO9 et TO9+

Nous allons donc créer une arborescence similaire:

`recalbox/share/roms/thomson/  
 ├── MO5  
 ├── MO6  
 ├── TO7  
 └── TO8,TO8D,TO9,TO9+`

Dans la racine du système, nous allons placer un fichier de surcharge core, pour forcer quelques options intéressantes pour tout le monde :

{% code title="/recalbox/share/roms/thomson/.core.cfg" %}
```text
theodore_rom = "Auto"
theodore_autorun = "enabled"
theodore_floppy_write_protect = "enabled"
theodore_tape_write_protect = "enabled"
```
{% endcode %}

Si on rajoute des jeux dans la racine, ou dans un autre répertoire, on indique à l’émulateur d'essayer de détecter la meilleure machine \(en se basant sur le nom du fichier\).  
  
On protège aussi les fichiers roms par défaut, et on enclenche la mécanique d'autorun bien pratique quand on ne connait pas trop les machines d'origine.

Ensuite dans chaque sous-répertoire, on va ajouter une surcharge sur le clef `theodore_rom` qui détermine la machine.

{% code title="/recalbox/share/roms/thomson/MO5/.core.cfg" %}
```text
theodore_rom = "MO5"
```
{% endcode %}

{% code title="/recalbox/share/thomson/MO6/.core.cfg" %}
```text
theodore_rom = "MO6"
```
{% endcode %}

{% code title="/recalbox/share/thomson/TO7/.core.cfg" %}
```text
theodore_rom = "TO7"
```
{% endcode %}

{% code title="/recalbox/share/thomson/TO8,TO8D,TO9,TO9+.core.cfg" %}
```text
theodore_rom = "TO9+"
```
{% endcode %}

Pour la dernière série, la machine la plus puissante a été sélectionnée : le TO9+


>C'est terminé! Vous avez maintenant 4 sous systèmes Thomson. L’émulateur n'est plus en automatique et le risque de le voir choisir le mauvais système ou un système par défaut disparaît.
>
>Bien entendu, le core Theodore peut parfois "auto-détecter" la machine, mais ce n'est pas le cas avec d'autres cores qui ont besoin d'avoir le bon sous-système au lancement.
{.is-success}

## Surcharger l'aspect des répertoires

Pour parfaire les possibilités offertes par la définitions de sous-systèmes, que ce soit en surchargeant la configuration Recalbox pour **MAME** par exemple, ou en surchargeant le core **Théodore** pour pleinement profiter des machines TO et MO de l'époque, nous avons ajouté le possibilité de surcharger l'image et la description d'un répertoire.

Ceci permet par exemple, d'avoir sur un répertoire, la photo et la description de la machine dont les roms se trouvent dans le-dit repertoire.

Il suffit pour ça d'ajouter au minimum, un fichier image au format **PNG**, et nommé `.folder.picture.png` dans le répertoire dont on veut surcharger l'image dans EmulationStation  
La résolution importe peu, mais gardez à l'esprit qu'une resolution identique ou approchante à vos images de _scrappe_ reste recommandée.

Optionnellement, vous pouvez ajouter une description texte, qui se glissera sous l'image, exactement comme pour les jeux _scrappés_.  
Le fichier doit être un fichier texte simple, nommé `.folder.description.txt`


>**Rappel :**  
>Surcharge image: **`/path/to/your/folder/.folder.picture.png`**  
>Surcharge description: **`/path/to/your/roms/.folder.description.txt`**
{.is-warning}



### Exemple 1: du MO5 au TO9

Reprenons le répertoire **thomson** utilisé plus haut, que nous avions découpé en 4 sous-systèmes comme l'a fait **TOSEC**.

`/recalbox/share/roms/thomson/  
 ├── .core.cfg  
 ├── gamelist.xml  
 ├── media  
 │ ├── box3d  
 │ ├── images  
 │ └── videos  
 ├── MO5  
 │ ├── .core.cfg  
 │ ├── .folder.description.txt  
 │ ├── .folder.picture.png  
 │ ├── [FD]  
 │ ├── [K7]  
 │ ├── [M5]  
 │ ├── [QD]  
 │ ├── [SAP]  
 │ └── [WAV]  
 ├── MO6  
 │ ├── .core.cfg  
 │ ├── .folder.picture.png  
 │ ├── .folder.description.txt  
 │ └── [K7]  
 ├── TO7  
 │ ├── .core.cfg  
 │ ├── .folder.picture.png  
 │ ├── .folder.description.txt  
 │ ├── [K7]  
 │ └── [M7]  
 └── TO8, TO8D, TO9, TO9+  
   ├── .core.cfg  
   ├── .folder.picture.png  
   ├── .folder.description.txt  
   ├── [FD]  
   ├── [K7]  
   ├── [QD]  
   └── [SAP]`



Le fichier `.folder.picture.png` du répertoire /recalbox/share/roms/thomson contient une image de la machine:

![Photo MO5](/migration-images/usage-avance/surcharge-de-configuration/.folder.picture.png)



Et le fichier `.folder.description.txt` contient:

{% code title="/recalbox/share/roms/thomson/MO5/.folder.description.txt" %}
```text
Brand:
    - Thomson (France)
CPU:
    - Motorola 6809E running at 1 MHz
RAM:
    - 48Kb (extensible)
ROM:
    - 16Kb
Graphics:
    - Text mode : 40 columns x 25 lines
    - Graphic mode: 320 x 200, 16 colors (proximity constraint)
Sound:
    - 1bit generator (6bit DAC module extention possible)
Input devices:
    - 57 keys integrated keyboard
    - Optical pen
    - Joysticks
Interfaces:
    - External power supply
    - DIN Connector (optical pen)
    - DIN Connector (tape drive)
    - Peritel (RGB)
    - Extension port
Software:
    - BASIC 1.0 Integrated
Standard devices:
    - Cartridge port (Mémo5)
    - External tape drive (MO5 specific model)
    - External disk drive
Dimensions:
    - 51 x 291 x 190 mm 
Weight:
    - 1.1 kg
Released:
    - 1984
    
```
{% endcode %}



Et voilà le résultat dans EmulationStation:

![EmulationStation](/migration-images/usage-avance/surcharge-de-configuration/capture-du-2019-09-07-11-52-59.png)



### Exemple 2: MAME

De la même façon, sur le premier exemple qui montre comment avoir plusieurs versions de **MAME** dans le répertoire MAME, nous pourrions imaginer avoir un joli logo MAME 2003 Plus et MAME 2010, suivit d'un petit texte qui donne le nombre de jeu, et la version du romset de MAME correspondante.



Un petit logo:

![/recalbox/share/roms/mame/MAME2003Plus/.folder.description.txt](/migration-images/usage-avance/surcharge-de-configuration/.folder.picture%20%281%29.png)



Un petit texte :

{% code title="/recalbox/share/roms/mame/MAME2003Plus/.folder.description.txt" %}
```text
MAME 2003 Plus est une version améliorée de MAME2003, avec énormement de correction de bug et des centaines de nouveaux jeux.

RomSet Special basé sur le romset MAME 0.78

4859 jeux au total!
```
{% endcode %}



Et voila le résultat :

![](/migration-images/usage-avance/surcharge-de-configuration/sans-titre%20%281%29.png)

## Emulateurs "Standalone"

Actuellement, nous ne pouvons pas surcharger les configuration des émulateurs standalone, hormis partiellement celles **d'Amiberry**, l’émulateur Amiga pour ARM.

Il n'est pas prévu d'ajouter ces surcharges, car elles demandent du code et des tests particuliers. Ce n'est en outre pas forcement faisable pour tous les émulateurs, mais dans tous les cas, ça demandera un travail plus ou moins long.

Cependant, en fonction des demandes et de leur pertinence, nous pourrons éventuellement voir au cas par cas.

