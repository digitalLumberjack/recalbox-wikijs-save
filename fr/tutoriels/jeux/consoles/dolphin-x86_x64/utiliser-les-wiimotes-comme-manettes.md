---
title: Utiliser les Wiimotes comme manettes
---

# Utiliser les Wiimotes comme manettes


>**Remarques :**
>
>**Dolphin** peut connecter jusqu'a **4 wiimotes en simultané**.
>
>Pour permettre le support des Wiimotes dans Dolphin, la barre **Dolphin Bar de chez Mayflash** \(accessoire\) est nécessaire. Vous devrez la mettre en mode 4.
{.is-warning}

## Configuration

* **Allez** dans le fichier **recalbox.conf** dans **le répertoire**  : `recalbox/share/system`  
* Puis **diriger** vous vers la section contrôleurs a cette emplacement  :

```text
## Wiimotes
## Real wiimotes must not be paired with recalbox system so that they can work with the wii emulator
## set emulatedwiimotes to 1 to emulate wiimotes with standard pads
wii.emulatedwiimotes=0
```

* Modifier la ligne : `wii.emulatedwiimotes=0`
* Comme ci dessous : `wii.emulatedwiimotes=1`

Vous pouvez à présent jouer avec les **Wiimotes.**

