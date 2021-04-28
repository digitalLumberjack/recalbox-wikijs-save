---
title: Unibios
---

# Unibios

## Que permet Unibios :

* Modifier la région \(Europe/USA/Japan\) et le mode \(AES/MVS\)
* Accéder au « soft dip » pour modifier la difficulté/vie/temps etc … du jeu
* Utiliser la base de données de cheats code
* Accéder au jukebox... et bien d'autres encore !

## FBNeo

### Installation

Lancez un jeu et aller dans le menu de retroarch \( **Hotkey + B** \)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUck9GGWWKOtN1H8A-%2Fscreenshot-2020-07-05T15-04-14-338Z.png?alt=media&token=ed2d90d3-2798-42d0-8a67-365852711411)

Aller dans :

> Quick Menu &gt; "Options"

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUczWu7rY7cUbRAwW7%2Fscreenshot-2020-07-05T15-04-24-712Z.png?alt=media&token=c1af0b4f-9110-4428-96a2-d33145b63378)

et passer "Use bios specified in BIOS dipswitch below" à "Use UNIBIOS bios"

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUdWNCiW42gDnd9NBX%2Fscreenshot-2020-07-05T15-04-44-781Z.png?alt=media&token=49b940fe-5bc4-4f26-bd0d-21a4ed1d4727)

> à / to :

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUdjU-KKE-LxRtB4yM%2Fscreenshot-2020-07-05T15-16-30-049Z.png?alt=media&token=5c6ee3b0-17f9-43f9-aa21-d848d9169a4d)

Ensuite descendre à "BIOS" et passer de "MVS Asia 6.1" à "Universe BIOS 4.0" ou "Universe BIOS 3.3"

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUe6ypsXo-wpizDUjX%2Fscreenshot-2020-07-05T15-05-04-261Z.png?alt=media&token=e4397547-295b-4b11-852e-e03da3f098b8)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUeD77bd-uem-_3pHh%2Fscreenshot-2020-07-05T15-05-14-178Z.png?alt=media&token=88dbcd52-185a-4194-903a-2b53c4e7b080)



### Utilisation

* Démarrez n'importe quel jeu neogeo, vous verrez alors le nouvel écran de boot UNIVERSE BIOS
* Pendant cet « écran de boot, pressez et maintenez `CBA (XBA)` pour modifier la région/mode - Appuyez sur `C` pour quitter
* To access the in-game menu, press and hold CBA \(XBA\) +START at the same time. 
* Pour accéder en jeu au menu, vous devez presser et maintenir 

  `CBA (XBA) + START`

## PiFBA

### Installation

1. Téléchargez-le ici \(version 4.0\): [http://unibios.free.fr/download.html](http://unibios.free.fr/download.html)  
2.  Extrayez le fichier téléchargé, puis renommez le fichier `uni-bios.rom` en `asia-s3.rom`
3. Ouvrez votre propre fichier `neogeo.zip`, il devrait déjà y avoir un fichier `asia-s3.rom` à l'intérieur ; faites en une sauvegarde si besoin.
4. Remplacez le fichier `asia-s3.rom` déjà présent dans le `neogeo.zip` par celui nouvellement renommé.
5. Uploadez le nouveau `neogeo.zip` dans les répertoires partagés `/bios` et `/finalburnalpha` de la Recalbox.



### Utilisation

* Démarrez n'importe quel jeu neogeo, vous verrez alors le nouvel écran de boot UNIVERSE BIOS v4.0.
* Pendant cet « écran de boot, pressez et maintenez `BXY` pour modifier la région/mode, ou maintenez `ABX` pour activer le menu « dip switch »
* Pour accéder en jeu au menu, vous devez presser et maintenir `BXY+START`

## Dip Switch

Pour accéder au menu « dip switch » pendant le démarrage de l'écran de boot UNIVERSE BIOS, maintenez `A+X+Y`

### Réglage du Dip Switch :

* Pour afficher le saignement :
  * Region Japan / Mode arcade
  * slot metal slug
  * blood &gt; on
  * Appuyez sur `C` pour quitter.

## BIOS

Neo Geo nécessite un fichier BIOS neogeo.zip.

* Il sera placé avec vos ROMs dans :

```text
/recalbox/share/roms/neogeo
or
/recalbox/share/roms/fbneo
```

* Voici le contenu d'un fichier BIOS neogeo.zip certifié fonctionnel

```text
000-lo.lo
asia-s3.rom
japan-j3.bin
neo-geo.rom
ng-lo.rom
ng-sfix.rom
ng-sm1.rom
sfix.sfix
sm1.sm1
sp-1v1_3db8c.bin
sp-45.sp1
sp-e.sp1
sp-j2.sp1
sp-s.sp1
sp-s2.sp1
sp-u2.sp1
sp1.jipan.1024
uni-bios_1_0.rom
uni-bios_1_1.rom
uni-bios_1_2.rom
uni-bios_1_2o.rom
uni-bios_1_3.rom
uni-bios_2_0.rom
uni-bios_2_1.rom
uni-bios_2_2.rom
uni-bios_2_3.rom
uni-bios_2_3o.rom
uni-bios_3_0.rom
uni-bios_3_1.rom
vs-bios.rom
```

