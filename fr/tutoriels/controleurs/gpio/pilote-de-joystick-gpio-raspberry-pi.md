---
title: Pilote de joystick GPIO Raspberry Pi
---

# Pilote de joystick GPIO Raspberry Pi

Le mk\_arcade\_joystick\_rpi est entièrement intégré dans la distribution de Recalbox.

**La branche hotkeybtn supporte désormais un bouton supplémentaire par joueur à la place du support MCP23017**

## Introduction

Le Raspberry Pi est un outil incroyable que j'ai découvert il y a un mois. Le projet Recalbox m'a donné envie de construire ma propre borne d'arcade avec de simples boutons et manettes d'arcade.

J'ai donc commencé à relier mes joysticks et mes boutons à mon Raspberry Pi et j'ai écrit la première moitié de ce pilote afin de relier mes joysticks et mes boutons directement aux ports GPIO de celui-ci..

Cependant, le Raspberry Pi B Rev 2 a un maximum de 21 ports GPIO utilisables, ce qui n'est pas suffisant pour câbler tous les 28 interrupteurs \(2 joysticks et 20 boutons\) qu'un panneau standard requiert.

UPDATE 0.1.5 : Ajout de la personnalisation GPIO

UPDATE 0.1.4 : Compatibilité avec le Raspberry Pi 2

UPDATE 0.1.3 : Compatibilité avec 3.18.3 :

L'installation du pilote fonctionne maintenant avec le noyau 3.18.3, diffusé avec le dernier firmware.

UPDATE 0.1.2 : Downgrade vers la 3.12.28+ :

Comme le module ne se charge pas avec un noyau et des en-têtes récents, nous ajoutons la possibilité de rétrograder votre firmware vers une version compatible, jusqu'à ce que nous trouvions une solution.

UPDATE 0.1.1 : Version Raspberry Pi B+ :

La nouvelle révision de Raspberry Pi B+ nous a apporté 9 ports GPIO supplémentaires, nous sommes donc maintenant en mesure de connecter 2 joysticks et 12 boutons directement aux ports GPIO. J'ai mis à jour le pilote afin de prendre en charge les 2 joysticks dans la configuration des ports GPIO.

### Encore plus de joysticks

Une petite puce bon marché appelée MCP23017 vous permet d'ajouter 16 GPIO externes, et ne prend que deux ports GPIO sur le Raspberry Pi. La puce vous permet d'utiliser les GPIO en entrée ou en sortie ;  l'entrée est ce que nous recherchons si nous voulons encore plus de joysticks.

Si vous souhaitez utiliser plus d'une puce, le protocole i2c vous permet de choisir différentes adresses pour le périphérique connecté, mais toutes utilisent les mêmes SDA et SCL GPIO.

En théorie, vous pouvez connecter jusqu'à 8 puces, donc 8 joysticks.

## Le logiciel

Le pilote du joystick est basé sur le pilote gamecon\_gpio\_rpi de [marqs](https://github.com/marqs85).

Il est écrit pour 4 joysticks directionnels et 8 boutons par joueur. L'utilisation d'un MCP23017 étend les numéros d'entrée à 16 : 4 directions et 12 boutons.

Il peut reconnaître un joystick + boutons câblés sur les ports GPIO du Raspberry Pi \(deux joysticks sur la révision RPi B+\) et jusqu'à 5 autres joysticks + boutons provenant de puces MCP23017.  
Un MCP23017 est nécessaire pour chaque joystick.

Il utilise des pull-up internes de Raspberry Pi et de MCP23017, de sorte que tous les interrupteurs doivent être directement connectés à son GPIO correspondant et à la terre \(GROUND\).

## Cas courants : Joysticks connectées à des ports GPIO

### Pinout

Considérons un panneau de commande à 6 boutons avec cet ordre de boutons :

```text
 ↑   Ⓨ Ⓧ Ⓛ  
← →	 Ⓑ Ⓐ Ⓡ  
 ↓  
```

Avec R = TR et L = TL

Voici le résumé du brochage des ports GPIO rev B :

[![GPIO Interface](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOs.png)](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOs.png)

Si vous avez un Raspberry Pi Rev B+ 1 ou 2 :

[![GPIO Interface](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOsb+.png)](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOsb+.png)

Bien sûr, la terre peut être commune à tous les interrupteurs.

## Installation

### Script d'installation

* Téléchargez le script d'installation :

```text
mkdir mkjoystick
cd mkjoystick
wget https://github.com/recalbox/mk_arcade_joystick_rpi/releases/download/v0.1.4/install.sh
```

* Mettre à jour votre système :

```text
sudo sh ./install.sh updatesystem
sudo reboot
```

* N'oubliez pas de redémarrer \(ou la partie suivante ne fonctionnera pas\) et de relancer le script sans aucun argument :

```text
sudo sh ./install.sh
```

Maintenant, rendez-vous à la partie [**Chargement du pilote**](/fr/tutoriels/controleurs/gpio/pilote-de-joystick-gpio-raspberry-pi#chargement-du-pilote).

### Installation manuelle

Mise à jour du système :

```text
sudo apt-get update
sudo apt-get upgrade
sudo rpi-update
```

1 - Installez tout ce dont vous avez besoin :

```text
sudo apt-get install -y --force-yes dkms cpp-4.7 gcc-4.7 git joystick
```

2 - Installez les derniers en-têtes de noyau :

```text
sudo apt-get install -y --force-yes raspberrypi-kernel-headers
```

3.a - Installer le pilote de la version \(de préférence\) :

```text
wget https://github.com/recalbox/mk_arcade_joystick_rpi/releases/download/v0.1.4/mk-arcade-joystick-rpi-0.1.4.deb
sudo dpkg -i mk-arcade-joystick-rpi-0.1.4.deb
```

3.b - Ou compilez et installez avec dkms :

3.b.1 - Télécharger les fichiers :

```text
git clone https://github.com/pinuct/mk_arcade_joystick_rpi/tree/customgpio
```

3.b.2 - Créer un dossier sous "/usr/src/_module_-_module-version_/"

```text
mkdir /usr/src/mk_arcade_joystick_rpi-0.1.5/
```

3.b.3 - Copiez les fichiers dans le dossier :

```text
cd mk_arcade_joystick_rpi/
cp -a * /usr/src/mk_arcade_joystick_rpi-0.1.5/
```

3.b.4 - Compiler et installer le module :

```text
dkms build -m mk_arcade_joystick_rpi -v 0.1.5
dkms install -m mk_arcade_joystick_rpi -v 0.1.5
```

## Chargement du pilote

Le pilote est chargé avec la commande `modprobe` et prend un paramètre nommé "map" représentant les joysticks connectés. Lorsque vous devez charger le pilote, vous devez passer une liste de paramètres qui représentent la liste des joysticks connectés. Le premier paramètre sera le joystick mappé sur /dev/input/js0, le second sur /dv/input/js1 etc.

Si vous avez connecté un joystick sur les ports GPIO du Raspberry Pi \(joystick 1 sur l'image du pinout\), vous devez passer "map=1" comme paramètre. Si vous êtes sur la révision B+ et que vous avez connecté 2 joysticks, vous devez passer map="1,2" en paramètre.

Si vous avez un joystick connecté sur votre version Raspberry Pi B ou B+, vous devrez exécuter la commande suivante :

```text
sudo modprobe mk_arcade_joystick_rpi map=1
```

Si vous avez deux joysticks connectés sur votre version Raspberry Pi B ou B+, vous devrez exécuter la commande suivante :

```text
sudo modprobe mk_arcade_joystick_rpi map=1,2
```

Si vous avez un écran TFT connecté sur votre Raspberry Pi B+, vous ne pouvez pas utiliser tous les ports GPIO. Vous pouvez exécuter la commande suivante pour n'utiliser que les GPIO non utilisés par l'écran TFT \(Attention, tous les écrans TFT n'utilisent pas les mêmes broches. Les GPIOs utilisés avec cette carte sont : 21, 13, 26, 19, 5, 6, 22, 4, 20, 17, 27, 16\) :

```text
sudo modprobe mk_arcade_joystick_rpi map=4
```

Si vous ne voulez pas utiliser tous les pins ou si vous voulez utiliser une carte avec **GPIO personnalisé** :

```text
sudo modprobe mk_arcade_joystick_rpi map=5 gpio=pin1,pin2,pin3,.....,pin12
```

Où _pinx_ est le numéro du port GPIO que vous souhaitez. Il existe 12 GPIO possibles avec **commande par bouton** : **Y-, Y+, X-, X+, Start, Select, A, B, TR, Y, X, TL**. Utilisez -1 pour les broches non utilisées. Par exemple `gpio=21,13,26,19,-1,-1,22,24,-1,-1,-1,-1,-1` utilise les ports GPIO 21, 13, 26, 19 pour les axes et les ports 22 et 24 pour les boutons A et B, le reste des boutons sont inutilisés.

Les actions du joystick 1 seront rapportées au fichier "/dev/input/js0" et les actions du joystick 2 seront rapportées au fichier "/dev/input/js1".

### Chargement automatique au démarrage

Ouvrez `/etc/modules` :

```text
sudo nano /etc/modules
```

Ajoutez la ligne que vous utilisez pour charger le pilote :

```text
mk_arcade_joystick_rpi
```

Ensuite, créez le fichier `/etc/modprobe.d/mk_arcade_joystick.conf` :

```text
sudo nano /etc/modprobe.d/mk_arcade_joystick.conf
```

Ajoutez la configuration du module :

```text
options mk_arcade_joystick_rpi map=1,2
```

### Test

Utilisez la commande suivante pour tester les actions des joysticks :

```text
jstest /dev/input/js0
```

### Autres cas de joysticks : MCP23017

Voici le résumé du brochage du MCP23017 :

![MCP23017 Interface](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_mcp23017.png)

#### Préparation du Raspberry Pi pour le MCP23017

Suivez les instructions d'installation des standards.

Activez i2c sur votre Pi :

```text
sudo nano /etc/modules
```

Ajoutez les lignes suivantes afin de charger automatiquement les modules i2c :

```text
i2c-bcm2708 
i2c-dev
```

Et si le fichier `/etc/modprobe.d/raspi-blacklist.conf` existe :

```text
sudo nano /etc/modprobe.d/raspi-blacklist.conf
```

Vérifiez si vous avez une ligne avec :

```text
i2c-bcm2708 
```

Ajoutez un \# au début de la ligne pour supprimer la liste noire. Redémarrez ou chargez les deux modules :

```text
modprobe i2c-bcm2708 i2c-dev
```

### Préparation de la puce MCP23017

Vous devez mettre les broches A0, A1 et A2 à 0 ou 1 afin de définir l'adresse i2c de la puce.

Si vous n'avez qu'une seule puce, connectez les 3 broches à la terre.  
Il suffit de connecter l'une des broches au 3,3V pour mettre son état à 1 et modifier l'adresse i2c de la MCP23017.

Vous devez également connecter la broche RESET au 3.3V.

### Configuration

Lorsque vous voulez charger le pilote, vous devez vérifier une liste de paramètres qui représentent la liste des joysticks connectés. Le premier paramètre sera le joystick mappé sur /dev/input/js0, le second sur /dev/input/js1, etc.

Si vous avez connecté un joystick sur les GPIO du Pi, vous devez entrer "1" comme paramètre.

Si vous avez connecté un ou plusieurs joysticks avec la puce MCP23017, vous devez entrer l'adresse des périphériques I2C connectés, que vous pouvez obtenir grâce à la commande :

```text
sudo i2cdetect -y 1
```

La configuration de chaque MCP23017 se fait en réglant les pads A0, A1 et A2 sur 0 ou 1.

Si vous avez configuré votre MCP23017 avec A0, A1 et A2 connectés à la terre, l'adresse renvoyée par `i2cdetect` devrait être 0x20.

Donc, si vous avez un joystick connecté à des GPIO sur le Pi et un joystick sur une puce MCP23017 avec l'adresse 0x20, pour charger le pilote, vous devez exécuter la commande suivante :

```text
sudo modprobe mk_arcade_joystick_rpi map=1,0x20
```

Les actions du joystick sur GPIO seront signalées dans le fichier "/dev/input/js0" et les actions du joystick de la puce MCP23017 seront signalées dans le fichier "/dev/input/js1".

J'ai testé jusqu'à 3 joysticks ; un sur ports GPIO, un sur une MCP23017 à l'adresse 0x20, un sur une MCP23017 à l'adresse 0x24 :

```text
sudo modprobe mk_arcade_joystick_rpi map=1,0x20,0x24
```

## Bugs connus

* Si vous essayez de lire ou d'écrire sur i2c avec un outil comme `i2cget` ou `i2cset` lorsque le pilote est chargé, vous allez passer un sale quart-d'heure...
* Si vous essayez `i2cdetect` lorsque le pilote est en cours d'exécution, il vous montrera des adresses de périphériques étranges...
* La version 256MB du Raspberry Pi Model B n'est pas supporté par le pilote actuel. Si vous voulez que le pilote fonctionne sur votre ancien Pi, vous devrez changer l'adresse de BSC1\_BASE en \(BCM2708\_PERI\_BASE + 0x205000\) afin d'utiliser la bonne adresse i2c, et recompiler.

