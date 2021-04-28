---
title: Romulus pour l'Arcade
description: >-
  Utilisation de Romulus Rom Manager pour les systèmes Arcade (MAME, FinalBurn
  Neo, ...)
---

# Romulus pour l'Arcade


>Merci de se référer à la partie [Romulus pour les Consoles](romulus-pour-les-consoles.md) afin de connaitre le fonctionnement de base de Romulus \(ajouter et paramétrer un .dat, reconstruire un romset, …\).
{.is-info}

## Modes de fichier

Les romsets d'Arcade comportent beaucoup de jeux donc certains ont une base commune. On parle alors de jeux "Parent / Clone", "Parent" pour le jeu principal \(le 1er jeu édité par exemple\) et de clones pour tous les dérivés de ce jeu \(une autre langue, une autre région, un autre nom, …\).

De plus, contrairement aux romsets console où la norme est "1 jeu = 1 rom", les jeux arcade comportent plusieurs roms pour constituer le jeu.

Dans Romulus, il y a 3 modes possibles pour l'assemblage des ces jeux \(ces mêmes modes sont similaires dans beaucoup de gestionnaire de roms\).

### Détail des 3 modes

![main set = parent  /  clone set = clone](./image%20%28313%29.png)

* **Split / Not Merged** : Toutes les roms nécessaires au fonctionnement du jeu sont dans le fichier ou le dossier du jeu \(plus d'espace de stockage est utilisé car des roms communes sont présentes dans chaque jeu\).
* **Split / Merged** : Toutes les roms nécessaires au fonctionnement du jeu Parent sont dans le fichier ou le dossier du jeu. Le fichier ou le dossier du jeu Clone ne contient que les roms particulières le composant \(mais pour fonctionner, le jeu clone a besoin de roms présentes dans le jeu parent\).
* **Not Split** : Toutes les roms des jeux parent ou clone sont dans le même fichier ou le même dossier.


>Pour une utilisation des jeux dans Recalbox, il est conseillé d'utiliser le mode **Split / Merged**.
{.is-info}

## Les jeux Arcade dans Romulus

![](./image%20%28269%29.png)

* **Ligne surlignée en bleu** : La colonne "**Clone de**" vide indique qu'il s'agit d'un jeu parent. L'icône verte à gauche indique que le jeu est complet \(Icône jaune = jeu incomplet, icône rouge = jeu absent\).
* **A** : Dans cette table se trouve le détail du jeu sélectionné. Il s'agit de la liste des roms composant le jeu. La pastille verte indique que que la rom est présente et conforme au fichier .dat \(Pastille rouge = rom manquante\).
* **B** : La colonne "**Clone de**" n'est pas vide, il s'agit de jeux clones. Le nom du jeu parent est indiqué dans cette colonne.

## Fichiers Sample et CHD

![](./image%20%28173%29.png)

Lors de la configuration du fichier .dat pour l'arcade \(voir [Configurer le fichier .dat ajouté](romulus-pour-les-consoles.md#configurer-le-fichier-dat-ajoute)\), il faut parfois définir d'autres répertoires en plus de celui des roms : un répertoire pour les **Samples** \(Fichiers audio nécessaires à certains jeux\) et un répertoire pour les **CHD** \(Image CD complémentaire de la rom pour le fonctionnement des jeux les plus récents\).

