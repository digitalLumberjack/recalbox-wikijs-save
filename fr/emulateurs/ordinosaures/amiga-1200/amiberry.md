---
title: Amiberry
---

# Amiberry

**Amiberry** est un core pour ARM optimisé pour Amiga.

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/gerald-g-parchment-background-or-border-5.svg)Licence

Ce core est sous licence [**GPLv3**](https://github.com/midwan/amiberry/blob/master/COPYING).

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/tqfp32.svg) BIOS

### Liste des bios obligatoires

Vous trouverez les bios avec le nom indiqué dans la colonne **Description** qu'il vous faudra renommer avec le nom indiqué dans la colonne **Nom de fichier**.

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| kick39106.A1200.rom | Kickstart v3.0 rev 39.106 \(1992\)\(Commodore\)\(A1200\)\[!\].rom |  | ❌ |
| kick40068.A1200.rom | Kickstart v3.1 r40.068 \(1993-12\)\(Commodore\)\(A1200\)\[!\].rom |  | ❌ |
| kick40068.A4000.rom | Kickstart v3.1 r40.068 \(1993-12\)\(Commodore\)\(A4000\)\[!\].rom |  | ❌ |

### Emplacement

Placez les BIOS comme ceci :

┣ 📁 recalbox  
┃ ┣ 📁 share  
┃ ┃ ┣ 📁 bios  
┃ ┃ ┃ ┣ 🗒 **kick39106.A1200.rom**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **kick40068.A1200.rom**  
┃ ┃ ┃ ┣ \*\*\*\*🗒 **kick40068.A4000.rom**  

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/rom-30098_640.png) Roms


>L'émulation Amiga est disponible en deux parfums : Amiga 600 et Amiga 1200.  
>Certains jeux peuvent être très capricieux donc essayez les deux systèmes si un jeu ne fonctionne pas.
>Les jeux peuvent être utilisés soit dans un format disque ADF soit dans un format WHDLoad, utilisant dans ce cas un fichier UAE complémentaire.
{.is-info}

### **Extensions supportées**

* Disques _**AFD**_ \(\*.adf\), le format de disque **le plus populaire**  **Ne peut pas intégrer** les protections de disque \(**Peut être zippé ou 7-zippé**\). 
* Disques _**IPF**_ \(\*.ipf\), plus généralement **utilisés par les copies de jeu sans intro** \(_peut_ intégrer les protections de disque\). **Peut être zippé.** 
* _**WHD**_ \(dossiers, \*.lha/lzh/lzx, \*.zip\), le format bien connu pour les jeux sur disque dur. Les dossiers WHD sont reconnus en utilisant le fichier \*.slave à l'intérieur du dossier, mais il est _fortement_ recommandé de les garder empaquetés en lha ou en zip. Les WHD dépaquetés ne sont pas plus rapides et encore pire, ils peuvent rendre EmulationStation super lent. 
* _**HDD FS**_, "Hard drive on filesystem" \(Disque dur sur système de fichier\). Doit être un dossier finissant par l'extension ".hd". Rarement utilisé. Pour les vrais fans d'Amiga qui ont sauvegardé le disque dur de leur machine. Peut être zippé, mais ce n'est pas recommandé. 
* _**HDF**_ \(\*.hdf\), Image disque dans un seul fichier. Peut être zippé \(Lecture uniquement !\) 
* _**RP9**_ \(\*.rp9\), Les paquets tout-en-un d'Amiga Forever


>**Information :**
>Les autres formats d'images disque _pourraient_ être supportés mais n'ont pas été testés par l'équipe de Recalbox.
{.is-info}


>**Remarque :**
>Quand vous jouez à partir de fichiers zippés/7-zippés, notre configurateur essaye d'identifier le type de rom en cherchant des extensions spécifiques à l'intérieur de l'archive.
>* Les extensions ADF/IPF/BIN/ISO sont rapides à identifier. 
>* Le WHD est rapide, mais LHA devrait être l'option préférée. 
>* Le HDDFS peut prendre plus longtemps à identifier et peut donner lieu à des interprétations fausses. Si vous utilisez le HDDFS, laissez-le en tant que fichiers et dossiers normaux et finissez le nom du dossier racine avec  **`.hd`** pour une identification facile.
{.is-warning}

### **Emplacement**

Placez les roms comme ceci :

┣ 📁recalbox  
┃ ┣ 📁share  
┃ ┃ ┣ 📁roms  
┃ ┃ ┃ ┣ 📁amiga600  
┃ ┃ ┃ ┃ ┣ \*\*\*\*🗒 **jeux.bin**  
┃ ┃ ┃ ┃ ┣ 🗒 **jeux.lst**  


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

### Fonctionnement

#### **Jeux ADF**

**Copiez-les** dans votre dossier de **roms Amiga.**  
Les **disques multiples** sont **automatiquement** chargés, **jusqu'à 4** pour les jeux utilisant **la bonne nomenclature** "\(Disk 1 of X\)".

#### **Jeux WHD**

**Les jeux WHD** sont **un peu plus difficiles** mais rien de trop compliqué.

* **Installation :**

Dézippez votre jeu WHDLoad, supprimez le fichier`.info` au même niveau que le dossier, et copiez seulement ce dossier vers votre dossier de roms \(vous pouvez utiliser des sous-dossiers si vous le souhaitez -&gt; ex.`/recalbox/share/roms/amiga1200/ShootEmUp)`

* **Utilisation :**

Vous aurez besoin d'un ficher `.uae` au même niveau que le dossier du même nom, donc deux solutions :

* En créer un vide. 
* Utiliser un fichier customisé qui va vous permettre de modifier la configuration de l'émulateur \(voir prochain paragraphe\).

**Par défaut je recommande de d'abord essayer le dossier amiga1200 pour n'importe quel jeu WHDL. Si certains sont trop rapides, alors essayez-les dans le dossier amiga600.**

Vous pouvez utiliser le script suivant pour générer massivement des fichiers uae : [UaeGenerator](http://www89.zippyshare.com/v/80w859p5/file.html)

* **Modification des jeux WHDL :**

#### Modification de fichiers .UAE

Dans le fichier uae, vous pouvez définir des blocs `;hardware`, `;controls` et `;graphics` pour remplacer la configuration standard de l'émulateur.

**Les parties customisées de la configuration dans le fichier .uae vont uniquement être utilisées si elles commencent avec le bon nom de bloc :** `;hardware`**,** `;controls` **ou** `;graphics`

Cela peut vous permettre d'utiliser deux joysticks par exemple, avoir une configuration matérielle très spécifique pour certains jeux qui sont un peu spéciaux, ou définir une résolution personnalisée.

Vous pouvez aussi tout supprimer dans le fichier uae et la configuration de base de l'émulateur sera alors utilisée.

Exemple de fichiers uae entièrement customisés pour le duo amiga600 et amiga1200 :  [UAEs Customisée](https://www100.zippyshare.com/v/1ttgYgks/file.html).

Copiez celui-ci \(correspondant au modèle d'Amiga que vous souhaitez utiliser\) à côté du dossier du jeu WHDL et renommez-le exactement comme le dossier du jeu \(gardez l'extension `.uae` \) ex. : si votre jeu à pour nom de dossier `Rick Dangerous`, votre fichier uae devrait être nommé `Rick Dangerous.uae` et être au même niveau que le dossier.

#### Modification de la séquence de démarrage \(experts seulement\) <a id="startup-sequence-tweaking-for-experts-only"></a>

La séquence de démarrage standard générée pour les jeux WHDL est`WHDload game.slave Preload` \(dans `WHDL/S/Startup-Sequence`\).

Mais quelques jeux WHDL peu nombreux \(comme History Line : 1914-1918 \) peuvent demander des paramètres additionnels au démarrage sous peine de simple crash.

Vous pouvez ajouter un deuxième fichier \(complètement optionnel\) contenant ces paramètres additionnels, par conséquent vous aurez, en prenant l'exemple d'History Line :

* HistoryLine \(dossier du jeu WHDL\) 
* HistoryLine.uae \(qui peut être vide ou perso.\) 
* HistoryLine.whdl \(optionnel, contenant des paramètres en plus `CUSTOM1=1`\)

Le jeu se lancera ensuite.

Voici une petite liste des jeux qui requiert des paramètres additionnels.

| Jeu | Paramètre\(s\) extra / Contenu du fichier |
| :--- | :--- |
| HistoryLine 1914-1918 | `CUSTOM1=1` pour l'intro, `CUSTOM1=2` pour le jeu |
| The Settlers / Die Siedlers | `CUSTOM1=1` passe l'intro |

## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/hammer-28636_640.png) Configuration avancée de l'émulateur



## ![](/migration-images/emulateurs/ordinosaures/amiga-1200/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes



