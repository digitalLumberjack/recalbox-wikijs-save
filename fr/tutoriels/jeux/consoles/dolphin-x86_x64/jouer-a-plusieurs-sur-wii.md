---
title: Jouer à plusieurs sur Wii
---

# Jouer à plusieurs sur Wii


>**Attention :**
>
>Valable pour **tous les contrôleurs** sauf les **Wiimotes qui fonctionnent directement.**
{.is-danger}

* **Allez** dans le fichier **recalbox.conf** dans **le répertoire** `recalbox/share/system` à cette emplacement  :

```text
## Wiimotes
## Real wiimotes must not be paired with recalbox system so that they can work with the wii emulator
## set emulatedwiimotes to 1 to emulate wiimotes with standard pads
wii.emulatedwiimotes=0
```

* **Rajoutez** à la suite de la configuration la ligne suivante:

`wii.configfile=dummy`

Vous pouvez à présent **jouer à plusieurs** sur **Wii** avec **vos contrôleurs**.

