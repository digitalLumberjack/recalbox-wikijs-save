---
title: Les Roms et les Isos
---

# Les Roms et les Isos

## Qu'est-ce qu'une Rom / un Iso

L'émulation d'un jeu consiste à reproduire sur une machine le comportement d'un jeu qui a été programmé pour un autre type de machine.

Sur la machine appropriée \(console ou borne d'arcade\), le programme n'est pas émulé, on dit que le jeu fonctionne en _**natif**_.   
Il est généralement stocké dans des mémoires mortes \(sur la carte mère ou dans des cartouches enfichables\) ; leur contenu est ainsi appelé ROM dans l’usage courant.

Un émulateur fonctionne de la même façon que cette machine, en chargeant cette ROM et en exécutant le programme \(jeu\) qui y est stocké, en s'adaptant aux ressources disponibles \(périphériques d'entrées/sorties, vitesse d'exécution, etc.\).

Plus récemment, le contenu des jeux stockés sur CD-ROM ou DVD peut être copié dans un fichier image appelé ISO ; sur le même principe que l'émulation de ROMs, on peut émuler un jeu stocké en fichier ISO.

Il existe souvent plusieurs versions du même dump \(sauvegarde\) d'une ROM, mais la plupart d’entre elles sont obsolètes. Certaines versions peuvent être des dumps incorrects, des hacks, des faux, des overdumps, des underdumps, etc... 

Un set de rom est plus souvent appelé **romset**.

### Fichier dat



### Fichier header

Un fichier header \(l'en-tête\) correspond aux 16 premiers octets d'une ROM pouvant être lus dans un émulateur.  
Il indique à l'émulateur la taille de la ROM, la région du jeu, le mappeur qu'il utilise, le type de mise en miroir dont il dispose, la console pour laquelle il est destiné \(console principale ou système VS.\), etc. \(IIRC\) le plus , sinon tous, certains émulateurs ne vous permettront pas d'exécuter le jeu s'il n'a pas d'en-tête.

Sur SNES, c'étaient les entêtes créés par les copieurs de l'époque.  
Ils ne servent à rien de nos jours et servaient uniquement à "signer" et verrouiller les ROMs sur le copieur.  
Pour les utilisateurs, les ROMs headered correspondent à des ROMs qui ont été extraites avec des anciens copieurs de type Super Wild Card \(extension SWC\), Super Magic Card \(format SMC\).  
Ces ROMs n'ont plus lieu d'être à ce jour et ne correspondent plus à une réalité, mais il est parfois nécessaire pour des hacks réalisés à cette époque \(fin années 90 au milieu des années 2000\).  
Afin de garder une certaine compatibilité pour d'anciens émulateurs comme ZSNES ou des versions anciennes de Snes9X.  
Les versions unheadered n'ont pas ces infos provenant des copieurs et correspondent au contenu des puces sur les PCBs. 

Pour la NES, c'est différent, on parle là des headers iNES, qui est un format qui a été conçu afin de schématiser les différents types de PCBs et révisions de cartouches existantes, notamment les co-processurs \(comme les puces MMC\) ou des processeurs sons \(comme les Konami VRCx\).  
Des émulateurs en ont besoin pour décrire les ROMs et savoir comment les lancer.  
Mais des émulateurs récents voient autrement, ce n'est pas à la ROM d'avoir cette information, mais bien avoir une base de données dans l'émulateur \(ou à côté\), contenant ces informations supplémentaires.  
La ROM ne devrait contenir que le code provenant des puces physiques, rien d'autre.  
Des émulateurs comme Nestopia ou Mesen, ont ces bases, et se servent des calculs CRC32 pour retrouver la bonne ROM avec le bon descripteur dans la base de données.

