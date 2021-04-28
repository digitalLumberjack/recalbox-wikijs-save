---
title: Guide complet sur la configuration video
---

# Guide complet sur la configuration video


>**Informations :** 
>
>Ce sont les meilleures recommandations pour configurer la vidéo de manière à ce qu'elle s'adapte à votre écran.  
>Il existe trois niveaux de configuration : système, mode vidéo par défaut de l'émulateur, mode vidéo spécifique de l'émulateur.
>
>Gardez à l'esprit que la résolution de l'écran peut avoir un impact important sur la fréquence d'images, en particulier avec les émulateurs gourmands en CPU \(N64, PSX et autres\).
{.is-info}

La majeure partie de ce guide se concentrera sur la sortie HDMI et exposera aussi souvent que possible les 3 cas : HDMI pur, HDMI vers DVI, HDMI vers VGA.

## Quels sont les modes vidéo possibles ?

Tout d'abord, comprendre les bases de la résolution d'écran : un nombre de pixels en largeur par un nombre de pixels en hauteur à \(@\) un taux de rafraîchissement donné en Hertz.

Par exemple : 1280x1024@60 qui est une résolution d'écran courante de 4x3 pour moniteurs 19".

De nos jours, les téléviseurs affichent tous du Full HD à 1080p par exemple, comme 1920x1080@60. Nous n'allons pas passer par les modes entrelacé ou progressif, c'est hors sujet.  
Veuillez vous référer au manuel du fabricant de votre écran pour connaître sa résolution native.

Il existe deux groupes de modes vidéo : CEA et DMT. Tous ces modes sont répertoriés [ici](http://elinux.org/RPiconfig) ou [ici](https://www.raspberrypi.org/documentation/configuration/config-txt/README.md).  
Assurez-vous que le mode est compatible avec votre résolution d'écran native.  
Une simple règle de base : CEA est le mode TV, DMT est pour tous les autres modes.

### Les modes les plus courants

* DMT 4 : 640x480@60
* DMT 9 : 800x600@60
* DMT 16 : 1024x768@60
* DMT 35 : 1280x1024@60
* DMT 57 : 1680x1050@60
* 720p : CEA 4
* 1080p : CEA 16

Dans ce tutoriel, nous allons couvrir 3 cas :

* Une télévision 1080p normale. Appelons-la 1080pTV
* un moniteur VGA 720p connecté avec le HDMI vers VGA. Surnom : 720pVGA
* un bon vieux DVI 17" capable d'afficher du 1280x1024@60. Nommez le disons ... DVIboy.

N'oubliez pas de consulter le tutoriel pour les écrans DVI [ici](/v/francais/tutoriels/video/lcd/connectez-votre-recalbox-a-un-ecran-dvi).

Avec ce que vous savez déjà sur les modes d'écran, ces réglages sont les plus courants :

* 1080pTV correspond à CEA 16
* 720pVGA correspond à CEA 4
* DVIboy correspond à DMT 35

## Votre système démarre

Au démarrage, le Pi demandera à votre moniteur sa résolution d'écran préférée.  
Votre moniteur envoie son _EDID \(Extended Display Identification Data\)_ et le Raspberry sélectionne la résolution d'écran notée comme "préférée".

C'est là que le tout premier problème se produit :

* la plupart - sinon la totalité - des écrans HDMI natifs \(TV, moniteurs\) devraient envoyer la bonne EDID
* le HDMI vers DVI devrait fonctionner presque aussi bien
* Les adaptateurs HDMI vers VGA peuvent être un peu délicats et fournir un EDID inexact ...

Maintenant que vous en savez un peu plus sur ce qui peut arriver, voici quelques exemples :

* Le 1080pTV est un bon garçon et aura tout de suite son 1080p natal,
* Le 720pVGA a un HDMI vers VGA merdique qui correspond au "DMT 16" comme mode préféré,
* Le DVIboy règle son DMT 35 de manière irréprochable.

Comme l'écran détecté au démarrage est celui qui affiche EmulationStation avec sa résolution préférée, le 720pVGA aura un affichage affreux.

Heureusement, cela peut être corrigé en éditant le fichier `/boot/config.txt`.

Voici les lignes que vous devez éditer :

```text
#hdmi_group=1
#hdmi_mode=1
```

* **hdmi\_group** : 1 pour CEA, 2 pour DMT
* **hdmi\_mode** : se référer aux lignes ci-dessus

Donc pour notre 720pVGA, voici comment nous éditons `/boot/config.txt` :

```text
hdmi_group=1
hdmi_mode=4
```


>**Prenez note :**
>
>* Le signe "\#" est supprimé, le terme technique pour cela est "non commenté". Une ligne commençant par un \# est un commentaire, et non une commande :
>  * hdmi\_group=1 signifie CEA
>  * hdmi\_mode=4 signifie 720p
{.is-info}

Maintenant que nous avons terminé, nos 3 écrans sont réglés.  
Continuons à avancer !

## Mode vidéo global pour les émulateurs

Maintenant qu'EmulationStation fonctionne en plein écran, votre main est impatiente de tester un jeu ...  
La principale chose que vous devez savoir ici, c'est que la résolution de l'écran est modifiée avant de lancer un émulateur.

Mais vers quelle résolution ?

* Vérifiez votre **recalbox.conf**
* Lisez le paramètre `global.videomode`. Sa valeur par défaut est `CEA 4 HDMI`. Cela signifie que la résolution de l'écran sera changée en 720p juste avant de lancer l'émulateur.

Il est temps de vérifier quelques exemples :

* 1080pTV peut afficher du 720p sans problème
* 720pVGA peut afficher le 720p sans une égratignure
* DVIboy est ... mmh ... hé bien, il ne peut pas afficher du 720p.
  * Il suffit donc d'éditer **recalbox.conf**
  * Puis de régler `global.videomode` sur son mode vidéo natif : `global.videomode=DMT 35 HDMI`


>**Conseil :**
>
>Vous vous sentez chanceux, vous voulez vous épargner un changement de résolution d'écran ? Alors, réglez `global.videomode=default`, Recalbox ne changera pas la résolution de l'écran avant de lancer un émulateur.
>
>Mais attention : cela peut avoir un impact considérable sur les performances.  
>Étendre une image de la résolution native de l'émulateur vers le 1080p peut être très exigeant pour le CPU et ralentir l'émulation. Je ne recommande pas le réglage par défaut si votre moniteur peut afficher une résolution supérieure à CEA 4.
{.is-info}

## Mode vidéo par émulateur

Enfin, le mode vidéo peut être réglé tout spécialement pour l'émulateur de votre choix.

Par exemple, si vous lisez le fichier `recalbox.conf`, vous remarquerez que `n64.videomode=DMT 4 HDMI`signifie que nous remplaçons le fichier **global.videomode** pour l'émulation **N64**.

J'espère que ce guide vous a aidé à comprendre comment la résolution d'écran est gérée sur Pi et Recalbox.  
N'hésitez pas à poser vos questions sur le forum ou sur Discord.

## Conseils pratiques

### tvservice

Le **tvservice** est un excellent outil pour diagnostiquer votre sortie :

```text
# tvservice --help
Utilisation : tvservice [OPTIONS]...
  -p, --preferred                   Allumer le HDMI avec les paramètres préférés
  -e, --explicit="GROUP MODE DRIVE" Mise en route de l'HDMI avec GROUPE explicite (CEA, DMT, CEA_3D_SBS, CEA_3D_TB, CEA_3D_FP, CEA_3D_FS)
                                      MODE (voir --modes) et DRIVE (HDMI, DVI)
  -t, --ntsc                        Utiliser la fréquence NTSC pour le mode HDMI (par exemple 59,94Hz au lieu de 60Hz)
  -c, --sdtvon="MODE ASPECT"        Mise en route de la SDTV avec MODE (PAL ou NTSC) et ASPECT (4:3, 14:9 ou 16:9)
  -o, --off                         Éteindre l'écran
  -m, --modes=GROUP                 Obtenir les modes GROUPE supportés (CEA, DMT)
  -M, --monitor                     Suivre les événements HDMI
  -s, --status                      Obtenir le statut HDMI
  -a, --audio                       Obtenir des informations sur le support audio
  -d, --dumpedid <filename>         Vider les informations EDID dans le fichier
  -j, --json                        Utiliser le format JSON pour les modes de sortie
  -n, --name                        Afficher l'ID de l'appareil à partir de l'EDID
  -h, --help                        Afficher cette information
```

Les commutateurs les plus couramment utilisés :

*  `tvservice -s` permet d'obtenir les informations d'affichage actuelles.
*  `tvservice -m CEA` ou `tvservice -m DMT` : liste des modes CEA ou DMT supportés.

Cette outil n'est disponible que sur les Raspberry Pi.

