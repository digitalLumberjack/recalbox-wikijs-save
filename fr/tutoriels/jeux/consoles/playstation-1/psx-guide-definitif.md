---
title: PSX - Guide Définitif
---

# PSX - Guide Définitif

## Multi-disques

Tout d'abord, nous allons voir les différentes possibilités offertes par Recalbox pour changer de disque.

### Mode PSP

Regroupez tous les disques dans un seul fichier eboot.pbp.  
Vous pouvez changer de disque dans le menu Retroarch.

#### Avantages :

* Les raccourcis des contrôleurs peuvent être utilisés pour changer de disque.
* Il existe un fichier de sauvegarde pour tous les disques.

#### Inconvénients :

* Les fichiers .sbi ne peuvent pas être utilisés dans les jeux multi-disques.
* Ne permet pas de basculer vers un disque patché \(avec la correction de protection LibCrypt\).
* Cela prend un certain temps de changer tous les jeux multi-disques en eboot.pbp.

### Mode PCSX-reARMed

Le disque suivant est recherché dans le menu Retroarch par le système de fichiers.

#### Avantages :

* Vos jeux sont au format .bin /.cue.

#### Inconvénients :

* Cela ne fonctionne pas actuellement.
* C'est moche et lent.
* Les fichiers sauvegardés ne sont pas partagés entre les disques.
* Les raccourcis des contrôleurs ne peuvent pas être utilisés pour changer de disque.

Par conséquent, les jeux avec protection LibCrypt et multi-disque sont une vraie plaie dans ces deux modes.

### Mode définitif

Pour ce mode, il est nécessaire d'ajouter l'extension .m3u à la partie PSX dans `/recalbox/share_init/system/.emulationstation/es_systems.cfg` \(les développeurs sont priés de l'ajouter dans la prochaine version, merci\). Pour cela, vous pouvez utiliser une machine virtuelle avec Ubuntu \(par exemple\) et brancher la carte SD pour modifier le fichier.

La ligne modifiée ressemblerait à ceci :

`<extension>.m3u .img .IMG .pbp .PBP .bin .BIN .cue .CUE .iso .ISO</extension>`

Il suffit ensuite de créer un fichier .m3u pour chaque jeu multi-disque. Ce fichier contiendra les noms des fichiers .cue. Par exemple :

![m3u](https://camo.githubusercontent.com/226ac7a2b8e6e9a79ae38a69973509493272c39f/68747470733a2f2f692e696d6775722e636f6d2f497339315132372e706e67)

Le dernier aspect devrait être comme suit :

![Dossier PSX](https://camo.githubusercontent.com/614395aa32769188757678ecdb0dcc34651a632e/68747470733a2f2f692e696d6775722e636f6d2f516c4d6e4a416d2e706e67)

Comme vous pouvez le voir, il y a des .cue /.bin /.sbi par disque et un .m3u par jeu multi-disque.

#### Avantages :

* Vos jeux sont au format .bin /.cue.
* Les raccourcis des contrôleurs peuvent être utilisés pour changer de disque.
* Les fichiers .sbi peuvent être utilisés.
* Il existe un fichier de sauvegarde pour tous les disques.

#### Inconvénients :

* Vous devez modifier le fichier es\_systems.cfg \(une seule fois\).
* Vous devez cacher les fichiers .cue dans le menu Recalbox.

## Définir les raccourcis contrôleur pour changer de disque

* Dans le jeu, allez dans le menu Retroarch \(Hotkey+B\).
* Appuyez sur A pour accéder au menu principal.
* Allez dans Paramètres &gt; Touche &gt; liaison des touches Hotkey
* Configurez les fonctions d'éjection de disque, disque suivant et disque précédent avec vos touches préférées.
* Exemple : Éjection du disque \(analogique à droite vers le haut\), Disque suivant \(analogique à droite vers la droite\) et Disque précédent \(analogique à droite vers la gauche\).
* Maintenant dans le jeu, vous pouvez appuyer sur la touche `Hotkey + "touche"` pour éjecter le disque, changer le disque et insérer un disque \(et réinitialiser le jeu si nécessaire\).

## Jeux multi-pistes

Certains jeux ont plusieurs pistes par disque. Cela signifie que le fichier .cue nécessite plusieurs entrées \(une par piste\).

Exemple de .cue multi-pistes :

![Cue &#xE0; pistes multiples](https://camo.githubusercontent.com/ab378b532b3cf6c821afbff21997a6e7b09ff480/68747470733a2f2f692e696d6775722e636f6d2f6265556e5637512e706e67)

Le dernier aspect devrait être le suivant :

![Jeu multi-pistes](https://camo.githubusercontent.com/64940efef21e347115f420cceebd89d8d708e952/68747470733a2f2f692e696d6775722e636f6d2f4347704b4555622e706e67)

## FAQ

### Que dois-je faire avec les fichiers .ecm et .ape ?

Vous devez les dézipper. Voir ce [guide](https://www.epforums.org/showthread.php?57757-ECM-And-APE-Guide).

### Comment puis-je activer le Dualshock \(analogues\) ?

Dans le jeu, allez dans le menu RetroArch \(Hotkey + A\) et dans le menu rapide, allez dans Options. Là, sélectionnez _analogue_ dans l'option **Type de pavé 1** \(identique pour tous les pavés que vous voulez\). Si le menu Ape Escape \(version PAL\) ne fonctionne pas, vérifiez le fichier .sbi.

##  Glossaire

* .ape : fichier compressé pour le fichier .wav.
* .bin : données de jeu et pistes de musique.
* .ccd/.img/.sub : Clonage de fichiers CD. Vous devez les transformer en .cue/.bin \(avec IsoBuster par exemple\).
* .cue : fichier dans lequel les pistes du disque sont définies. Un par données .bin.
* .ecm : fichier compressé pour le fichier .bin.
* .pbp : Fichier PSP pour les jeux PSX.
* .ppf : fichier correctif pour les jeux avec protection LibCrypt.
* .sbi : fichier qui contient les informations de protection et qui sont nécessaires pour exécuter des jeux protégés dans des émulateurs. Ils doivent porter le même nom que le fichier .cue.
* .wav : fichier de piste musicale. Vous devez le renommer en .bin.

## Liens utiles

* [Guide ECM-APE](https://www.epforums.org/showthread.php?57757-ECM-And-APE-Guide)
* [Liste des jeux PSX](https://psxdatacenter.com/pal_list.html)
* [Fichiers .sbi](http://psxdatacenter.com/sbifiles.html)
* [Générateur de fichier .cue](http://nielsbuus.dk/pg/psx_cue_maker/)

