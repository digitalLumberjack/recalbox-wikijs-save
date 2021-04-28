---
title: Libretro Hatari
---

# Libretro Hatari

## 

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/hatari/blob/master/readme.txt).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| tos.img | TOS Image Boot | 036c5ae4f885cbf62c9bed651c6c58a8 0604dbb85928f0598d04144a8b554bbe 066f39a7ea5789d5afd59dd7b3104fa6 091a4d95f6c600231a3f1391a309ac26 143343f7b8e0b1162af206fe8f46b002 1c92855316a33faee602b8007f22d2cb 25789a649faff0a1176dc7d9b98105c0 27ac71b59d59f65571b972e0f894054a 2a8e39c60317b921eabd7e25b5d74395 30f69d70fe7c210300ed83f991b12de9 332fe3803a7e20cd625b27a69f07ae69 41b7dae4e24735f330b63ad923a0bfbc 4a0d4f282c3f2a0196681adf88862dd4 52248cc70ae48b3050e197e270917130 5491b3755992feaf743ceecaa3b18f34 5d65c6a384d847a0b8013d5e22ec0887 61b620ad951815a25cb37895c81a947c 696ba04b3bc963aee2ba769298e342de 6f9471098a521214fad1e2c6f2dd3d08 736adb2dc835df4d323191fdc8926cc9 7449b131681f1dfe62ebed1392847057 7c040857bdcfcd7d748ca82205463efa 7cdd45b6aac66a21bfb357d9334e46db 7e87d8fe7e24e0b4c55ad1b7955beae3 800d48825be45ec7f39ba7bb2c3f0b59 91ce7c1903006da75c823ff3c938e5d2 941baac767269649f92f7918dd5740b8 94a75c1c65408d9f974b0463e15a3b11 992bac38e01633a529121a2a65f0779e 9e880168d0a004f7f5e852be758f39e4 a0982e760f9807d82667ff5a69e78f6b a4cfd3c7412002dd693f69a15d4d961c a7dc40dc5c1086bce1a8f3d44fd29051 b2873004a408b8db36321f98daafa251 b2a8570de2e850c5acf81cb80512d9f6 b9e37f0f0a700fc673049794870bdb85 bc7b224d0dc3f0cc14c8897db89c5787 c1c57ce48e8ee4135885cee9e63a68a2 d0f682ee6237497004339fb02172638b d41ae4efaa2c97f632dbe75d24d51bea d6521785627d20c51edc566808a6bf28 e5ea0f216fb446f1c4a4f476bc5f03d4 e690bec90d902024beed549d22150755 ed2647936ce4bd283c4d7dfd7ae09d1c ed5fbaabe0219092df74c6c14cea3f8e f3f92cd4e2c331aef8970a156be03b7c f62bc9777f28bc6876422738758db365 febb00ba8784798293a7ae709a1dafcb | ❌ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 tos.img

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .st
* .stx
* .ipf
* .msa
* .dim
* .zip
* .7z

Ce système supporte les roms compressées au format .zip/.7z. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip/.7z doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip/.7z ne doit contenir qu'une seule rom compressée.

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁atarist
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **No-Intro** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur

### 

## **Configuration par default**

Voici le mapping pour l'émulateur ATARI ST basé sur une manette SNES :

* A : clic droit
* B : clic gauche
* X : ouvre l'interface \(pour changer de disquette etc...\)
* Y : Shift
* Select : bascule du mode souris/joystick
* R1 : change la sensibilité de la souris
* L1 : ouvre le clavier virtuel
* L2 : ouvre un menu permettant de voir le monde de controle dans lequel on est \(souris/joystick\) ainsi que le niveau de réglage de la sensibilité de la souris \(un chiffre qui varie à coté de MS: - valeur que tu modifies avec R1\)

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/hatari/](https://github.com/libretro/hatari/)
* **Doc Libretro** : [https://docs.libretro.com/library/hatari/](https://docs.libretro.com/library/hatari/)

