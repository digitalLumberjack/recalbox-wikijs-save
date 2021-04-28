---
title: ScummVM
---

# ScummVM

## Qu'est-ce que SCUMM ? <a id="quest-ce-que-scumm"></a>

**Script Creation Utility for Maniac Mansion** \(SCUMM\) est un moteur de jeu vidéo développé par Lucasfilm Games, renommé ensuite LucasArts, pour faciliter le développement de son premier jeu d'aventure graphique Maniac Mansion \(1987\).  
Il fut ensuite réutilisé comme moteur pour les jeux d'aventure suivants de **Lucasarts.**

Il se situe entre le moteur de jeu et le langage de programmation, permettant aux designers de créer de endroits, objets et séquences de dialogues sans écrire de code.  
  
Cela permet aussi au scénario et aux fichiers de données d'être indépendants de la plateforme. SCUMM est aussi le réceptacle de moteurs de jeu embarqués, tels que Interactive **MUsic Streaming Engine** \(iMUSE\), **INteractive Streaming ANimation Engine** \(INSANE\), **CYST** \(le moteur d'animation dans le jeu\), **FLEM** \(endroits et noms des objets dans une pièce\), et **MMUCUS**.

**SCUMM** a été porté sur **les** **plateformes suivantes**: 3DO, Amiga, Apple II, Atari ST, CDTV, Commodore 64, Fujitsu FM Towns & Marty, Apple Macintosh, Nintendo Entertainment System, DOS, Microsoft Windows, Sega CD \(Mega-CD\), et TurboGrafx-16/PC Engine.

## Qu'est-ce que ScummVM ? <a id="quest-ce-que-scummvm"></a>

**ScummVM** est un programme qui vous permet de jouer à certains jeux d'aventure graphiques **point-and-click**, à partir du moment où vous fournissez les fichiers du jeu.  
  
L'idée derrière cela est que **ScummVM** remplace juste les exécutables du jeu, vous permettant **d'y jouer sur des systèmes** pour lesquels il n'était **pas prévu initialement** !

## Comment jouer à des jeux ScummVM sur Recalbox ? <a id="comment-jouer-a-des-jeux-scummvm-sur-recalbox"></a>

Pour **ajouter un jeu** ScummVM :

* **créez** un dossier avec le nom court du jeu, suivi par **l'extension ".scummvm"** et **copiez-y les fichiers du jeu**. 
* Dans ce dossier, vous devrez **ajouter un simple fichier**, nommé **\[nom court\].scummvm**


>Vous pouvez trouver les noms courts des jeux supportés sur la page [http://scummvm.org/compatibility/](http://scummvm.org/compatibility/)​
{.is-info}


>**Astuce :**  
>Ajouter le **`Nom long`** du site précédent comme contenu du fichier \[nom court\].scummvm.  
>Cela permettra au scraper de le détecter plus facilement.
{.is-success}

**Par exemple**, vous pouvez **copier** le jeu **"Broken Sword"** dans le répertoire **"Broken Sword 1.scummvm"** sous le répertoire **scummvm**.  
Dans ce répertoire, **créez un fichier** nommé **sword1.scummvm**

```text
scummvm
|- Broken Sword 1.scummvm
|  |- sword1.scummvm
|  |- ... autres fichiers du jeu
```


>Le **nom de ce répertoire** sera affiché comme **nom du jeu** dans le menu **Recalbox**.
>
>* Sélectionnez-le pour démarrer le jeu 
>* Vous pouvez quitter le jeu et obtenir les options ScummVM en utilisant le raccourci _Ctrl_ + _F5_.
{.is-info}

## Est-ce que tous les jeux Scumm sont compatibles ? <a id="est-ce-que-tous-les-jeux-scumm-sont-compatibles"></a>

Veuillez lire la [liste de compatibilité](http://scummvm.org/compatibility/%3E) sur le site Web de **ScummVM.**


>Il contient une **liste à jour** des **jeux supportés** et leur **niveau de compatibilité.**
{.is-info}

## Comment configurer l'émulation Roland MT-32 pour les jeux ScummVM ? <a id="comment-configurer-lemulation-roland-mt-32-pour-les-jeux-scummvm"></a>

* D'abord, vous devez **copier** les ROMs MT32 \(**MT32\_CONTROL.ROM** et **MT32\_PCM.ROM**\) dans un répertoire, par exemple **/recalbox/share/bios.** 
* Ensuite, **éditez** votre fichier de configuration ScummVM \(**scummvm.ini** ou **.scummvmrc**\) et **ajoutez les lignes** suivantes dans la section `[scummvm]`:

```text
extrapath=/recalbox/share/bios
mt32_device=mt32
music_driver=mt32
```

\*\*\*\*

**Autre solution:**  
Vous pouvez aussi simplement **copier les deux fichiers ROMs** dans le **répertoire du jeu**.


>Ainsi, **pas besoin de modifier** le fichier de configuration, mais ces fichiers seront alors **dupliqués pour chaque jeu** nécessitant la **musique Roland** !
{.is-info}

Vous devez utiliser les **fichiers ROM supportés** par ScummVM.

**Par exemple**, avec les **signatures MD5** suivantes:

```text
5626206284b22c2734f3e9efefcd2675  MT32_CONTROL.ROM
89e42e386e82e0cacb4a2704a03706ca  MT32_PCM.ROM
```

