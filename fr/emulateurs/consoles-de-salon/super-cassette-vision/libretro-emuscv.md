---
title: Libretro-EmuSCV
---

# Libretro-EmuSCV



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv3**](https://gitlab.com/MaaaX-EmuSCV/libretro-emuscv/-/blob/master/licence.txt).

## 🔧 Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC x86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Redémarrer | ✔ |
| Captures d'écran | ✔ |
| Sauvegardes | ✔ |
| Contrôles | ✔ |
| Remapping | ✔ |

## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| upd7801g.s01 | BIOS - Requis | 635a978fd40db9a18ee44eff449fc126 | ❌ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 upd7801g.s01

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les ISOs doivent avoir les extensions suivantes :

* .bin
* .cart
* .zip
* .7z

### Emplacement

Placez les roms comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 roms
> > >
> > > > 📁 scv
> > > >
> > > > > 🗒 fichier.zip

La particularité est que si on charge une ROM en .bin, .rom ou .0 \(.1, .2, etc.\) connu, ça crée un fichier ROM au format .CART qui indique à l'émulateur le bon mappage des données \(la cartouche pouvant contenir plusieurs ROMs, éventuellement de la RAM, voire de la SRAM sauvegardée par une pile\). Pour les jeux où on pouvait sauvegarder, ça crée aussi un fichier .SAVE qui contient les données de la SRAM \(sauvegarde quand on quitte\).

Le .CART est créé dans le repertoire roms

S'il ne peut pas créer le .CART, ça ne charge pas le jeux, ça démarre sur l'écran de test de la console comme quand la console n'arrive pas à lire une cartouche.  
Je vais modifier le code pour que ça charge quand même et voir comment je peux mettre ça dans le répertoire des sauvegardes.

## ![](./cogwheel-145804_640.png) Configuration avancée de l'émulateur



## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Gitlab** : [https://gitlab.com/MaaaX-EmuSCV/libretro-emuscv/](https://gitlab.com/MaaaX-EmuSCV/libretro-emuscv/)
* **Doc Libretro** : -

