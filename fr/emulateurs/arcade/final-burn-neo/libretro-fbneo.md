---
title: Libretro FBNeo
---

# Libretro FBNeo

**FinalBurn Neo**, un émulateur pour les jeux d'arcade et certaines consoles. Il est basé sur les émulateurs FinalBurn et les anciennes versions de [MAME](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&pto=aue&rurl=translate.google.com&sl=auto&sp=nmt4&tl=fr&u=https://www.mamedev.org/&usg=ALkJrhjL5Yb9Jg7_b8C5_KyBfDfO-WpD1A) \(émulant moins de bornes d'arcade\) mais il fonctionne suivant les mêmes principes.

FB Neo \(a.k.a. FinalBurn Neo\) est un émulateur d'arcade qui supporte les plateformes suivantes :

* Capcom CPS-1
* Capcom CPS-2
* Capcom CPS-3
* Cave
* Data East DEC-0, DEC-8, Cassette System, DECO IC16 and DECO-32 based games
* Galaxian based hardware
* Irem M62, M63, M72, M90, M92 and M107 hardware
* Kaneko 16
* Konami
* Namco Mappy, System 86, System 1 & 2 and others
* Neo-Geo
* NMK16
* Pacman based hardware
* PGM
* Psikyo 68EC020 and SH-2 based hardware
* Sega System 1, System 16 \(and similar\), System 18, X-Board and Y-Board
* Seta-Sammy-Visco \(SSV\) based hardware
* Super Kaneko Nova System
* Toaplan 1
* Toaplan 2
* Taito F2, F3, X, Z and others
* Divers pilotes pour d'autres matériels
* FB Neo contient aussi des pilotes en cours de travail pour les système suivants :
  * Sega Megadrive/Genesis
  * ColecoVision
  * Sega SG-1000
  * Sega Master System
  * Game Gear
  * MSX-1
  * ZX Spectrum
  * PC-Engine
  * TurboGrafx 16
  * SuperGrafx.

## \*\*\*\*![](./gerald-g-parchment-background-or-border-5.svg)**Licence**

Ce core est sous licence [**non commerciale**](https://github.com/finalburnneo/FBNeo/blob/master/src/license.txt).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | ✔ |
| RetroAchievements | ✔ |
| RetroArch Cheats | ✔ |
| Native Cheats | ✔ |
| Controllers | ✔ |
| Multi-Mouse | ✔ |
| Subsystem | ✔ |

## ![](./tqfp32.svg)Bios

### Liste des bios

En fonction des jeux, certains bios seront nécessaires et seront à placer dans le même répertoire que les jeux.

### **Emplacement**

Placez les **bios** comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁 fbneo
> > > >
> > > > > 🗒 bios.zip

## ![](./rom-30098_640.png)**Roms**

### Extensions supportées

Tous les jeux FinalBurn Neo utilisent les jeux au formats suivants :

* .fba
* .zip
* .7z

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁fbneo
> > > >
> > > > > 🗒**fichier.zip**

### Dat

Utilisez clrmamepro \(qui fonctionne bien sur linux avec wine et sur mac avec crossover\) pour créer des romsets valides avec des données à partir du répertoire [dats](https://github.com/libretro/FBNeo/tree/master/dats) .  
Ne signalez pas les problèmes si vous n'avez pas créé de romset valide.  
De plus, seul les dat "parent seulement" sont fournis, car il n'est pas recommander d'utiliser uniquement des roms parent \(certains ne fonctionnent pas et certains clones sont vraiment différents de leur parent\).

### Émuler des consoles

Vous pouvez émuler des consoles \(avec des romsets spécifiques, les dats sont également dans le répertoire [dats](https://github.com/libretro/FBNeo/blob/master/dats)\) en préfixant le nom des roms avec `XXX_`et en supprimant l' `zip|7z`extension, ou en utilisant l' `--subsystem XXX`argument de la ligne de commande, voici la liste des préfixes disponibles:

* CBS ColecoVision: `cv`
* MSX 1: `msx`
* Nec PC-Engine: `pce`
* Nec SuperGrafX: `sgx`
* Nec TurboGrafx-16: `tg`
* Nintendo Entertainment System: `nes`
* Nintendo Family Disk System: `fds`
* Sega GameGear: `gg`
* Système maître Sega: `sms`
* Sega Megadrive: `md`
* Sega SG-1000: `sg1k`
* Poche SNK Neo-Geo: `ngp`
* Spectre ZX: `spec`

Il est également possible d'utiliser le nom du dossier pour la détection \(cette deuxième méthode a été ajoutée car certains appareils ne sont pas compatibles avec les sous-systèmes\):

* CBS ColecoVision: `coleco`
* MSX 1: `msx`
* Nec PC-Engine: `pce`
* Nec SuperGrafX: `sgx`
* Nec TurboGrafx-16: `tg16`
* Nintendo Entertainment System: `nes`
* Nintendo Family Disk System: `fds`
* Sega GameGear: `gamegear`
* Système maître Sega: `sms`
* Sega Megadrive: `megadriv`
* Sega SG-1000: `sg1000`
* Poche SNK Neo-Geo: `ngp`
* Spectre ZX: `spectrum`

## ![](./hammer-28636_640.png)Configuration avancée des émulateurs


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/v/francais/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder aux options

Vous pouvez configurer diverses options de deux façons différentes.

* Via le Menu RetroArch :

> 📁Menu RetroArch
>
> > 📁Options du core
> >
> > > 🧩Name\_option

* Via le fichier `retroarch-core-options.cfg`:

> 📁recalbox
>
> > 📁share
> >
> > > 📁system
> > >
> > > > 📁configs
> > > >
> > > > > 📁retroarch
> > > > >
> > > > > > 📁cores
> > > > > >
> > > > > > > 🧩**retroarch-core-options.cfg**

### Options du core

### Sample

Les échantillons doivent être placés sous `SYSTEM_DIRECTORY/fbneo/samples`

### Hiscore.dat

Copiez [hiscore.dat](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&pto=aue&rurl=translate.google.com&sl=auto&sp=nmt4&tl=fr&u=https://github.com/libretro/FBNeo/blob/master/metadata/hiscore.dat&usg=ALkJrhhLOOX0Q7fJfbQ3IYe5E2T1bgBobQ) dans`SYSTEM_DIRECTORY/fbneo/`

### MAPPING

Nous n'avons pas d'outil pratique comme l'OSD MAME, mais nous utilisons l'API RetroArch pour personnaliser les mappages, vous pouvez le faire en allant dans `Quick menu > Controls`.  
Pour ceux qui ne souhaitent pas personnaliser entièrement leur mappage, il existe 2 préréglages pratiques que vous pouvez appliquer en changeant le "type d'appareil" pour un lecteur dans ce menu:

* **Classic/Classique** : il appliquera le mappage "carré" du cd neogeo original dans les jeux neogeo, et utilisera L / R comme 5ème et 6ème bouton pour les jeux à 6 boutons comme Street Fighter II.
* **Modern/Moderne** : il appliquera la cartographie King of Fighters de Playstation 1 et supérieure dans les jeux de combat neogeo, et il utilisera R1 / R2 comme 5ème et 6ème bouton pour les jeux à 6 boutons comme Street Fighter II \(pour la même raison que les jeux neogeo\) , c'est vraiment pratique pour la plupart des sticks d'arcade.

Les "types d'appareils" suivants existent également, mais ils ne seront pas compatibles avec tous les jeux:

* **Mouse \(ball only\)/Souris \(balle uniquement\)** : elle utilisera la souris / trackball pour les mouvements analogiques, les boutons resteront sur retropad
* **Mouse \(full\)/Souris \(pleine\)** : comme ci-dessus, mais les boutons seront sur la souris
* **Pointer/Pointeur** : il utilisera un dispositif "pointeur" \(peut être une souris / trackball\) pour déterminer les coordonnées à l'écran, les boutons resteront sur retropad
* **Lightgun** : il utilisera le lightgun pour déterminer les coordonnées à l'écran, les boutons seront également sur le lightgun.

## Faq

#### Le jeu XXX ne se lance pas, pourquoi?

Ce n'est pas supporté ou vous avez une mauvaise rom, vos logs vous donneront plus de détails. Créez un romset valide avec clrmamepro comme indiqué ci-dessus. Il y a aussi quelques jeux marqués comme ne fonctionnant pas, essayez l'un de leurs clones.



#### J'ai corrigé le jeu XXX et je ne peux pas l'exécuter, pourquoi?

Parce que c'est considéré comme une mauvaise rom car les crcs ne correspondront pas, cependant il existe une méthode pour utiliser un romset patché, si vous mettez la version patché du romset dans `SYSTEM_DIRECTORY/fbneo/patched`cela fonctionnera \(NB: vous pouvez le retirer de tout fichier qui ne pas différent des romset non patché si vous voulez\)

#### 

#### Le jeu XXX a des problèmes graphiques, pourquoi?

Rédigez un rapport avec des détails sur le problème et votre plateforme.

#### 

#### Le jeu XXX s'exécute lentement, pourquoi?

Votre matériel est probablement trop lent pour exécuter le jeu avec des paramètres normaux. Essayez ce qui suit:

* Vérifiez s'il y a un commutateur DIP Speedhack dans les options principales, réglez-le sur "Oui".
* Essayez de définir une valeur pour frameskip dans les options principales.
* Essayez de réduire l'horloge du processeur dans les options de base
* Essayez de désactiver le rembobinage, le runahead ou tout autre paramètre retroarch connu pour augmenter la surcharge.
* Essayez de réduire les paramètres audio dans les options principales.
* Si cela ne suffit pas, mettez à niveau / overclockez votre matériel ou utilisez un autre noyau.

Nous n'accepterons pas les demandes de "rendre le noyau plus rapide", en ce qui nous concerne, ce noyau a un bon équilibre entre précision et vitesse, et pour la plupart, il fonctionne déjà très bien sur des bras bon marché \(rpi3, .. .\).

#### 

#### Le jeu XXX a un son saccadé, pourquoi?

Très probablement pour la même raison que ci-dessus.

#### 

#### Le jeu XXX s'exécute plus rapidement dans MAME2003 / MAME2010, pourquoi?

Ce n'est pas MAME, nous utilisons généralement un code plus "à jour". Dans l'ensemble, FB Alpha est plus lent que l'ancienne version MAME mais plus précis et moins buggé. Ce port libretro prend également en charge diverses fonctionnalités qui sont généralement boguées ou absentes dans les cœurs MAME \(netplay, rembobinage, rétro-réalisations, ...\). Il peut utiliser des ressources supplémentaires.

#### 

#### Le code de triche ne fonctionne pas, pourquoi?

Il devrait y avoir un support partiel à travers la nouvelle API reposant sur l'exposition principale du ram.

#### 

#### Le CD Neogeo ne fonctionne pas, pourquoi?

Il y a plusieurs choses à savoir:

* Vous avez besoin d'une copie de neocdz.zip et neogeo.zip dans votre répertoire système libretro
* Vous devez ajouter `--subsystem neocd`à la ligne de commande ou placer vos jeux dans un `neocd`dossier
* Les formats pris en charge sont ccd / sub / img \(trurip\) et le fichier unique MODE1 / 2352 cue / bin \(utilisez des utilitaires comme "CDmage" pour convertir votre iso si nécessaire\), **ils ne doivent pas être compressés**

Vous pouvez convertir vos isos non pris en charge en suivant ce didacticiel:

* Obtenez [CDMage 1.02.1](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&pto=aue&rurl=translate.google.com&sl=auto&sp=nmt4&tl=fr&u=https://www.videohelp.com/software/CDMage&usg=ALkJrhiIi-9TZ8wTKlsje8X97w6ge-XfSQ) \(gratuit et sans publicité\)
* Fichier&gt; Ouvrir&gt; sélectionnez votre iso \(NB: pour le multi-piste, sélectionnez le fichier .cue, pas le fichier .iso\)
* Fichier&gt; Enregistrer sous&gt; écrivez le nom de votre nouveau fichier
* Assurez-vous de sélectionner MODE1 / 2352 dans le deuxième menu déroulant
* Appuyez sur OK, attendez la fin du processus \(quelques secondes sur mon ordinateur\), et c'est fait!

#### 

#### L'instinct de tueur ne fonctionnera pas, pourquoi?

Ce pilote a été désactivé pour l'instant, il ne répond pas à nos critères de qualité. ~~Il y a plusieurs choses à savoir:~~

* ~~Il ne fonctionne qu'à une vitesse jouable sur x86\_64 \(les autres arches auront essentiellement besoin d'un processeur à 4Ghz car elles manquent d'un dynarec mips3\), et le noyau doit être construit comme ceci pour activer ce dynarec: `make -j5 -C src/burner/libretro USE_X64_DRC=1`~~
* ~~Si votre rom est à `ROM_DIRECTORY/kinst.zip`, vous aurez besoin de l'image disque non compressée à`ROM_DIRECTORY/kinst/kinst.img`~~
* ~~Pour obtenir l'image du disque non compressé, vous devrez utiliser l'outil chdman de MAME sur le chd de mame, la commande ressemble à ceci: `chdman extracthd -i kinst.chd -o kinst.img`~~

#### 

#### Hiscore ne fonctionnera pas, pourquoi?

Avoir hiscore.dat et l'option de base activée ne garantit pas que ses scores fonctionneront pour un jeu spécifique, parfois un pilote manquera le code nécessaire. Vous pouvez demander une assistance dans le suivi des problèmes tant que la demande est raisonnable \(c'est-à-dire éviter de faire une liste de plusieurs dizaines / centaines de jeux\)

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github :** [https://github.com/libretro/FBNeo/tree/master](https://github.com/libretro/FBNeo/tree/master)
* **Doc Libretro :** [https://docs.libretro.com/library/fbneo/](https://docs.libretro.com/library/fbneo/)
* **Site Officiel :** [https://neo-source.com/](https://neo-source.com/)
* **Wiki du core :** [http://emulation.gametechwiki.com/index.php/FinalBurn\_Neo](http://emulation.gametechwiki.com/index.php/FinalBurn_Neo) ****[https://github.com/finalburnneo/FBNeo/wiki](https://github.com/finalburnneo/FBNeo/wiki)

