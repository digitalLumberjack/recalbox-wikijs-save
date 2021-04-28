---
title: Configurer des overlays \(4.1\)
---

# Configurer des overlays \(4.1\)

## Overlays par jeu

Ce qu'il vous faut :

* créer le dossier `overlays` + sous-répertoire du même nom du système
* ajoutez-y votre `.png`, un `romName.cfg` + `romName.zip.cfg`

**Voici donc les informations de base à travers un exemple**

* Système : MAME
* Rom : Double Dragon \(ddragon.zip\)

Dossier : /recalbox/share/overlays/**mame**  
Fichiers :

* /recalbox/share/overlays/mame/ddragon.zip.cfg :

```text
input_overlay = "/recalbox/share/overlays/mame/ddragon.cfg"
```

* /recalbox/share/overlays/mame/**ddragon**.cfg :

```text
overlays = "1"
overlay0_overlay = "ddragon.png"
overlay0_full_screen = "true"
overlay0_descs = "0"
```

Voyez donc le lien : Recalbox va chercher `overlays/<system>/<rom.extension>.cfg` qui lui-même fait référence à un autre .cfg \(le fichier n'a pas besoin d'être nommé comme la rom, à vous de personnaliser le paramètre input\_overlay\). Il en va de même pour le nom de l'overlay.

Ce sont les exigences minimales. Vous pouvez bien sûr ajouter quelques paramètres de retroarch personnalisés à `ddragon.zip.cfg`  
La plupart du temps, vous devriez forcer les viewports.

## Overlays par système

Ce qu'il vous faut :

* créer le dossier `overlays`
* ajoutez-y votre `.png` + `systemName_overlay.cfg` dans le dossier`/recalbox/share/system/configs/retroarch/overlays`
* ajoutez votre `systemName.cfg` dans le dossier `/recalbox/share/system/configs/retroarch`
* `systemName.cfg` est nommé comme le nom du dossier dans `/recalbox/share/roms/...`. Par exemple, le fichier Sega 32X est appelé `sega32x.cfg`. Il y a une exception pour Odyssey2. Le fichier doit s'appeler `odyssey2.cfg` \(donc pas o2em.cfg\).

**Voici donc les informations de base à travers un exemple**

* Système : PSW

Dossier : /recalbox/share/system/configs/retroarch  
Fichier : /recalbox/share/system/configs/retroarch/**psx.cfg**

```text
input_overlay = "/recalbox/share/system/configs/retroarch/overlays/psx_overlay.cfg"
```

Dossier : /recalbox/share/system/configs/retroarch/overlays  
Fichiers : /recalbox/share/system/configs/retroarch/overlays/**psx\_overlay.cfg** :

```text
overlays = "1"
overlay0_overlay = "psx.png"
overlay0_full_screen = "true"
overlay0_descs = "0"
```

Voyez donc le lien : Recalbox va chercher `retroarch/<systemName>.cfg` qui lui-même fait référence à un autre .cfg \(le fichier n'a pas besoin d'être nommé comme le`systemName_overlay`, à vous de personnaliser le paramètre input\_overlay\). Il en va de même pour le nom de l'overlay.

Ce sont les exigences minimales. Vous pouvez bien sûr ajouter quelques paramètres de retroarch personnalisés à `psx_overlay.cfg`  
La plupart du temps, vous devriez forcer les viewports.

## Viewports personnalisés

Maintenant que les overlays par système sont définis, pour afficher correctement le jeu à l'intérieur de l'overlay, nous allons définir des fenêtres de visualisation personnalisées \(_viewports_\) pour chaque système.

Prenons l'exemple de la Gamegear :

* Définir le ratio dans les options d'Emulationstation en `custom`. `GAMES SETTINGS / GAME RATIO = CUSTOM`

![ratio personnalis&#xE9;](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/overlays/overlays_2.png)

* Lancez un jeu Gamegear puis ouvrez le menu Retroarch avec `Hotkey+B`.
* Activez l'option qui permet d'afficher les overlays dans le menu Retroarch. Allez dans menu `settings/onscreen_display/onscreen_overlay`, puis activez cette option : `hide_overlay_in_menu = on` -&gt; `off`
* Allez dans le `menu paramètres/ menu vidéo` :
  * définir le ratio d'aspect sur `custom`
  * définir des `valeurs de largeur` et `de hauteur de ratio d'aspect personnalisées` pour afficher parfaitement le jeu à l'intérieur de l'overlay.
  * Notez ces 2 valeurs.

![custom\_viewports](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/overlays/overlays_1.png)

* Quittez le menu Retroarch et le jeu **sans sauvegarder aucun paramètre**.
* Éditez le fichier `/recalbox/share/system/configs/retroarch/gamegear.cfg` créé précédemment.

  * ajouter les valeurs définies à l'étape précédente :

  ```text
  custom_viewport_width = "992"
  custom_viewport_height = "720"
  aspect_ratio_index = "22"
  ```

Notre dossier contient ces informations :

```text
input_overlay = "/recalbox/share/system/configs/retroarch/overlays/gamegear.cfg"
custom_viewport_width = "992"
custom_viewport_height = "720"
aspect_ratio_index = "22"
```

Si vous souhaitez afficher un rapport prédéfini, voici les codes de rapport d'aspect :

```text
0: 4:3
1: 16:9
2: 16:10
3: 16:15
4: 1:1
5: 2:1
6: 3:2
7: 3:4
8: 4:1
9: 4:4
10: 5:4
11: 6:5
12: 7:9
13: 8:3
14: 8:7
15: 19:12
16: 19:14
17: 30:17
18: 32:9
19: config (video_aspect_ratio setting)
20: 10:9 (1:1 PAR)
21: Core Provided
22: Custom
```

Donc pour forcer, par exemple, un rapport d'aspect 4:3, vous devez écrire dans le fichier : `aspect_ratio_index = "0"`

* Sauvegardez votre fichier et quittez.
* Lancez un jeu pour tester.
* Amusez-vous

**Ajout des bezels de The Bezel Project** : allez au _The Bezel Project_ et téléchargez le zip pour votre système : [https://github.com/thebezelproject?tab=repositories](https://github.com/thebezelproject?tab=repositories)

Dans cet exemple, je vais utiliser Atari7600. Comme dans l'exemple du début, créez le dossier atari7800 : `/recalbox/share/overlays/atari7800/` Et puis un dossier bezel à l'intérieur :`/recalbox/share/overlays/atari7800/bezel`

Dézippez votre **bezelproject-Atari7800-master.zip** et copiez tous les fichiers .png et .cfg : `bezelproject-Atari7800-master\retroarch\overlay\GameBezels\Atari7800` vers `/recalbox/share/overlays/atari7800/bezel`

Maintenant, éditez tous les fichiers .cfg \(utiliser **Notepad++** pour cela\). Dans Notepad++, utilisez la fonction _replace_ et remplacez : `/opt/retropie/configs/all/retroarch/overlay/GameBezels/Atari7800/` sans rien d'autre et appuyez sur la fonction Remplacer dans tous les documents.

Les fichiers devraient ressembler à ceci :

_overlays = 1 overlay0\_overlay = "Alien Brigade \(USA\).png" overlay0\_full\_screen = true overlay0\_descs = 0_

Faites maintenant une copie de tous les fichiers .cfg et collez-les dans ce dossier : `/recalbox/share/overlays/atari7800`

Editez-les tous dans Recalbox : remplacez `overlays = 1` par rien du tout.

Remplacez : `overlay0_overlay = "` par `input_overlay = "/recalbox/share/overlays/atari7800/arcade-artwork/`

Remplacez : **.png"** par **.cfg"**

Remplacez : `overlay0_full_screen = true` par `input_overlay_enable = true`

Remplacez : `overlay0_descs = 0` par `input_overlay_opacity = 0.900000`

Ajoutez cette ligne : `input_overlay_scale = 1.000000`

Le fichier devrait maintenant ressembler à ceci : **input\_overlay = "/recalbox/share/overlays/atari7800/arcade-artwork/Alien Brigade \(USA\).cfg" input\_overlay\_enable = true input\_overlay\_opacity = 0.900000 input\_overlay\_scale = 1.000000**

Vous pouvez maintenant lancer un jeu et tester le résultat.

