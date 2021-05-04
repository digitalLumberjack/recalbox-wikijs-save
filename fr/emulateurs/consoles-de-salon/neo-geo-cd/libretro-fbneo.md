---
title: Libretro FBNeo
---

# Libretro FBNeo

\*\*\*\*

## ![](/migration-images/emulateurs/consoles-de-salon/neo-geo-cd/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**non commerciale**](https://github.com/finalburnneo/FBNeo/blob/master/LICENSE.md).

## ![](/migration-images/emulateurs/consoles-de-salon/neo-geo-cd/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | PC x86 | PC x86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ 🐌  | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

🐌 Basses performances mais jouable au format .iso/cue et .img/.ccd.

## ![](/migration-images/emulateurs/consoles-de-salon/neo-geo-cd/cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Sauvegardes | ✔ |
| Sauvegardes d'état | ✔ |
| RetroAchievements | ✔ |
| Cheats RetroArch | ✔ |
| Cheats natifs | ✔ |
| Manettes | ✔ |
| Multi-Mouse | ✔ |

## ![](/migration-images/emulateurs/consoles-de-salon/neo-geo-cd/tqfp32.svg)Bios

### Liste des bios obligatoires

| Nom du fichier | Description | **MD5** |
| :---: | :---: | :---: |
| neocdz.zip | Neo Geo CDZ System BIOS | 389dbeb0cb857c130414747462cf9d71 c85b8132799f1b2ad3754a97947809d2 b9ab07a79997fc044ca164fc72cd5680 f39572af7584cb5b3f70ae8cc848aba2 |
| neogeo;zip | Neo Geo BIOS | 005b843b6e70b939c2cca41887cbc371 2b4ffdf24d5d4f24c4b116c50c4bafc3 42e359e394f0be1d61b94ddca0efbe6c 42e359e394f0be1d61b94ddca0efbe6c 4b9432a4571d03cc8bae9d24d8d6eb40 4cd64313e26537c04cdb561b8f84b0e4 50bbfd6bf297038b085e29265c65723a 76ee7390ccd537cddea1018025ca29a8 84d6c35aad790a77ba3cfc1b319e1061 8cbdff53661f41ddbe486a98915e1ec9 912c0a56bafe0fba39d0c668b139b250 94748719c0ef31e7375b0c357d82fc89 a3b2c9a69c28ad0bd4ea07877b744bbe ab25b9e25052a6064901a7a221037eb6 ae9e5825cde82c58e39dfd48534f7060 b18f83feef474b8a1306ef199cd810a2 b4519df27a352c2a6e42e06d31330d91 bf00272e7150b31156a8995d60bf185d c1e0a738d266926f604186aa9d63e4db ca66fd463ef7dcab492a6de8ce5f45eb d12bba59121229ff13702878b415cb7c e023d0a4b5249fdff2a4620c28963944 f4a125538dfd7a8044e025fc5188fb88 |

### Emplacement

Placez les BIOS comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁bios  
┃ ┃ ┃ ┣ 🗒 **neocdz.zip**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **neogeo.zip**  

## ![](/migration-images/emulateurs/consoles-de-salon/neo-geo-cd/rom-30098_640.png) Roms

### Remarques concernant le format des jeux

#### Version "normale" et "cdz pached"

FBNeo prend les 2 formats, mais d'autres émulateurs Neogeo cd ne prennent que les versions patchés cdz. Il vaut peut-être mieux ne garder que celles-là.

#### Format Redump

Les fichiers Redump sont au format `.CUE` avec plusieurs fichiers `.BIN` appelés **multibin**. Ce core n'accepte pas le multibin et vous devez convertir vos jeux pour avoir un seul fichier bin.

**Conversion**

Vous pouvez le faire avec le logiciel **CDmage** 1.02.1 :

* **File** &gt; **Open** &gt; Sélectionnez votre jeu au format .CUE
* **File** &gt; **Save As** &gt; Indiquez le nouveau nom de votre jeu pour ne pas écraser l'existant et cliquez sur `Enregistrer`
* Assurez-vous avoir choisi « MODE1/2352 » dans la liste déroulante de droite de la nouvelle fenêtre et cliquez sur `OK`

Sources :

* [https://neo-source.com/index.php?topic=2487.msg26465\#msg26465](https://neo-source.com/index.php?topic=2487.msg26465#msg26465)
* [https://github.com/libretro/FBNeo/blob/master/src/burner/libretro/README.md\#neogeo-cd-doesnt-work-why-](https://github.com/libretro/FBNeo/blob/master/src/burner/libretro/README.md#neogeo-cd-doesnt-work-why-)

### Extensions supportées

Les isos doivent avoir les extensions suivantes :

* .bin/.cue \(**1 seul .bin**, voir [Remarques concernant le format des jeux](/fr/emulateurs/consoles-de-salon/neo-geo-cd/libretro-fbneo#remarques-concernant-le-format-des-jeux)\)
* .iso/.cue
* .img/.cue
* .img/.ccd/.sub

### Emplacement

Placez les isos comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁fbneo  
┃ ┃ ┃ ┃ ┣ 🗒 **jeux.zip**  

## ![](/migration-images/emulateurs/consoles-de-salon/neo-geo-cd/hammer-28636_640.png)Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
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

## \*\*\*\*⛏ **Dépannage**

### Doublon

Dans EmulationStation, assurez vous de n'avoir que 1 ccd + img + sub par jeu \(le cue ne sert en fait à rien si vous avez le ccd\) et ça devrait régler vos soucis de doublons dans le menu.

## ![](/migration-images/emulateurs/consoles-de-salon/neo-geo-cd/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github utilisé :** [https://github.com/libretro/FBNeo/](https://github.com/libretro/FBNeo)
* **Doc Libretro :** [https://docs.libretro.com/library/fbneo/](https://docs.libretro.com/library/fbneo/)
* **Les différences dans les jeux :** [https://www.neogeocdworld.info/html/jeux/jeux/differences.htm](https://www.neogeocdworld.info/html/jeux/jeux/differences.htm)

