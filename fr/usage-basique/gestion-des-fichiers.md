---
title: Gestion des fichiers
---

# Gestion des fichiers

**Recalbox** vous permet de gérer vos fichiers via le [dossier "share"](/fr/usage-basique/gestion-des-fichiers).

Vous avez deux possibilités :

* [En connexion direct](/fr/usage-basique/gestion-des-fichiers)
* [Par le réseau](/fr/usage-basique/gestion-des-fichiers)

## I - Dossier "Share"


>**Information :**
>
>Le dossier **"Share"** est celui qui vous permet de **gérer le contenu** de votre Recalbox, il est disponible **via le réseau**.
{.is-info}

![](./image%20%2822%29.png)



Il est constitué de **plusieurs répertoires** :

* **bios**

![](./image%20%2838%29.png)

Placez ici **les bios** dont Recalbox a besoin, vous pouvez consulter la liste des bios nécessaires via le **Web-Manager.**


>**Remarque :**
>
>Certains émulateurs exigent d'avoir le bios dans un sous-dossier ou d'une copie en plus dans son répertoire roms. Référez-vous à la documentation des émulateurs.
{.is-warning}

* **cheats** Contenu des cheats **téléchargeables via le menu Retroarch.**
* **extractions** Répertoire où vos roms zippées, s'extraient avant de lancer le jeu.
* **kodi** Placer ici **les médias** que vous souhaiter intégrer à Kodi dans les sous-répertoires correspondant.
  * music
  * movie
  * picture
* **lost+found** Répertoire où, quand un disque crashe, pour une raison ou pour une autre, on utilise le programme fsck pour le réparer \(équivalent de scandisk\); c'est là qu'il dépose les fragments de fichiers perdus.
* **music** Placez ici vos fichiers pour remplacer la musique par défaut de background dans emulationstation.


>**Remarques :**  
>  
>Les fichiers doivent être **aux formats mp3 ou ogg** et avoir un **taux d'échantillonnage de 44100Hz** et un **débit supérieur à 256 kb / s**.
{.is-warning}

* **overlays**

  Placez ici vos overlays pour habiller les contours de votre écran quand un jeu est lancé.

* **roms**

  Placez ici vos roms dans les sous-répertoires correspondant à la console souhaitée.

* **saves** Répertoire où vos sauvegardes de jeux sont stockées.
* **screenshots** Répertoire où vos screenshots de jeux sont stockés.
* **system** Répertoire relatif aux configurations et système de Recalbox.
* **themes** Placez ici vos thèmes pour l'interface d'EmulationStation de votre Recalbox.

## II - Transfert de fichier

Pour **ajouter vos fichiers** \(roms, sauvegardes de jeux, bios, données de scrap etc...\) sur votre **périphérique de stockage**, vous avez deux possibilités :

### 1 - En connexion direct


>**Remarque :**  
>Sous réserve de logiciel sous Windows si stockage SD système
{.is-warning}

* Connecter votre support de stockage à votre ordinateur.
* Ouvrez **l'explorateur de fichier** sur votre OS.
* Allez dans l'onglet **Périphériques.**
* Sélectionner **le nom de votre support de stockage.**
* Puis **Recalbox**.
* Et enfin **Share**.
* **Copier** vos fichiers dans le répertoire souhaité.
* Une fois **le transfert terminé**, il ne vous reste plus qu'à **rebrancher** votre périphérique **à votre Recalbox**, l'allumer et jouer.

### 2 - Par le réseau


>**Information :**
>
>Lorsque vous **configurez votre wifi** ou **branchez un câble réseau** sur Recalbox, celle-ci **partage automatiquement** des dossiers sur le **réseau local**.
{.is-info}

* Une fois votre machine **connectée** en wifi ou en câble.
* Ouvrez **l'explorateur de fichier** sur votre OS.
* Allez dans l'onglet **Reseaux**.
* Puis **Recalbox**.
* Et **Share**.
* **Copiez** vos fichiers dans le répertoire souhaité.


>**Remarque :**
>
>Si vous ne **voyez pas votre Recalbox** sur le réseau, essayez de taper **\\RECALBOX** dans la barre d'adresse de l'explorer. 
>
>Si cela ne fonctionne toujours pas, 
>
>* Aller dans le menu de votre Recalbox,
>* **"OPTIONS RÉSEAU**"
>* **Notez** votre **adresse IP**
>* Puis **tapez alors votre IP** dans la **barre d'adresse de explore**r
>
>\(exemple : **\\192.168.1.30**\)
>
>Si cela ne fonctionne toujours pas et que vous êtes sur Windows 10, vous pouvez aussi suivre [ce tutoriel](/fr/tutoriels/reseau/partage/windows-10-impossible-dacceder-a-recalbox-depuis-le-partage-reseau).
{.is-warning}

### 3 - Pour que les ajouts apparaissent :

* Mettre à jour la liste des jeux :

  * Menu EmulationStation \(Start\).
  * Option de l'interface.
  * Mettre à jour la liste des jeux.

* Redémarrer votre Recalbox :
  * Par le Menu EmulationStation :

    * Menu EmulationStation \(Start\).
    * En bas dans le menu "."
    * Redémarrer

    ou

  * Par le raccourci :
    * Faites Select
    * Redémarrer

## III- Ajouter du contenu

### 1 - Ajouter des jeux

Il vous suffit de **copier** vos fichiers de roms dans le **répertoire correspondant à la console.**


>**Exemple pour la Super Nintendo:**
>
>`share/roms/snes`
{.is-success}

Vous pouvez utiliser des **roms compressées** \(**.zip, .7z\)** ou des **roms décompressées** selon l'émulateur.


>Pour plus d'informations sur le **formats des roms qui sont supportées** par un émulateur.  
>Veuillez **consulter le fichier "Lisez-moi"** présent dans **chaque dossier de roms**.
{.is-info}

### 2 - Ajouter des **bios**


>Certains émulateurs nécessitent un bios afin d'émuler les jeux correctement.
{.is-warning}

* Si vous souhaitez **ajouter un BIOS** dans votre système, **ouvrez le dossier BIOS** partagé via **Samba** ou aller directement à **/recalbox/share/bios/** 
* Vos "**noms de BIOS" et code "CRC"** doivent correspondre à **la liste** présente dans le [**Bios Manager**](/fr/usage-basique/fonctionnalites/bios-manager)**.**

Pour **vérifier la signature d'un BIOS**, se référer à la page ["Tutoriel MD5 - Vérifier l'empreinte MD5 d'une rom ou bios"](/fr/tutoriels/utilitaires/gestion-des-roms/verifier-lempreinte-md5-dune-rom-ou-bios)


>* **Neo-Geo :** vous devez ajouter le BIOS**`neogeo.zip`**dans le dossier **rom de l'émulateur avec vos jeux Neo-Geo /recalbox/share/roms/neogeo ou /recalbox/share/roms/fbneo** 
>* **Neo-Geo CD** : vous devez ajouter le bios**`neogeo.zip`** et **`neocdz.zip`** dans le dossier **/recalbox/share/bios/**
{.is-danger}

Exemple :

Le nom et l'empreinte du BIOS doivent être les mêmes que ci-dessous \(par exemple, `neogeo.zip` doit provenir de la version romset requise\) :

```text
FBA and FBA Libretro
798e5538be8b6557e7c4529f52d2938c  neogeo.zip
Mame (Pimame4all)
12f370a3fc42c3e413c4a0771d6d089f  neogeo.zip
```

