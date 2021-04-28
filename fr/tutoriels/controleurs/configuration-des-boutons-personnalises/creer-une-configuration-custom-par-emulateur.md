---
title: Créer une configuration custom par émulateur
---

# Créer une configuration custom par émulateur

Vous avez la possibilité de **créer votre propre configuration custom pour chaque émulateur** sur Recalbox.

## I - RetroArch <a id="i-retroarch"></a>

**La configuration de RetroArch** peut être créer à la main en **appuyant votre propre configuration sur le standard** [retroarch.cfg](https://github.com/libretro/RetroArch/blob/master/retroarch.cfg) ou **en l'éditant dans le menu de RetroArch.** Vous devrez alors **créer une nouvelle configuration** et **paramétrer** le nouveau fichier de config **recalbox.conf** afin qu'il soit chargé par votre émulateur.

### En utilisant le menu de RetroArch

Partons sur l'exemple de **créer un fichier de config** spécifique pour la **neogeo**.

* **Lancez un jeu** de l'émulateur que vous **souhaitez personnaliser** \(ici neogeo\) 
* **Entrez dans le menu** de RetroArch \(**Hotkey + B**\) 
* **Modifiez** toutes les configurations comme vous le souhaitez 
* **Retournez dans la première entrée** du menu de RetroArch, ensuite faites **`Save new config`**\(le nom du fichier de config **devra ressembler** à _**fba\_libretro.cfg**_, avec le nom du _core_ que vous être en train d'utiliser\) 
* En [accès root](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal), **modifiez le nom du fichier de config** pour quelque chose de plus simple à se rappeler.   **Exemple :** `mv /recalbox/share/system/configs/retroarch/fba_libretro.cfg /recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`   
* **Ajoutez la ligne** suivante à **recalbox.conf** : `neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`

### Inputs

#### Édition manuelle

Vous pouvez ajouter des fichiers de configuration spécifiques au système et/ou au jeu. Il y a bien sûr une priorité si un même paramètre apparaît dans chaque fichier de configuration. Ainsi, J**eu &gt; Système &gt; RetroArch**, ce qui signifie qu'un paramètre existant dans un fichier .cfg de jeu sera celui utilisé sur un système ou le fichier de RetroArch par défaut.

Voici les fichiers que vous pouvez modifier \(ou créer s'ils n'existent pas\) :

*  `~/configs/retroarch/<system>.cfg` où `<système>` est le nom du système tel qu'il apparaît dans le dossier `<roms>`. Par exemple : `~/configs/retroarch/snes.cfg`.
*  `~/configs/retroarch/<system>/<romname>.cfg` où `<system>` est le nom du système tel qu'il apparaît dans le dossier `roms` , et `<romname>` est le nom exact de la rom avec l'extension du fichier. Par exemple : `~/configs/retroarch/snes/mario.zip.cfg`

## II - piFBA <a id="ii-pifba"></a>



