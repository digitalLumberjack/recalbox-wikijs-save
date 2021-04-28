---
title: Testez votre joystick avec sdl2-jstest
---

# Testez votre joystick avec sdl2-jstest

Pour **tester votre manette** vous devez :

* **Ouvrir** une session **ssh via putty** 
* Puis **exécuter la commande** suivante : `sdl2-jstest`

## Lister le numéro de vos pads avec la commande suivante <a id="lister-le-numero-de-vos-pad-avec-la-commande-suivante"></a>

```text
sdl2-jstest --list
```

Résultat :

```text
Joystick Name: 'DragonRise Inc.   Generic   USB  Joystick'
Joystick Path: '/dev/input/event0'
Joystick GUID: 030000001008000001e5000010010000
Joystick Number: 0
Number of Axes: 2
Number of Buttons: 10
Number of Hats: 0
Number of Balls: 0
GameController:
not a gamepad
Axis code 0: 0
Axis code 1: 1
Button code 0: 288
Button code 1: 289
Button code 2: 290
Button code 3: 291
Button code 4: 292
Button code 5: 293
Button code 6: 294
Button code 7: 295
Button code 8: 296
Button code 9: 297​
```

## Test votre pad avec la commande suivante <a id="test-votre-pad-avec-la-commande-suivante"></a>

```text
sdl2-jstest -e 0
```

Où 0 est le numéro de votre manette détectée avec la commande `sdl2-jstest --list`

Exemple avec une manette N64 en cliquant [ici](https://forum.recalbox.com/topic/9016/a-lire-manettes-n64)

