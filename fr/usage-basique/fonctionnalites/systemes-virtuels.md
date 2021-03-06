---
title: Systèmes Virtuels
---

# Systèmes Virtuels


>**Information :**
>
>Disponible à partir de la version **7.0**
{.is-info}

## Présentation

Longtemps attendus également, des systèmes virtuels \(comme le système Favoris\) parmi les classiques :

* Tous les jeux.
* Tous les jeux multi-joueurs \(2 joueurs et plus\).
* Tous les derniers jeux joués, triés automatiquement par date.

Sans oublier le système **Arcade**, qui réunit tous les systèmes MAME, FBN, NEO-GEO, ... qui sera désormais activable/désactivable dans les menus.  
Mais ce n'est pas tout.

Pour ceux qui rescraperont leurs systèmes avec le nouveau scrapeur interne \(Skraper n’étant pas encore à jour 😉 \), _**de nouveaux systèmes virtuels par genre de jeux pourront être activés**_.  
Oui, vous avez bien lu :

* Par genre.
* Par jeux de Shoot'em up ?
* Par jeux de plateforme ?
* Par jeux de combat ?
* Par jeux de puzzle ?

Activez les systèmes virtuel des genres qui vous intéressent, et ils seront tous réunis au sein d'une même liste !

## Configuration via le Menu EmulationStation

* Menu EmulationStation

![](/migration-images/usage-basique/fonctionnalites/image%20%28326%29.png)

* Paramètres avancées

![](/migration-images/usage-basique/fonctionnalites/image%20%28183%29.png)

* Systèmes Virtuels
  * Montrer tout les jeux \(On/Off\)
  * Montrer les jeux multijoueurs\(On/Off\)
  * Montrer les derniers jeux jouer \(On/Off\)
  * Afficher le système Lightgun \(On/Off\)
  * Systèmes Virtuels par genre

![](/migration-images/usage-basique/fonctionnalites/screenshot-2021-04-24t09-46-58-403z.png)

![](/migration-images/usage-basique/fonctionnalites/image%20%28224%29.png)

* Système Virtuel Arcade
  * Activer le système Virtuel Arcade \(On/Off\)
  * Inclure la Neo-Geo \(On/Off\)
  * Cacher les systèmes originels \(On/Off\)
  * Position
    * Veuillez sélectionner l'emplacement voulu dans la liste des systèmes.

![](/migration-images/usage-basique/fonctionnalites/image%20%2882%29.png)

![](/migration-images/usage-basique/fonctionnalites/image%20%28267%29.png)

## Configuration via le fichier recalbox.conf \(Facultatif\)

```text
## Arcade metasystem
## Activate the Arcade metasystem to group all games from piFBA, FBN (libretro), MAME and optionally Neogeo
## into a single "Arcade" system.
;global.arcade=1
## You may want to specify its position in the system list. (Default: 0)
## Negatives values may be used to tart from the end (-1 = last position)
;global.arcade.position=0
## Include NeoGeo or not (default: 1)
;global.arcade.includeneogeo=1
## Hide included system or leave them in the system list (default: 1)
;global.arcade.hideoriginals=1
```

### Option pour activer la position dans la liste de systèmes. 

`## You may want to specify its position in the system list. (Default: 0) ## Negatives values may be used to tart from the end (-1 = last position) ;global.arcade.position=0`

###  Cacher les sous dossiers dans le dossier principale 

`## Hide included system or leave them in the system list (default: 1) global.arcade.hideoriginals=1`  

