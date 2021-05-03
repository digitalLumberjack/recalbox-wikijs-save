---
title: Dolphin
---

# Dolphin

Dolphin est un émulateur pour deux récentes consoles de jeu de Nintendo : la GameCube et la Wii. Il permet aux joueurs sur PC d'apprécier les jeux réalisés pour ces deux consoles en **full HD** \(1080p\) avec différentes améliorations : compatibilité avec tous les contrôleurs de PC, vitesse turbo, jeu en ligne en réseau, et bien plus encore !

Plus de 200 personnes ont travaillé dur depuis des années pour créer Dolphin. La liste des contributeurs peut être trouvée [sur GitHub](https://github.com/dolphin-emu/dolphin/graphs/contributors).

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/dolphin-emu/dolphin/blob/master/license.txt).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC X86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## \*\*\*\*![](./tqfp32.svg) **BIOS**


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](./rom-30098_640.png) **Roms**

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .iso
* .wbfs
* .wad

### **Emplacement**

Placez les isos comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁wii
> > > >
> > > > > 🗒**fichier.iso**


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

Dolphin fonctionne avec les roms dans les formats suivants :

* **GCM**/**ISO** \(dumps non compressés ~4,7 GB pour un jeu de Wii\)
* **WBFS** \(non pris en charge par Dolphin 3.0 ou plus ancien\)
* **WAD** \(mini jeux wiiware\)


>Notez que WBFS et CISO sont des formats de compression à perte : ils retirent des informations non utilisées sur les disques pour les rendre plus petits. Ainsi nous vous recommandons d'essayer de dumper vos jeux au format GCM/ISO si vous avez des problèmes avec un dump WBFS.
{.is-warning}

## ![](./hammer-28636_640.png) Configuration avancée des émulateurs

### Options de Dolphin

-

### Définir la position de la Dolphin Bar

* Ouvrez le fichier : `/recalbox/share/system/recalbox.conf`
* Dans la section "D3 - Dolphin Controllers" cherche la ligne :
  * `wii.sensorbar.position`
* Si vous placez votre Dolphin Bar au-dessus de votre écran,, remplacez par ceci :
  * `wii.sensorbar.position=1`
* Si vous placez votre Dolphin Bar en dessous de votre écran, remplacez par ceci :
  * `wii.sensorbar.position=0`

### **Jouer avec de véritables Wiimotes**


>La barre Dolphin Bar de chez Mayflash est nécessaire pour utiliser pleinement les Wiimotes avec Dolphin.
{.is-danger}

* Branchez votre Dolphin Bar à votre Recalbox puis passer la en mode 4.
* Ouvrez  le fichier : `/recalbox/share/system/recalbox.conf`
  * Dans la section "D3 - Dolphin Controllers" cherchez la ligne suivante :
    * `wii.realwiimotes=0` 
  * puis modifiez par ceci :
    * `wii.realwiimotes=1` 
* Voilà, vos Wiimotes fonctionnent maintenant dans Dolphin.

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/dolphin-emu/dolphin/](https://github.com/dolphin-emu/dolphin)
* **Site officiel** : [https://www.dolphin-emu.org/](https://www.dolphin-emu.org/)

