---
title: Connectez un afficheur LCD avec I2C à votre recalbox
---

# Connectez un afficheur LCD avec I2C à votre recalbox

## Prérequis

Un écran **LCD I2c** comme le modèle **Hd44780** en version **A00** \(support ascii + caractères japonais\) ou **A02** \(support ascii + caractères européen\)

![](http://i.imgur.com/YrDDhwUm.jpg)

## Installation

### Branchement I2C sur GPIO Raspberry Pi 3

**Connexion** de l'I2c sur un **Raspberry Pi 3**

![](http://i.imgur.com/NKswbgr.png)



### Activation de l'I2C dans recalbox

* **Editez** le fichier `/etc/modules.conf` **Ajoutez à la fin** du fichier :

```text
i2c-bcm2708
i2c-dev
```

* **Editez** le fichier `/boot/config.txt` **Ajouter les lignes** suivantes : 

```text
#Activate I2C
dtparam=i2c1=on
dtparam=i2c_arm=on
```

* **Editez** le fichier `/boot/cmdline.txt` **Ajoutez** à la **fin de ligne :**

```text
bcm2708.vc_i2c_override=1
```

* **Redémarrez** votre recalbox

### Vérifier l'adresse de l'I2C

Vous devrez **connaître l'adresse de votre I2C** pour faire fonctionner certains **scripts d'affichage**. En règle générale, **l'adresse est**  `0x27` ou `0x3f`

* Lancez la commande suivante ; celle-ci prend un certain temps !
  * sur les très vieux modèles de Raspberry : `i2cdetect -y 0` 
  * sur les Raspberry récent \(pi3, pi2\) :  `i2cdetect -y 1`

```text

     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- 27 -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
```

**L'adresse retournée** par la commande dans le tableau nous indique : `0x27`

## Script d'affichage disponible pour Recalbox.

[https://forum.recalbox.com/topic/8689/script-clcd-display-on-recalbox](https://forum.recalbox.com/topic/8689/script-clcd-display-on-recalbox)

![](http://i.imgur.com/fsXfArEm.jpg)

