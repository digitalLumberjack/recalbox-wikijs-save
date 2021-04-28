---
title: Vidéos d'introduction
---

# Vidéos d'introduction

### 1. Ajouter de nouvelles vidéos d'introduction \( splashscreen \)

L'ajout de vidéo d'introduction se fait via le répertoire **share/bootvideos**. Il est à noter toutefois que cet ajout ne peut se faire que via le réseau.

En voici l'explication : 

Le répertoire où se trouvent les vidéos n'est pas accessible car en dehors de la partition **/share**. Afin de palier à cette contrainte nous avons mis en place un "faux" répertoire sur cette dernière, destiné à recevoir vos vidéos custom.

Le "vrai" répertoire se trouve dans la partition **/overlay** du système Recalbox. Lors du démarrage, le système relie le "faux" répertoire \(share/bootvideos\) et le "vrai" \(/overlay/bootvideos\).

Cette manipulation permet au système de lire les vidéos que vous avez placé dans le "faux" répertoire.

La raison à ça est que le dossier share n'est monté que bien après que le chargement des vidéos. Dans l'ordre de démarrage, le script de montage du share est en position 11, les vidéos en 6.

### 2. Paramètres liés aux vidéos d'introduction \( splashscreen \)

system.splash.select=all dans recalbox.conf

