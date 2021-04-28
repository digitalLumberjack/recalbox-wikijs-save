---
title: Emulateur Amiga 600 & 1200 & AmigaCD32
---

# Emulateur Amiga 600 & 1200 & AmigaCD32

Voici une rapide introduction au nouvel émulateur Amiga.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LyGfKSLcIDCh_LGWdwY%2F-LyGjOUWj0iTtI56ZehI%2Ff7c5336e-ff11-4946-ae58-a5fecf99ecb2.png?alt=media&token=43324b57-aa51-4735-8b94-e67cf0015452)

**Amiberry a été mis à jour en v2.24** sur Raspberry 2, 3B\(+\) et Odroid XU4.

C'est un gros bouleversement et la nouvelle version supporte **beaucoup de nouvelles fonctionnalités** !

## Sous-systèmes

Dans Recalbox, les machines Amiga ont été divisées en 3 sous-systèmes virtuels :  


* **Amiga 600** : Toutes les machines _OCS/ECS_ de l'**A1000** jusqu'à la dernière **A600**     
* **Amiga 1200** : Toutes les machines _AGA_, à partir de la **1200**     
* **Amiga CD32** : La seule vraie console de la série Amiga     
  * Le _CDTV_ **n'est pas encore pris en charge**, bien que les configurations du thème Recalbox et du _CDTV_ soient prêtes. Il **sera ajouté plus tard** comme nouveau sous-système, dès qu'**Amiberry** le supportera complètement.

## « Roms » supportées

Voici une liste des formats de fichiers supportés, classé par sous-système :  


* **Amiga600 & Amiga1200** :  
    

  * Disques **ADF** \(_\*.adf_\), le format de disque le plus populaire \(ne peut pas intégrer de protections de disque\). Peut être zippé ou 7-zippé.
  * Disques **IPF** \(_\*.ipf_\), le plus utilisé par les dumps sans intro \(peut intégrer des protections de disque\). Peuvent être zippés.
  * **WHD** \(dossiers, _\*.lha/lzh/lzx, \*.zip_\), le format bien connu pour les jeux sur disque dur. Les dossiers _WHD_ sont reconfigurés en utilisant le fichier _\*.slave_ interne ; cependant il est **fortement recommandé** de les stocker au format _lha_ ou _zip_. Les _WHD_ décompressés **ne sont pas plus rapides et même pire**, ils peuvent rendre EmulationStation extrêmement lent :\)
  * **HDD FS**, Disque dur sur système de fichiers. Les dossiers doivent se terminer par des extensions de type "_.hd_". Rarement utilisé. Pour les vrais amateurs d'Amiga qui ont sauvegardé leur Amiga HD. Peut être zippé, mais pas recommandé.
  * **HDF** \(_\*.hdf_\), Images de disque dur dans un seul fichier. Peut être zippé \(Lecture/Écriture !\)
  * **RP9** \(_\*.rp9_\), Packs « tout-en-un » Amiga Forever

* **Amiga CD32** : 
  * **ISO** \(_\*.bin, \*.iso_, avec ou sans _\*.cue_\), CD dumps. Peut être zippé.

D'autres formats d'images de CD peuvent être pris en charge mais n'ont pas été testés par l'équipe Recalbox.

Lors de l'exécution de fichiers zippés/7-zippés, notre configurateur essaie d'identifier le type de rom en recherchant des **extensions spécifiques** à l'intérieur de l'archive. 

* _ADF/IPF/BIN/ISO_ sont rapides à identifier.
* _WHD_ sont rapides, mais _LHA_ doit être préféré.
* _HDDFS_ **peut être plus long à vérifier** et peut conduire à des interprétations erronées. Si vous utilisez _HDDFS_, laissez-les comme des fichiers et des dossiers normaux et créez le nom du dossier racine se terminant par `.hd` pour une identification rapide.

## Configurations prioritaires

Comme vous pouvez le voir, ce nouvel **Amiberry supporte tous les formats de roms d'Amiga**. Pour rendre les choses plus faciles pour tout le monde, nous avons fait un énorme travail pour **configurer automatiquement l'émulateur** en fonction de ce que vous voulez démarrer.

Recalbox construit une configuration de machine par défaut par sous-système. Cependant, dans certaines situations, **vous pouvez vouloir outrepasser les paramètres** générés automatiquement.

Recalbox génère les fichiers de configuration dans `/tmp/amiga/conf`. Le plus important est le fichier `uaeconfig.uae`, **dans lequel vous trouverez toutes les clés** définissant la machine, les disques durs, etc.

Je ne peux pas décrire toutes les clés ici. Si vous êtes curieux, je vous recommande de **jeter un coup d'oeil aux documentations Amiberry et UAE** appropriées.  


Vous avez deux façons d'écraser les paramètres :

### Par système :

Créer un fichier nommé `/recalbox/share/system/configs/amiberry/<subsystem>.uae` \(`/recalbox/share/system/configs/amiberry/amiga1200.uae` pour outrepasser l’Amiga1200\)

* Réglez la clé que vous voulez contourner. 
* Par exemple, vous pouvez créer un fichier de configuration avec :

```text
show_leds=false
```

pour **désactiver l'affichage LED** dans le coin inférieur droit.

### Par jeu

Créez un fichier nommé exactement comme votre "rom" \(ou dossier\) mais qui se termine par `.uae`.

Par exemple, dans votre dossier rom, si vous avez un fichier nommé `Aladdin (AGA).ipf`, vous pouvez créer un `Aladdin (AGA).uae` et remplacer les clés dans ce fichier.  


Recalbox génère la configuration dans l'ordre suivant :  


* Créer la configuration par défaut concernant le type de rom et le sous-système.
* Chargez `/recalbox/share/configs/<subsystem>.uae` si le fichier existe, et ajoutez/écrasez les clés de configuration.
* Chargez `<game>.uae` si le fichier existe, et ajoutez/écrasez les clés de configuration.

## Dans le jeu

Comme dans les autres émulateurs :

* **Hotkey + START** permettent de quitter l'émulateur, 
* **Hotkey + B** lance l'interface **Amiberry.**

## BIOS

La nouvelle Recalbox est livrée avec un **remplaçant de Kickstart open-source, le bios AROS** \(version 2019\). Notre configurateur automatique utilise ce BIOS **lorsqu'aucun autre BIOS n'est disponible** dans le dossier _share/bios_. Plusieurs jeux ont été démarrés et testés avec succès en utilisant le BIOS **AROS**.

Mais gardez à l'esprit qu'**il s'agit d'un remplacement**. Il est **fortement recommandé d'obtenir le BIOS requis**. En particulier si vous voulez lancer des jeux _WHD_, car le _WHDLoader_ de l'**Amiberry** peut modifier les paramètres du bios et **rechercher le meilleur Kickstart** disponible.



Voici la liste des nouveaux Kickstarts requis :

* Ordinateurs : 

**kick33180.A500.rom** \(Kickstart v1.2 rev 33.180 \(1986\)\(Commodore\)\(A500-A1000-A2000\).rom\)

**kick34005.A500.rom** \(Kickstart v1.3 rev 34.5 \(1987\)\(Commodore\)\(A500-A1000-A2000-CDTV\).rom\)

**kick37175.A500.rom** \(Kickstart v2.04 rev 37.175 \(1991\)\(Commodore\)\(A500+\).rom\)

**kick39106.A1200.rom** \(Kickstart v3.0 rev 39.106 \(1992\)\(Commodore\)\(A1200\)\[!\].rom\)

**kick40063.A600.rom** \(Kickstart v3.1 rev 40.63 \(1993\)\(Commodore\)\(A500-A600-A2000\)\[!\].rom\)

**kick40068.A1200.rom** \(Kickstart v3.1 rev 40.68 \(1993\)\(Commodore\)\(A1200\).rom\)

**kick40068.A4000.rom** \(Kickstart v3.1 rev 40.68 \(1993\)\(Commodore\)\(A4000\).rom\)



* CD32 : 

**kick40060.CD32.rom** \(Kickstart v3.1 rev 40.60 \(1993\)\(Commodore\)\(CD32\).rom\)

**kick40060.CD32.ext.rom** \(CD32 Extended-ROM rev 40.60 \(1993\)\(Commodore\)\(CD32\).rom\)



En espérant que cela puisse vous aider =\)

