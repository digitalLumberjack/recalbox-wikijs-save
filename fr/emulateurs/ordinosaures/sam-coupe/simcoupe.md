---
title: SimCoupe
---

# SimCoupe



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://gitlab.com/recalbox/packages/standalone/simcoupe/-/blob/dev/License.txt).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS


>**Aucun bios n'est requis.**
{.is-success}

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .dsk
* .sad
* .mgt
* .sdf
* .td0
* .sbt
* .cpm

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁samcoupe
> > > >
> > > > > 🗒**fichier.dsk**


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

SimCoupe peut utiliser des logiciels au format disque suivants :

`.MGT` - Simple dump de secteur des disques +D/SAM : 2 faces, 80 pistes par face, 10 secteurs par piste, 512 bytes par secteur = 819200 bytes. Les images les plus anciennes dans ce format peuvent avoir l'extension de fichier .dsk. C'est le format préféré pour les disques SAM au format normal, et est compatible avec les périphériques Linux /dev/fd0u800.

`.SAD` - Format de disque SAM, crée par Aley Keprt. C'est aussi un dump basé sur les secteurs mais avec un fichier en-tête de 22 bytes permettant des ajustements géométriques sur les pistes par disque, les pistes par face, les secteurs par piste and les bytes par secteur. Les disques normaux SAM qui sont stockées au format SAD contiennent 819222 bytes, mais une différence dans l'ordre des pistes évite de supprimer l'en-tête de 22 bytes pour donner un équivalent d'une image MGT. La version 2 des images SAD sont du même format mais compressé avec gzip.

`.DSK` - Images étendues DSK \(EDSK\), utilisées originellement avec les supports Amstrad CPC et Spectum +3. Un format flexible capable de représenter tous les disques SAM existants, et aussi le format préféré du site d'archives worldofsam.org. La taille des images est proportionnelle à la géométrie des disques, avec un disque SAM normal autour de 840K.

`.SBT` - Fichier bootables Sam, crée par Andrew Collier. Ces fichiers sont des fichiers auto-bootables fait pour être copiés sur un disque SAM vide quand ils sont démarrés. Bien que ce ne soit pas des images bootables techniquement, SimCoupe les traite comme tels \(lecture seule\).

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur



## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://gitlab.com/recalbox/packages/standalone/simcoupe/](https://gitlab.com/recalbox/packages/standalone/simcoupe/)

