---
title: Textures haute résolution
---

# Textures haute résolution

## Général <a id="general"></a>

### Qu'est ce que sont les textures haute résolution ? <a id="quest-ce-que-sont-les-textures-haute-resolution"></a>

Les textures haute résolution \(Hi-res\) sont des packages crée par les fans destiné à embellir les textures par défaut d'un jeu.

**Rice**, développeur du plugin **Rice Vidéo**, fut le premier qui rendit possible d''extraire les textures d'un jeu, de les modifier et des les ré-importer dans une résolution plus haute. Maintenant il est possible de remplacer les textures floues dans les jeux par des versions haute définition ou par une version complètement différente. Emballé par cette nouvelle possibilité, de nombreux graphistes ont commencé à créer des textures de substitution pour leurs jeux préférés.


>**Important**
>
>Lorsque vous téléchargez un pack de textures haute résolution \(Google est votre ami\), regardez dans le fichier readme la description, les messages du forum ou tout autre élément. Beaucoup de ces packs ne fonctionnent qu'avec un fichier rom spécifique. Par exemple, la rom \(U\) fonctionne, la rom \(E\) ne fonctionne pas. Avant de commencer, vous devez le savoir.
{.is-warning}

### Configuration

**Activer le chargement des fichiers de texture haute résolution dans la Recalbox :**

Nous commençons par éditer le fichier _mupen64plus.cfg_ afin de pouvoir charger des textures haute résolution. Le chemin d'accès au dossier est `recalbox/share/system/configs/mupen64/`

Ouvrez le fichier _mupen64plus.cfg_ avec un éditeur et modifiez la ligne suivante :

#### **Option 1 \(pour les systèmes hors x86 et x86\_64\)** : 

Modifiez la ligne suivante :

```text
# Enable hi-resolution texture file loading
LoadHiResTextures = False
```

Par celle-ci :

```text
# Enable hi-resolution texture file loading
LoadHiResTextures = True
```

#### **Option 2 \(pour les systèmes x86 et x86\_64\) :**

Modifiez la ligne suivante :

```text
# Hi-res texture pack format (0 for none, 1 for Rice)
ghq_hirs = 0
```

Par celle-ci :

```text
# Hi-res texture pack format (0 for none, 1 for Rice)
ghq_hirs = 1
```

Modifiez la ligne suivante :

```text
# Compress hi-res texture cache
ghq_hirs_gz = True
```

Par celle-ci :

```text
# Compress hi-res texture cache
ghq_hirs_gz = False
```

**Copiez vos textures haute résolution dans la Recalbox :**

L'emplacement, c'est `recalbox/share/system/.local/share/mupen64plus/hires_texture/GAMENAME/`

Si le dossier **hires\_texture** n'existe pas, créez-en un.  
Si le dossier .../.local n'existe pas :

Le dossier `.local` sera créé si vous démarrez un jeu N64 après avoir modifié les lignes du fichier `mupen64plus.cfg`.

**Activez l'émulateur Mupen64Plus avec le noyau RICE \(sur les systèmes x86, utilisez les paramètres par défaut\) :**

Vous avez copié le pack texture haute résolution et la bonne rom \(la rom de votre dossier n64 rom\) ?  
Ok, alors redémarrez le système.

* Après le redémarrage, allez dans EmulationStation vers votre rom et appuyez sur Select.
* Maintenant, allez modifier les métadonnées.
* Changez l'émulateur pour MUPEN64PLUS
* Changez le noyau pour RICE.
* Sauvegardez

Quand le pack de textures haute résolution et la rom seront les bons, le jeu démarrera en haute résolution.

## Dépannage <a id="depannage"></a>

### Vous avez bien suivi les instructions ci-dessus et cela ne fonctionne toujours pas ? <a id="vous-avez-bien-suivi-les-instructions-ci-dessus-et-cela-ne-fonctionne-toujours-pas"></a>

Peut-être est-ce **un problème de nom**...  
Beaucoup de **ces packs de textures** sont fourni avec **le bon nom de dossier** mais **pas tous ! Le nom de dossier** doit être exactement **le nom interne de votre rom.**


>#### Attention: <a id="attention"></a>
>
>Le nom de fichier est **Mario Kart 64 \(USA\).v64** mais le nom interne de la rom est **`MARIOKART64`**
{.is-danger}

### Comment connaitre le nom interne de ma rom ? <a id="comment-connaitre-le-nom-interne-de-ma-rom"></a>

Sur Windows, vous pouvez utilisez par exemple **Tool64** \(Google est aussi votre ami ici\).

* Démarrez **Tool64**.
* `File` -&gt; `Open`
* Sélectionnez votre dossier de rom.

![](https://cloud.githubusercontent.com/assets/21189571/24712193/7c626906-1a22-11e7-942b-d1701ebe6dc6.png)

* Faites un clic droit sur une rom puis cliquez sur `Rom Properties…`

![](https://cloud.githubusercontent.com/assets/21189571/24712198/82bb47a0-1a22-11e7-9546-baa23e74b550.png)

Regardez la ligne `Rom Name` pour avoir le nom interne de la rom.

