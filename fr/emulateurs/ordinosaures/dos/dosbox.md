---
title: DOSBox
description: Pour émuler des jeux DOS
---

# DOSBox

## **Présentation du core**

### Qu'est-ce que DOSBox ?

DOSBox est un émulateur capable d'émuler un ordinateur **PC compatible IBM** tournant sous le système d'exploitation **DOS**.  
Plusieurs types de cartes graphiques ou sonores peuvent être émulées.

Cela permet de jouer à d'anciens jeux PC sur Recalbox.

### Quelle version de DOSBox est fournie avec Recalbox ?

Bonne question: la dernière version officielle de DOSBox est la 0.74.3 . Heureusement, les développements continuent dans une version SVN pour corriger les bugs ou améliorer l'émulateur.

La version comprise dans Recalbox est la **version SVN**, complétée par certaines améliorations:

* Utilisation de SDL2 pour améliorer les performances graphiques
* Support des joysticks jusqu'à 8 axes, pour des questions de mapping \(tous les axes, hats et boutons sont désormais mappables\).
* Permet d'émuler une souris \(mouvements et boutons\) à partir du clavier ou d'un joystick
* Permet l'affichage d'un clavier virtuel \(pour des systèmes sans clavier ni souris\)

## ![](/migration-images/emulateurs/ordinosaures/dos/gerald-g-parchment-background-or-border-5.svg)**L**icence

Ce core est sous licence [**GPLv2**](https://gitlab.com/lmerckx/recalbox-dosbox/-/blob/master/COPYING).

## ![](/migration-images/emulateurs/ordinosaures/dos/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ordinosaures/dos/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :--- | :--- |
| Screenshots | Oui |
| Saves | - |
| Core options | Oui |
| Controls | Oui |
| Remapping | Oui |

## ![](/migration-images/emulateurs/ordinosaures/dos/tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](/migration-images/emulateurs/ordinosaures/dos/rom-30098_640.png)**Roms**

### **Extensions supportées**

La rom doit avoir l'extension :

* .exe
* .com
* .bat
* .conf

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁**dos**
> > > >
> > > > > 🗒**fichier.exe**

### Fonctionnement basique

Prenons un exemple simple avec **le jeu Alley Cat :**

* Commencez par **créer le répertoire** pour votre jeu **en le nomment** `AlleyCat.pc`. **La première** partie du nom du répertoire avant le '**.**' doit avoir au **maximum 8 caractères** et **ne pas contenir de caractères spéciaux.** 
* **Copiez-y** les fichiers de votre jeu \(pour les gros jeux, installez les sur votre ordinateur avant de les copier\). 
* **A l'intérieur** de AlleyCat.pc, **créez un fichier** `dosbox.bat` et **éditez** pour appeler l'executable du jeu.  **Ceci nous donne :** `c: CAT.EXE`  
* **Le disque C**: est positionné par DOSBox **sur votre le répertoire de votre jeu**  \(ici **C**: est donc **égal à** `/recalbox/share/roms/dos/AlleyCat.pc`\). **De même** pour '**.**' 
* **Rebootez** ou **rafraichissez votre gamelist** pour voir le jeu. 
* **Pour sortir** de l'émulateur, appuyez sur `CTRL+F9` sur votre clavier.

### Fonctionnement avancé

* **Ajouter** un fichier `dosbox.cfg` **dans votre répertoire** de jeu au même niveau que `dosbox.bat` vous permet de **définir une configuration** DOS spécifique pour ce jeu. 
* Vous pouvez :
  * soit **copier le fichier** `dosbox.conf` depuis `\recalbox\share\system\configs\dosbox\dosbox.conf` \(**attention** l'extension dans le répertoire du jeu doit bien être `cfg` et non `conf`\)
  * soit **utiliser** celui-ci : [https://pastebin.com/13xrJdkw](https://pastebin.com/13xrJdkw) ​
* Dans ce fichier, la **ligne** `mapperfile=mapper.map` vous permet **d'utiliser un fichier** `mapper.map` pour **mapper n'importe quelle touche clavier** ou même **la souris sur votre gamepad.** Ce fichier peut être créée **depuis votre jeu en pressant** `CTRL+F1` à n'importe quel moment et sera alors **sauvé à côté de vos fichiers** `dosbox.cfg` et `dosbox.bat`. 
* **Quelques paramètres** du fichier `dosbox.cfg` peuvent aussi **être mis au début** de votre fichier `dosbox.bat` si **vous ne voulez pas utiliser un fichier** `dosbox.cfg` spécifique mais certains de ces paramètres **ne fonctionneront pas dans le** `dosbox.bat`, tout ce qui est **graphique semble fonctionner,** mais **le paramètre mapperfile ne fonctionne pas** par exemple.

### Convertir un jeu pour l'utiliser sur Recalbox

Comment **convertir un jeu** pour l'utiliser sur Recalbox, qu'il soit **acheté sur GOG** ou **provenant de l'excellente ExoDOS Collection.**

* Tout d'abord, **copiez le contenu** du répertoire de jeu \(**renommez** le correctement avec le .pc\). 
* Nous devons ensuite **adapter le contenu du dosbox.cfg** et **du fichier bat** utilisé pour lancer le jeu.

Prenons un exemple avec **la version ExoDOS de Wacky Wheels :**

* **Ne copiez pas directement le** `dosbox.cfg` \(or .conf\) **du répertoire original** car ceci peut conduire à **des bugs dificiles à débusquer.** **Copiez plutôt le fichier standard linké plus haut**, il suffit ensuite de **vérifier si le** `dosbox.cfg` **avait une configuration spéciale** et si oui **l'utilisez dans votre** `dosbox.cfg`. Celle-ci se **trouve dans la partie** `[autoexec]` du fichier. 
* **Déplacer** tout d'abord **le contenu de cette partie au début** de votre fichier `dosbox.bat` et **adaptez les chemins**. Ici nous avons :

```text
[autoexec] cd .. cd .. mount c .\games\WackyWhe  imgmount d .\games\WackyWhe\cd\wackywheels.iso -t cdrom c: cd wackycls @wwexit
```

et cela va **nous donner une fois converti** pour Recalbox :

```text
imgmount d .\cd\wackyw~1.iso -t cdromc: cd WACKYpauseWW.EXE
```

#### Explications :

* **C**: est **déjà monté** par DOSBox \(dans le répertoire du jeu\), nous **n'en avons pas besoin.** 
* '**.**' est **également positionné** par DOSBox sur **le même répertoire**, et en **utilisant des chemins relatifs,** votre jeu ne sera **pas configuré en dur** sur un répertoire \(vous pourrez l'utiliser **dans un sous-répertoire différent** ou avec une autre distribution\). 
* **exit** est **supprimé** car ceci **est géré** par DOSBox aussi. 
* **Le chemin utilisé par** `imgmount` est simplifié et nous devons **convertir le nom d'iso** à un **nom DOS standard** \(8 caractères maximum avec les deux derniers changés à ~1, ~2, ~3 etc. si le chemin est plus long et si vous avez plusieurs fichiers du même nom\).

  Dans ce cas il vaut de toute façon mieux **changer le nom du fichier** pour quelque chose **de simple.**  

* **Les noms longs** ne sont **pas supportés dans** les fichiers **.cue** non plus, donc vous aurez peut-être à **renommer** les fichiers **.vue/.bin** manuellement et **à éditer** le fichier **.cue** pour **référencer le nouveau nom** du fichier .bin

  Et **DOSBox** peut-être plutôt strict : **pas de caractères spéciaux**, et parfois **pas de caractères majuscules.**  

* **La commande** `pause` permet de **figer l'écran** et de **débugger facilement les instructions** DOS, vous pouvez la **supprimer une fois que vous aurez vérifié** que la commande `imgmount` **fonctionne bien** \(n'utilisez pas pause après l'appel de l'exécutable du jeu ou vous ne verrez rien\). 
* **@ww** devient **WW.EXE** \(il s'agit juste de l'appel de l'exécutable du jeu\).

Et voilà ! Certains jeux **peuvent aussi utiliser un lanceur en** `.bat`, **copiez ses instructions à la fin** de votre `dosbox.bat` après **celles-provenant de la partie** `[autoexec]` **de** `dosbox.cfg` et **adaptez les.**

### Comment émuler des jeux DOS dans Recalbox ?

Ce wiki a pour objectif de vous permettre de jouer au jeu DOS via l'émulateur DOSBox mis à disposition par RecalBox.


>Il faut savoir qu'il y a une multitude de contextes possibles, chaque jeu a sa spécificité.  
>C'est pourquoi il est impossible, à l'heure actuelle, d'avoir quelque chose de "Plug&Play" sur l'émulation DOS.
>
>Cependant, dans les grandes lignes et pour la majorité des jeux, c'est à peu près toujours la même chose.
{.is-danger}

Nous allons voir 3 cas de figure ici : 1. le jeu ne nécessitant ni installation, ni support CD; 2. le jeu nécessitant une installation, mais pas de support CD; 3. le jeu nécessitant une installation et un support CD.

Mais avant cela, quelques généralités sur le fonctionnement de l'émulateur DOSBox mis à disposition par Recalbox.

### Les généralités

* Vos fichiers/dossiers de jeux seront à placer dans le répertoire "dos" du répertoire "roms"; il ne faut pas y placer un zip/rar mais bien les fichiers/dossiers du jeux après extraction d'une éventuelle archive; 
* pour nommer vos répertoires de jeu dans le répertoire "dos", deux règles importantes :
  * suffixer le nom du répertoire par ".pc", cela permet à EmulationStation de repérer le répertoire et de le lister dans l'interface;
  * pour faire simple, éviter tant que possibles les espaces \(" "\) ou caractère spéciaux/accentués dans les noms, cela simplifiera l'accès; 
* le répertoire du jeu \(celui suffixé par ".pc"\) est automatiquement "monté" en tant que "C:" dès le lancement depuis EmulationStation; ainsi, vous devez bien avoir en tête que votre contexte se limite au répertoire du jeu en cours d'exécution; le reste n'existe pas pour DOSBox; 
* à l'intérieur du répertoire du jeu \(celui suffixé par ".pc"\) on doit y placer un fichier "dosbox.bat"; ce dernier va nous permettre d’exécuter les commandes nécessaire à l'installation/configuration du jeu et à son lancement; à la mise en place d'un jeu, il faudra généralement éditer le "dosbox.bat" plusieurs fois successivement \(en lançant le jeu à chaque édition\) afin de compléter les différentes étapes nécessaire à son fonctionnement; mais ce n'est à faire qu'une seule et unique fois, une fois que le jeu est installé/configuré et fonctionne, plus besoin d'y toucher; dernier point au sujet des fichiers "dosbox.bat" : vous pouvez les éditer avec des éditeurs textes basiques \(comme notepad sous windows\); 
* les fichiers qui vont nous être important de manière générale sont ceux dont l'extension est ".bat" en priorité et ".exe" sinon; 
* un clavier/souris est, à défaut d'indispensable, fortement recommandé \(dans cette documentation nous partons du principe que vous en êtes équipé\).  


  **Les différents cas de figure**

  Nous allons exposer ci-dessous les différents cas de figure.  
  Ne lisez pas que le cas de figure qui vous intéresse, mais bien l'ensemble : certains points acquis dans les premiers cas de figure ne seront pas répétés dans les suivants.  


  **Le jeu ne nécessitant ni installation, ni support CD :**

  Le plus simple de tous les cas de figure : vous avez un jeu version disque, qui ne possède pas de fichier "install.bat" \(ou ".exe"\) ou qui, à défaut, ne nécessite pas d'installation \(le fichier "install.bat" servant parfois également à faire la configuration, notamment du son\).  
  
  Idéalement, vous avez deux fichiers clés dans le répertoire du jeu \(que ce soit en ".bat" ou en ".exe"\) : "setup" \(parfois le fichier "install" fait office de "setup"\) et un autre portant soit le nom du jeux \(par exemple "wolf3d" pour "Wolfenstein 3D" ou bien "s2" pour "settlers2" ou bien tout simplement "go" signifiant "lancer"\).

Donc créer le fichier "dosbox.bat" si ce n'est pas déjà fait, puis édité le pour qu'il contienne les lignes suivantes :

```text
setup
pause
```

L'instruction `pause` va nous permettre de demander à DOSBox d'attendre avant de "clôturer sa session" et donc de retourner sous EmulationStation.  
Cela nous permettra notamment de pouvoir lire les éventuelles erreurs retournées par l’exécution de telle ou telle commande.  
  
Une fois le fichier "dosbox.bat" édité et enregistré, retourné à EmulationStation, mettez à jour la liste des jeux \(si ça n'a pas déjà été fait une fois depuis la création du fichier dosbox.bat\), et lancé le jeu !  
  
Vous arrivez dans le programme de configuration du jeu. Ce dernier est surtout intéressant pour configurer le son.  
Chaque "setup" est différent mais en règle général on vous propose un menu en anglais avec "setup sound...".  
Vous devez sélectionner \(pour le "midi" ET pour le "sound effect" si la différence est faite\) l'entrée "Sound Blaster 100% compatible" et le paramétrage automatique \(ou à défaut, tous les choix par défaut que l'on vous proposera\).  
  
Parfois, un test vous est proposé ce qui vous permettra de constater que tout est OK.  
Une fois cela fait, vous pouvez quitter le setup \(il y a une entrée dans le setup à cet effet, pensez bien à sauvegarder les modifications si l'on vous pose la question\).  
Vous aurez alors un "prompt" vous demandant de presser une touche pour passer l'instruction pause : exécutez-vous après avoir constaté un éventuel message d'erreur.

Après retour sur l'interface EmulationStation, éditez le fichier "dosbox.bat" comme suit \(nous prenons ici l'exemple du fichier exécutable cité précédemment "s2.bat" pour "Settlers 2", remplacé "s2" par le nom du fichier ".bat" ou ".exe" correspondant au jeu traité\) :

```text
s2
pause
```

Sauvegardé, puis lancé le jeu à nouveau. Et normalement tout fonctionne ;-\)  
Si ce n'est pas le cas, exposez votre problème sur le forum ou Discord, en précisant les messages d'erreurs éventuellement capté.

### Le jeu nécessitant une installation, mais pas de support CD

Le principe est le même que dans le cas de figure précédent, mais avec l'étape d'installation en plus.  
Si le cas de figure précédent ne vous a pas donné satisfaction, c'est probablement que le jeu nécessite d'être installé.  
Afin d'éviter toute confusion de fichier, je vous conseille de créer un sous répertoire "source" dans le répertoire type ".pc" et de placer les fichiers/dossiers du jeu dans celui-ci.  
Assurez-vous de bien avoir un fichier "install" \(que ce soit en ".bat" ou en ".exe" - parfois en fichier "setup" propose également l'option d'installation\).  
Puis créez/éditez le fichier "dosbox.bat" comme suit :

```text
cd source
install
pause
```

Lancé à nouveau le jeu depuis EmulationStation, cette exécution vous mène au programme d'installation.  
Parfois similaire à la présentation du "setup" classique, il a une option supplémentaire proposant l'installation.  
Tout comme le "setup", il n'y a rien d'universel ou de standard, il faut donc s'adapter.  
Mais les intitulés, bien que souvent anglophone, sont généralement clairs.  
Lors du processus d'installation, un chemin vous sera demandé.  
  
Assurez-vous qu'il soit renseigné comme suivant :

```text
c:\cible
```

Le nom "cible" est un exemple \(il faut ici écho au nom "source" précédemment utilisé\), vous pouvez le remplacer par ce que vous souhaitez, mais dans cette documentation nous partirons sur le principe qu'il s'appelle "cible".  
Une fois l'installation terminé, procédé à la configuration du son si elle vous est proposée. Ensuite, quitter le programme d'installation.  
Vous arrivez sur le prompt provoqué par "pause", encore une fois cela vous permet de relever les éventuelles erreurs renvoyées.  
Appuyer sur une touche pour revenir à EmulationStation.

Ensuite, process est similaire au cas de figure précédent si ce n'est qu'il faut ajouter l'accès au répertoire "cible" en plus.

Donc pour configurer le son, si ça n'a pas déjà été fait et avec l'exemple d'un fichier nommé "setup", votre fichier "dosbox.bat" doit ressembler à cela :

```text
cd cible
setup
pause
```

Lancé de nouveau l'entrée, et procédé comme indiqué dans le cas de figure précédent.

Ensuite, une fois toute installation/configuration OK, vous pouvez procéder au lancement du jeu en lui-même.  
Votre fichier "dosbox.bat" doit alors contenir les lignes suivantes :

```text
cd cible
s2
pause
```

Et, normalement, le tour est joué ;-\).


>_**Remarque :**_
>
>Le répertoire "source" n'est parfois plus utile après installation, ce genre d'installation étant faites à l'époque pour simplement copier le contenu de la disquette sur disque dur pour se passer du support amovible. A tester.
{.is-warning}

### Le jeu nécessitant une installation et un support CD

Ce dernier cas de figure a de nombreux points communs avec le cas précédent, avec deux différences majeures :

* il va être nécessaire de "monter" le CD sur un lecteur CD virtuel \(pas de panique, en une ligne de commande ce sera fait ;-\) \);
* en règle générale il sera nécessaire de conserver le montage du CD afin de faire fonctionner le jeu ou, à minima, de bénéficier de contenu supplémentaires "in game" tel que des cinématiques et/ou des musiques.

Donc, dans un premier temps, nous allons créer un répertoire "source\_cd" en racine de notre répertoire suffixé ".pc". Ce dernier va recevoir le ou les fichiers image CD \(bin, cue, iso, img, ...\).

Par rapport au cas précédent \(un jeu sur support CD nécessitant toujours une installation\), la différence majeure est donc le montage de l'image CD sur un lecteur CD virtuel. La ligne de commande utilisée pour cela va légèrement varié en fonction du format de l'image CD. Quelques exemples \(en dos, les noms excédant 6 ou 7 caractères - j'ai un doute - sont tronqué avec "~x"\) :

* format bin/cue : `imgmount D "C:\source~1\settle~1.cue" -t iso -fs iso`
* format iso : `imgmount D "C:\source~1\settle~1.iso" -t iso -fs iso`
* format img : `imgmount D "C:\source~1\settle~1.img"`
* format fichier/dossier directe \(là, le montage n'est pas indispensable, sauf pour profiter d'éventuels contenus supplémentaire\) : `mount D "C:\source~1"`

Certains CD de jeu sont des CD "mixtes". C'est à dire qu'ils comportent les données de jeu ainsi que les pistes audio qui permettront de jouer la musique dans le jeu.  
Il est important pour ces CD que l'image soit contenue dans un seul fichier .img ou .bin car DOSBOX ne supporte pas les images CD splittées en plusieurs fichiers .bin.  
Le montage devra alors se faire impérativement via le fichier .cue correspondant pour que toutes les pistes audio soient correctement chargées.

A l'exception de cette ligne de montage, le reste est quasi identique au cas de figure précédent.  
Il faut simplement ajouter la ligne "mount ..." en début de fichier "dosbox.bat" de manière systématique puis procéder à l'installation, la configuration, puis le lancement du jeu.  
Attention aussi a bien se déplacer dans le bon répertoire \(commande "cd"\) : ainsi il faut faire `cd source_cd` pour l'installation, puis `cd cible` pour accéder au répertoire du jeu \(comme dans le cas de figure précédent\).


>_**Information :**_
>
>Une fois qu'un jeu est fonctionnel, vous pouvez retirer l'instruction "pause" afin d'éviter de subir le prompt de temporisation à chaque sortie du jeu.
{.is-info}

## ![](/migration-images/emulateurs/ordinosaures/dos/hammer-28636_640.png)Configuration avancée de l'émulateur

### Comment utiliser le clavier virtuel ?

Par défaut, le clavier virtuel s'ouvre avec Ctrl-F2.  
Mais un nouveau bouton est disponible dans le mapper \(Ctrl-F1 &gt; _Virt Keyb_\) pour l'associer à une autre événement \(clavier, souris ou joystick\).

Une fois ouvert, utilisez la souris ou le joystick pour sélectionner et actionner les touches:

* Utiliser le bouton gauche de la souris ou le premier bouton du joystick simule une simple pression-relâcher de la touche. 
* Utiliser le bouton droit de la souris ou le second bouton du joystick simule une pression maintenue de la touche \(la touche devient plus foncée\).

  Cliquez à nouveau avec n'importe quel bouton de la souris ou du joystick pour la relâcher.

  Cela permet de réaliser des combinaisons avec Shift, Ctrl ou Alt.

Finalement, appuyez sur le bouton V vert pour fermer le clavier virtuel et envoyer les événements à DOSBox. Il est aussi possible de presser la croix rouge pour annuler les événements et fermer le clavier virtuel.


>_**Attention :**_
>
>* Si vous utilisez un fichier de mapping existant, la combinaison par défaut Ctrl-F2 ne sera pas configurée 
>* Si vous quittez le clavier virtuel avec une touche maintenue, cet événement sera constamment envoyé à DOSBox, jusqu'à ce que vous ouvriez à nouveau le clavier virtuel ! 
>* Tous les mappings configurés du joystick ou de la souris seront ignorés tant que le clavier virtuel est ouvert
{.is-danger}

## Dépannage \(dans `dosbox.cfg`\) <a id="depannage-dans-dosbox-cfg"></a>

* **L'image est déformée :** Pour certains vieux jeux, vous aurez peut-être à modifier le paramètre `aspect=false` en `aspect=true` pour obtenir une image en 4/3 ratio. Attention sur des jeux plus récents, ceci pourrait conduire à un problème de performances. 
* **Le joystick bouge tout seul :** Essayez de modifier `timed=false` en `timed=true`. Ceci peut-être dû aux deadzone des joysticks également et malheureusement il n'y aucun moyen de configurer celle-ci dans DOSBox pour le moment. 
* **On ne peut pas mapper le D-pad d'une manette xbox360 :** Oui, le mapper DOSBox permet de configurer le D-PAD mais ça ne marche pas en jeu, vous pouvez peut-être essayer de changer le type de joystick. 
* **Comment configurer la deadzone d'un joystick :** Malheureusement ce n'est pas possible dans DOSBox pour le moment. 
* **CD Not Found / CD Driver not present :** Vous avez du mal renommé vos fichiers cd \(io, cue, bin, edition du cue\) ou utiliser des noms ne respectant pas le standard DOS \(voir adv. rundown\). 
* **Je n'arrive pas à faire marcher** `mount a` **ou** `mount d` **:** Contrairement à imgmount, la commande mount ne peut pas utiliser des chemins 'virtuels' de l'intérieur de la machine DOSBox. Pour que `mount` marche, vous ne pouvez utiliser que des chemins réels locaux du file system de recalbox. Comme '.' est positionné sur le répertoire root / au lancement de DOSBox, il est obligatoire d'utiliser le chemin absolu complet vers le fichier ou le répertoire. 
* **Le mapper est bugué, il efface mon fichier ou mélange mes boutons :** Vous êtes vraisemblablement victime du paramètre `buttonwrap`. Quand celui-ci est mis à true, il configure les boutons de votre pad avec une id supérieure à celle du nombre de boutons du joystick émulé en repartant à zéro \(5 sera remappé à 0, 6 à 1, etc...\) . Mettez ce paramètre à false et tout devrait rentrer dans l'ordre.

## ![](/migration-images/emulateurs/ordinosaures/dos/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github utilisé :** [https://gitlab.com/lmerckx/recalbox-dosbox/](https://gitlab.com/lmerckx/recalbox-dosbox/)
* **Doc Libretro :** [https://docs.libretro.com/library/dosbox/](https://docs.libretro.com/library/dosbox/)
* **Wiki du core :**[ https://www.dosbox.com/wiki/](https://www.dosbox.com/wiki/)
* **Liste des jeux :** [https://www.dosbox.com/wiki/GAMES](https://www.dosbox.com/wiki/GAMES)
* **Jeux jouable :** [https://www.dosbox.com/comp\_list.php?letter=playable](https://www.dosbox.com/comp_list.php?letter=playable)

