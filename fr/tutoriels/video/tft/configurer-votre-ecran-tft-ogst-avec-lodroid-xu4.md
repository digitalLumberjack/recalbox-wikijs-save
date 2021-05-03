---
title: Configurer votre écran TFT OGST avec l'Odroid XU4
---

# Configurer votre écran TFT OGST avec l'Odroid XU4

Cette méthode d'intégration ne vous sera utile que sur les versions avant Recalbox 7.0.0. Un grand merci à [littlebalup](https://forum.recalbox.com/uid/32680) pour son travail.

## Qu'est-ce qu'un écran TFT OGST

{% embed url="https://www.hardkernel.com/shop/ogst-gaming-console-kit-for-xu4/" %}

## La partie suivante est obsolète, le support OGST est désormais natif dans Recalbox.

Voir [/tutorials/video/tft/second-minitft-for-scrapes-and-videos-ogst-case-raspeberry-pi-1-2-3-spi-dpi-small-tft-screens](/tutorials/video/tft/second-minitft-for-scrapes-and-videos-ogst-case-raspeberry-pi-1-2-3-spi-dpi-small-tft-screens)d \(lien pas encore éditer\)

## Installation

Prérequis :

* Un ODROID XU4\(Q\) avec le kit OGST console de jeu.
* Recalbox installé \(testé sur la version stable 18.07.13, 2018 christmas beta, v6 0 et v6.1\).
* Recalbox connecté à Internet.

Le déroulé du script d'installation sera le suivant :

* Téléchargez le paquet.
* Installez le script `/recalbox/share/system/custom.sh`
* Extrayez le pack de logos vers `/recalbox/share/system/tft_logos`.
* Remplacez le binaire `/usr/bin/ffmpeg` par un nouveau. \( l'existant est trop vieux et buggé pour les opérations en boucle vidéo...\).
* Modifier et recompiler `/usr/lib/python2.7/site-packages/configgen/emulatorlauncher.py`
* Redémarrez le système.

Procédure d'installation :

* Obtenir un [accès root sur le terminal](/fr/tutoriels/systeme/acces/acces-root-via-terminal)
* Faites un copier/coller sur votre terminal et exécutez la ligne de commande suivante pour la **Recalbox 2018** :

```text
wget https://www.dropbox.com/s/jp85fh6j4lkoz8m/install.sh && chmod +x install.sh && ./install.sh
```

* Faites un copier/coller sur votre terminal et exécutez la ligne de commande suivante pour la

   **Recalbox v6.0** :

```text
wget https://www.dropbox.com/s/1c63n1kakkpylbw/install_6x.sh && chmod +x install_6x.sh && ./install_6x.sh
```

* Faites un copier/coller sur votre terminal et exécutez la ligne de commande suivante pour la

   **Recalbox v6.1** :

```text
curl -sL https://www.dropbox.com/s/9bhrq0bta8aah8o/install_6.1.sh | bash
```

C'est tout. Profitez-en !

Notes:


>Notes :
>
>Après une mise à jour du système Recalbox, il se peut que vous deviez procéder à une réinstallation. Si vous avez fait des modifications \(voir la section "Personnalisation"\), faites une sauvegarde de votre fichier `custom.sh` et de votre dossier **tft\_logos** avant. Puis restaurez-les après l'installation.
>
>Le script `custom.sh` a été mis à jour pour la v6.1. Si vous avez fait un script `custom.sh` personnalisé pour une ancienne version, vous devrez le recréer sur la base du nouveau script "officiel", pour l'utiliser sur la v6.1.
{.is-info}

## Quelques informations sur son fonctionnement

* Au démarrage du système, le script `/recalbox/share/system/custom.sh` est exécuté \(via le script de démarrage `/etc/init.d/S99custom` avec le paramètre de démarrage pour initialiser l'écran TFT et afficher le logo par défaut.
* Lorsqu'un jeu \(ou Kodi\) est lancé, le lanceur d'émulateur modifié `/usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc` exécute le script `custom.sh` avec le nom de l'émulateur lancé en argument, affichant le logo correspondant sur l'écran TFT.
* Le script `custom.sh` continue à s'exécuter silencieusement en arrière-plan le temps que l'émulateur est en cours \(le temps que le processus python / émulatorlauncher existe\), attendant et surveillant l'arrêt du processus.
* Une fois que l'émulateur est arrêté, le script _custom.sh_ affiche à nouveau le logo par défaut.

## Personnalisation

* Tous les logos \(images statiques ou vidéoclip\) sont stockés dans `/recalbox/share/system/tft_logos`.
* Vous pouvez ajouter, modifier, supprimer, etc... les logos comme vous le souhaitez mais vous devrez peut-être modifier le script `/recalbox/share/system/custom.sh` en conséquence pour que certains changements prennent effet \(le chemin des fichiers de logos y est stocké ainsi que le paramètre loop si vous souhaitez mettre un vidéoclip en boucle\). Veillez à conserver l'intégrité de la structure du script.
* Si vous avez malencontreusement corrompu le script `custom.sh`, faites une sauvegarde de votre dossier `tft_logos` si vous avez fait des modifications, refaites la procédure d'installation, puis restaurez votre dossier `tft_logos` le cas échéant.
* Pour être correctement affichées, toutes les images ou clips vidéo des logos doivent être de 320 x 240 pixels \(la résolution de l'écran TFT\).
* Fonctionne avec fichiers \*.mp4, \*.jpg, \*.png et \*.gif. Tous les fichiers supportés par ffmpeg devraient fonctionner. Essayez de voir.

## Contributions

### Quelques tests avec des vidéos d'introduction spécifiques à Recalbox

[Sujet apparenté sur le forum Recalbox \(français\)](https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case)

![Support d&apos;&#xE9;cran Recalbox TFT OGST ](https://camo.githubusercontent.com/023df5dcb580f1748871c3f927635d6c3d97131f/687474703a2f2f696d672e796f75747562652e636f6d2f76692f5a585a5362582d2d3278672f302e6a7067)

[https://youtu.be/ZXZSbX--2xg](https://youtu.be/ZXZSbX--2xg)



### Quelques vidéos au format 320x240

* Téléchargez cette archive, et remplacez la valeur par défaut par celle que vous souhaitez :\) [https://mega.nz/\#!Kp8BkYoD!SAeq9xcDUX4po\_Xmhed\_KypmycQ8iQRS1SZI9vBRb3Q](https://mega.nz/#!Kp8BkYoD!SAeq9xcDUX4po_Xmhed_KypmycQ8iQRS1SZI9vBRb3Q)



### Pack vidéo complet avec tous les systèmes

* Depuis [https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case/97](https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case/97) grâce à @kevinnash Pack vidéo complet avec tous les systèmes : télécharger [https://uptobox.com/gsic8c6h72fq](https://uptobox.com/gsic8c6h72fq)

