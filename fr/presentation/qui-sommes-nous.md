---
title: Qui sommes-nous ?
---

# Qui sommes-nous ?

## Présentation

**La Recalbox** est une **console de retrogaming open-source** qui vous permet de rejouer à une variété de consoles et de plateformes dans votre salon, en toute simplicité !

**RecalboxOS** est le **système d'exploitation** du projet Recalbox, une console d'émulation **prête à l'emploi** basée sur le **Raspberry Pi** qui est entièrement **libre et gratuit**, et à été conçu spécialement pour que **vous puissiez créer la votre en un rien temps**.

La Recalbox vous propose **une large sélection de consoles et de systèmes**, depuis les premières bornes d'arcade, jusqu'aux plateformes comme la Playstation, en passant par la Nes et la Megadrive.​

**RecalboxOS** utilise plusieurs éléments existants, comme [EmulationStation2](https://github.com/Aloshi/EmulationStation) en tant qu**'interface**, [piFBA](https://github.com/digitalLumberjack/pifba) et [RetroArch](https://github.com/libretro/RetroArch) comme **émulateurs**, [Raspberry Pi NOOBS](https://github.com/raspberrypi/noobs) comme **système d'installation/recovery**.

**RecalboxOS** peut être décrit en un mot : **FACILE**.  
Nous voulons fournir un système qui soit le plus convivial et intuitif possible.  
Pas besoin de modifier une multitude de fichiers de configuration ou de se connecter en SSH.  
Il suffit d'installer le système et de jouer.  
La configuration de l'OS se fait via un fichier unique, nommé `recalbox.conf`.   
Ce dernier permet une configuration fine de tous les émulateurs !

Mais pour **les utilisateurs avancées** voulant avoir une **configuration plus poussée**, nous leur avons donné la possibilité de faire un système à leur convenance avec **les surcharges** \(modifiez uniquement si vous êtes certain de l'issue\).



### Des dizaines de logiciels open-source...... réunis au sein d'un même OS.

**Recalbox OS** est basé sur le système **GNU/Linux**.  
Il intègre des centaines de logiciels open-sources, du plus petit utilitaire, jusqu' à ses émulateurs et son frontend EmulationStation.

Retrouvez les dizaines d'émulateurs de retroarch/libretro, le fameux Media Player Kodi, et le frontend EmulationStation customisé !

![](https://www.recalbox.com/images/opensource/opensource.png)



### Avec les homebrews et les hacks. Découvrez des jeux jamais sortis sur console !

Les Homebrews sont des jeux créés de toutes pièces par des développeurs. Beaucoup sont de très bonnes surprises, et vous feront passer de très bons moments.

Les hacks sont des modifications de jeux existants. Ils reprennent l'ensemble ou une partie des graphismes et du gameplay d'un jeu, et divergent sur l'histoire, la difficulté, l'ambiance.  
Certains sont considérés comme des suites à part entière des jeux originaux, comme Super Mario Bros 4 \(hack de Super Mario World\) ou Legend Of Zelda - Parallels Worlds \(hack de A Link To The Past\)

![](/migration-images/presentation/image%20%28339%29.png)



### Media Center

Propulsée par **Kodi**, la Recalbox fait aussi office de **Media Center**.  
En la connectant au réseau domestique, vous pourrez lire les vidéos depuis tout vos appareils compatibles \(box internet, ordinateur\).



### Caractéristiques

* Système :
  * [​Les systèmes supportés](/hardware-compatibility/emulators-compatibility)
  * **Version de FBA optimisée avec support de 4 joueurs.**
  * **Compilé avec buildroot :**

    Ce qui signifie que le système de fichier root ne pèse que 150Mo compressé.

  * **Système de secours basé sur NOOBS :** Possibilité de réinstaller le système directement depuis la carte SD, ou en obtenant la dernière version sur Internet.
  * **Langage système supporté :** Français, Anglais, Espagnol, Allemand, Italien, Portugais et peut-être d'autres à venir si vous participez.
  * **Interface :** Basée sur EmulationStation2 développée par Aloshi.
  * **Musiques de fond sur l'interface.**
  * **Gestion des favoris.**
* Réseau :
  * **Accès via le réseau :** Aux répertoires des roms, captures d'écran et sauvegardes des parties.
  * **Support du wifi et RJ45**
  * **Mise à jour en ligne.**
* Contrôleurs :
  * **Configuration de votre contrôleur de jeu directement depuis l'interface :** Une fois la configuration effectuée, elle sera compatible avec tous les émulateurs.
  * **Support intégré des manettes PS3, Xbox360, 8BitDo et Bluetooth :** Associez une manette, et jouez !
  * **Présence des pilotes GPIO :** Pour utiliser des contrôles arcade ou vos manettes originales Nes, Snes, Megadrive, PSX.
  * **Support des contrôleurs Xin-Mo 2 joueurs.**
  * **Support de gamepad virtuel** [Miroof's Virtual Gamepad](https://github.com/miroof/node-virtual-gamepads) : Utilisez votre téléphone comme manette.
* Fonctionnalité :
  * **Kodi Media Center :**
  * **Moonlight :** Diffusez des jeux en streaming sur votre réseau local ou via Internet
  * **Netplay retrogaming :** Jeux en ligne
  * **Retroarch AI :** Traduction du texte dans les jeux.
  * **Scraper Interne et externe.** Insérer une image, une vidéo et une description pour chaque jeu.
  * **Snaps videos :** Vidéo de présentation du jeu dans les scrapes.

## Remerciement

RecalboxOS **n'existerait pas** sans les émulateurs **Open Source** qu'il utilise.  
Nous tenons **à remercier toutes les personnes** qui contribuent à fournir **des émulateurs Open-Source,** grâce à qui on a eu la chance de jouer, à nouveau, à **tous ces classiques du jeu vidéo** 🤩



### Voici la liste des logiciels utilisés dans recalboxOS

* Buildroot : [http://buildroot.uclibc.org/](http://buildroot.uclibc.org/)
* EmulationStation : [http://emulationstation.org/](http://emulationstation.org/)​
* EmulationStation UI Design & thème de stock “simple” original: Nils Bonenberger - [http://blog.nilsbyte.de/](http://blog.nilsbyte.de/)



### Emulateurs

* Noyaux Retroarch et Libretro : [http://www.libretro.com/](http://www.libretro.com/)
* PiFBA : [https://code.google.com/p/pifba/](https://code.google.com/p/pifba/)
* Mupen64 : [https://github.com/mupen64plus/](https://github.com/mupen64plus/)​
* Dolphin-emu : [https://fr.dolphin-emu.org/](https://fr.dolphin-emu.org/)​
* PPSSPP : [https://www.ppsspp.org/](https://www.ppsspp.org/)



### Autres

* Lecteur multimédia Kodi : [http://kodi.tv/](http://kodi.tv/)
* Qtsixa : [http://qtsixa.sourceforge.net/](http://qtsixa.sourceforge.net/)

