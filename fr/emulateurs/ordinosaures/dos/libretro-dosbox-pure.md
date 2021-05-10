---
title: Libretro DOSBox Pure
---

# Libretro DOSBox Pure



## ![](/migration-images/emulateurs/ordinosaures/dos/gerald-g-parchment-background-or-border-5.svg) Licence <a id="licence"></a>

​Ce core est sous licence [**GPLv2**](https://gitlab.com/recalbox/packages/libretro/libretro-dosbox-pure/-/blob/main/LICENSE).

## ![](/migration-images/emulateurs/ordinosaures/dos/compatibility.png) Compatibilité <a id="compatibilite"></a>

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC X86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ​ ❌ | ❌​ | ​ ✅ | ✅ | ​✅ | ✅​ | ​✅ | ​✅ | ✅​ |

## ​ ![](/migration-images/emulateurs/ordinosaures/dos/cogwheel-145804_640.png) Fonctionnalités <a id="fonctionnalites"></a>

​

## ​ ![](/migration-images/emulateurs/ordinosaures/dos/tqfp32.svg) BIOS <a id="bios"></a>


>**Aucun bios n'est requis.**
{.is-success}

## ​ ![](/migration-images/emulateurs/ordinosaures/dos/rom-30098_640.png) Roms <a id="roms"></a>

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .zip

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁dos  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  

## ​ ![](/migration-images/emulateurs/ordinosaures/dos/hammer-28636_640.png) Configuration avancée de l'émulateur <a id="configuration-avancee-de-lemulateur"></a>


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder aux options

Vous pouvez configurer diverses options de deux façons différentes.

* Via le Menu RetroArch :

┣ 📁Menu RetroArch  
┃ ┣ 📁Options du core  
┃ ┃ ┣ 🧩Name\_option  

* Via le fichier `retroarch-core-options.cfg`:

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁system  
┃ ┃ ┃ ┣ 📁configs  
┃ ┃ ┃ ┃ ┣ 📁retroarch  
┃ ┃ ┃ ┃ ┃ ┣ 📁cores  
┃ ┃ ┃ ┃ ┃ ┃ ┣ 🧩**retroarch-core-options.cfg**  

### Options du core

### ​Utiliser la souris avec la manette

Pour utiliser la souris sur un joystick de votre manette, il y a une manipulation à effectuer dans les options de RetroArch. Nous allons voir ci-dessous comment utiliser la souris sur le joystick droit.

* Lancez votre jeu
* Une fois lancé, allez dans les options de RetroArch et descendez sur **Touches**.
* Dans la configuration des touches, entrez dans **Port 1 Touches**.
* Mettez-vous sur l'option **Type de périphérique** et utilisez la flèche droite pour vous arrêter sur `Mouse with Right Analog Stick`.
* Retournez en jeu et profitez ! Vous aurez les clics de souris sur L1 et R1 \(clic gauche et clic droit\).

## ​ ![](/migration-images/emulateurs/ordinosaures/dos/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes <a id="liens-externes"></a>

* **Gitlab utilisé** : [https://gitlab.com/recalbox/packages/libretro/libretro-dosbox-pure/](https://gitlab.com/recalbox/packages/libretro/libretro-dosbox-pure/)
* **Github original** : [https://github.com/libretro/dosbox-pure](https://github.com/libretro/dosbox-pure)/

