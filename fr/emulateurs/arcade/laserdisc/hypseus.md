---
title: Hypseus
---

# Hypseus

**Hypseus** pour l'émulation **des jeux d'arcade sur disque-laser,** est un fork de Daphne écrit par Jeffrey Clark pour lui apporter **quelques améliorations :**

* Mise à jour du décodeur MPEG2
* Supporte SDL2
* Etc...

## ![](./gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence :

**Hypseus**, Multiple Arcade Laserdisc Emulator  
 Copyright \(C\) 2016 [Jeffrey Clark](https://github.com/h0tw1r3)

**Daphne**, the First Ever Multiple Arcade Laserdisc Emulator  
 Copyright \(C\) 1999-2013 [Matt Ownby](http://www.daphne-emu.com/site3/statement.php)**GPLv2**

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |


## ![](./tqfp32.svg)BIOS <a id="bios"></a>


>**Aucun bios n'est requis.**
{.is-success}

## ![](./rom-30098_640.png)**Roms** <a id="roms"></a>

### Comment jouer à des jeux disque-laser sur Recalbox ?

* Pour **ajouter un jeu sur disque-laser**, vous avez besoin des **deux composants d'un tel jeu** :
  * L'image du disque-laser original, qui contient les contenus vidéo et audio
  * Le fichier ROM, qui est le programme du jeu

**La ROM** est un simple **fichier ZIP** qui doit être **copié sous le sous-répertoire** `roms/daphne/`.

* **L'image du disque-laser** est constitué de **plusieurs fichiers:** 
  * **Un ou plusieurs fichiers vidéo** \(`*.m2v`\)
  * **Un ou plusieurs fichiers audio** \(`*.ogg`\)
  * **Un ou plusieurs fichiers d'index** \(`*.dat`\) : Peuvent être **créés** par l'émulateur **au premier lancement** \(opération lente\)
  * **Un fichier frame** \(`.txt`\) : Pour **associer les numéros de frame aux fichiers vidéo.** 
* **Tous ces fichiers** doivent être **copiés dans un répertoire avec une extension** `.daphne`, **sous le répertoire**  `.daphne`  
* **La première ligne** de votre ficher **txt** est **un chemin et doit être .** \(juste le caractère point\), **modifiez là si ce n'est pas le cas.** 
* Vous pouvez aussi **créer un fichier avec l'extension** `.commands` pour passer à l'émulateur des **paramètres spécifiques à un jeu.** Voir **ci-dessous** pour **plus de détails.** 
* **Le répertoire, le fichier frame et le fichier commands** doivent **porter le même nom que le fichier ROM !** \(seules les extensions diffèrent\) 

Voici un exemple de la **structure attendue pour le jeu Dragon's Lair:**

```text
daphne
|- roms
|  |- dle21.zip
|- dle21.daphne
|  |- dle21.txt
|  |- dle21.commands
|  |- *.m2v
|  |- *.ogg
|  |- ...
```

### Où puis-je trouver les jeux ?

* **Certains jeux** peuvent être **directement et légalement téléchargés** par l'outil **DaphneLoader** de la [distribution Windows de Daphne](http://www.daphne-emu.com/site3/index_hi.php). 
* **Pour d'autres** \(Dragon's Lair, Dragon's Lair II, Space Ace, ...\), vous devez prouver que vous **possédez une licence valide du jeu** \(version DVD par exemple\).

Une fois téléchargé, **copiez les fichiers nécessaires** \(ROM et fichiers d'image du disque-laser\) sur votre Recalbox, comme expliqué ci-dessous.

### **Emplacement**

Placer vos roms **Daphné** dans le dossier : `/recalbox/share/roms/daphne`

## Configuration de base

Configuration de base requise pour le fonctionnement des jeux.

### Jeux supportés et configuration recommandée

**Pour chaque jeu,** la table suivante décrit :

* **Le niveau de compatibilité** de l'émulateur. 
* **Le fichier ROM recommandé** pour une meilleure expérience. 
* **Le contenu recommandé du fichier commands :** pour une difficulté normale, 5 vies, crédit minimum, etc...

| Nom du jeu | Compatibilité | ROM recommandée | commands |
| :--- | :--- | :--- | :---: |
| Astron Belt | \*\* | astron.zip | `-bank 0 00000000 -bank 1 01000000` |
| Badlands | _\*_ | badlands.zip | `-bank 0 00000000 -bank 1 10000010` |
| Bega's Battle | **\*** | bega.zip | `-bank 0 00000000 -bank 1 00000001` |
| Cobra Command | _\*\*_ | cobraconv.zip | `-bank 0 11010000 -bank 1 00010001` |
| Dragon's Lair | **\*** | dle21.zip | `-bank 1 00110111 -bank 0 10011000` |
| Dragon's Lair II | _\*\*_ | lair2.zip | ​ |
| Esh's Aurunmilla | _\*\*_ | esh.zip | ​ |
| Galaxy Ranger | **\*** | galaxy.zip | `-bank 0 00000000 -bank 1 00000000` |
| GP World | \* | gpworld.zip | ​ |
| Interstellar Laser Fantasy | **\*** | interstellar.zip | `-bank 0 00100001 -bank 1 00000000` |
| M.A.C.H. 3 | **\*** | mach3.zip | `-bank 0 01000100` |
| Road Blaster | **\*** | roadblaster.zip | ​ |
| Space Ace | _\*\*_ | sae.zip | `-bank 1 01100111 -bank 0 10011000` |
| Super Don Quix-Ote | **\*** | sdq.zip | `-bank 0 00100001 -bank 1 00000000` |
| Us Vs Them | **\*** | uvt.zip | `-bank 0 00000000` |
| Autres jeux | non testés | ​ | ​ |

### Qu'est-ce que le fichier commands ? <a id="quest-ce-que-le-fichier-commands"></a>

Comme expliqué précédemment, **ce fichier** doit être **créé dans le répertoire du jeu**, avec le **même nom que le fichier ROM** mais avec **l'extension** `.commands`.  
Il vous permet de passer **des paramètres additionnels** à l'émulateur pour **un jeu spécifique.**  
  
La plupart de temps, il contient **l'option** `-bank`, qui **définit la configuration du jeu** \(aussi connu sous le nom **DIP switch**\) :

* Nombre de crédits pour une partie 
* Nombre de vies pour un crédit 
* Niveau de difficulté 
* Etc...


>**Informations :**
>
>Des **valeurs recommandées** pour les jeux les plus courants sont décrites plus loin, mais vous pouvez consulter le site [LaserDisc Game Tech Center](http://www.dragons-lair-project.com/tech/%3E) pour **obtenir les informations complètes.**   
>  
>Veuillez aussi noter que, pour **un même jeu, les DIP switch peuvent varier d'une version de ROM à une autre.**
>
>**D'autres paramètres** sont aussi possibles.
>
>**Vérifiez** le[ Wiki de Daphne](http://www.daphne-emu.com/mediawiki/index.php/CmdLine) pour **plus de détails.**
{.is-info}

**Exemple pour Dragon's Lair \(DLE 2.x\):**   
  
`-bank 1 00110111 -bank 0 10011000`   
  
La page [http://www.dragons-lair-project.com/tech/dips/dle20.asp](http://www.dragons-lair-project.com/tech/dips/dle20.asp) nous indique que:

* Le son est toujours présent, avec la voix du narrateur \(même en dehors d'une partie\)
* 1 pièce = 1 crédit
* 1 crédit = 5 vies
* Pas de test ou diagnostique
* Mode de jeu standard

### Boutons du joystick


>**Information :**
>
>Un seul joystick est supporté, **seulement le joueur 1.**
{.is-info}

* **Utilisez le stick gauche** pour **les déplacements** et **les boutons standards** pour **les actions.**


>Pour la plupart des jeux, **seul le bouton B** est utilisé \(A pour les contrôleurs Xbox, X pour Playstation\).
{.is-danger}

* **Ajoutez une pièce** avec **le bouton select** et **démarrez une partie** avec **le bouton start**.
* Pour **quitter l'émulateur**, appuyez sur **le bouton hotkey**.
* **Si hotkey** correspond à **un bouton déjà utilisé** \(select, par exemple\), **le bouton** **pagedown** est utilisé **pour quitter.**

## ![](./hammer-28636_640.png)Configuration avancée des émulateurs <a id="configuration-avancee-des-emulateurs"></a>


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
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

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes** <a id="liens-exterieur"></a>

* **Github :** [https://github.com/btolab/hypseus](https://github.com/btolab/hypseus)
* **Site Officiel :** [http://www.daphne-emu.com/site3/index\_hi.php](http://www.daphne-emu.com/site3/index_hi.php)
* **FAQ :** [http://www.daphne-emu.com/site3/FAQ\_USA.php](http://www.daphne-emu.com/site3/FAQ_USA.php)
* **Wiki du core :** [https://www.daphne-emu.com:9443/mediawiki/index.php/Main\_Page](https://www.daphne-emu.com:9443/mediawiki/index.php/Main_Page)

