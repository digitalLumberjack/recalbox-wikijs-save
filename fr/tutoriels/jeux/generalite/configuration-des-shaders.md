---
title: Configuration des shaders
---

# Configuration des shaders

## Introduction

Les shaders sont des filtres qui peuvent modifier l'image que vous obtenez lorsque vous utilisez vos émulateurs. Il est souvent utilisé pour obtenir une image "rétro", proche de l'image sur laquelle nous avons joué à l'époque.

Les différents fichiers que vous avez dans Recalbox sont :

*  **glsl** : le shader lui-même
*  **glslp** : le shader préréglé. Peut combiner plusieurs shaders.
* /recalbox/share/system/configs/shaders/**xxx.cfg** : les fichiers de configuration des pack de shaders

Le fichier de configuration des pack de shaders \(.cfg\) fait référence à un préréglage de shader \(glslp\) pour chaque système de la Recalbox. Chaque fichier glslp fait référence à un ou plusieurs shaders \(glsl\).

## Pack de shaders

Avec les packs de shaders, vous pouvez configurer des shaders pour tous vos systèmes en une seule option.

Les packs sont créés par la communauté, et sont optimisés à chaque nouvelle version de Recalbox.

Packs disponibles :

* **scanlines** : activer les lignes de balayage \(_scanlines_\) sur tous les émulateurs
* **retro** : sélectionner les "meilleurs" shaders pour chaque système, choisis par la communauté, qui vous offriront l'expérience de jeu la plus proche de l'original.
* **none** : pas de shaders

Vous pouvez définir le pack de shaders que vous souhaitez activer dans le menu "PARAMÈTRES DE JEU" d'EmulationStation, ou directement dans recalbox.conf avec l'option `global.shaderset`.

## Shaders personnalisés

Vous pouvez combiner la puissance des **packs de shaders** avec la personnalisation poussée de recalbox.conf. Le `global.shaderset` peut définir un shader de base pour chaque émulateur. Vous pouvez ensuite modifier le préréglage des shaders d'un système avec l'option `systemname.shader`. Les préréglages par défaut des shaders sont définis dans `/recalbox/share_init/shaders/`

Par exemple, si je veux les meilleurs shaders sur tous les émulateurs, mais pas de shaders pour ma Gameboy, un shader déjà existant préréglé pour la Megadrive, et un shader personnalisé préréglé pour ma Snes :

```text
# Set the retro shader set for all emulators, now i know that i have the best selection
global.shaderset=retro
# But my gameboy seem better for me with no shaders
gb.shaders=
# We use the already existing 4xbr_retro.glslp shader for megadrive
megadrive.shaders=/recalbox/share_init/shaders/4xbr_retro.glslp
# And i want to apply my own shader preset on snes
snes.shaders=/recalbox/share/shaders/custom/snes.glslp
```

Vous pouvez également changer de shaders dans le jeu en utilisant votre contrôleur.  
Utilisez les commandes spéciales **Hotkey + R2** ou **Hotkey + L2** pour aller au shader suivant ou précédent.

## Screenshots

**Aucun** shader : 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lko7NXwWuq6o_JbyMiN%2F-LkoAc09tMdSbcRo-zYm%2Fimage.png?alt=media&token=7405b2a7-c30b-402c-b242-1c87c8f5c871)

Avec **le set retro** activé : 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lko7NXwWuq6o_JbyMiN%2F-LkoAh6LO-z5waVpIwto%2Fimage.png?alt=media&token=907375ea-ea6b-4f9e-ae00-9ff2bb1f358b)

