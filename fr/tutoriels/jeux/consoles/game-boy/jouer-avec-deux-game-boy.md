---
title: Jouer avec deux Game Boy
---

# Jouer avec deux Game Boy

Il est possible de jouer à deux joueurs avec deux GameBoy sur Recalbox. Il existe 3 méthodes pour y arriver.


>Même si cela peut être tentant, Recalbox ne supporte pas le Netplay dans ce mode.
>
>De plus, en mode un jeu pour deux Game Boy, les sauvegardes ne sont pas supportées pour la deuxième Game Boy, contrairement au mode [deux jeux deux Game Boy](/fr/tutoriels/jeux/consoles/game-boy/jouer-a-deux-jeux-differents-en-mode-gamelink), où là encore, le Netplay n'est pas supporté.
{.is-warning}

## La méthode "no edit" <a id="la-methode-no-edit"></a>

1. **Allumez** votre Recalbox
2. Une fois sous EmulationStation, **sélectionnez la Game Boy** ou la **Game Boy Color**.
3. **Dans la liste de jeux**, positionnez-vous sur **le jeu voulu** et **appuyer sur START**.
4. **Sélectionnez** "Éditer les données du jeu" :
   1. **Emulateur :** selectionnez "libretro" ua lieu de "Default \(Libretro\)"
   2. **Core :** selectionnez "TGBDUAL"
5. **Sauvegardez**
6. **Lancez le jeu**
7. Quand le jeu **démarre**, **allez dans le menu de RetroArch** en faisant "HotKey+B"
8. **Settings -&gt; Configuration** -&gt; **Mettez** "save configuration on" sur **"ON"**
9. Toujours **dans le menu de RetroArch**, quick menu/Options **Mettre** "GB link enable \(restart\)" sur "enable"

Vous pouvez remettre "Save Configuration On Exit" sur OFF après avoir redémarré le jeu.

## L'édition du Recalbox.conf <a id="lancienne-methode-a-la-dure"></a>

* **Modifiez** le fichier recalbox.conf pour **remplacer** l'émulateur GameBoy par `tgbdual`

```text
# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
gb.core=tgbdual ;GameBoy
gb.ratio=custom
gbc.core=tgbdual ;GameBoyColor
gbc.ratio=custom
```

* **Enregistrez puis redémarrez** proprement votre Recalbox. 
* **Lancez un jeu GameBoy** comme Ballon Kid par exemple. 
* **Ouvrez le menu RetroArch** avec le bouton Hotkey et le bouton B. 
* **Changez** les paramètres suivants:

```text
Setting / Configuration / Save Configuration On Exit : ON
Quick menu / Core Options / GB Link Enable (restart) : enabled
Quick menu / Core Options / Screen placement (restart) : horizontal
Quick menu / Core Options / Switch player screens : normal ; joueur 1 à gauche et joueur 2 à droite
Quick menu / Core Options / Show player screens : both players
Settings / Video / Aspect Ratio Index : 20:9 (1:1 PAR) ; 100% conforme ratio GB
Quick menu / Restart Content
```

* Vous pouvez **remettre** "Save Configuration On Exit" sur **OFF** après avoir r**edémarré le jeu.**


>Pensez que si votre TV n'est pas réglée en **16/9** - si le menu de Recalbox n'occupe pas l'intégralité de l'écran - alors le ratio ne sera pas bon.  
>  
>Notez aussi que **les jeux mono-joueurs** vont aussi êtres doublés. Deux GB côte à côte, bien pour un duel de speed run, sinon inutile.  
>  
>Pour éviter trop de manipulations, vous pouvez appliquer tous ces paramètres que sur GB ou que sur GBC.
{.is-warning}

## L'utilisation de fichiers de surcharge \(pour utilisateurs avancés\)

Les surcharges de configuration sont un moyen de forcer des paramètres pour un jeu, un sous-dossier ou tout un système.

Dans le cas qui nous intéresse, il nous faudra un fichier nomdujeu.extension.recalbox.conf \(par exemple : **Pac-Man \(Europe\).zip.recalbox.conf**\) contenant les lignes suivantes :

```text
gb.core=tgbdual
gbc.core=tgbdual
```


>Ici, on force le core TGBDual pour le jeu.
{.is-info}

Un fichier nomdujeu.extension.core.cfg \(par exemple : **Pac-Man \(Europe\).zip.core.cfg**\) contenant :

```text
tgbdual_audio_output = "Game Boy #1"
tgbdual_gblink_enable = "enabled"
tgbdual_screen_placement = "left-right"
tgbdual_single_screen_mp = "both players"
tgbdual_switch_screens = "normal"
```


>On règle TGBDual pour utiliser le son de la Game Boy \#1, activer le GameLink, afficher deux GameBoy côte à côte, une à gauche et une à droite, et la GameBoy du joueur \#1 est à gauche.
{.is-info}

Et un dernier fichier nomdujeu.extension.retroarch.cfg \(par exemple : **Pac-Man \(Europe\).zip.retroarch.cfg**\) contenant :

```text
aspect_ratio_index = "22"
input_overlay_enable = "false"
```


>On force l'aspect ratio dans le mode 22 : Core Provided, tout en désactivant les overlays.
{.is-info}

Ces fichiers doivent être placés au même endroit que le jeu souhaité \(dans l'exemple pris précédemment, au même endroit que le jeu **Pac-Man \(Europe\).zip**\).


>Si les fichiers de surcharges se nomment uniquement **.recalbox.conf, .retroarch.cfg** et **.core.cfg**, alors ils s'appliqueront à tout le dossier dans lequel ils sont placés, ainsi que les sous-dossiers si il y en a.
{.is-info}


>Les fichiers de surcharges ne sont pas affectés par la configuration depuis l'interface de Recalbox, et ils prennent le dessus sur ces derniers, il est impératif de pouvoir accéder à ces fichiers pour effectuer une modification ultérieure sur les paramètres que ils affectent.
{.is-warning}

