---
title: CHDMAN
description: Convertir vos roms CD en un format compressé lisible.
---

# CHDMAN

## I - Introduction

Les formats de fichiers à adopter pour les CDs et autres supports optiques.

Nous avons parlé d'un format, dérivé de recherches dont nous avons eus sur MAME, afin de pouvoir représenter au mieux ces supports, de manière compressée, sans perdre l'intégrité des données et que celles-ci puissent rester scrappables.

Ce format est le CHD \(Compressed Hunks of Data\), datas qui pourraient être pratiques pour les consoles SEGA CD, PS1, PC Engine...

Malheureusement, l'utilisateur classique aura du mal à utiliser le convertisseur, qui est un exécutable en ligne de commandes.

Voici donc un fichier Zip, avec des scripts automatisés, pour passer du format BIN+CUE \(format Redump\) vers CHD, et inversément. 

Il à été ajouté aussi pour le format GDI, qui est pour la Dreamcast  
Pour les jeux PS1 protégés par LibCrypt, normalement vous avez des fichiers SBI \(Subchannel Information\), vous les conservez et les mettre avec les CHDs, sinon vos jeux ne passeraient pas.

Si jamais vous lez perdez ou mauvaise manipulation, ces fichiers sont disponibles sur les fiches de chaque disque correspondant chez Redump, à côté des fichiers CUE retéléchargeables.


>Évitez d'utiliser pour le moment avec vos sets Saturn, sinon dans les bug reports/fiches d'incident utilisateur sur les émulateurs, les demandes seront invalidées côté RetroArch ou chez les devs des cores carrément.
{.is-warning}

## II - Logiciel

{% tabs %}
{% tab title="Windows" %}
Vous pouvez télécharger le logiciel en cliquant sur **CHDMAN.zip** ci-dessous.

![Type de fichier joint&#xA0;: archive](https://discord.com/assets/73d212e3701483c36a4660b28ac15b62.svg)[CHDMAN.zip](https://cdn.discordapp.com/attachments/438686828418039818/776962833412784128/CHDMAN.zip)

Dans ce zip vous trouverez 6 fichiers :

* **chdman.exe** Le logiciel CHDMAN.
* **CUE or GDI to CHD.bat** Un fichier .bat qui vous permet de convertir vos roms aux formats CUE ou GDI en CHD.
* **Extract CHD to CUE.bat** Un fichier .bat qui vous permet de convertir vos roms au format CHD en BIN+CUE.
* **Extract CHD to GDI.bat** Un fichier .bat qui vous permet de convertir vos rom au format CHD en GDI.
* **README\_EN.txt**
* **README\_FR.txt**

### Contenu du fichier Readme

* **CUE or GDI to CHD**

  Compresse tous types de fichiers disques BIN avec un entête CUE ou GDI vers le format CHD \(v5\).  
  Recherche tous les sous-dossiers et crée des fichiers CHD \(v5\) dans le dossier dans lequel les fichiers sont placés avec CHDMAN.

* **Extract CHD to CUE** Décompresse un fichier CHD \(V5\) en fichier BIN+CUE. Le format CUE est utilisé par les jeux sur CD.  Sur le Raspberry Pi, CHD est pris en charge par TurboGrafx-CD / PC Engine CD, Sega CD / Mega CD et Dreamcast.
* **Extract CHD to GDI**

  Décompresse un fichier CHD \(V5\) vers GDI. \(GDI est un format disque pour Dreamcast\).
{% endtab %}

{% tab title="macOS" %}
CHDMAN existe pour macOS via Homebrew.

* **Installation de** [**Homebrew**](https://brew.sh/index_fr)\*\*\*\*

Vous devez utiliser la commande suivante dans le Terminal :

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

* **Installation de** [**rom-tools**](https://formulae.brew.sh/formula/rom-tools)\*\*\*\*

Vous devez utiliser la commande suivante dans le Terminal un fois Homebrew installé :

`brew install rom-tools`
{% endtab %}
{% endtabs %}

## III - Utilisation automatisé avec les fichiers .bat

Ce qui suit est valable pour Windows seulement.

### 1 - Convertir votre jeu en CHD

* Placer "**chdman.exe**" et "**CUE or GDI to CHD.bat**" dans le dossier contenant votre jeu comme ci-dessous

Exemple pour le jeu "**Grandia \(France\)**" :

![](./image%20%28193%29.png)

* Puis cliquer sur le fichier "**CUE or GDI to CHD.bat**" pour lancer la conversion.

![](./image%20%28288%29.png)

* Une fois que la fenêtre CMD ci-dessus c'est fermé automatiquement, votre conversion est terminer.

![](./image%20%28204%29.png)

* Vous pouvez supprimer "**chdman.exe**" et "**CUE or GDI to CHD.bat**", votre rom est prête.

![](./image%20%28217%29.png)


>Vous pouvez également lancer le fichier.bat pour lancer la conversion de plusieurs jeux d'un coup.
{.is-info}


>Pour les roms multi-disques pour votre confort, vous devriez [créer le fichier m3u](/fr/tutoriels/utilitaires/conversion-des-roms/chdman).
{.is-warning}

### 2 - Créer le fichier m3u

En conversion CHD pour les jeux multi-disques, il faut faire un fichier **M3U** pour déclarer tous les disques.

Le fichier au format m3u est une liste des différents CD pour un même jeu qui permet de passer d'un cd à un autre de façon simple en utilisant la combinaison de changement du disque \(`HK` + `STICK G.` vers la _GAUCHE_ ou vers la _DROITE_\).

Exemple pour le jeu "**Grandia \(France\)**" :

* Créer un fichier m3u via notepad++ :
  * 🗒 Grandia \(France\).m3u
* Dedans renseigner les fichiers CHD du jeu :

```text
Grandia (France) (Disc 1).chd
Grandia (France) (Disc 2).chd
```

* **Sur Windows** vous devez activer la vue sur extension pour pouvoir créer ce fichier :
  * Allez dans affichage en haut de la fenêtre de votre explorateur de fichier.
  * Puis cocher "Extensions de noms de fichiers" en haut à droite.

![](./image%20%28113%29.png)

* Confirmer la modification de l'extension

![](./image%20%28300%29.png)

## Crédit 

Un grand Merci à **Zet-sensei**, l'une des personnes de l'ombre qui travaillent en préservation dans le patrimoine vidéoludique.  
Vous ne le connaissez pas, mais il été à l'origine ou grandement participant sur des projets majeurs à ce sujet, notamment co-fondateur de No-Intro et Redump dans ceux les plus connus.

