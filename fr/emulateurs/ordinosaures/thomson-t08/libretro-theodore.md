---
title: Libretro Theodore
---

# Libretro Theodore

**Cet ordinateur** est émulé par le **core libretro** [theodore](https://github.com/Zlika/theodore).  
**Ce core** est capable d'émuler **tous les modèles de la gamme MOTO** \(MO5, MO6, TO7, TO7/70, TO8, TO8D, TO9, TO9+\) ainsi que l'Olivetti PC128, un clone de MO6 pour le marché Italien.

## ![](/migration-images/emulateurs/ordinosaures/thomson-t08/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv3**](https://github.com/Zlika/theodore/blob/master/LICENSE).

## ![](/migration-images/emulateurs/ordinosaures/thomson-t08/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ordinosaures/thomson-t08/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/ordinosaures/thomson-t08/tqfp32.svg) BIOS


>**Aucun bios n'est requis.**
{.is-success}

## \*\*\*\*![](/migration-images/emulateurs/ordinosaures/thomson-t08/rom-30098_640.png) **Roms**

### Extensions supportées

Les roms doivent avoir les extensions suivantes  :

* .fd \(disquette\)
* .sap \(disquette\)
* .k7 \(cassette\)
* .rom \(cartouche\)
* .m7 \(cartouche\)
* .m5 \(cartouche\)
* .zip
* .7z

Ce système supporte les roms compressées au format .zip/.7z. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip/.7z doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip/.7z ne doit contenir qu'une seule rom compressée.

### **Emplacement**

Placez les roms comme ceci : 

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁thomson  
┃ ┃ ┃ ┃ ┣ 🗒**fichier.zip**  


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/ordinosaures/thomson-t08/hammer-28636_640.png) Configuration avancée de **l'**émulateur

### Utilisation

**Par défaut**, le **type d'ordinateur** émulé dépend du **nom du fichier utilisé.**

_**Exemple :**_  
**super-tennis-fil\_mo5.k7** provoquera l'émulation du **MO5**


>_**Information :**_
>**Si le fichier** ne contient pas **le nom d'une des machines émulées**, l'émulateur **basculera en mode TO8** par défaut\).  
>Il est possible de **forcer le type de machine** émulée via **une option dans RetroArch.**
{.is-info}

Les jeux **ne démarrent pas automatiquement** au chargement de la machine.  
Sur les ordinateurs **Thomson**, il est en effet **nécessaire d'appuyer** sur une \(ou plusieurs\) touche\(s\) du clavier **pour lancer un programme.**  
  
**Afin de faciliter** l'utilisation de l'émulateur **à la manette**, le bouton **`Start`** de la manette **essaye de lancer le jeu** en choisissant une méthode qui dépend de l'ordinateur émulé ainsi que du type de média inséré \(cf. [fichier README de Theodore](https://github.com/Zlika/theodore/blob/master/README-FR.md#video_game-correspondance-des-boutons-de-la-manette)\).  
  
**En cas d'échec**, il faut essayer **une autre méthode** via **le clavier** ou **le clavier virtuel** \(cf. plus bas\).

### Manettes

**Mise à part** le bouton **B** de la manette qui permet **d'émuler l'unique bouton des joysticks** pour **Thomson**, les **autres boutons** de la manette sont utilisés pour **la fonctionnalité de "clavier virtuel".**

**Cette fonctionnalité** permet de **jouer facilement** à la plupart des jeux **sans avoir besoin d'un clavier réel.**

<table>
  <thead>
    <tr>
      <th style="text-align:center">Bouton</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center"><b>B</b>
      </td>
      <td style="text-align:left">
        <p>Bouton &quot;Action&quot; quand le clavier virtuel n&apos;est pas affich&#xE9;.</p>
        <p>Quand le clavier virtuel est affich&#xE9; :</p>
        <ul>
          <li>Appuie court : Appuie sur la touche du clavier ayant le focus.</li>
          <li>Appuie long : Maintien permanent de la touche (ou rel&#xE2;chement si
            elle &#xE9;tait d&#xE9;j&#xE0; maintenue). Jusqu&apos;&#xE0; 3 touches
            peuvent &#xEA;tre maintenues. La disparition du clavier virtuel rel&#xE2;che
            toutes les touches maintenues.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Y</b>
      </td>
      <td style="text-align:left">D&#xE9;place le clavier virtuel en haut ou en bas de l&apos;&#xE9;cran.</td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Start</b>
      </td>
      <td style="text-align:left">
        <p>D&#xE9;marrage du jeu si le clavier virtuel n&apos;est pas affich&#xE9;.</p>
        <p>Raccourci pour appuyer sur la touche &quot;Entr&#xE9;e&quot; si le clavier
          virtuel est affich&#xE9;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Select</b>
      </td>
      <td style="text-align:left">Afficher/cacher le clavier virtuel.</td>
    </tr>
  </tbody>
</table>

## ![](/migration-images/emulateurs/ordinosaures/thomson-t08/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/Zlika/theodore/](https://github.com/Zlika/theodore/)
* **Doc Libretro** : [https://docs.libretro.com/library/theodore/](https://docs.libretro.com/library/theodore/)

