---
title: Libretro REminiscence
description: 'REminiscence Core pour: Flashback - The Quest for Identity'
---

# Libretro REminiscence

Stuart Carnie a porté REminiscence, l'émulateur Flashback de Gregory Montoir, sur libretro! REminiscence est une reconstitution du moteur de jeu du jeu d'aventure et d'action de 1992/1993 Flashback. C'est le successeur spirituel de Another World / Out Of This World et il se distingue par des graphismes rotoscopiques, des cinématiques polygonales et un système de jeu de style Prince of Persia.

Ce port est toujours un travail en cours, mais il est en état de fonctionnement. Actuellement, il saute directement dans le jeu, sautant le menu principal.

Nous avons également ajouté le support modplug au cœur pour une lecture de musique améliorée.

Le noyau REminiscence a été créé par

* Grégory Montoir
* Stuart Carnie

## \*\*\*\*![](./gerald-g-parchment-background-or-border-5.svg)**Licence**

Ce core est sous licence **GPLv3**.

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC X86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  |  |  |  |  |  |  |  |  |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| **Fonctionnalités** | **Supporté** |
| :--- | :--- |
| Screenshots | ✔ |
| Saves | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](./tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## ![](./rom-30098_640.png)**Roms**

### Comment installer les fichiers nécessaires

Versions de jeu Flashback reconnues:

* Flashback DOS Demo \(disquette\)
* Flashback DOS Full version \(disquette\)
* Flashback DOS Full version \(CD\)

### Emplacement

Placez lez roms comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 ports
> > >
> > > > 📁 Flashback
> > > >
> > > > > 📁 data
> > > > >
> > > > > > 🗒 **instru\_e.pal**

## 🗂 Contenus complémentaires

### Ajouter le son pendant les cinématiques

L'exécutable prend également en charge les musiques pendant les cinématiques de la version **Amiga**. Il faut récupérer les fichiers dans le répertoire `music\` des diskettes d'origines OU récupérer les fichiers sur le web et ajouter `mod.flashback-` devant chaque fichier music de la version Amiga. ATTENTION: ne pas mettre d'extensions de fichiers.

| Liste des fichiers à placer dans `roms\ports\Flashback\data\` |
| :--- |
| `mod.flashback-ascenseur` |
| `mod.flashback-ceinturea` |
| `mod.flashback-chute` |
| `mod.flashback-desintegr` |
| `mod.flashback-donneobjt` |
| `mod.flashback-fin` |
| `mod.flashback-fin2` |
| `mod.flashback-game_over` |
| `mod.flashback-holocube` |
| `mod.flashback-introb` |
| `mod.flashback-jungle` |
| `mod.flashback-logo` |
| `mod.flashback-memoire` |
| `mod.flashback-missionca` |
| `mod.flashback-options1` |
| `mod.flashback-options2` |
| `mod.flashback-reunion` |
| `mod.flashback-taxi` |
| `mod.flashback-teleport2` |
| `mod.flashback-teleporta` |
| `mod.flashback-voyage` |

### Ajouter les dialogues en jeu

Pour les dialogues en jeu, vous devez copier le fichier `VOICE.VCE` du répertoire `data\` de la version SegaCD dans le répertoire `roms\ports\Flashback\data\`


>Ne chercher pas la version française des voix en SegaCD. Il n'existe que la version \(USA\) du jeu SegaCD.
{.is-warning}

## Joypad

| Entrées RetroPad | Descriptions |
| :--- | :--- |
| ![](https://docs.libretro.com/image/retropad/retro_b.png) | Dégainer / Rengainer |
| ![](https://docs.libretro.com/image/retropad/retro_y.png) | Inventaire / Ignorer |
| ![](https://docs.libretro.com/image/retropad/retro_a.png) | Utilisation |
| ![](https://docs.libretro.com/image/retropad/retro_x.png) | Action |
| ![](https://docs.libretro.com/image/retropad/retro_dpad_up.png) | Vers le haut |
| ![](https://docs.libretro.com/image/retropad/retro_dpad_down.png) | Vers le bas |
| ![](https://docs.libretro.com/image/retropad/retro_dpad_left.png) | La gauche |
| ![](https://docs.libretro.com/image/retropad/retro_dpad_right.png) | Droite |

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github utilisé :** [https://github.com/libretro/REminiscence/](https://github.com/libretro/REminiscence)\*\*\*\*
* **Site Officiel :** [http://cyxdown.free.fr/reminiscence/](http://cyxdown.free.fr/reminiscence/)

