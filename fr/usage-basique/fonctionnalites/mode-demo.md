---
title: Mode Démo
description: A partir de la version 6.0
---

# Mode Démo

Le mode démo n'est ni plus, ni moins qu'un écran de veille qui lance vos jeux en fond d'écran.

Le mode demo pioche dans une liste de systèmes \(par défaut il y a toutes les consoles 8/16 bits, hormis les portables\), et il lance un jeu au hasard dans un système choisi.  
Il conserve un historique interne pour éviter de lancer 2 fois le même système d'affilée ou de lancer 2 fois le même jeu.

![](./image%20%28328%29.png)

## Configuration

### Activation dans le Menu EmulationStation

Pour activer cette fonction :

* Menu EmulationStation
* 
### Personnalisation via le fichier recalbox.conf

```text
## Demo screensaver parameters
## Set the system list from which ES will run random games.
## Empty list or unexisting key means all available systems
global.demo.systemlist=3do,amigacd32,atari2600,atari5200,atari7800,daphne,fba_libretro,fds,gamegear,gba,lynx,mame,mastersystem,megadrive,neogeo,nes,ngpc,o2em,pcengine,sega32x,sg1000,snes
## Default demo game sessions last 90s. Change this value if you want shorter or longer sessions
;global.demo.duration=90
```

