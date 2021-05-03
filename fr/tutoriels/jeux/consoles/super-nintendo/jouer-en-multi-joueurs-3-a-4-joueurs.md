---
title: Jouer en multi-joueurs \(3 à 4 joueurs\)
---

# Jouer en multi-joueurs \(3 à 4 joueurs\)

Il est possible de jouer jusqu’à 4 sur l'émulateur SNES sur Recalbox.

Si vous souhaitez pouvoir profiter du multi-joueur sur SNES, vous aurez besoin d'une manette par joueur, correctement configurée.

* Modifiez le fichier [_recalbox.conf_](/fr/usage-basique/premieres-notions/le-fichier-recalbox.conf) pour remplacer l'émulateur SNES par `snes9x_next`

```text
# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
snes.core=snes9x_next
```

* Enregistrez puis redémarrez proprement votre Recalbox. 
* Lancez un jeu SNES, comme Micro Machines par exemple. 
* Ouvrez le menu RetroArch avec les boutons **Hotkey + B**. 
* Changez les paramètres suivants :

```text
Setting / Configuration / Save Configuration On Exit : ON
Setting / Input / User 2 Device Type / Multitap
Quick menu / Restart Content
```

* Vous pouvez remettre `Save Configuration On Exit` sur `OFF` après avoir redémarré le jeu.

Et voilà. Le jeu fonctionne, et vous êtes le roi de la soirée !

