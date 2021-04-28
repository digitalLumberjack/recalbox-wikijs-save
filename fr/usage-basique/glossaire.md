---
title: Glossaire
description: Liste de termes en lien avec Recalbox.
---

# Glossaire

Cette section donne la définition de termes techniques en lien avec Recalbox, si vous avez un mot que vous ne comprenez pas, cette page devrait pouvoir vous aider.

## A

* **Arcade** : L'arcade fait généralement référence à des machines de jeux-vidéos dans lesquelles ont insère des pièces pour avoir des crédits. De part leur nature \(une grande quantité de machines différentes, là où les consoles ont généralement un matériel défini sur lequel un grand nombre de jeux va tourner\) il est important de comprendre comment faire fonctionner les émulateurs associés, car mettre des fichiers sans savoir précisément ce que l'on fait ne va généralement pas fonctionner. De plus, dans le contexte de Recalbox, les jeux Neogeo sont émulés de la même manière que les titres arcade. 
* **API :** 
* **Archive de support** : voir _Support Archive_.

## B

* **Big-Endian :** est le moyen le plus courant de stocker [binaire](https://techlib.fr/definition/binary.html) Les données. Il place la valeur la plus significative \(ou la plus grande\) en premier, suivie des valeurs moins significatives. Par exemple, la représentation big-endian du [entier](https://techlib.fr/definition/integer.html) 123 place la valeur des centaines \(1\) en premier, suivie de la valeur des dizaines \(2\), puis de la valeur de unités \(3\) ou de \[123\]. 
* **Bios** : Fichiers représentant des programmes lus par le système d'origine, requis par certains émulateurs. 
* **Buildroot :** est un ensemble de Makefiles et de correctifs qui simplifie et automatise le processus de construction d'un environnement Linux complet et amorçable pour un système embarqué , tout en utilisant la compilation croisée pour permettre la construction de plusieurs plates-formes cibles sur un seul système de développement basé sur Linux. Buildroot peut automatiquement créer la chaîne d'outils de compilation croisée requise , créer un système de fichiers racine , compiler une image du noyau Linux et générer un chargeur de démarrage pour le système intégré ciblé, ou il peut effectuer toute combinaison indépendante de ces étapes. Par exemple, une chaîne d'outils de compilation croisée déjà installée peut être utilisée indépendamment, tandis que Buildroot crée uniquement le système de fichiers racine.

## C

* **Changelog** : Fichier texte contenant les modifications pour chaque version d'un logiciel, voir le [changelog](https://gitlab.com/recalbox/recalbox/raw/master/CHANGELOG.md) et les [release-notes](https://gitlab.com/recalbox/recalbox/raw/master/RELEASE-NOTES.md) de Recalbox.
* **Chd** : Image disque de jeu d'Arcade utilisée par certains jeux MAME, stocke une version compressée de l'intégralité du contenu du disque dur d'une machine d'arcade.
* **Cheats** : Dans le contexte de Recalbox, les cheats permettent de reproduire le comportement de certains appareils de triche des systèmes originaux, permettant d'activer ou désactiver des codes pré-entrés modifiant le comportement du jeu.
* **Checksum** _\(ou Somme de contrôle\)_ ****: Une chaîne de caractère calculée à partir du contenu d'un fichier, si deux fichiers de la même taille ont le même checksum, ils sont probablement identiques. Utilisé principalement pour le Netplay.
* **Core** : Un programme chargé par un émulateur \(généralement Retroarch\).
* **CRC** : Un type de Checksum utilisé pour le Netplay.
* **Cue** _\(ou .cue\)_ : Fichiers décrivant comment des données brutes sont réparties sur un disque, principalement utilisé pour des consoles utilisant des disques, avec des fichiers .bin.

## D

* **Dat** _\(or .dat\)_ ****: Fichiers utilisés pour vérifier des lots de roms afin de vérifier que elles appartiennent à un set donné, principalement utilisé pour l'Arcade et le Netplay. 
* Débogage :  Réparer un problème informatique dû à un bogue \(ou bug\), c'est-à-dire à un mauvais fonctionnement d'un programme informatique, qui empêche le bon fonctionnement d'une application, d'un logiciel, etc. Exemple : Il a débogué sa Recalbox en le redémarrant.
* **Demo mode** : Une fonctionnalité de Recalbox, permettant à EmulationStation de lancer des jeux au hasard après un temps d'inactivité défini.
* **DragonBlaze** : Nom de la version 6.0 de Recalbox.

## E

* **Endianité :** est en [Informatique](https://techlib.fr/definition/computer_science.html) terme qui décrit comment [date](https://techlib.fr/definition/data.html) est stocké. Plus précisément, il définit quelle extrémité d'un multi-octet [Type de données](https://techlib.fr/definition/datatype.html) contient les valeurs les plus significatives. Les deux types d’endianité sont le big-endian et le petit-endian.
* **EmulationStation** _\(ou ES\)_ : Le front-end \(ou l'interface pour gérer et accéder aux jeux\) utilisé dans Recalbox.
* **Emulateur** : Programme imitant le comportement d'un matériel défini.

## F

* **Front-end :**

## G <a id="g"></a>

* **Gamelist** _\(ou gamelist.xml\)_ **:** Fichier spécifique à chaque système émulé, listant des informations pour chaque jeu.
* **Gitlab :** 
* **GPI :** fr
* **GPIO** _\(ou General Purpose Input/Output\)_ **:** Contacts accessibles sur un Raspberry Pi, pouvant être utilisés pour différents usages \(Principalement pour attacher des boutons et autres contrôles dans le cas de Recalbox\).

## H <a id="h"></a>

* **Hash** : Fonctionnalité calculant les checksums des roms pour le Netplay.
* **Hotkey** : Bouton utilisé pour des combinaisons de touches interprétés par l'émulateur comme des raccourcis pour des fonctionnalités.

## I <a id="i"></a>

* **Interface :** 
* **Iso** _\(ou .iso\)_ : Fichiers images d'un disque physique.
* **Issue** : Dans le cas de Gitlab, une Issue représente un rapport de bug ou une demande d'ajout de fonctionnalité, il est possible de voir les issues ou d'en créer une en suivant ce lien : [https://gitlab.com/recalbox/recalbox/issues](https://gitlab.com/recalbox/recalbox/issues)​

## K <a id="k"></a>

* **Kodi** : Lecteur multimédia inclus dans Recalbox.

## L <a id="l"></a>

* **Libretro** : API multiplateforme utilisée par Retroarch.
* **Licence** : Une licence défini ce qui peut être fait ou non avec un logiciel, il est possible de lire la licence de Recalbox [ici](https://gitlab.com/recalbox/recalbox/blob/master/LICENSE.md), il faut aussi prendre en compte que Recalbox est fourni avec d'autres logiciels, qui sont eux-aussi soumis à leur licence.
* **Link-Cable** : Un câble utilisé pour relier deux systèmes portables ensemble dans le but d'utiliser des fonctionnalités multijoueur pour les jeux supportés, certains émulateurs peuvent imiter ce comportement.
* **Little Endian :** stocke d'abord la valeur la moins significative, suivie de valeurs de plus en plus significatives. Par exemple, le nombre 123 en notation little-endian est \[321\]. Le texte [un magnifique](https://techlib.fr/definition/string.html) "ABC" est représenté par \[CBA\].

## M <a id="m"></a>

* **MAME** :\(Multiple Arcade Machine Emulator\) est un émulateur gratuit et à source ouverte conçu pour recréer le matériel des systèmes de jeux d’arcade dans des logiciels sur des ordinateurs personnels modernes et d’autres plateformes.
* **MD5** : un type de checksum, utilisé pour les BIOS.
* **MITM** : _\(ou Man In The Middle\)_ : Réglage utilisé pour le Netplay, utilisant un serveur distant pour synchroniser les parties plutôt que une connexion directe, en contrepartie d'une perte de fiabilité et de vitesse.
* **Multitap** : Périphérique permettant de brancher d'avantages de manettes qu'il n'y a de ports manettes sur une console, permettant d'avoir un mode 4 joueurs sur des systèmes avec uniquement deux ports manettes d'origines pour les jeux supportés, certains émulateurs peuvent imiter ce comportement.

## N <a id="n"></a>

* **Netplay** : Une technologies permettant de jouer en réseau, dans le cas de Recalbox, cela permet de jouer à des jeux rétros en ligne.
* **No-intro** : Nom d'un groupe qui référence des Roms, sont spécialisé dans les jeux cartouches et on pour objetif et vision de ne garder que les dump le plus proche de celles d'origines. **Romsets de référence** pour les systèmes utilisant des **cartouches**, principalement **utilisé pour le Netplay**.
* **NOOBS :** \(New Out Of the Box Software\) porte un nom qui peut paraître péjoratif, mais cet utilitaire permet d'installer un OS de manière fiable et rapide parmi une sélection assez large. NOOBS n'est en réalité qu'un simple gestionnaire d'installation de système d'exploitation pour Raspberry Pi, il a été conçu pour simplifier cette tâche au maximum en permettant d'installer un OS en seulement quelques clics.

## O <a id="o"></a>

* **OCR** : La **reconnaissance optique de caractères** \(ROC\), en anglais 'optical character recognition', ou océrisation, désigne les procédés informatiques pour la traduction d'images de textes imprimés ou dactylographiés en fichiers de texte.
* **Open-source :** La désignation **open source** ou « **code source ouvert** », s'applique aux logiciels dont la [licence](https://fr.wikipedia.org/wiki/Licence_de_logiciel) respecte des critères précisément établis par l'[Open Source Initiative](https://fr.wikipedia.org/wiki/Open_Source_Initiative), c'est-à-dire les possibilités de libre redistribution, d'accès au [code source](https://fr.wikipedia.org/wiki/Code_source) et de création de travaux dérivés. Mis à la disposition du grand public, ce code source est généralement le résultat d'une collaboration entre programmeurs.
* **OS :** Voir **Système d'exploitation**.
* **Overlays** : Image affichée au dessus du jeu, principalement utilisés pour des raisons cosmétiques.

## P <a id="p"></a>

* **PBP** _\(ou .pbp\)_ : Fichiers image correspondant à des UMD physiques de la Playstation Portable, ou à des jeux multi-disques de la Playstation.
* **Pi :** Voir **Raspberry Pi**.
* **Plug and play :** l'abréviation **PnP** est également utilisée, qui signifie « connecter et jouer » ou « brancher et utiliser », est une technologie permettant aux systèmes d'exploitation de reconnaître rapidement et automatiquement les périphériques compatibles avec cette technologie dès le branchement, sans redémarrage de l'ordinateur. Le Plug and Play permet une mise en œuvre requérant un minimum d'intervention de la part de l'utilisateur, sans installation de logiciel dédié, et donc en minimisant les erreurs de manipulation et de paramétrage.

## R <a id="r"></a>

* **Raspberry Pi :** 
* **Rebuild** : 
* **Recalbox** : Le système d'exploitation lui-même, basé sur Buildroot System From Scratch.
* **Recalbox.conf** : Fichier contenant la majorité des réglages de Recalbox et de ces émulateurs, voir ["Le fichier recalbox.conf"](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf).
* **Retroachievements** : Un servie permettant d'activer un système de trophées/succès pour les jeux et émulateurs supportés.
* **Retroarch** : Le Front-End Libretro utilisé par certains émulateurs dans Recalbox, voir [Retroarch](../usage-avance/retroarch.md).
* **Rewind** : Un réglage permettant de rembobiner dans certains émulateurs, en contrepartie d'une perte de performances.
* **Roms** : Fichiers images de jeux physiques.
* **Romset** : Un lot de roms spécifique, principalement utilisé pour le Netplay et l'Arcade.

## S <a id="s"></a>

* **Savestates** : Fonctionnalité permettant de sauvegarder l'état exact de la machine émulée, permettant une sauvegarde complète d'une partie à n'importe quel moment, même si le jeu ne supporte pas originellement les sauvegardes, il est important de noter que les sauvegardes traditionnelles d'un jeu et les savestates peuvent rentrer en conflit.
* **Samba** : SMB \(Server Message Block\), Le partage de dossiers et d'imprimantes dans un réseau local est une fonctionnalité des systèmes d'exploitation modernes permettant d'accéder à des ressources d'un ordinateur \(dossiers de données et imprimantes\) à partir d'un autre ordinateur situé dans un même réseau local \(réseau domestique ou d'entreprise\).
* **Scrapper** : Programme capable d'aller chercher des informations sur les jeux via internet, et de les sauvegarder dans un format interprétable par EmulationStation.
* **Shaders** : Filtres pouvant altérer le rendu visuel d'un jeu au prix d'une baisse de performance, principalement utilisé pour des raisons cosmétiques.
* **Share** : Partition de Recalbox, accessible depuis le réseau, voir [Share]().
* **Somme de contrôle** : Voir _Checksum_
* _**SSH :**_ 
* **Surcharge** : Fichiers permettant d'outrepasser la configuration par défaut pour certains jeux ou dossiers, voir [Surcharge](../usage-avance/surcharge-de-configuration/).
* **Support Archive** _\(ou Archive de support\)_ : Option du Webmanager, permettant de générer un lien de déboggage utile aux développeurs en cas de soucis.
* **Système d'exploitation :** Appelé aussi **OS** \(de l'anglais Operating System\) est un ensemble de programmes qui dirige l'utilisation des ressources d'un ordinateur par des logiciels applicatifs.

## T <a id="t"></a>

* **Thèmes** : Fichiers définissant l'apparence globale de EmulationStation.

## U

* **UMD :**

## V <a id="v"></a>

* **Verbose** : Pour Recalbox, il s'agit d'un mode de démarrage affichant des informations de débogage pour certaines architectures, utile pour comprendre pourquoi le système ne démarre pas correctement.

## W <a id="t"></a>

* **Webmanager** : Une interface réseau activée par Recalbox, permettant de faire des réglages de manière simple, de gérer les fichiers, de vérifier les BIOS et plus encore.

## X <a id="v"></a>

* **Xin-Mo :** 

