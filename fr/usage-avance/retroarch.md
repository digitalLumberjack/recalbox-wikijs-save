---
title: Retroarch
---

# Retroarch

**RecalboxOS** utilise [**RetroArch**](https://github.com/libretro/RetroArch), créé par [Twinaphex](https://github.com/twinaphex), comme interface pour les émulateurs.

Retroarch est le programme qui fait fonctionner la plupart des émulateurs de RecalBox.

## Qu'est-ce que c'est ? <a id="quest-ce-que-cest"></a>

Retroarch est un front-end libretro, ce qui veut dire qu'il peut lancer le contenu des cores libretro, il unifie aussi la façon dont ces cores fonctionnent avec le système.

Un core est un programme adapté pour fonctionner avec les front-ends libretro, dans ce cas, la plupart sont des émulateurs.

## Fonctionnalités <a id="fonctionnalites"></a>

Retroarch, dans sa nature, est un programme lançant d'autres petits programmes, cependant, il leur dit aussi comment les commandes sont configurées \(donc vous n'aurez besoin de configurer votre manette qu'une seule fois pour tous les cores, à la place d'une fois par core\), les fonctionnalités ajoutées sont généralement disponibles à travers plusieurs cores, et peuvent être accédées de la même façon pour chacun des cores. 

En bref, il met en place un standard que les cores suivront.

L'interface de Retroarch permet de modifier de nombreux paramètres, mais dans la plupart des cas, les valeurs par défaut devraient être correctes. Cependant, les options de Core, par exemple, peuvent vous permettre de changer la région du système dans laquelle vous jouez actuellement, si nécessaire. Comme d'habitude, ces paramètres ne doivent pas être modifiées sans une réflexion préalable.

Elle comprend également les fonctionnalités de base offertes par un émulateur \(telles que les save states, les captures d'écran, le disc-wrapping pour les systèmes basés sur CD, ...\), ainsi que des paramètres plus avancés \(shaders, rembobinage et avance rapide, netplay, ...\) dont certains sont accessibles à l'aide de **combinaisons avec la hotkey**.

## Exigences <a id="required"></a>

Bien que Retroarch et Recalbox essaient tant que faire se peut de simplifier les choses pour l'utilisateur final, certains cores ont des exigences pour fonctionner correctement, comme des BIOS ou le bon format de fichier pour un jeu ; le webmanager peut vous dire de quels BIOS vous disposez ou avez besoin pour les différents systèmes émulés, et les fichiers `readme.txt` à l'intérieur de chaque système vous indiqueront quels formats sont pris en charge pour chaque système.

Nous vous conseillons aussi vivement de comprendre ce que vous faites pour certains systèmes \(comme l'arcade par exemple\), car le fait de mettre des fichiers aléatoires et de s'attendre à ce que cela fonctionne peut tout simplement ne pas fonctionner du tout selon la situation.

