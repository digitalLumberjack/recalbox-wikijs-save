---
title: DatUtil
---

# DatUtil

## Introduction

Depuis quelques temps, il y a des questions sur comment créer un fichier dat filtré à partir du fichier dat original.

Voici comment le faire avec l'outil en ligne de commande [DatUtil](http://www.logiqx.com/Tools/DatUtil/dutil246.zip) avec un exemple.  
Faites défiler jusqu'à la fin pour voir les commandes les plus utilisés.

## Description

**DatUtil** est un **outil de ligne de commande**, ce qui vous permet de **modifier** et d' **ajuster** les fichiers DAT de plusieurs façons différentes.  
Il peut gérer des fichiers DAT de toute taille, ce qui le rend plus confortable et plus utilisable que **DatWorkshop Pro**.

### Exemple

* Vous souhaitez créer un fichier DAT qui comprend **SEULEMENT** Jeux NeoGeo
* En sommes, ce fichier ne comprend que les roms **parents** \(**pas de Clones**\).
* Dans cet exemple, nous utilisons le fichier "MAME-ROMs \(v0.176\_XML\) .dat"

## Contenu

L'outil est livré avec un `readme.txt` , qui est, à mon humble avis, tout à fait claire.

Dans ce qui suit, vous pouvez voir la partie la plus importante du `readme.txt` :

### Valeurs par defaut

> Fix fusion \(anciennement l'option -m\)  
> Supprimer des ROM / disques / échantillons en double

### **Enregistrements**

> -f format de sortie \(listinfo, listxml, romcenter2, délimité, sous-liste, etc.\)  
>  -q toujours utiliser des guillemets autour de chaînes \(s'applique uniquement à la sortie listinfo\)  
>  -k conserver autant d'informations que possible du fichier source  
>  -j Nebula Jukebox - chargez seulement Z80 et des ROM d'échantillon de romdata  
>  -o sortie au fichier  
>  -a ajouter au dossier  
>  -t mode de test - aucun fichier de données n'est en fait enregistré \(juste chargé et nettoyé\)

### **Texte en entête**

> -un auteur  
>  -V version  
>  -C catégorie  
>  -R réf nom  
>  -F nom complet \(c.-à-d. Description\)  
>  -T date  
>  -E-mail  
>  -H page d'accueil  
>  -U url  
>  -O commentaire  
>  -M fusion \(aucune, fractionnée ou complète\)  
>  -P emballage \(zip ou unzip\)  
>  -N nodump \(obsolète, requis ou ignoré\)

### **Selection des jeux**

> -g sélection de jeu individuel. Utilisez le symbole @ pour spécifier un fichier de noms  
>  -c inclut des clones \(à utiliser avec l'option -g\)  
>  -G sélectionner des jeux à partir d'un fichier source spécifié. La méthode @ est également prise en charge  
>  -S sélectionner des jeux en utilisant une sous-chaîne de description. La méthode @ est prise en charge  
>  -! Change les options -g, -G, -S \(y compris l'option -c\) pour exclure les jeux  
>  -r supprimer des clones

### **Nettoyage**

> -l noms de jeu en minuscules et noms de ROM  
>  -s trient les jeux par parent \(triés par nom de parent puis par nom de jeu\)  
>  -i inclure les informations manquantes d'un fichier de données de référence  
>  -I Incorporer les jeux à partir d'un fichier de données «complément»  
>  -X réparer la fusion \(ne pas utiliser si vous ne comprenez pas les conséquences!\)  
>  -D supprimer les ROM / disques / échantillons en double \(comme ci-dessus en termes d'utilisation\)  
>  -p prune \(supprimer\) ROMs, disques et / ou échantillons \(par exemple '-p disque, échantillon'\)

### **MD5 / SHA1:**

> -x Calculer SHA1 / MD5 lors de la numérisation de fichiers ou ZIP dans un répertoire  
>  -m Utilisez des checksums MD5 plutôt que SHA1 \(par exemple, en utilisant -x, -m peut être utilisé\)  
>  Information:  
>  -v Enregistrement détaillé  
>  -d Afficher les messages de débogage

## Instructions sur un exemple

1.copier le fichier `MAME - ROMs (v0.176_XML).dat` dans le répertoire DatUtil  
 2. Ouvrir une invite de commande CMD et lexecuter en tant qu'administrateur.  
 3. Dans l'invite de commande CMD ouvrir le répertoire DatUtil d  
 4. Executer la ligne suivante : `datutil.exe -g neogeo -c -r -f generic -A Nachtgarm -C "Standard DatFile" -F NeoGeoOnlyNoClones -R NeoGeo_only_NO_clones -V "1.0" -o NeoGeoOnlyNoClones.dat "MAME - ROMs (v0.176_XML).dat"`

Le résultat donnera un nouveau fichier `dat` avec le nom `NeoGeoOnlyNoClones.dat`, lequel peut être ouvert avec Romulus, ou clrmamepro.  
Les inclus sont 159 Jeux et un Bios.

Voici un extrait du fichier créé :

```text
<?xml version="1.0"?>

<!DOCTYPE datafile PUBLIC "-//Logiqx//DTD ROM Management Datafile//EN" "http://www.logiqx.com/Dats/datafile.dtd">

<datafile>

	<header>

		<name>NeoGeo_only_NO_clones</name>

		<description>NeoGeoOnlyNoClones</description>

		<category>Standard DatFile</category>

		<version>1.0</version>

		<author>Nachtgarm</author>

	</header>

	<game name="2020bb" romof="neogeo">

		<description>2020 Super Baseball (set 1)</description>

		<year>1991</year>

		<manufacturer>SNK / Pallas</manufacturer>

		<rom name="sp-s2.sp1" merge="sp-s2.sp1" size="131072" crc="9036d879" sha1="4f5ed7105b7128794654ce82b51723e16e389543"/>

		<rom name="sp-s.sp1" merge="sp-s.sp1" size="131072" crc="c7f2fa45" sha1="09576ff20b4d6b365e78e6a5698ea450262697cd"/>

		<rom name="sp-u2.sp1" merge="sp-u2.sp1" size="131072" crc="e72943de" sha1="5c6bba07d2ec8ac95776aa3511109f5e1e2e92eb"/>

		<rom name="sp-e.sp1" merge="sp-e.sp1" size="131072" crc="2723a5b5" sha1="5dbff7531cf04886cde3ef022fb5ca687573dcb8"/>

		<rom name="v2.bin" merge="v2.bin" size="131072" crc="62f021f4" sha1="62d372269e1b3161c64ae21123655a0a22ffd1bb"/>

		<rom name="asia-s3.rom" merge="asia-s3.rom" size="131072" crc="91b64be3" sha1="720a3e20d26818632aedf2c2fd16c54f213543e1"/>

		<rom name="vs-bios.rom" merge="vs-bios.rom" size="131072" crc="f0e8f27d" sha1="ecf01eda815909f1facec62abf3594eaa8d11075"/>

		<rom name="sp-j2.sp1" merge="sp-j2.sp1" size="131072" crc="acede59c" sha1="b6f97acd282fd7e94d9426078a90f059b5e9dd91"/>

		<rom name="sp1.jipan.1024" merge="sp1.jipan.1024" size="131072" crc="9fb0abe4" sha1="18a987ce2229df79a8cf6a84f968f0e42ce4e59d"/>

		<rom name="sp-45.sp1" merge="sp-45.sp1" size="524288" crc="03cc9f6a" sha1="cdf1f49e3ff2bac528c21ed28449cf35b7957dc1"/>

		<rom name="japan-j3.bin" merge="japan-j3.bin" size="131072" crc="dff6d41f" sha1="e92910e20092577a4523a6b39d578a71d4de7085"/>

		<rom name="sp-1v1_3db8c.bin" merge="sp-1v1_3db8c.bin" size="131072" crc="162f0ebe" sha1="fe1c6dd3dfcf97d960065b1bb46c1e11cb7bf271"/>

		<rom name="uni-bios_3_2.rom" merge="uni-bios_3_2.rom" size="131072" crc="a4e8b9b3" sha1="c92f18c3f1edda543d264ecd0ea915240e7c8258"/>

		<rom name="uni-bios_3_1.rom" merge="uni-bios_3_1.rom" size="131072" crc="0c58093f" sha1="29329a3448c2505e1ff45ffa75e61e9693165153"/>

		<rom name="uni-bios_3_0.rom" merge="uni-bios_3_0.rom" size="131072" crc="a97c89a9" sha1="97a5eff3b119062f10e31ad6f04fe4b90d366e7f"/>

		<rom name="uni-bios_2_3.rom" merge="uni-bios_2_3.rom" size="131072" crc="27664eb5" sha1="5b02900a3ccf3df168bdcfc98458136fd2b92ac0"/>

		<rom name="uni-bios_2_3o.rom" merge="uni-bios_2_3o.rom" size="131072" crc="601720ae" sha1="1b8a72c720cdb5ee3f1d735bbcf447b09204b8d9"/>

		<rom name="uni-bios_2_2.rom" merge="uni-bios_2_2.rom" size="131072" crc="2d50996a" sha1="5241a4fb0c63b1a23fd1da8efa9c9a9bd3b4279c"/>

		<rom name="uni-bios_2_1.rom" merge="uni-bios_2_1.rom" size="131072" crc="8dabf76b" sha1="c23732c4491d966cf0373c65c83c7a4e88f0082c"/>

		<rom name="uni-bios_2_0.rom" merge="uni-bios_2_0.rom" size="131072" crc="0c12c2ad" sha1="37bcd4d30f3892078b46841d895a6eff16dc921e"/>

		<rom name="uni-bios_1_3.rom" merge="uni-bios_1_3.rom" size="131072" crc="b24b44a0" sha1="eca8851d30557b97c309a0d9f4a9d20e5b14af4e"/>

		<rom name="uni-bios_1_2.rom" merge="uni-bios_1_2.rom" size="131072" crc="4fa698e9" sha1="682e13ec1c42beaa2d04473967840c88fd52c75a"/>

		<rom name="uni-bios_1_2o.rom" merge="uni-bios_1_2o.rom" size="131072" crc="e19d3ce9" sha1="af88ef837f44a3af2d7144bb46a37c8512b67770"/>

		<rom name="uni-bios_1_1.rom" merge="uni-bios_1_1.rom" size="131072" crc="5dda0d84" sha1="4153d533c02926a2577e49c32657214781ff29b7"/>

		<rom name="uni-bios_1_0.rom" merge="uni-bios_1_0.rom" size="131072" crc="0ce453a0" sha1="3b4c0cd26c176fc6b26c3a2f95143dd478f6abf9"/>

		<rom name="030-p1.p1" size="524288" crc="d396c9cb" sha1="47ba421d14d05b965a8d44e7475b227a208e5a07"/>

		<rom name="030-s1.s1" size="131072" crc="7015b8fc" sha1="8c09bc3e6c62e0f7c9557c1e10c901be325bae7f"/>

		<rom name="sfix.sfix" merge="sfix.sfix" size="131072" crc="c2ea0cfd" sha1="fd4a618cdcdbf849374f0a50dd8efe9dbab706c3"/>

		<rom name="000-lo.lo" merge="000-lo.lo" size="131072" crc="5a86cff2" sha1="5992277debadeb64d1c1c64b0a92d9293eaf7e4a"/>

		<rom name="sm1.sm1" merge="sm1.sm1" size="131072" crc="94416d67" sha1="42f9d7ddd6c0931fd64226a60dc73602b2819dcf"/>

		<rom name="030-m1.m1" size="131072" crc="4cf466ec" sha1="6a003b53c7a4af9d7529e2c10f27ffc4e58dcda5"/>

		<rom name="030-v1.v1" size="1048576" crc="d4ca364e" sha1="b0573744b0ea2ef1e2167a225f0d254883f5af04"/>

		<rom name="030-v2.v2" size="1048576" crc="54994455" sha1="76eb62b86e8ed51a77f44313d5cc8091b3f58d57"/>

		<rom name="030-c1.c1" size="1048576" crc="4f5e19bd" sha1="ef7975c4b33a7aea4a25a385f604799f054d3200"/>

		<rom name="030-c2.c2" size="1048576" crc="d6314bf0" sha1="0920cc580d7997fcb0170dd619af2f305d635577"/>

		<rom name="030-c3.c3" size="1048576" crc="47fddfee" sha1="297c505a63448c999a2510c27bf4549102134db8"/>

		<rom name="030-c4.c4" size="1048576" crc="780d1c4e" sha1="2e2cf9de828e3b48642dd2203637103438c62142"/>

	</game>

[...]

</datafile>
```

## Explications sur la chaîne :

`datutil.exe` = La commande pour exécuter l'outil  
 `-g` = jeu individuel ou de la sélection du système. Dans notre cas neogeo  
 `neogeo` = voir ci - dessus  
 `-c` = Inclut tous les jeux \(le readme est un peu déroutant ici\). Si vous n'utilisez pas cette option, seuls les bios NEOGEO seront trouvés  
 `-r` = supprime tous les clones  
 `-f` = détermine le format de la nouvelle DAT. Dans notre cas `generic`  
 `-A` = Détermine l'auteur. Dans notre cas `Nachtgarm`  
 `-C` = Détermine le type de DAT \(Catégorie\). Dans notre cas `"Standard DatFile"` . Notez le `" "` , qui sont nécessaires, en raison des ébauches  
 `-F` = Détermine le nom \(Description\) du DAT dans un gestionnaire de ROM. Dans notre cas `NeoGeoOnlyNoClones`  
 `-R` = Détermine le nom qui est affiché dans un gestionnaire de ROM. Dans notre cas `NeoGeo_only_NO_clones`  
 `-V` = Détermine la version du fichier DAT. Dans notre cas `"1.0"` . Notez le `" "` ici aussi, en raison de l'arrêt complet  
 `-o` = détermine le nouveau nom de fichier. Dans notre cas `NeoGeoOnlyNoClones.dat`

## Chaines les plus utilisées

Chacune des chaînes suivantes attend le DAT d' origine pour être placé dans le même répertoire que l'outil `datutil.exe`

**Créer un fichier DAT qui inclue uniquement les jeux NEOGEO avec leurs clones**

`datutil.exe -g neogeo -c -f generic -C "Standard DatFile" -o NewFileName.dat "OriginalFile.dat"`

**Créer un fichier DAT qui inclue uniquement les jeux NEOGEO \(sans les clones\)**

`datutil.exe -g neogeo -c -r -f generic -C "Standard DatFile" -o NewFileName.dat "OriginalFile.dat"`

**Créer un fichier DAT uniquement les roms parentes \(sans NEO-GEO et sans les clones\)**

`datutil.exe -g neogeo -c -! -r -f generic -C "Standard DatFile" -o NewFileName.dat "OriginalFile.dat"`

