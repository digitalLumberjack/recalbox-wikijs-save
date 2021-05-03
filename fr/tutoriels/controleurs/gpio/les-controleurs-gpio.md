---
title: Les contrôleurs GPIO
---

# Les contrôleurs GPIO


>Recalbox est compilé avec le pilote mk\_arcade\_joystick\_gpio qui permet de gérer un contrôleur connecté directement sur les GPIO du Raspberry Pi.  
>Donc si vous avez prévu de vous construire un **Bartop**, une **Borne d'arcade** ou un **Stick d'arcade portable**, vous n'avez pas besoin d'investir dans un contrôleur usb.
>
>Le pilote peut gérer jusqu'à **2 contrôleurs** composés chacun d'un **joystick 4 directions** et de **9 boutons**.  
>  
>Si vous utilisez un **RPi1 révision B,** reportez-vous à : mk\_arcade\_joystick pinout.
{.is-info}

## Pinout <a id="pinout"></a>

Prenons comme exemple **un panel à 7 boutons** avec cette disposition :

```text
 ↑   Ⓨ Ⓧ Ⓛ  
← →     Ⓑ Ⓐ Ⓡ Ⓗ
 ↓  
```

**Avec** 

```text
Ⓡ = Gâchette droite = TR  |  Ⓛ = Gâchette gauche = TL  |  Ⓗ = HK = Hotkey
```

Sur **RPI B+, RPI2 et RPi3,** vous devez **connecter vos boutons** en suivant ce pinout :

![Rpi2 Pinout](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LkUFvu3yt-NWo65aPpY%2F-LkUIh76x_R_LdMYBlVY%2Fimage.png?alt=media&token=7c3424bb-6e03-44cc-bb27-0dcd811cd42f)


>**Le bas de l'image correspond au côté du Pi où se trouvent les ports USB.**
{.is-info}

Vous pouvez **connecter** vos boutons **directement à la masse,** étant donné que **le pilote active** les _**gpio internal pullups**_.

## Configuration <a id="configuration"></a>

* Dans le fichier [recalbox.conf](/fr/usage-basique/premieres-notions/le-fichier-recalbox.conf), **activez le pilote GPIO** en **réglant** `controllers.gpio.enabled` sur 1 : `controllers.gpio.enabled=1` et vous êtes prêt à jouer !

**Les GPIO** sont configurés _out the box_ dans **l'interface** et **les différents systèmes** émulés.

