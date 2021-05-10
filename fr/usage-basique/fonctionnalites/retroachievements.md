---
title: Retroachievements
---

# Retroachievements

## **Challenge/Succès avec retroarch** <a id="challenge-succes-avec-retroarch"></a>

Le site internet [retroachievements.org](http://www.retroachievements.org/) propose **des challenges/succès/trophées** sur les plateformes tels que NES, SNES, GB, GBC, GBA, Megadrive/Genenis, PCengine etc...

## **Création d'un compte** <a id="creation-dun-compte"></a>

* **Vous devez** [créer un compte](http://retroachievements.org/createaccount.php) sur le site [retroachievements.org](http://www.retroachievements.org/). 
* **Noter votre pseudonyme** \(_Username_\) et **votre mot de passe** \(_password_\) dans un coin car ils vont servir à **configurer Retroachievements.**

## **Activation du compte dans Recalbox**

### **Activation du compte dans l'interface Emulationstation**

* **Ouvrir le menu** d'Emulationstation \(START\) 
* Aller dans **Options des jeux** 
* Puis **Options de Retroachievements** 
* **Éditer** comme ceci : `Retroachievements > ON`  `Nom Utilisateur > mettre votre pseudonyme`  `Mot de passe > votre mot de passe`

### **Activation du compte manuellement sous Recalbox**

Vous pouvez également l'activer manuellement \(inutile si vous l'avez via l'interface\).

Vous devez **éditer** le fichier **recalbox.conf :**

* **Via ssh** avec putty et le commande nano : `nano /recalbox/share/system/recalbox.conf`  ou  [winscp](/fr/tutoriels/systeme/acces/acces-reseau-via-winscp) avec l'éditeur Notepad++. ​
* **Ajout ses 3 lignes** en remplaçant pseudonyme et motdepasse par ceux créer lors de votre inscription.

```text
## Enable retroarchievements (0,1)
## Set your www.retroachievements.org username/password
## Escape your special chars (# ; $) with a backslash : $ => \$
global.retroachievements=1
global.retroachievements.hardcore=0
global.retroachievements.username=
global.retroachievements.password=
```


>_**Information :**_
>
>**Le mode** hardcore **désactive les fonctions** de rewind, crédit illimité etc...
{.is-info}

* **Sauvegarder** votre **recalbox.conf** 
* **Redémarrer** votre Recalbox.

## **Les émulateurs compatibles avec Retroachievements.** <a id="configuration-des-emulateurs-core-compatible-avec-retroachievements"></a>


>_**Remarques :**_
>
>**Tous les cores** Libretro **ne sont pas compatibles** avec **Retroachievements.**
{.is-warning}

Voici la **liste des emulateurs** qui fonctionnent avec **Retoachievements** :

| Systèmes | Core | Supporté | Notes |
| :---: | :---: | :---: | :---: |
| **Arcade - FBA Libtreto** | [FinalBurn Neo](https://github.com/libretro/FBNeo) |  | Le bios AES est requis pour la plupart des réalisations Neo Geo. AES Asia est généralement anglais. |
| **3DO** | [Opera](https://github.com/libretro/opera-libretro) |  |  |
| **32X / 32X CD** | [Picodrive](https://github.com/libretro/picodrive) |  | La qualité de l'émulation peut être douteuse. |
| **Atari 2600¶** | [Stella](https://github.com/libretro/stella-libretro) |  |  |
|  | [Stella 2014](https://github.com/libretro/stella2014-libretro) |  |  |
| **Atari 7800¶** | [ProSystem](https://github.com/libretro/prosystem-libretro) |  |  |
| **Atari Jaguar¶** | [Virtual Jaguar](https://github.com/libretro/virtualjaguar-libretro) |  | En raison de vastes problèmes de base, la prise en charge de ce système est extrêmement limitée. |
| **ColecoVision¶** | [SMS Plus GX](https://github.com/libretro/smsplus-gx) |  |  |
|  | [blueMSX](https://github.com/libretro/blueMSX-libretro) |  |  |
|  | [FinalBurn Neo](https://github.com/libretro/FBNeo) |  | Nécessite des jeux dans le sous-répertoire coleco, des archives exactes comme arcade. Tous les jeux peuvent ne pas être liés pour ce noyau. |
| **Game Boy / Game Boy Color¶** | [Gambatte](https://github.com/libretro/gambatte-libretro) |  |  |
|  | [SameBoy](https://github.com/libretro/SameBoy) |  | Précision la plus élevée, peut avoir des problèmes avec certains ensembles de réalisations pour le moment |
|  | [Gearboy](https://github.com/libretro/gearboy) |  |  |
|  | [VBA-M](https://github.com/libretro/vbam-libretro) |  | Supporte le gyroscope via des sticks analogiques |
|  | [mGBA](https://github.com/libretro/mgba) |  |  |
|  | [Mesen-S](https://github.com/SourMesen/Mesen-S) |  | Actuellement, le seul noyau pris en charge avec un support SGB complet. Prend également en charge GB et GBC sans SGB. |
| **Game Boy Advance** | [mGBA](https://github.com/libretro/mgba) |  |  |
|  | [VBA-M](https://github.com/libretro/vbam-libretro) |  |  |
|  | [VBA Next](https://github.com/libretro/vba-next) |  |  |
|  | [gpSP](https://github.com/libretro/gpsp) |  | Très haute vitesse, mais n'a pas été soigneusement testé avec des réalisations. Quelques jeux échoueront à démarrer ou planteront fréquemment. Veuillez préférer d'autres cœurs lorsque les performances de l'appareil le permettent. |
|  | [Beetle GBA](https://github.com/libretro/beetle-gba-libretro) |  | Noyau expérimental, ne doit pas être utilisé sans raison. |
| **Game Gear** | [Genesis Plus GX](https://github.com/libretro/Genesis-Plus-GX) |  |  |
|  | [SMS Plus GX](https://github.com/libretro/smsplus-gx) |  |  |
|  | [Gearsystem](https://github.com/drhelius/Gearsystem) |  |  |
| **Intellivision** | [FreeIntV](https://github.com/libretro/FreeIntv) |  | Les commandes impliquent une superposition à l'écran qui peut ne pas être facile à utiliser pour tous les jeux. |
| **Lynx** | [Beetle Lynx](https://github.com/libretro/beetle-lynx-libretro) |  |  |
|  | [Handy](https://github.com/libretro/libretro-handy) |  |  |
| **Master Sytem / Megadrive** | [Genesis Plus GX](https://github.com/libretro/Genesis-Plus-GX) |  |  |
|  | [BlastEm](https://github.com/libretro/blastem) |  |  |
|  | [Picodrive](https://github.com/libretro/picodrive) |  |  |
|  | [SMS Plus GX](https://github.com/libretro/smsplus-gx) |  |  |
|  | [Gearsystem](https://github.com/drhelius/Gearsystem) |  |  |
| **MSX** | [blueMSX](https://github.com/libretro/blueMSX-libretro) |  |  |
|  | [FinalBurn Neo](https://github.com/libretro/FBNeo) |  |  |
| **MSX2** | [blueMSX](https://github.com/libretro/blueMSX-libretro) |  |  |
|  | [FinalBurn Neo](https://github.com/libretro/FBNeo) |  |  |
| **Néo-Géo** | [FinalBurn Neo](https://github.com/libretro/FBNeo) |  | Le bios AES est requis pour la plupart des réalisations Neo Geo. AES Asia est généralement anglais. |
| **N64** | [Mupen64Plus-Next](https://github.com/libretro/mupen64plus-libretro) |  | Noyau préféré. Prend en charge une plus grande personnalisation graphique et mise à l'échelle. |
|  | [ParaLLEl N64](https://github.com/libretro/parallel-n64) |  | Prend en charge les jeux 64DD. Peut jouer à certains hacks en fonction d'une faible précision via des plugins alternatifs. |
| **N64DD** |  |  |  |
| **Neo Geo Pocket / Neo Geo Pocket Color¶** | [Beetle NeoPop](https://github.com/libretro/beetle-ngp-libretro) |  |  |
|  | [RACE](https://github.com/libretro/RACE) |  |  |
| **Nintendo DS** | [MelonDS](https://github.com/libretro/melonDS) |  | BIOS requis |
|  | [DeSmuME](https://github.com/libretro/desmume) |  | BIOS externe recommandé, doit être activé dans les options de base |
|  | [DeSmuME 2015](https://github.com/libretro/desmume2015) |  |  |
| **NES** | [FCEUmm](https://github.com/libretro/libretro-fceumm) |  |  |
|  | [Mesen](https://github.com/SourMesen/Mesen) |  |  |
|  | [QuickNES](https://github.com/libretro/QuickNES_Core) |  |  |
|  | [Mesen](https://github.com/SourMesen/Mesen) |  |  |
| **Odyssey 2** | [o2em](https://github.com/libretro/libretro-o2em) |  |  |
| **PC-Engine** | [Beetle PCE FAST](https://github.com/libretro/beetle-pce-fast-libretro) |  | Vitesse la plus élevée. Ne prend pas en charge les jeux SuperGrafx. |
|  | [Beetle SuperGrafx](https://github.com/libretro/beetle-supergrafx-libretro) |  | Grande vitesse. Prend en charge les jeux SuperGrafx. |
|  | [Beetle PCE](https://github.com/libretro/beetle-pce-libretro) |  | Haute précision, vitesse inférieure. Prend en charge les jeux SuperGrafx. |
|  | [FinalBurn Neo](https://github.com/libretro/FBNeo) |  | Nécessite des jeux dans les sous-répertoires pce, tg16 ou sgx, des archives exactes comme arcade. Tous les jeux peuvent ne pas être liés pour ce noyau. Le CD n'est pas pris en charge. |
| **PC-FX¶** | [Beetle PC-FX](https://github.com/libretro/beetle-pcfx-libretro) |  |  |
| **PC-8000** | [QUASI88](https://github.com/libretro/quasi88-libretro) |  | Certains jeux peuvent ne pas être pris en charge dans Retroarch en raison d'options manquantes. Les ensembles attendent généralement le bios MkIISR. Les jeux doivent être exécutés à partir des archives pour empêcher l'écrasement de la prise en charge des succès jusqu'à ce qu'un bogue soit corrigé. |
|  | [Beetle PSX HW](https://github.com/libretro/beetle-psx-libretro) |  | Identique à Beetle PSX, avec des fonctionnalités matérielles supplémentaires. Haute précision. |
|  | [Beetle PSX](https://github.com/libretro/beetle-psx-libretro) |  | Identique à la Beetle PSX HW en mode logiciel. |
|  | [DuckStation](https://github.com/stenzek/duckstation) |  | Précision assez élevée, vitesse extrêmement élevée. |
|  | [PCSX ReARMed](https://github.com/libretro/pcsx_rearmed) |  | Précision inférieure à celle de la Beetle PSX \(HW\), vitesse plus élevée. |
| **Pokemon Mini** | [PokeMini](https://github.com/libretro/PokeMini) |  |  |
| **Saturn** | [Beetle Saturn](https://github.com/libretro/beetle-saturn-libretro) |  |  |
|  | [Yabause](https://github.com/libretro/yabause) |  |  |
| **Sega CD - Mega-CD** | [Genesis Plus GX](https://github.com/libretro/Genesis-Plus-GX) |  |  |
|  | [Picodrive](https://github.com/libretro/picodrive) |  |  |
| **SG-1000** | [Genesis Plus GX](https://github.com/libretro/Genesis-Plus-GX) |  |  |
|  | [SMS Plus GX](https://github.com/libretro/smsplus-gx) |  |  |
|  | [Gearsystem](https://github.com/drhelius/Gearsystem) |  |  |
|  | [blueMSX](https://github.com/libretro/blueMSX-libretro) |  |  |
|  | [FinalBurn Neo](https://github.com/libretro/FBNeo) |  | Nécessite des jeux dans le sous-répertoire sg1000, des archives exactes comme arcade. Tous les jeux peuvent ne pas être liés pour ce noyau. |
| **SNES** | CORE SNES9X\_NEXT |  |  |
|  | [Snes9x](https://github.com/libretro/snes9x) |  | Vitesse élevée, précision modérée. Activement entretenu. |
|  | [Snes9x 2010](https://github.com/libretro/snes9x2010) |  |  |
|  | [Snes9x 2005 Plus](https://github.com/libretro/snes9x2005) |  |  |
|  | [Snes9x 2005](https://github.com/libretro/snes9x2005) |  |  |
|  | [Snes9x 2002](https://github.com/libretro/snes9x2002) |  |  |
|  | [Mesen-S](https://github.com/SourMesen/Mesen-S) |  | Haute précision, coût de haute performance. |
|  | [Beetle bsnes](https://github.com/libretro/beetle-bsnes-libretro) |  |  |
|  | [bsnes-mercury Accuracy](https://github.com/libretro/bsnes-mercury) |  | [SRAM n'est pas exposé actuellement](https://github.com/libretro/bsnes-mercury/issues/88) |
|  | [bsnes-mercury Balanced](https://github.com/libretro/bsnes-mercury) |  | [SRAM n'est pas exposé actuellement](https://github.com/libretro/bsnes-mercury/issues/88) |
|  | [bsnes-mercury Performance](https://github.com/libretro/bsnes-mercury) |  | [SRAM n'est pas exposé actuellement](https://github.com/libretro/bsnes-mercury/issues/88) |
|  | [bsnes 2014 Accuracy](https://github.com/libretro/bsnes-libretro) |  |  |
|  | [bsnes 2014 Balanced](https://github.com/libretro/bsnes-libretro) |  |  |
|  | [bsnes 2014 Performance](https://github.com/libretro/bsnes-libretro) |  |  |
|  | [bsnes C++98 \(v085\)](https://github.com/libretro/bsnes-libretro-cplusplus98) |  | A des problèmes de rendu des couleurs |
| **Supervision** | [Potator](https://github.com/libretro/potator) |  | Une version de RetroArch 1.9.1 ou plus récent est nécessaire pour le soutien des exploits \(achievement\). |
| **Vectrex** | [vecx](https://github.com/libretro/libretro-vecx) |  |  |
| **Virtual Boy** | [Beetle VB](https://github.com/libretro/beetle-vb-libretro) |  |  |
| **Wonderswan** | [Beetle Cygne](https://github.com/libretro/beetle-wswan-libretro) |  |  |
| **Wonderswan Color** | [Beetle Cygne](https://github.com/libretro/beetle-wswan-libretro) |  |  |




>_**Informations :**_
>
>​Pour **visionner les challenges/trophées** dans **Retroach** , il suffit d'**activer le menu retroarch** \(Hotkey+B\)   
>`Quick Menu > Achievements list`
>
>La **liste des jeux compatibles** sont disponibles sur [cette page](http://retroachievements.org/gameList.php)
{.is-info}

## **Quelles roms sont compatibles ?**  <a id="quelles-roms-sont-compatibles"></a>

En général, pour les consoles les **roms No-Intro en version USA** fonctionnent mieux pour les **Retroachievements,** à quelques rares exceptions où l'**on peut avoir aussi quelques roms européennes** et pour l'arcade avoir la bonne version du set.  
****  
Vous pouvez trouver **une liste de roms compatibles** avec leurs **HASHES \(MD5\)** autrement dit **leur signature numérique** en vous rendant **sur la page du jeu** et en **cliquant sur le lien à droite** :`HASHES LINKED TO THIS GAME` .

Exemple :  


