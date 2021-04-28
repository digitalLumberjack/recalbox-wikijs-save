---
title: Convertir les fichiers ISO + CUE + WAV/BIN en BIN + CUE
---

# Convertir les fichiers ISO + CUE + WAV/BIN en BIN + CUE


>**Informations :**
>
>Les jeux **SegaCD** ou **PSX** peuvent utiliser **différents formats :**
>
>* iso+cue accompagné par des fichiers tracks au format wav, bin
>* iso
>* bin+cue
>* ccd+img+sub
>* bin seul
{.is-info}

**Exemple :**

```text
Wonder Dog (1993)(Sega)(PAL)(Track 01 of 21)[!].iso
Wonder Dog (1993)(Sega)(PAL)(Track 02 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 03 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 04 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 05 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 06 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 07 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 08 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 09 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 10 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 11 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 12 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 13 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 14 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 15 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 16 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 17 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 18 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 19 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 20 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 21 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)[!].cue   

Rockman 8 - Metal Heroes (Japan) (Track 1).bin   
Rockman 8 - Metal Heroes (Japan) (Track 2).bin   
Rockman 8 - Metal Heroes (Japan) (Track 3).bin   
Rockman 8 - Metal Heroes (Japan) (Track 4).bin   
Rockman 8 - Metal Heroes (Japan).cue
```

Voici une technique pour convertir **les iso+cue avec fichiers wav** pour ceux qui **ne veulent pas créer de dossiers pour contenir tous les fichiers d'un jeu.**


>**Remarque :**
>
>**Cette technique** est valable pour PSX, SEGACD.
{.is-info}

* Téléchargez [Daemons Tools Lite \(gratuit\)](https://www.daemon-tools.cc/fra/products/dtLite).
* Installez le logiciel.
* Choisissez les images disques que vous souhaiter convertir puis cliquer le signe `+`
  * Sélectionnez le fichier \*.CUE puis appuyer sur `Entrée`. OU
  * Faites un clic droit et choisissez `Monter` dans le menu contextuel pour créer le lecteur virtuel.
* Téléchargez [ImgBurn](http://imgburn.com/).
* Téléchargez le fichier de langue en français en cliquant sur [le lien](http://download.imgburn.com/translations/french.zip).
* Installez le logiciel.
* Dézippez le fichier de langue et placez-le dans le dossier `C:\Program Files(x86)\imgburn\languages`.
* Ouvrez le logiciel et vous l'aurez en français.
* Cliquez sur le bouton `Créer une image à partir du disque`.
* Choisissez le lecteur virtuel comme source.
* Choisissez un dossier de destination pour la création des fichiers BIN et CUE.
* Cliquez sur le bouton `Lire` et patientez.

Une fois la conversion terminée, vous pouvez démonter le lecteur virtuel \(clic droit sur l’icône dans **Daemon Tools** puis cliquez sur `Démonter`\).

## Créer un fichier .CUE manquant pour votre unique fichier .BIN <a id="creer-une-fichier-cue-manquant-pour-votre-unique-fichier-bin"></a>

Exemple avec le fichier `r-type.bin`.

* Ouvrez [**Notepad++**](https://notepad-plus-plus.org/downloads/) sur un nouveau fichier vide.
* Vous allez devoir écrire 3 lignes dans ce nouveau fichier :
  * La première ligne doit contenir le **BINARY**
  * La ****seconde ligne doit contenir les pistes toujours en **MODE2/2352**
  * La troisième ligne doit contenir l'index 01
* Vous obtenez quelque chose comme ceci qui devrait fonctionner :

```text
FILE "r-type.bin" BINARY
TRACK 01 MODE2/2352
INDEX 01 00:00:00
```

* Enregistrez le fichier avec l'extension .cue : `r-type.cue`.
* Il reste plus qu'à transférer votre fichier .bin et .cue.

