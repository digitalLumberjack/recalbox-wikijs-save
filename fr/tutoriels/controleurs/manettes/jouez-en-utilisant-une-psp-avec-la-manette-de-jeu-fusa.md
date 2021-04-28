---
title: Jouer en utilisant une PSP avec la manette de jeu FuSa
---

# Jouer en utilisant une PSP avec la manette de jeu FuSa

Avec un firmware personnalisé tel que le **pro CFW** et le **ME CFW**, mais aussi grâce à la flexibilité naturelle de la PSP et au matériel semi-ouvert, avec l'aide de la manette FuSa \(une application homebrew pour la PSP\), vous pouvez obtenir l'une des meilleures manettes SNES pour votre Raspberry Pi.

## Ce qu'il nous faut ?

* Un PSP modèle 1xxx 2xxx ou 3xxx \(modèles 2xxx & 3xxx de préférence\)
* Une carte mémoire de 1GB ou supérieur Pro Duo
* Un câble mini USB à USB A
* Un firmware personnalisé \(Pro ou ME / LME\)
* Un PC ou votre Pi pour transférer les fichiers sur SAMBA
* L'application de la [manette FuSa](http://foosa.do.am/load/fusa_gamepad_version_03/3-1-0-33)

## Pour commencer

Téléchargez le zip de la manette de jeu FuSa, puis allumez votre PSP avec votre carte mémoire dans votre console et si c'est un modèle 3000 ou bien lancer votre CFW \(les anciens modèles n'ont pas besoin de le lancer car ces modèles démarrent déjà avec le CFW chargé\), branchez votre câble USB à votre PSP et à votre PC, décompressez votre zip dans `/PSP/GAMES/` et débranchez-le de votre PC de manière sûre.

Lancez maintenant l'application et connectez-la à votre Pi, l'écran de votre PSP devrait être éteint mais la LED d'alimentation devrait normalement rester allumée.

## Disposition recommandée

Pour une expérience homogène à l'intérieur et à l'extérieur d'EmulationStation, y compris dans Kodi et tous les noyaux RetroArch et parce que toutes les manettes de jeu Playstation au Japon utilisent la même disposition qu'une manette de jeu SNES mais avec des symboles différents, je suggère d'utiliser cette configuration de boutons plus ma petite suggestion pour les boutons de volume et le bouton d'accueil dans Kodi.

![Disposition PSP](https://cloud.githubusercontent.com/assets/10035308/16599632/7f34c9ec-42c0-11e6-8988-0b2d6e795d10.png)

## A prendre en considération

* La PSP Street n'est pas supportée.
* Si votre PSP est en bon état, elle est bien meilleure qu'une manette générique ou qu'une manette de jeu 360. Les boutons sont très réactifs et le D-Pad est idéal pour les jeux rétro.
* Le Pi n'est PAS capable de charger complètement une PSP.
* Les boutons de volume ne fonctionnent pas dans EmulationStation ou RetroArch
* Vous pouvez accéder à une configuration plus approfondie dans les fichiers .ini du FuSa.

