---
title: Affichage des systèmes
description: >-
  Fonctionnement et modifications de l'affichage des systèmes. (Recalbox v6.1 et
  supérieur)
---

# Affichage des systèmes

## Fonctionnement de l'affichage

L’affichage des systèmes dans le menu de Recalbox est géré par le fichier _« es\_systems.cfg »_. Ce fichier se situe dans le dossier :


>./recalbox/**share\_init**/system/.emulationstation/es\_systems.cfg
{.is-info}

Il contient les noms des différents systèmes qui sont supportés par votre version de Recalbox. Il est construit de la manière suivante :

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Panasonic 3DO</fullname>
    <name>3do</name>
    <path>/recalbox/share/roms/3do</path>
    <extension>.iso .ISO .cue .CUE .chd .CHD</extension>
    <command>python /usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc %CONTROLLERSCONFIG% -system %SYSTEM% -rom %ROM% -emulator %EMULATOR% -core %CORE% -ratio %RATIO% %NETPLAY%</command>
    <platform>3do</platform>
    <theme>3do</theme>
    <emulators>
      <emulator name="libretro">
        <cores>
          <core>4do</core>
        </cores>
      </emulator>
    </emulators>
  </system>
  <system>
      [. . .]
  </system>
  [. . .]
</systemList>
```

L’affichage des systèmes respecte l’ordre dans lequel ils sont listés dans ce fichier. Il contient aussi la configuration de ces systèmes.

## Modifier l'ordre d'affichage


>**IMPORTANT** :  
>Il ne faut **PAS MODIFIER** le fichier _« es\_systems.cfg »_ original \(qui est dans le répertoire _«_ share\_init _»_\). En cas de problème sur les modifications apportées plus tard, il reste la seule et unique source pour faire fonctionner correctement Recalbox.
{.is-danger}

La modification de l’ordre d’affichage doit se faire uniquement à partir du fichier _« es\_systems.cfg »_ présent dans le répertoire suivant :


>./recalbox/**share**/system/.emulationstation/es\_systems.cfg
{.is-info}

**D'origine, ce fichier n’existe pas**. Il faut soit copier le fichier original, soit créer un nouveau fichier. Une fois le nouveau fichier créé, il est possible de mettre les systèmes dans l'ordre que l’on désire. La configuration des systèmes sera toujours prise à partir du _« es\_systems.cfg »_ originel, mais l'ordre des systèmes sera celui défini dans le nouveau fichier.

Si, dans le nouveau fichier, un système est absent ou mal renseigné, la priorité est rendue au fichier origin**a**l. Pour le nouveau fichier, il n’y a que 2 clés d’entrées qui sont obligatoires : _**« fullname »**_ et _**« platform »**_, toutes les autres sont optionnelles. Le fichier devra être construit au minimum de la manière suivante :

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Nintendo Entertainment System</fullname>
    <platform>nes</platform>
  </system>
  <system>
    <fullname>Family Computer Disk System</fullname>
    <platform>fds</platform>
  </system>
  <system>
    <fullname>Super Nintendo Entertainment System</fullname>
    <platform>snes</platform>
  </system>
  <system>
    <fullname>Satellaview</fullname>
    <platform>satellaview</platform>
  </system> 
    [. . .]
  </system>
  [. . .]
</systemList>
```

## Ajouter un système **«** Custom **»**


>**IMPORTANT** : Il ne faut **PAS MODIFIER** le fichier _« es\_systems.cfg »_ original \(qui est dans le répertoire _«_ share\_init _»_\). En cas de problème sur les modifications apportées plus tard, il reste la seule et unique source pour faire fonctionner correctement Recalbox.
>
>Cette manipulation ne permet pas d'ajouter un nouvel émulateur à Recalbox mais d'ajouter une nouvelle entrée système dans le menu de sélection.
>
>Il est possible de combiner la modification de l'ordre des systèmes et l'ajout d'un ou plusieurs systèmes customs.
{.is-danger}

Comme pour la modification de l'ordre des système, l'ajout d'un système _«_ custom _»_ doit se faire uniquement à partir du fichier _« es\_systems.cfg »_ présent dans le répertoire suivant :


>./recalbox/**share**/system/.emulationstation/es\_systems.cfg
{.is-info}

**D'origine, ce fichier n’existe pas**. Il faut soit copier le fichier original, soit créer un nouveau fichier. Une fois le nouveau fichier créé, il est maintenant possible d'y ajouter un nouveau système.

Si, dans le nouveau fichier, un système est mal renseigné, la priorité est rendue au fichier origin**a**l. Pour le nouveau fichier, toutes les clés d’entrées sont obligatoires. Donc, pour créer un nouveau système, le plus simple est de partir d'un système existant \(et correspondant aux roms que l'on veut y inclure\) et de ne modifier que le stricte nécessaire :   
- _**« fullname »**_ : Permet de donner le nom du nouveau système.  
_****- **« path »**_ : Permet d'indiquer le répertoire contenant les roms du nouveau système.  
_****- **« theme »**_ : Permet d'indiquer quel thème utiliser. Il faut, au préalable, créer ce nouveau thème \(logo, fond, ...\)  
_****_**Toutes les autres entrées ne doivent pas être modifiées.** 

Voici un exemple d'ajout pour un système basé sur la SNES pour n'y inclure que des roms traduites :

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Super Nintendo Fan Trad</fullname>
    <name>snes</name>
    <path>/recalbox/share/roms/snestrad</path>
    <extension>.smc .sfc .SMC .SFC .mgd .MGD .zip .ZIP .7z .7Z</extension>
    <command>python /usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc %CONTROLLERSCONFIG% -system %SYSTEM% -rom %ROM% -emulator %EMULATOR% -core %CORE% -ratio %RATIO% %NETPLAY%</command>
    <platform>snes</platform>
    <theme>snestrad</theme>
    <emulators>
      <emulator name="libretro">
        <cores>
          <core>snes9x2005</core>
          <core>snes9x2010</core>
          <core>snes9x2002</core>
        </cores>
      </emulator>
    </emulators>
  </system>
</systemList>
```

