---
title: Uzebox
---

# Uzebox

![](/migration-images/emulateurs/consoles-fantasy/uzebox/image%20%28213%29.png)

## Fiche technique

* **Fabricant** : Belogic Software
* **Année de sortie** : 2008
* **CPU** : Amtel ATmega644 microcontroller @ 28.6 Mhz
* **RAM** : 4 K
* **Mémoire des programmes** : 64 K
* **Son** : 5 canaux wavetable synthesis, 8-bit mono, mixé à ~15Khz et sortie via PWM
* **Résolution** : 9 modes vidéo allant jusqu'à 360x224 pixels en mode mosaïque uniquement
* **Couleurs** : 256 couleurs simultanées arrangées dans un espace colorimétrique 3:3:2
* **Média** : carte SD

## Présentation 

L'Uzebox est une console de jeu rétro-minimaliste open source. Il est basé sur un microcontrôleur AVR 8 bits à usage général fabriqué par Atmel. La particularité du système est qu'il est basé sur un moteur alimenté par interruption et n'a pas de frame buffer. Des fonctions telles que la génération de synchronisation vidéo, le rendu des tuiles et le mixage de musique sont effectuées en temps réel dans le logiciel par une tâche d'arrière-plan afin que les jeux puissent être facilement développés en C.  
L'objectif de conception était d'être aussi simple que possible tout en ayant un son et des graphiques suffisamment bons tout en laissant suffisamment ressources pour mettre en œuvre des jeux intéressants. L'accent a été mis sur le fait de le rendre facile et amusant à assembler et à programmer pour tous les amateurs. La conception finale ne contient que deux puces: un ATmega644 et un convertisseur AD725 RVB vers NTSC.

De nombreuses versions commerciales sont disponibles ou lorsqu'elles sont disponibles: Uzebox AVCore par Embedded Engineering llc et Fuzebox par Adafruit Industries. Il y a aussi le kit Uzebox deluxe et l'EUzebox, une version avec une interface SCART. Obtenez-en un si vous ne connaissez rien à l'électronique !

Traits :

* Interruption : aucun comptage de cycle requis, le mixage sonore et la génération vidéo sont tous réalisés en arrière-plan
* Moteur sonore à 5 canaux : le sous-système sonore est composé de 3 canaux de table d'ondes, 1 bruit et 1 canal PCM. Le son est mono 8 bits, mixé à ~ 15Khz
* 256 couleurs simultanées disposées dans un espace colorimétrique 3: 3: 2 \(rouge: 3 bits, vert: 3 bits, bleu: 2 bits\)
* Résolution : 9 modes vidéo offrant jusqu'à 360 x 224 pixels \(mosaïques uniquement, mosaïques et sprites et modes vidéo bitmap\)
* Défilement plein écran dans certains modes vidéo
* Sprites : jusqu'à 32 sprites simultanés
* Entrées prises en charge : deux entrées de joypad compatibles SNES \(y compris la souris SNES\)
* MIDI In : Avec un séquenceur musical, permet la création de musique directement sur la console
* API SD / MicroSD et FAT16
* Extension 'Uzenet' pour wifi ESP8266 et 1 Mo de RAM SPI
* Interface clavier PS / 2
* GameLoader : 4K Bootloader qui permet de flasher des jeux à partir d'une carte SD formatée FAT16 standard
* Émulateur multiplate-forme avec prise en charge de GDB pour faciliter le développement
* Plusieurs outils pour convertir MIDI, fichier audio et graphiques pour inclure des fichiers

Les sources sont livrées avec des jeux entièrement fonctionnels, des démos, des outils de génération de contenu et même un émulateur multiplate-forme !

## Émulateurs

{% page-ref page="libretro-uzem.md" %}

