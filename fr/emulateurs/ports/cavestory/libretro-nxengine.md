---
title: Libretro NXEngine
---

# Libretro NXEngine

Libretro NXEngine est un moteur de réécriture open-source de Cave Story pour Dingux et MotoMAGX. Auteur - Caitlin Shaw \(rogueeve\).

## ![](/migration-images/emulateurs/ports/cavestory/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**GPLv3**](https://github.com/gameblabla/nxengine-nspire/blob/master/LICENSE).

## ![](/migration-images/emulateurs/ports/cavestory/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ports/cavestory/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](/migration-images/emulateurs/ports/cavestory/tqfp32.svg)BIOS


>**Aucun bios n'est requis.**
{.is-success}

## ![](/migration-images/emulateurs/ports/cavestory/rom-30098_640.png)**Roms**

### **Extensions supportées**

Les roms doivent avoir l'extension :

* .exe

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁ports
> > > >
> > > > > 📁Cave Story
> > > > >
> > > > > > 📁CaveStory
> > > > > >
> > > > > > > 🗒 Doukutsu.exe

Cette ensemble de fichiers est fourni dans votre Recalbox en version demo.

Ci-dessous la procédure pour la mise en place de la version complète:

1. Rendez-vous sur [http://www.cavestory.org/](http://www.cavestory.org/)
2. Téléchargez la version Windows anglais \(pré-patché\) en ZIP seulement \(version traduite : non testée/en cours de validation\).
3. Extraire le fichier ZIP dans un répertoire nommé sous quelque chose comme `cave_story` ou autre
4. Renommer le fichier `DoConfig.exe` en `DoConfig.exe.old`
5. Télécharger l'intégralité du contenu du répertoire dans votre recalbox dans /recalbox/share/roms/cavestory/  `with winscp under windows` scp cave\_story root@RECALBOXIP:/recalbox/share/roms/cavestory/ \(par exemple sous linux\)

## ![](/migration-images/emulateurs/ports/cavestory/hammer-28636_640.png)Configuration avancée de l'émulateur

### Options du core <a id="options-du-core"></a>

| Nom de l'option | Default | Description |
| :---: | :---: | :---: |
|  |  |  |

## ![](/migration-images/emulateurs/ports/cavestory/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github utilisé :** [https://github.com/libretro/nxengine-libretro/](https://github.com/libretro/nxengine-libretro)
* **Github officiel :** [https://github.com/EXL/NXEngine/](https://github.com/EXL/NXEngine)\*\*\*\*
* **Site Officiel :** [nxengine.sourceforge.ne](http://nxengine.sourceforge.net/)t
* **Wiki du jeu :** [https://www.cavestory.org/guides-and-faqs/list.php](https://www.cavestory.org/guides-and-faqs/list.php)

