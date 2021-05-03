---
title: Plusieurs packs de textures haute résolution différents sur le même jeu
---

# Plusieurs packs de textures haute résolution différents sur le même jeu

## Informations <a id="information"></a>

Dans le guide « [Textures haute résolution](/fr/tutoriels/jeux/consoles/nintendo-64/textures-haute-resolution) »_,_ vous avez appris comment utiliser les packs de textures haute résolution.

## Général <a id="general"></a>

Pour certains jeux, différents pack de textures ont été crée.  
Le problème étant qu'ils ont en général tous le même nom. Si vous voulez utiliser plusieurs versions, suivez ce guide.

## Déroulement <a id="deroulement"></a>

Pour chaque version de la texture haute résolution, nous modifions le nom de la rom interne. Lorsque cela sera fait, nous modifierons les noms des textures haute résolution.

## Ce dont nous avons besoin

Dans ce guide, nous utiliserons _N64 Rom Renamer_ par Einstein II \(Google est votre ami\), pour modifier le nom interne de la rom.  
Vous aurez aussi besoin d'un batch de renommage \(exemple sous Windows : _AntRenamer_\). Pour ce guide, nous utiliserons _Better Rename_ \(macOS\).

## C'est parti <a id="cest-parti"></a>

### Modifiez le nom interne de la rom

* Ouvrez _N64 Rom Renamer_ avec les droits administrateur \(cela ne fonctionnait pas sans pour ma part\).

![](https://cloud.githubusercontent.com/assets/21189571/24708781/34a419e8-1a18-11e7-8751-c46bc0f495d0.png)

* Appuyez sur `F2` ou allez dans `Tools - Headereditor`  ****
* Validez l'avertissement.

![](https://cloud.githubusercontent.com/assets/21189571/24708944/ae3da576-1a18-11e7-9f43-0db16524c2f4.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LlEX5DYb-17IklPbtZ-%2F-LlEX8rcviyjOMTdk5Sy%2Fimage.png?alt=media&token=33b8d97c-fb70-4182-87bf-28e5cf37e3a0)

* En haut à gauche, cliquez sur l’icône de dossier et sélectionnez ****votre rom  ****\(pour notre exemple, nous utiliserons Mario Kart 64\).

![](https://cloud.githubusercontent.com/assets/21189571/24709113/2c9691d0-1a19-11e7-8704-d9217ebf926a.png)

* Ici vous pouvez modifier le nom interne de la rom.



### **Attention**

Le nom **ne peut pas être trop long.** La longueur totale des lettres et espaces doit être respectée \(20 caractères\). Dans notre cas, nous voyons que **MARIOKART64** possède neuf espaces en plus de son nom, ce qui nous donne la longueur totale possible pour le nom interne.

![](https://cloud.githubusercontent.com/assets/21189571/24709501/667ddcb8-1a1a-11e7-927f-e7b5276d766d.png)

* Dans notre exemple, nous supprimerons quatre espaces qui seront remplacés par quatre lettres \(SNES\).

![](https://cloud.githubusercontent.com/assets/21189571/24709636/d69617ae-1a1a-11e7-9ec6-5d9d43e1983b.png)

* Cliquez sur `Save changes` pour sauvegarder les modifications puis cliquez sur `Back` pour revenir en arrière.
* Le nom interne de la rom a été modifié avec succès.

Renommez ensuite le fichier rom ; exemple : Mario Kart 64 SNES Edition.ext Le nom de fichier de la rom n'est pas important pour les textures.

### Modifiez le pack de textures haute résolution et les fichiers :

Notre exemple de structure de fichier de notre pack haute résolution ressemble à cela :

![](https://cloud.githubusercontent.com/assets/21189571/24709885/a5b8cdba-1a1b-11e7-9623-d0ee243b5af3.png)

Le dossier et les fichiers nommés **MARIOKART64** sont bien sûr maintenant incorrects, après que nous ayons modifié le nom interne de la rom. Nous devons corriger cela !

* Ouvrez _Better Rename_
* Category : Text
* Action : Replace text
* Replace : **MARIOKART64**
* With : **MARIOKART64SNES**

![](https://cloud.githubusercontent.com/assets/21189571/24710019/1caa6e4c-1a1c-11e7-82da-1b7ddfa3d05d.png)

Après le renommage, vous devez **vérifier que tous les noms correspondent.**  
Si le nom de dossier et les noms de fichiers correspondent, vous pouvez copier votre pack de textures.


>**Par précaution :**
>
>Ancien nom de dossier : MARIOKART64  
>Ancien nom de fichier dans le dossier : MARIOKART64\#......
>
>Nouveau nom de dossier : MARIOKART64SNES  
>Nouveau nom de fichier dans le dossier : MARIOKART64SNES\#...
{.is-warning}

## FIN

**Suivre** ces étapes pour **chaque pack de textures haute résolution** voulu.

