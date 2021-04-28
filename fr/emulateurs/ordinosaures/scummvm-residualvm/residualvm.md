---
title: ResidualVM
---

# ResidualVM

## Qu'est-ce que ResidualVM ? <a id="quest-ce-que-residualvm"></a>

**ResidualVM** est un projet frère de **ScummVM**.  
Il permet de jouer aux jeux qui ne sont pas \(et probablement jamais\) supportés par ScummVM. Par exemple, les jeux utilisant le moteur **GrimE**.  
Trois jeux sont pour le moment supportés par cet émulateur: **Grim Fandango**, **Escape from Monkey Island** et **Myst III - Exile**.

## Comment jouer à des jeux ResidualVM sur Recalbox ? <a id="comment-jouer-a-des-jeux-residualvm-sur-recalbox"></a>

**ResidualVM** a été ajouté comme un **second émulateur au système ScummVM**.  
**Le changement** entre **ScummVM** et **ResidualVM** est automatique.  
En effet, la **façon d’ajouter des jeux** dans votre Recalbox est la **même que pour ScummVM**.  
**La seule différence** concerne **l'extension du fichier** à utiliser.  
Une fois votre **jeu copié** dans le répertoire `/recalbox/share/roms/scummvm`, vous **devez nommer** le fichier de raccourci **gameShortName.residualvm** à la place de **gameShortName.scummvm** \(par exemple, grim.residualvm pour Grim Fandango\).  
Recalbox sélectionnera alors **automatiquement le bon émulateur.**

Si vous désirez **plus d'informations**, merci de consulter la [documentation ResidualVM](http://www.residualvm.org/documentation/).

## Quels jeux sont compatibles ? <a id="quels-jeux-sont-compatibles"></a>

Vous trouverez la [liste complète de compatibilité](http://www.residualvm.org/compatibility/) sur le site **ResidualVM.**

Notez bien que, pour le moment, **Escape from Monkey Island** coince après l'introduction sur les plateformes RPI.

