---
title: Amiga recup
---

# Amiga recup

## Les "roms" supportées <a id="les-roms-supportees"></a>

* **Amiga600 & Amiga1200**:
  * Disques _**AFD**_ \(\*.adf\), le format de disque **le plus populaire** N**e peut pas intégrer** les protections de disque \(**Peut être zippé ou 7-zippé**\).
  * Disques _**IPF**_ \(\*.ipf\), plus généralement **utilisés par les copies de jeu sans intro** \(_peut_ intégrer les protections de disque\). **Peut être zippé.**
  * _**WHD**_ \(dossiers, \*.lha/lzh/lzx, \*.zip\), le format bien connu pour les jeux sur disque dur. Les dossiers WHD sont reconnus en utilisant le fichier \*.slave à l'intérieur du dossier, mais il est _fortement_ recommandé de les garder empaquetés en lha ou en zip. Les WHD dépaquetés ne sont pas plus rapides et encore pire, ils peuvent rendre EmulationStation super lent :\)
  * _**HDD FS**_, "Hard drive on filesystem" \(Disque dur sur système de fichier\). Doit être un dossier finissant par l'extension ".hd". Rarement utilisé. Pour les vrais fans d'Amiga qui ont sauvegardé le disque dur de leur machine. Peut être zippé, mais ce n'est pas recommandé.
  * _**HDF**_ \(\*.hdf\), Image disque dans un seul fichier. Peut être zippé \(Lecture uniquement!\)
  * _**RP9**_ \(\*.rp9\), Les paquets tout-en-un d'Amiga Forever

**Information:**

Les autres formats d'images disque _pourraient_ être supportés mais n'ont pas été testés par l'équipe de Recalbox.

**Remarques :**

Quand vous jouez à partir de fichiers zippés/7-zippés, notre configurateur essaye d'identifier le type de rom en cherchant des extensions spécifiques à l'intérieur de l'archive.

* Les extensions ADF/IPF/BIN/ISO sont rapides à identifier.
* Le WHD est rapide, mais LHA devrait être l'option préférée.
* Le HDDFS peut prendre plus longtemps à identifier et peut donner lieu à des interprétations fausses. Si vous utilisez le HDDFS, laissez-le en tant que fichiers et dossiers normaux et finissez le nom du dossier racine avec **`.hd`** pour une identification facile.

## Reparamétrage des configuration <a id="reparametrage-des-configurations"></a>

Comme vous pouvez le voir, le nouvel Amiberry prend en charge **tous** les formats de "roms" Amiga. Pour rendre les choses plus faciles pour tout le monde, nous avons beaucoup travaillé à pouvoir configurer auto-magiquement l'émulateur en fonction de ce que vous souhaitez lancer. Recalbox construit une configuration machine par défaut par sous-système, cependant, dans certaines situations, vous pourriez avoir envie de surplanter les paramètres auto-générés.

Recalbox génère des fichiers de configuration dans /tmp/amiga/conf. Le fichier le plus important est uaeconfig.uae, dans lequel vous allez trouver toutes les clés définissant la machine, lecteurs de disquettes, disque durs, etc. Je ne peut pas toutes les décrire ici. Si vous êtes curieux, je vous recommande de regarder les documentations respectives d'Amiberry et d'UAE.

Vous avez deux moyens de supplanter les configurations:



### **Par système / Dossier:** <a id="par-systeme-dossier"></a>

Créez un fichier nommé`/recalbox/share/roms/<amigasystem>/.uaeconfig.uae`

\(`/recalbox/share/roms/amiga1200/.uaeconfig.uae` pour l'Amiga1200\)

Réglez la clé que vous souhaitez modifier. Par exemple, vous pouvez réaliser un fichier de configuration avec: `show_leds=false` pour désactiver l'affichage LED dans le coin en bas à droite.



### Par jeu <a id="par-jeu"></a>

Créez un fichier nommé exactement comme votre "rom" \(ou dossier\) mais qui finit avec`.uae`. Par exemple, dans votre dossier de roms, si vous avez un fichier nommé `Aladdin (AGA).ipf`, vous pouvez créer un fichier `Aladdin (AGA).uae` et modifier les clés dans ce fichier.

Recalbox construit les configurations dans l'ordre suivant:

* Construction de la config. par défaut en fonction du type de rom et du sous-système.
* Chargement de`/recalbox/share/roms/<amigasystem>/.uaeconfig.uae`si le fichier existe, et ajout/supplantation des clés de configuration.
* Chargement de`<game>.uae`si le fichier existe, et ajout/supplantation des clés de configuration.



### En jeu <a id="en-jeu"></a>

Comme dans les autres émulateurs: **HoyKey + START** quitte l'émulateur et **HoyKey + B** lance l'interface d'Amiberry.

## BIOS <a id="bios-1"></a>

Le nouveau Recalbox vient avec un remplacement kickstart open-source, le bios AROS \(version 2019\). Notre configurateur auto-magique utilise ce bios quand aucun autre bios n'est disponible dans le dossier share/bios. Plusieurs jeux ont booté et ont été testés avec succès en utilisant le bios AROS. Mais, gardez en tête que c'est un _**remplacement**_. Il est très recommandé d'utiliser le bios requis. Surtout si vous voulez lancer des jeux WHD, car le WHDLoader d'Amiberry pourrait changer des paramètres du bios et chercher le meilleur kickstart disponible.



### _Ordinateurs:_ <a id="ordinateurs"></a>

* **kick33180.A500.rom** \(Kickstart v1.2 rev 33.180 \(1986\)\(Commodore\)\(A500-A1000-A2000\).rom\)
* **kick34005.A500.rom** \(Kickstart v1.3 rev 34.5 \(1987\)\(Commodore\)\(A500-A1000-A2000-CDTV\).rom\)
* **kick37175.A500.rom** \(Kickstart v2.04 rev 37.175 \(1991\)\(Commodore\)\(A500+\).rom\)
* **kick39106.A1200.rom** \(Kickstart v3.0 rev 39.106 \(1992\)\(Commodore\)\(A1200\)\[!\].rom\)
* **kick40063.A600.rom** \(Kickstart v3.1 rev 40.63 \(1993\)\(Commodore\)\(A500-A600-A2000\)\[!\].rom\)
* **kick40068.A1200.rom** \(Kickstart v3.1 rev 40.68 \(1993\)\(Commodore\)\(A1200\).rom\)
* **kick40068.A4000.rom** \(Kickstart v3.1 rev 40.68 \(1993\)\(Commodore\)\(A4000\).rom\)

## Utilisation <a id="utilisation"></a>

L'émulation Amiga est disponible en deux parfums : Amiga 600 et Amiga 1200. Certains jeux peuvent être très capricieux donc essayez les deux systèmes si un jeu ne fonctionne pas.

Les jeux peuvent être utilisés soit dans un format disque ADF soit dans un format WHDLoad, utilisant dans ce cas un fichier UAE complémentaire.

Clavier et souris sont quelque peu obligatoires comme beaucoup de jeux Amiga ont besoin d'appui sur des touches spécifiques pour se lancer.

## Commandes spéciales <a id="commandes-speciales"></a>

* Entrer dans le GUI : Start ou F12
* Quitter l'émulateur : Hotkey ou F12 puis Q

## Jeux ADF <a id="jeux-adf"></a>

**Copiez-les** dans votre dossier de **roms Amiga.** Les **disques multiples** sont **automatiquement** chargés, **jusqu'à 4** pour les jeux utilisant **la bonne nomenclature** "\(Disk 1 of X\)".

## Jeux WHD <a id="jeux-whd"></a>

**Les jeux WHD** sont **un peu plus difficiles** mais rien de trop compliqué.

### Installation : <a id="installation"></a>

Dézippez votre jeu WHDLoad, supprimez le fichier`.info` au même niveau que le dossier, et copiez seulement ce dossier vers votre dossier de roms \(vous pouvez utiliser des sous-dossiers si vous le souhaitez -&gt; ex.`/recalbox/share/roms/amiga1200/ShootEmUp)`

###  <a id="utilisation-1"></a>

### Utilisation : <a id="utilisation-1"></a>

Vous aurez besoin d'un ficher `.uae` au même niveau que le dossier du même nom, donc deux solutions :

* En créer un vide.
* Utiliser un fichier customisé qui va vous permettre de modifier la configuration de l'émulateur \(voir prochain paragraphe\).

**Par défaut je recommande de d'abord essayer le dossier amiga1200 pour n'importe quel jeu WHDL. Si certains sont trop rapides, alors essayez-les dans le dossier amiga600.**

Vous pouvez utiliser le script suivant pour générer massivement des fichiers uae : [UaeGenerator](http://www89.zippyshare.com/v/80w859p5/file.html)



### Modification des jeux WHDL <a id="modification-des-jeux-whdl"></a>

#### Modification de fichiers .UAE <a id="modification-de-fichiers-uae"></a>

Dans le fichier uae, vous pouvez définir des blocs `;hardware`, `;controls` et `;graphics` pour remplacer la configuration standard de l'émulateur.

**Les parties customisées de la configuration dans le fichier .uae vont uniquement être utilisées si elles commencent avec le bon nom de bloc :** `;hardware`**,** `;controls` **ou** `;graphics`

Cela peut vous permettre d'utiliser deux joysticks par exemple, avoir une configuration matérielle très spécifique pour certains jeux qui sont un peu spéciaux, ou définir une résolution personnalisée.

Vous pouvez aussi tout supprimer dans le fichier uae et la configuration de base de l'émulateur sera alors utilisée.

Exemple de fichiers uae entièrement customisés pour le duo amiga600 et amiga1200 : [UAEs Customisée](https://www100.zippyshare.com/v/1ttgYgks/file.html).

Copiez celui-ci \(correspondant au modèle d'Amiga que vous souhaitez utiliser\) à côté du dossier du jeu WHDL et renommez-le exactement comme le dossier du jeu \(gardez l'extension `.uae` \) ex. : si votre jeu à pour nom de dossier `Rick Dangerous`, votre fichier uae devrait être nommé `Rick Dangerous.uae` et être au même niveau que le dossier.

​

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

​

## Bugs connus <a id="bugs-connus"></a>



* Dans certains cas \(deux joysticks connectés, ...\) l'émulateur peut ne pas arriver à savoir quel joystick utiliser. Si cela vous arrive, allez dans le menu "Inputs" du GUI et essayez de changer le joystick en port 1.
* Les jeux WHDL qui utilisent plusieurs esclaves \(slaves\) peuvent avoir des introductions montrées après le jeu en lui-même.
* Pour certains jeux, votre clavier devra être configuré en US dans `recalbox.conf` pour qu'ils se lancent. Souvenez-nous, si vous utilisez un clavier azerty, quitter l'émulateur se fera par F12 puis A.
* Cette solution utilise l'émulateur Amiberry, donc ses erreurs actuelles sont écrites ici : [https://github.com/midwan/amiberry/issues](https://github.com/midwan/amiberry/issues)

