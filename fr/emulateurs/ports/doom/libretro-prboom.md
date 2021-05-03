---
title: Libretro PrBoom
---

# Libretro PrBoom

**PrBoom** est l'aboutissement d'années de travail par diverses personnes et projets sur le code source de Doom.  
PrBoom comprend le travail de tous les projets suivants :

* Original Doom source release
* DosDoom
* [Boom](http://www.teamtnt.com/boompubl/boom2.htm)
* MBF
* [LxDoom](http://lxdoom.linuxgames.com/)
* lSDLDoom

PrBoom est un portage du moteur graphique de Doom. Il peut faire fonctionner Doom 1 et Doom 2.

## ![](/migration-images/emulateurs/ports/doom/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/libretro-prboom/blob/master/COPYING).

## ![](/migration-images/emulateurs/ports/doom/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ports/doom/cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| Core Options | ✔ |
| RetroArch Cheats | ✔ |
| Native Cheats | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](/migration-images/emulateurs/ports/doom/tqfp32.svg) BIOS


>**Le bios est déjà présent** dans le répertoire `/recalbox/share/bios/prboom/prboom.wad`
{.is-info}

## \*\*\*\*![](/migration-images/emulateurs/ports/doom/rom-30098_640.png) **Roms**


>**Remarque :**  
>Les fichiers **WADs** sont assimilable à des "roms".
{.is-info}


>**Remarque :**  
>Placez vos roms Doom dans le répertoire`/recalbox/share/roms/ports/doom/`
{.is-warning}


>**Attention :**  
>N'utilisez que des minuscules pour vos fichiers `.wad`
{.is-danger}

### Quelques infos sur les WADs

Même si les fichiers portent tous l'extension `.wad`, il en existe de plusieurs sortes :

* **IWAD** : c'est un `.wad` qui contient toutes les données et fonctionne tout seul.  
  Pour les plus connus:

  * `doom1.wad` pour les versions shareware de **DOOM.**
  * `doom.wad` pour les versions commerciales de **DOOM.**
  * `doom.wad ou doomu.wad` pour les versions de **The Ultimate DOOM.**
  * `doom2.wad` pour les versions de **DOOM II - Hell on Earth.**
  * `tnt.wad` pour les versions de **Final DOOM - TNT Evilution**
  * `plutonia.wad` pour les versions de **Final DOOM - The Plutonia Experiment**
  * `sigil.wad` pour les versions du dernière épisode de **DOOM - SIGIL**

  \*\*\*\*

* **PWAD** : c'est un `.wad` 'add-on' qui aura besoin d'un IWAD pour fonctionner \(par exemple: quasi tous les niveaux amateurs créés par la communauté Doom\).

Les WADs doivent aussi être compatibles avec PrBoom. Certains mods vont très loin dans la modification **\(comme Brutal Doom, Doom Raider, Golden Eye,...\)** mais **ne** **fonctionnent pas** avec PrBoom. Vous devrez chercher les infos sur le WAD auquel vous désirez jouer !  
Si un WAD remplace un seul niveau, ce ne sera pas forcément le niveau 1 de l'épisode 1. Il faudra atteindre le bon niveau ou utiliser un cheat pour y accéder directement.

### Liste de compatibilité des jeux WADs

<table>
  <thead>
    <tr>
      <th style="text-align:left">Fichier WAD</th>
      <th style="text-align:left">
        <p>Nom du fichier</p>
        <p>MD5</p>
      </th>
      <th style="text-align:left">Statut</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>SIGIL</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">SIGIL (v1.21)</td>
      <td style="text-align:left">
        <p><code>SIGIL_v1_21.WAD</code>
        </p>
        <p>743d6323cb2b9be24c258ff0fc350883</p>
      </td>
      <td style="text-align:left">
        <p>&#x2705; On</p>
        <p>Recalbox</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>MASTER LEVEL for DOOM II (Registred)</b>
      </td>
      <td style="text-align:left">----------------------------------------------------------------</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Master Levels for Doom II (Classic Complete) (PlayStation 3)</td>
      <td style="text-align:left">
        <p><code>MASTERLEVELS.WAD</code>
        </p>
        <p>84cb8640f599c4a17c8eb526f90d2b7a</p>
      </td>
      <td style="text-align:left">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:left">Master Levels for Doom II</td>
      <td style="text-align:left">
        <p><code>20x fichiers WADs s&#xE9;par&#xE9;s</code>
        </p>
        <p>n/a</p>
      </td>
      <td style="text-align:left">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>FINAL DOOM (Registred)</b>
      </td>
      <td style="text-align:left">----------------------------------------------------------------</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Final Doom - Evilution <em>&quot;v1.9&quot;</em>
      </td>
      <td style="text-align:left">
        <p><code>TNT.WAD</code>
        </p>
        <p>4e158d9953c79ccf97bd0663244cc6b6</p>
      </td>
      <td style="text-align:left">&#x2705;</td>
    </tr>
    <tr>
      <td style="text-align:left">Final Doom - The Plutonia Experiment <em>&quot;v1.9&quot;</em>
      </td>
      <td style="text-align:left">
        <p><code>PLUTONIA.WAD</code>
        </p>
        <p>75c8cf89566741fa9d22447604053bd7</p>
      </td>
      <td style="text-align:left">&#x2705;</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>DOOM II - Hell on Earth (Registred)</b>
      </td>
      <td style="text-align:left">----------------------------------------------------------------</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Doom II - Hell on Earth (v1.9)</td>
      <td style="text-align:left">
        <p><code>DOOM2.WAD</code>
        </p>
        <p>25e1459ca71d321525f84628f45ca8cd</p>
      </td>
      <td style="text-align:left">&#x2705;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>The Ultimate DOOM (Registred)</b>
      </td>
      <td style="text-align:left">----------------------------------------------------------------</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Ultimate Doom, The <em>&quot;v1,9ud&quot;</em>
      </td>
      <td style="text-align:left">
        <p><code>DOOM.WAD, UDOOM.WAD, DOOMU.WAD</code>
        </p>
        <p>c4fe9fd920207691a9f493668e0a2083</p>
      </td>
      <td style="text-align:left">&#x2705;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>DOOM (Registred)</b>
      </td>
      <td style="text-align:left">----------------------------------------------------------------</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Doom (v1.9)</td>
      <td style="text-align:left">
        <p><code>DOOM.WAD</code>
        </p>
        <p>1cd63c5ddff1bf8ce844237f580e9cf3</p>
      </td>
      <td style="text-align:left">&#x2705;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>DOOM (Shareware)</b>
      </td>
      <td style="text-align:left">----------------------------------------------------------------</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Doom (v1.9) (Demo)</td>
      <td style="text-align:left">
        <p><code>DOOM1.WAD</code>
        </p>
        <p>f0cefca49926d00903cf57551d901abe</p>
      </td>
      <td style="text-align:left">
        <p>&#x2705; On</p>
        <p>Recalbox</p>
      </td>
    </tr>
  </tbody>
</table>

## Jouer à SIGIL: 


>Le fichier `doom.wad` dans le répertoire des roms est en réalité la version 1.9 Shareware du jeu **Doom** est devrait être renommé en `doom1.wad`
{.is-info}

* Pour jouer à **SIGIL** vous devez obligatoirement remplacer cette version Shareware `doom.wad`

  par la version **Registred** de **The Ultimate DOOM** **v1.9.**


>Aucune autre version de `doom.wad` ne pourra faire fonctionner **SIGIL** !
{.is-warning}

* Pour cela:
  * Renommez le fichier existant à la racine de`roms\ports\doom\doom.wad` en `doom1.wad` \(ou supprimez-le\).
  * Collez le nouveau fichier `doom.wad` issue de la version **The Ultimate DOOM** **v1.9** en lieu et place de l'ancien.
  * Relancez une mise à jour de votre liste de jeux et lancez **SIGIL.**


>**BUG de SIGIL:**  
>Quand vous lancez **SIGIL**, ****le lancement des quatre premiers épisodes vous lancera immanquablement le première épisode. Pour lancer **SIGIL**, ****sélectionnez simplement l'épisode SIGIL.
{.is-info}


>Pour obtenir une version **Registered** de **DOOM**, vous devez avoir les disquettes ou CD-Rom originaux. Ou encore les obtenir sur STEAM ou GOG.
{.is-danger}

## **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁ports
> > > >
> > > > > 📁Doom
> > > > >
> > > > > > 🗒\*.WAD

## **Liens externes**

* **Github utilisé** : [https://github.com/libretro/libretro-prboom/](https://github.com/libretro/libretro-prboom)
* **Docs Libretro** :  [https://docs.libretro.com/library/prboom/](https://docs.libretro.com/library/prboom/)
* **Site officiel** : [http://prboom.sourceforge.net/about.html](http://prboom.sourceforge.net/about.html)

