---
title: Brancher un Monnayeur Comparatif sur un Raspberry Pi \(toutes versions\)
---

# Brancher un Monnayeur Comparatif sur un Raspberry Pi \(toutes versions\)

Tout d'abord, pour ce tutoriel, j'ai repris des éléments de la notice fournie avec [ce monnayeur exclusif](http://www.smallcab.net/monnayeur-comparateur-facade-silver-p-902.html).

Aussi, sachez qu'en aucun cas, je ne fais de publicité pour les enseignes ci-dessus, ce ne sont juste que des exemples. Enfin, je ne saurai être tenu responsable en cas de problème.

## 1 - Principe de fonctionnement du monnayeur

Le monnayeur comparateur fonctionne par comparaison entre la pièce insérée et la pièce dite « témoin » installée en permanence dans le monnayeur. Le monnayeur analyse la signature électronique de la pièce insérée et la compare avec la signature électronique de la pièce témoin.

Si la pièce insérée a une signature proche de la pièce témoin, la pièce est acceptée, sinon la pièce est refusée. Lorsqu'une pièce est acceptée, le monnayeur génère une impulsion électrique à destination du Raspberry Pi.

Cette impulsion est reconnue par Recalbox \(Touche **Select**\) et un crédit de jeu est alors octroyé au joueur.


>**Note** : il est possible d'utiliser des jetons métalliques \(« _token_ »\) à la place des pièces.
{.is-info}

Très simple à faire, à base de quatre fils :

* Rouge : +12V à brancher sur [une alimentation 12V/1A](https://www.amazon.fr/dp/B00B0T5D5W/).
* Blanc : "Insert coin" à brancher sur le GPIO \(ou contrôleur USB\), correspondant à la touche **Select** sous Recalbox.


>Obligatoirement par l'intermédiaire d'un "relais" !
{.is-danger}

* Noir : Masse à brancher sur le 0V de l'alimentation 12V/1A.
* Gris : Compteur \(non utilisés ici\)

## 2 - Installation avec un Raspberry Pi

Vous l'aurez compris, l'utilisation de CE monnayeur avec un Raspberry Pi nécessite obligatoirement l'utilisation d'un composant électronique intermédiaire appelé « relais » ou « hack clavier » pour les puristes.

Voici donc une solution à moindre frais pour fabriquer vous même ce "hack clavier".

## 3 - Liste du matériel à prévoir

* 1 bon fer à souder, du fil pour faire les pistes, de l'étain et de l'huile de coude
* 1 [relais 12V](https://www.amazon.fr/dp/B013SPRXQC) \(5 fils\)
* 1 [carte prototype](https://www.amazon.fr/dp/B01GUZ5L6G/)
* 2 [borniers](https://www.amazon.fr/dp/B00I00OHHY)

## 4 - Câblage


>N'hésitez surtout pas à tester votre carte AVANT de la raccorder à votre Raspberry et votre monnayeur !
{.is-warning}

Le câblage du monnayeur avec un Raspberry Pi nécessite donc l' installation de ce "hack clavier" ENTRE le monnayeur ET le GPIO de votre Raspberry pi.

Les 2 broches du « Bornier 1 » sont à connecter :

* l'une sur le fil "0V" de votre alimentation 12V/1A.
* l'autre sur le fil "blanc" de votre monnayeur.

Les 2 broches du « bornier 2 » sont à connecter :

* l'une sur la pin « GND » du connecteur GPIO du Raspberry Pi.
* l'autre sur une pin « GPIOxx » du connecteur GPIO du Raspberry Pi. \(touche Select\)


>Il existe plusieurs modèles / générations de Raspberry Pi
{.is-warning}

Se reporter à la documentation spécifique à votre modèle pour bien identifier le connecteur GPIO du Raspberry Pi et la position des broches « GND » et « GPIOxx » au sein de ce connecteur.

• [https://fr.wikipedia.org/wiki/Raspberry\_Pi](https://fr.wikipedia.org/wiki/Raspberry_Pi)

• [https://www.raspberrypi.org/](https://www.raspberrypi.org/)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzcIIKiUTJkoR6QgOtm%2F-LzcJioU5qb9FZhzDZNf%2F68747470733a2f2f73332d65752d776573742d312e616d617a6f6e6177732e636f6d2f666f72756d732e726563616c626f782e636f6d2f33643837316434632d663734322d346266372d393366632d3062383035613439666365312e6a7067.jpg?alt=media&token=11d964cb-5a54-4747-8b6f-7e0a7a0ac089)

