---
title: Configuration Recalbox pour Bartop/Borne Arcade
---

# Configuration Recalbox pour Bartop/Borne Arcade

Si vous voulez utiliser un Raspberry Pi avec Recalbox pour créer un "**Bartop**" ou une **borne d'arcade**.  
Vous pouvez facilement configurer Recalbox pour répondre à votre besoin.

## A - GPIO <a id="a-gpio"></a>

Vous pouvez **configurer le pilote GPIO** de la Recalbox dans le fichier [recalbox.conf.](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf)  
Ce pilote **crée deux joysticks sur le système** et directement contrôlés par les **PINS GPIO** du Raspberry Pi.

Pour cela vous n'avez **pas besoin d'un hub USB** car vous **connecterez vos boutons** directement sur les [GPIO](/v/francais/tutoriels/controleurs/gpio/les-controleurs-gpio)

## B - Configuration vidéo <a id="b-configuration-video"></a>

Beaucoup de "bartops" utilisent un **vieil écran LCD** ou des **écrans de télévision CRT** utilisant une des connexions suivante :

* **Ecran VGA** : vous aurez besoin d'un convertisseur HDMI / VGA \(convertisseur actif\) coûtant dans les 10€. Si vous êtes sur un écran 4/3 vous aurez besoin de changer le mode vidéo pour le passer à `global.videomode=default` pour tout vos émulateurs dans le fichier [recalbox.conf](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf). 
* **Ecran DVI** : vous aurez besoin d'un adaptateur HDMI / DVI \(convertisseur passif\). Vous aurez probablement besoin de modifier votre fichier [recalbox.conf ](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf)en vous basant basant sur le [Mini HowTo - Connectez votre recalbox à un écran DVI.](/v/francais/tutoriels/video/lcd/connectez-votre-recalbox-a-un-ecran-dvi)
* **Ecran CRT** : Vous aurez besoin d'une prise jack vers RCA avec un câble vidéo. Vous devez changer le mode vidéo pour le positionner sur `global.videomode=default` pour tous vos jeux dans le fichier [recalbox.conf](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf) et modifier les paramètres décris dans [HowTo - Connectez votre recalbox à un écran CRT en utilisant le composite](/v/francais/tutoriels/video/crt/connectez-votre-recalbox-a-un-crt-avec-composite) 

## C - Configuration audio <a id="c-configuration-audio"></a>

Vous pouvez sélectionner le **périphérique de sortie audio** dans le fichier [recalbox.conf](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf) :

* Utilisez `audio.device=jack` si vous voulez forcer la **sortie audio sur la prise jack.** 
* Utilisez `audio.device=hdmi` si vous voulez forcer la **sortie audio sur le HDMI.**

## D - Configuration du menu

Vous pouvez **désactiver Kodi** dans le fichier [recalbox.conf](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf) _****_en **positionnant le paramètre** suivant `kodi.enable=0`dans le but de **supprimer le raccourci affecté au bouton "X".**  
Cela **supprimera aussi l'entrée Kodi** dans le menu d'**EmulationStation.**

Vous pouvez aussi vouloir **changer les réglages du menu** :

* **Pour ES** :
  * En positionnant `system.es.menu=bartop`, vous aurez **accès à un minimum d'options** quand vous presserez le **bouton "start" sous EmulationStation**. 
  * En positionnant `system.es.menu=none`, **seul le menu de sélection du jeu** \(bouton select\) sera disponible.  
* **Pour les émulateurs** :
  * En positionnant `system.emulators.specialkey` sur `nomenu` vous **désactiverez les menus dans les émulateurs**. 
  * En positionnant `system.emulators.specialkey` sur `none` vous **désactiverez les menus** et toutes les **fonctions spéciales dans les émulateurs.** \(Sauf la combinaison pour sortir d'un jeu bien entendu\).

## En rapport :

[Activer le bouton GPIO pour fermer l'émulateur en appuyant sur un seul bouton](/v/francais/tutoriels/controleurs/gpio/activer-le-bouton-gpio-pour-fermer-lemulateur-en-appuyant-sur-un-seul-bouton)

