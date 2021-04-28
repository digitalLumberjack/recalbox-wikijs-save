---
title: Configurez des contrôleurs Xin-mo
---

# Configurez des contrôleurs Xin-mo

## Xin-mo

Les interfaces USB Xin Mo **fonctionnent en natif** avec **Recalbox** et gère 2 joueurs.

## Pinout <a id="pinout"></a>

Prenons comme exemple **un panel à 6 boutons + stick + 1 bouton crédit \(select\) + 1 bouton start** \(généralement bouton 1 player et 2 players\) avec cette disposition **pour chaque joueur** :

```text
 ↑   Ⓨ Ⓧ Ⓛ  
← →	 Ⓑ Ⓐ Ⓡ    ($) (1P)
 ↓  
```

Il est préférable de **rajouter un bouton hotkey dédié** : Ⓗ

Il faut _**absolument**_ mapper les deux joueurs **de la même manière.**

**Exemple :**

![XinMo pinout](https://github.com/digitalLumberjack/recalbox-os/wiki/images/XinMo_Arcade_Recalbox.jpg)

## Configuration <a id="configuration"></a>

Ensuite il suffit de faire _**seulement**_ la configuration du **joueur 1** directement **dans Emulationstation.**  
La configuration du **joueur 2** devrait fonctionner **si le mappage est bien le même.**


>**Attention :**
>
>* **N’essayez pas** de ****configurer le **joueur 2**, ça va **écraser la config du joueur 1.**
>* **Les joysticks** doivent être **configurés sur le D-PAD** et non sur joystick dans le menu d'Emulationstation.
{.is-danger}


>**La configuration joystick** est réservé aux **sticks analogiques** tels que les manettes **Playstation ou Xbox.**
{.is-info}

