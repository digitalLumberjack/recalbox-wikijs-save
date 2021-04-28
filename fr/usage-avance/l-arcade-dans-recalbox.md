---
title: L' Arcade dans Recalbox
---

# L' Arcade dans Recalbox

![](./image%20%2835%29.png)

## **I - LA BORNE D'ARCADE**

Les années 70 marquent le début de l'histoire de l'arcade!!  
Chaque bornes utilisent un matériel spécifique et unique, avec souvent plusieurs processeurs, des puces sonores et vidéos très spéciales, et toujours la meilleure technologie informatique d'affichage du moment.  
Les premières bornes d'arcade étaient dédiées et utilisables uniquement pour le jeu avec lequel elles avaient été livrées \(Pac-man, Space Invaders, Pong etc.\). Quand un jeu arrivait en fin de vie commerciale, il était laborieux de réutiliser le meuble.

Les systèmes d'arcade en 1986  évoluent et sont souvent basés sur une de carte mère couplées avec une cartouche de jeu ou une [**PCB**](https://fr.wikipedia.org/wiki/Circuit_imprim%C3%A9) \(connectique [**JAMMA**](https://fr.wikipedia.org/wiki/JAMMA)\).  
Les bornes d'arcade deviennent alors génériques et le matériel se rapproche d'une console de jeux vidéo de salon ou d'un ordinateur haut de gamme.  
Cela a permis de réduire les coûts de production, les temps de création ainsi que facilité la vie des exploitants de bornes et de salles de jeux.

Il reste toutefois beaucoup de systèmes d’arcade qui utilisent toujours un matériel spécifique et optimisé pour un jeu unique : jeux de voiture, jeux avec pistolet optique, jeux de dance...

## II - MAME

\*\*\*\*[**MAME**](https://fr.wikipedia.org/wiki/MAME) ****\(Multiple Arcade Machine Emulator\) est un système d’émulation polyvalent.

Le but de MAME est de préserver des décennies d'histoire du logiciel.  
Alors que la technologie électronique continue d'avancer, MAME empêche que cet important logiciel "vintage" ne soit perdu et oublié.  
Ceci est réalisé en documentant le matériel et son fonctionnement.

### 1 - La documentation MAME

Le fait que la documentation soit utilisable sert principalement à valider l'exactitude de celle-ci \(comment prouver autrement que vous avez recréé fidèlement le matériel?\).  
Au fil du temps, MAME a absorbé le projet sœur [**MESS**](https://fr.wikipedia.org/wiki/MESS) ****en 2015 \(Multi Emulator Super System\). Ainsi MAME documente maintenant une grande variété d'ordinateurs \(principalement rétro\), de consoles de jeux vidéo, de calculatrices, en plus des jeux vidéo d'arcade qui étaient son objectif initial.

La première version publique \(0.1\) de MAME, par Nicola SALMORIA, est sortie le 5 février 1997.  
Le 21 octobre 2010, la version 0.140 de l'émulateur prend en charge plus de 4 510 jeux.  
Le 4 Avril 2020, la version 0.220 prend en charge plus de 6 000 jeux et ordinateurs 

MAME étant un émulateur en constante évolution, il est nécessaire de faire évoluer son romset parallèlement à la version de l’émulateur.

### **2 - Principe de documentation MAME**

MAME documente cette fabuleuse bibliothèque de machines par le principe du [**DUMP**](https://fr.wikipedia.org/wiki/Dump)**.**  
Le dump ****consiste à transférer les données contenues dans les différents composants \(carte mère, PCB, cartouches\) vers un format numérique afin d’être utilisées avec des émulateurs.

![](https://lh4.googleusercontent.com/Qup-yI2vf4N-rnoV-sIsq6orwABRSbw63JJO57cERkJbXk97VzSw5zur8YYnMLUqZpez4o8jKflVRaAEptRTVOPKnNfzFPUgGti8wqaCPpNe5xz8qxzCiEI7bkCG6PziJO_9_dzQ)

Pour certaines machines plus ou moins récentes cette documentation s’accompagne d’un support CD-ROM, DVD ou même cassette appelé CHD ****\(Compressed Hunks of Data ou morceaux de données compressés\).  
Sans ce CHD l’émulation sera imparfaite ou elle ne se lancera pas du tout.

![](https://lh3.googleusercontent.com/OqyH6-ovw8MizbPn_BWTxxrwITyNU9FufTDjXH-RmLug701yZdE8koL4HaUQZSF3A5zYk9qC6PvElLIBnTiflYRR5XZZfb6eSrwIZltocicVH0U4c_kXdoWlcQHyNX1GYjW9f9jA)

Cette documentation n’est pas toujours parfaite et cela donne des versions ”BAD DUMP” de certains jeux malheureusement et donc une émulation imparfaite ou impossible.

## **III - LES ROMSETS**

### **1 - Contenu d’un romset**

Comme on vous a expliqué plus haut il y a dans vos romsets à boire et à manger.  
En effet le fait d’avoir voulu documenter du “vintage” et l’ensemble des mémoires mortes de la planètes nous amènes à se poser la question : qu’avons nous dans un ROMSET ?

Grace au  logiciel [**CLRMAMEPRO**](/v/francais/tutoriels/utilitaires/gestion-des-roms/clrmamepro) il est possible de lire l'ensemble du contenu d'un romset en ayant au préalable une référence: le fichier ****[**.dat**](https://fr.wikipedia.org/wiki/Index.dat). ****  
Ce fichier rassemble la liste complète des données qui constituent le romset par rapport à l'émulateur.  
_**Il est important de comparer votre romset avec ce fichier .dat via clrmamepro et d'éviter de piocher des ROMs à droite et à gauche pour des problèmes de compatibilité !**_  
  
Dans MAME ****on va retrouver les familles ci-dessous :

* **STANDARD :** C’est la plus grosse partie du romset \(55Go\). On va trouver dedans des jeux d’arcade, des flippers, des consoles, des machine à sous, des calculatrices, même des tamagotchis... 
* **MECHANICAL :** Traduction “électromécanique” sont des machines difficilement émulables car mi-mécaniques / mi-numériques. 
* **DEVICE :** Traduction “matériel” sont des fichiers de configuration qui accompagnent certaines machines pour l’émulation. 
* **BIOS :** Certains systèmes sont rangés par BIOS \(environs 70\).

### **2 - Les BIOS / les Drivers**

Certaines ROMs de jeux d'un romset peuvent nécessiter des fichiers de BIOS ou un drivers, le cas le plus connu étant les jeux [**Neo-Geo**](https://fr.wikipedia.org/wiki/Neo-Geo_MVS). 

* Exemple **Neo-Geo** : Si vous voulez utiliser des jeux Neo-Geo, vous allez devoir copier le fichier de “BIOS” \(dans ce cas neogeo.zip\) dans le même répertoire que le jeu. 
* Exemple [**CPS**](https://fr.wikipedia.org/wiki/CP_System) : Si vous voulez utiliser certains jeux CPS, vous allez devoir copier le fichier de “driver” \(dans ce cas qsound\_hle.zip\) dans le même répertoire que le jeu.

Bien sûr si vous utilisez des sous répertoires pour vos jeux \(genre ou hardware par exemple\), vous devrez copier les fichiers de BIOS et driver dans chaque répertoire contenant des jeux qui les nécessitent.  
Étant donné que ces fichiers de BIOS et driver sont plutôt petits en taille, il est plus simple de les copier tous dans chacun de vos sous-répertoires.

Où trouver ces fichiers de BIOS et driver me dites vous ?  
Eh bien c'est plutôt simple : dans votre romset !

### **3 - Les CHD**

Comme pour un BIOS ou un DRIVER, le CHD doit accompagner sa ROM mais attention car le format et le rangement de celui-ci est bien spécifique.

Le fichier ****CHD ****\(non compressé\) ne porte pas le même nom que la ROM mais doit être rangé dans un dossier \(non compressé\) portant le nom exact de cette ROM pour fonctionner.  
Ces fichier CHD ****sont rarement avec les romsets car volumineux.

**Exemple ROM+CHD : sfiii3**

![](./image%20%28220%29.png)

### **4 - Types de fichiers dans un romset**

* **PARENT :** La ROM du jeu original que l'équipe de MAME a décidé de nommer "version originale". Excepté pour les fichiers ROM BIOS, les fichiers ROM pour ces jeux contiennent tout ce qui est nécessaire au fonctionnement du jeu. L'ensemble original est jugé comme étant la révision la plus récente et si de multiples versions régionales sont disponibles, est utilisée la révision world \(internationale\) ou US \(américaine\). ****
* **CLONES :** La ROM est une différente version ou variante d'un même jeu \(par exemple, Street Fighter II Turbo est considéré comme variante de Street Fighter II Champion Edition\). On retrouvera aussi les versions: Bootleg / homebrew / hack... ****
* **BIOS :** La ****ROM commune utilisée par tous les jeux d'une même machine \(comme Neo-Geo MVS\). Ce sont les programmes utilisés au démarrage de la machine, permettant d'effectuer des opérations de base, lors de sa mise sous tension.

### **5 - Type de romsets : split / merged / non-merged**

**Il existe trois types de romsets :**

* **Split :** \[divisé\] les fichiers en communs entre parents et clones ne sont que dans le zip parent, pour utiliser un clone il faut donc avoir les deux ROMs parent et clone. ****
* **Non-merged :** \[non-fusionné\] tous les fichiers nécessaires pour le clone sont dans le zip de celui-ci. ****
* **Merged :** \[fusionné\] parent et clone sont fusionnés dans le même zip.

**Ci-dessous un exemple ROM dans les différents types de romsets :** en rouge les éléments du parents, en jaune les éléments du clone et en blanc les éléments servant au fonctionnement du jeu.  
On remarquera que dans le cas du romset **split** le dossier **clone** ne peut pas fonctionner sans le dossier **parent**.

![](https://lh4.googleusercontent.com/xkvxwYrIhGoXzASQ2iOB5PSCS91LFrYRjoSKsc4R0k_7ulZI7RFR8rerfoOEwZV3-BKF3SVd5Cf8VAU94W5GhNB4NmoGcjnDtlKHMrAuL5wMl57v12eI_fGj_4DARX_wNmXt3rup)

## **IV - L' ARCADE ET RECALBOX**

Les différents ****émulateurs dans **Recalbox** font référence à **différents romsets MAME** pris en charge par ceux-ci.

_**Il est important de comparer votre romset avec un fichier .dat via clrmamepro et d'éviter de piocher des rom à droite et à gauche pour des problèmes de compatibilité.**_

### **1 - Mame**

* **LIBRETRO-MAME 2003 :** Basé sur le **ROMSET 0.78** a été publié le 25 décembre 2003. ****
* **LIBRETRO-MAME 2003-Plus :**  
  \(également appelé MAME 2003+ et mame2003-plus\) est un noyau d'émulateur de système arcade Libretro qui met l'accent sur des performances élevées et une compatibilité étendue avec les périphériques mobiles, les ordinateurs à carte unique, les systèmes intégrés et autres plates-formes similaires.  
  Basé sur le **ROMSET 0.78-0.188** \(MAME 0.78 en tant que ligne de base avec d'autres ROMs basées sur des jeux de ROMs MAME ultérieurs\).

* **LIBRETRO-MAME 2010** :  
  Basé sur le **ROMSET 0.139** a été publié le 29 juillet 2010.

* **LIBRETRO-MAME 2015 :**  
  Basé sur le **ROMSET 0.160** a été publié le 25 mars 2015.

* **LIBRETRO-MAME :** Basé sur le **ROMSET 0.220**

### **2 - FbNeo** 

* **LIBRETRO-FBNEO :** Basé sur le **ROMSET 0.189** mais reconstruit via le fichier Dat pour l'émulateur : **1.0.0.0** 

### **3 - Neo-Geo**

* **LIBRETRO-FBNEO :** Basé sur le **ROMSET 0.189** mais reconstruit via le fichier Dat pour l'émulateur : **0.2.97.44**   

### **4 - Naomi**

* \*\*\*\*[**Libretro-Flycast**](/v/francais/emulateurs/arcade/naomi/libretro-flycast#romset-mame) **:** Basé sur le **ROMSET 0.220**

### **5 - Naomi GD**

* \*\*\*\*[**Libretro-Flycast** ](/v/francais/emulateurs/arcade/naomi-gd-rom/libretro-flycast#romset-mame)**:** Basé sur le **ROMSET 0.220**

### **6 - Atomiswave**

* \*\*\*\*[**Libretro-Flycast**](/v/francais/emulateurs/arcade/atomiswave/libretro-flycast#romset-mame) **:** Basé sur le **ROMSET 0.220**

## **V - LES PROBLÈMES CONNUS** 

| **Type de problème** | **MAUVAISE ROM** | **MAUVAIS EMULATEUR**  | **CHD MANQUANT** | **MAUVAIS DUMP** | MAUVAIS MAPPING |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Mon jeu ne se lance pas**  | **X** | **X** | **X** | **X** |  |
| **Problème de son du jeu** |  | **X** |  | **X** |  |
| **Le jeu que j’utilise est buggé, glitché**  |  | **X** |  | **X** |  |
| **Le jeu se lance mais les touches ne sont pas les bonnes** |  |  |  |  |       **X** |

## **VI - GLOSSAIRE**

**A**

* **AtomisWave :** Système d’arcade crée par Sammy dont l’architecture est similaire à la Naomi de Sega.

**B**

* **Boot :** Désigne la phase de démarrage d’un système, comme par exemple celui d’une carte d’arcade ou d’une console. ****
* **Bootleg :** Copies non officielles de jeux sur PCB ou cartouche, généralement vendu bien moins chers que les originaux reconnaissable assez facilement du fait qu’il n’y ai quasiment jamais la marque de l’éditeur du jeu inscrit sur le pcb ou la cartouche contrairement aux originaux. Il est courant que les bootlegs sont atteints de bugs divers, de musiques en moins, des bruitages qui manquent, des freezes aléatoires...

**C**

* **Carte mère :** Désigne souvent le support qui contient tous les composants de calcul et qui est nécessaire pour faire fonctionner les jeux qui doivent y être installés. Exemple avec le MVS ou autre système à cartouche ou disque : les unités de calcul, les processeurs son ou graphiques, etc \(appelé aussi le Hardware\) sont concentrés dans la carte mère alors que le jeu \(le software\) est contenue dans la cartouche ou le disque. ****
* **Chihiro :** Nom d’un système d’arcade édité par SEGA en 2002. L’architecture de cette plate-forme est basée sur celle de la console Xbox de Microsoft. Parmi les jeux édités, les plus populaires sont : Outrun 2, House of the Dead 3 et Virtua Cop 3. ****
* **CPS 1 :** Acronyme de Capcom Play System 1. Nom d’un système d’arcade créé par Capcom sorti en 1988. Parmi les jeux édités sur ce système, Street Fighters II est l’un des plus célèbres ! ****
* **CPS 2 :** Acronyme de Capcom Play System 2. Nom d’un système d’arcade créé par Capcom sorti en 1993. Parmi les jeux édités se trouvent : Gigawing, Marvel Vs Capcom, la série des Street Fighters Zéro ou Alpha, Vampire Savior ou Progear no Arashi. ****
* **CPS 3 :**

  Acronyme de Capcom Play System 3. Nom d’un système d’arcade créé par Capcom sorti en 1996.  
  Ce système est très puissant dans la gestion des graphismes 2D.  
  Sont sorti sur ce système : Jojo’s Bizarre Adventure, Warzard, et la série des Street Fighters III.  
  ****

* **Crystal System :**[ ****](https://fr.wikipedia.org/wiki/Syst%C3%A8me_d%27arcade)Système d'arcade au format JAMMA sorti en 2001 fabriqué et commercialisé par la société BrezzaSoft. Le Crystal System est créé dans le but de remplacer le système Neo-Geo sur le marché des jeux d'arcade bon marché. Rappelons que la quasi-totalité des employés travaillant chez BrezzaSoft sont des transfuges de SNK, partis de la société venant juste de faire faillite pour créer BrezzaSoft. Ce système propose des jeux bénéficiant de graphismes 2D très poussés et très agréables. Le Crystal System n'aura pas le succès escompté et ce sera un désastre commercial, il connaîtra une durée de vie très courte. Très peu de jeux seront édités sur ce nouveau système, mais on peut noter des jeux comme Evolution Soccer, un jeu de football copié sur Super Sidekicks, et Crystal of the Kings, un Beat them all de type médiéval dans la lignée de Golden Axe ou Knights of the Round.

**D**

* **DECO Cassette System :**[ ****](https://fr.wikipedia.org/wiki/Borne_d%27arcade)Borne d'arcade développé par Data East. Sorti en 1980, il fut le premier système d'arcade permettant au possesseur de la borne de changer de jeux. L'acheteur devait acheter la cabine d'arcade, tandis que les jeux étaient disponibles sur des cassettes audio. Il suffisait ensuite d'insérer dans la cabine, la cassette et un dongle de sécurité \(il s'agit de l'une des premières formes de gestion numérique des droits, empêchant la copie\). ****
* **Dump / Dumping / Dumper :**

  Technique qui consiste à transférer les données contenues dans la ou les ROMs d’un jeu d’arcade au disque dur d’un ordinateur \(image de ROM\) pour ensuite être mis à la disposition sur internet et utilisé dans les émulateurs comme MAME.

**E**

* **Emulation :** Procédé permettant de reproduire sur un ordinateur ou une console le comportement d’une autre appareil, grâce à ce qu’on appelle un émulateur. Par exemple l’émulateur Kawaks permet de jouer à la Neo.Geo sur son PC.

**H**

* **Hyper Neo-Geo 64 :** Il a été créé par la société SNK et commercialisé en septembre 1997, afin de succéder au système Neo-Geo MVS datant à l'époque de sept ans. Techniquement, comme son nom l'indique, l'Hyper Neo-Geo 64 est doté d'un microprocesseur 64 bits permettant de faire fonctionner des jeux en 3D, affichant 4096 couleurs simultanément parmi une palette de 16,7 millions de couleurs, dans une résolution de 640 x 480 pixels. Parmi les 7 jeux sortis : Fatal Fury, Wild Ambition, Samurai Shodown 64, Samurai Shodown 64, Warriors Rage...

**I**

* **Image de ROM :** Copies des ROMs \(Read Only Memory\), les composants électronique qui se trouvent sur les cartouches et de cartes d’arcades et qui contiennent le jeu. Le fait de copier un jeu d’arcade sur le disque dur d’un pc s’appelle «dumper» un jeu et ça nécessite du matériel spécial. Les copies/images de roms sont ensuite mise sur internet sous forme de fichiers généralement compressé en .zip lisible par les émulateurs, puis téléchargés par vous et moi. Par soucis de simplicité, les images de ROMs sont tout simplement appelées des « roms » par la majorité des sites d’émulation.

**J**

* **JAMMA :** Standard de connectique pour tous les jeux d’arcade afin que tous les jeux d’arcade marchent sur toutes les bornes, créé au milieu des années 80 par la «Japanese Amusement Machine Manufacturers Association». Techniquement, le standard définit les connexions pour : deux joysticks à huit directions, deux boutons start, et six boutons de contrôle \(trois par joueur\), ainsi que le support du son \(mono\).

**K**

* **Konami Sytem 573 :** Le System 573 est une série de cartes système d'arcade de Konami basées sur la Playstation originale. Le matériel a été utilisé principalement pour les séries d'arcade de jeux vidéo misicaux Benami de Konami, le plus souvent la série Dance Dance Révolution introduite en 1998. ****
* **Konami Viper :** Konami lance la Konami Viper en 1998 pour les salles d'arcades. Cette Arcade utilise le système JAMMA+PCB. Parmi les 13 jeux sortis : Jurrassic Park 3, GTI club 2, Silent Scope EX, Thrill Drive II…

**L**

* **Lindbergh :** Nom d’un système d’arcade créé par SEGA sorti en 2006. L’architecture et les composants de ce système sont à peu de chose près ceux d’un PC, ce qui tranche avec les autres systèmes créés par SEGA auparavant. Parmi les jeux sorti sur Lindbergh on trouve Virtua Fighters 5, Virtua Tennis 3, House of The Dead 4, After Burner Climax… \[Note\] Lindbherg est aussi le nom d’un des pionniers de l’aviation, l’américain Charles Lindbergh \(1902-1974\). Il est la première personne à avoir effectué la traversée en solitaire de l’océan Atlantique en avion.

**M**

* **MAME :** Célèbre émulateur arcade qui émule plus de 6000 systèmes et arcade. MAME est aussi considéré comme un véritable musée virtuel du jeu d’arcade. ****
* **Model 1 :** Nom d’un système d’arcade créé par SEGA sorti en 1992. Véritable avancée technologique, c’est sur ce système que sortiront Virtua Racing et Virtua Fighter 1. ****
* **Model 2 :** Nom d’un système d’arcade créé par SEGA sorti en 1993. Quelqu’un des jeux les plus populaires édité sur ce système sont Daytona USA, House of the Dead, Sega Rally CHampionship et Virtua Fighter 2. ****
* **Model 3 :** Nom d’un système d’arcade créé par SEGA sorti en 1996 qui devient alors le système le plus puissant à son époque. Quelqu’un des jeux les plus populaires édité sur ce système sont Daytona USA 2, Scud Race, Sega Rally 2 et Virtua Fighter 3.

**N**

* **Namco System 246 :** Le System 246 est un système de jeux vidéo destiné aux salles d'arcade, basé sur la Playstation 2. Il a été créé par la société Namco en 2001 et a connu plusieurs évolutions : le System 256, le Super System 256 et le System 147. ****
* **Naomi et Naomi GD :** Système de jeu vidéo à cartouche et GD-ROM pour borne d’arcade, sorti en 1998 comme successeur du système Sega Model 3. Acronyme de New Arcade Operation Machine Idea \(littéralement « nouvelle idée de machine d’arcade »\), Naomi se traduit aussi par « beauté » en japonais. ****
* **Neo-geo MVS :** \(Multi Video System\) est un système de jeux vidéo pour borne d'arcade compatible JAMMA destiné aux salles d'arcade et créé par la société japonaise SNK en 1990. ****
* **Nintendo playchoice 10 :** Basé sur le système Nintendo Entertainment \(NES\), la carte mère Playchoice 10 a permis d'installer jusqu'à 10 cartes ROMs à la fois. Contrairement à la plupart des autres jeux d'arcade, les pièces ajoutent du temps plutôt que des crédits, vous permettant de changer de jeu à la volée quand vous le souhaitez.

**P**

* **PCB :** Initiales de « Printed Circuit Board » \(« Circuit imprimé » en français\). Plaque destinée à regrouper des composants électroniques. En arcade une PCB est un circuit imprimé qui contient un jeu et qui se branche sur la borne d’arcade par le connecteur JAMMA. 
* **PGM :** Initiale de « Poly Game Master » développé par IGS \(International Games System\). Ce système d’arcade similaire au MVS dans ses performances, son apparence et son utilisation. ****
* **Pinball :** Flipper

**R**

* **ROM :** Sigle de "**Read Only Memory"** appelé aussi « mémoire morte »

**S**

* **Sega Hikaru ;** Nom d’un système créé par la société Sega en 1999. Le Hikaru est pensé à l'origine pour accueillir le jeu Brave Fire Fighters. Il possède la capacité d'afficher à l'écran des graphismes complexes représentant des mouvements de feu ou d'eau. Il fut le premier système d'arcade à proposer de l'ombrage de Phong à l'écran. Ce système n'a connu que six jeux et fut vite abandonné, car son exploitation était trop coûteuse par rapport notamment à la Naomi2. ****
* **Sega Mega Play:** Système d’arcade basé sur la console de salon Sega Megadrive. Lorsque vous insérez des pièces, vous achetez des crédits comme un jeu vidéo d'arcade standard. ****
* **Sega Mega-Tech :** Système d’arcade basé sur la console de salon Sega Megadrive. Lorsque vous insérez une pièce, vous achetez le temps, le jeu est terminé lorsque votre temps est écoulé, vous pouvez ajouter des pièces supplémentaires au cours du jeu pour gagner du temps supplémentaire. 
* **Set :** Dans le langage arcade un set=jeu ou un BIOS composé de multiple mémoires mortes ou ROM. 
* **ST-V TItan :** \(acronyme de Sega Titan Video\) : Système arcade de Sega lancé en 1994, à l’architecture identique à celle de la console Sega Saturn \(à la différence que le ST-V utilisait des cartouches\). Un des but était de faciliter la vie des programmeurs, de faire des conversions arcade vers console bien plus rapides, et d’obtenir des conversions les plus fidèles possibles.

**T**

* **Triforce :** Nom d’un système d’arcade conjointement développé par Nintendo, SEGA et Namco et sorti en 2002. L’architecture de ce système est basée sur celle de la console GameCube de Nintendo. Parmi les jeux édités, les plus populaires sont : F-Zero AX, Virtua Striker 4 et Mario Kart Arcade GP. Note : le nom Triforce représente l’alliance entre les 3 sociétés mais est aussi une référence à la série The Legend Of Zelda.

## VII Sources:

* [http://www.system16.com/](http://www.system16.com/)
* [https://fr.wikipedia.org/wiki/Wikip%C3%A9dia:Accueil\_principal](https://fr.wikipedia.org/wiki/Wikip%C3%A9dia:Accueil_principal)

