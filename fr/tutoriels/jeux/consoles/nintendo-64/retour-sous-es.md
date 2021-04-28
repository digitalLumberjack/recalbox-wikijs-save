---
title: Retour sous ES
---

# Retour sous ES

Mupen64plus n'est pas auto-configuré par Recalbox comme les autres émulateurs. Vous devez donc le faire manuellement.

Le mode vidéo de la N64 est défini dans votre fichier [recalbox.conf.](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf)  
Par défaut, nous utilisons le mode vidéo : `n64.videomode=DMT 4 HDMI`

Ce mode affiche une résolution de **640x480**.  
Nous avons défini cette résolution par défaut, car le Raspberry Pi 2 ne peut pas émuler le N64 à une résolution supérieure avec un bon taux de rafraîchissement.  
Ainsi, **640x480** est la résolution maximale à utiliser sur la Recalbox.


>**Attention** : si votre écran ne peut pas changer de résolution \(ex : écran tactile officiel Pi\), vous aurez des bordures noires autour de l'image car elle ne sera pas étirée pour s'adapter à l'écran.
{.is-danger}

* Dans ce cas, vous devez définir `n64.videomode=default` et modifier `/recalbox/share/system/configs/mupen64/mupen64plus.cfg` pour changer la résolution de sortie à celle native de votre écran \(ici **800x480**\) :

```text
[Video-General]
# Use fullscreen mode if True, or windowed mode if False
Fullscreen = False
# Width of output window or fullscreen width
ScreenWidth = 800
# Height of output window or fullscreen height
ScreenHeight = 480
```

Mais, tous les écrans n'ont pas la même compatibilité de mode vidéo.  
Ainsi, lorsque vous essayez de démarrer une partie de N64, vous pouvez avoir un écran noir avec un renvoi à EmulationStation. Dans ce cas, vous devez déterminer quels modes vidéo sont compatibles avec votre propre écran.  
  
Utiliser un [accès root](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal), puis tapez ces 2 commandes :

`tvservice -m DMT`

et

`tvservice -m CEA`

Les commandes renverront quelque chose comme ça :

```text
[root@RECALBOX ~]# tvservice -m DMT
Group DMT has 16 modes:
           mode 4: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 5: 640x480 @ 72Hz 4:3, clock:31MHz progressive 
           mode 6: 640x480 @ 75Hz 4:3, clock:31MHz progressive 
           mode 8: 800x600 @ 56Hz 4:3, clock:36MHz progressive 
           mode 9: 800x600 @ 60Hz 4:3, clock:40MHz progressive 
           mode 10: 800x600 @ 72Hz 4:3, clock:50MHz progressive 
           mode 11: 800x600 @ 75Hz 4:3, clock:49MHz progressive 
           mode 16: 1024x768 @ 60Hz 4:3, clock:65MHz progressive 
           mode 17: 1024x768 @ 70Hz 4:3, clock:75MHz progressive 
           mode 18: 1024x768 @ 75Hz 4:3, clock:78MHz progressive 
           mode 21: 1152x864 @ 75Hz 4:3, clock:108MHz progressive 
           mode 32: 1280x960 @ 60Hz 4:3, clock:108MHz progressive 
           mode 35: 1280x1024 @ 60Hz 5:4, clock:108MHz progressive 
           mode 36: 1280x1024 @ 75Hz 5:4, clock:135MHz progressive 
  (prefer) mode 57: 1680x1050 @ 60Hz 16:10, clock:119MHz progressive 
           mode 58: 1680x1050 @ 60Hz 16:10, clock:146MHz progressive 
```

et

```text
[root@RECALBOX ~]# tvservice -m CEA
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 2: 720x480 @ 60Hz 4:3, clock:27MHz progressive 
           mode 3: 720x480 @ 60Hz 16:9, clock:27MHz progressive 
  (native) mode 4: 1280x720 @ 60Hz 16:9, clock:74MHz progressive 
           mode 16: 1920x1080 @ 60Hz 16:9, clock:148MHz progressive 
```

Ok, maintenant nous disposons de tous les modes vidéo qui peuvent être utilisés sur ce moniteur.  
Il faut trouver un mode vidéo, avec une résolution égale ou inférieure à 640x480, puis définir ce mode dans le fichier [recalbox.conf.](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf)

Si je choisis ce mode vidéo :

```text
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive
```

Le fichier[ recalbox.conf](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf) doit être modifié comme suit :

* mode vidéo par défaut : `n64.videomode=DMT 4 HDMI`
* nouveau mode vidéo : `n64.videomode=CEA 1 HDMI`

## Cas particulier : écran CRT

Si vous utilisez un écran CRT, vous devez modifier votre mode vidéo comme suit :  
 `n64.videomode=default`

