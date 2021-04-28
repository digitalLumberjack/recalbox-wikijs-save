---
title: Activer le bouton GPIO pour fermer l'émulateur en appuyant sur un seul bouton
---

# Activer le bouton GPIO pour fermer l'émulateur en appuyant sur un seul bouton

Ce script python pour Raspberry Pi permet d'utiliser un bouton pour fermer l'émulateur en appuyant sur un seul bouton GPIO. Il est compatible avec toute autre fonction ou tout autre script précédemment affecté aux boutons.

Le bouton sélectionné par défaut est le Player ONE Start ; il peut être changé lors de l'installation par n'importe quel autre car il ne supprime aucune fonction précédente.  
L'émulateur se ferme après avoir maintenu le bouton enfoncé pendant au moins 0,5 sec. Le délai d'activation du bouton peut également être modifié.

## Requis

* Une Recalbox sur Raspberry Pi qui utilise les commandes GPIO \(il n'est pas nécessaire d'avoir un bouton libre\).
* Le Raspberry Pi doit avoir un accès à Internet :
  * Vous pouvez activer et configurer le **wifi** et le **nom d'hôte**, obtenir l**'IP** de la Recalbox, le SSID de votre réseau et la clé du réseau avec un clavier. Une fois que vous avez validé, le wifi est activé. Il existe un bug connu qui ne vous permet pas de saisir tous les caractères nécessaires pour le SSID ou la Clé. Vous pouvez le configurer directement depuis votre wifi en utilisant [recalbox.conf](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf).
* Un ordinateur à partir duquel on peut faire une [session root SSH](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal) sur Raspberry \(sur Windows, vous aurez besoin d'un programme comme PuTTY\).

## Installation

* Ouvrez une session SSH depuis votre ordinateur vers le Raspberry.
* Une fois connecté, copiez et collez cette commande dans la session ssh :

`wget --quiet --show-progress -O /recalbox/share/system/exit-emu-1b https://gist.githubusercontent.com/DjLeChuck/446cd415575f03c927627e378979027d/raw/9ebe3a5e178ff047b536220afd513981095fb41d/exit-emu-1b-installer && chmod 755 /recalbox/share/system/exit-emu-1b && /recalbox/share/system/exit-emu-1b install`

L'installateur affichera une liste des cartographies de ports GPIO possibles correspondant à la cartographie GPIO pour Recalbox, correspondant à l'image suivante :

![Cartographie des ports GPIO](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M1pg9d9WjOYChpb5hus%2F-M1pzARovpy60-nqM0ZG%2FgaU6t.png?alt=media&token=89aed639-da21-4c6c-afe6-590fe47e423e)

Après avoir sélectionné le port du bouton auquel vous souhaitez que le script soit affecté, l'installateur vous demandera le délai pour quitter l'émulateur, vous devez taper le délai souhaité en secondes.  
**\(Il est important de répondre aux deux questions, sinon l'installateur échouera\)**.

Après quelques secondes, si le résultat est un message à l'écran disant "**Bouton de démarrage**", alors tout s'est déroulé correctement et nous avons maintenant le script du bouton installé et fonctionnel.

## Fichiers installés

* [/recalbox/scripts/rpi-exit-emu-1b.py](https://gist.github.com/DjLeChuck/445ce3d37f41f12d5bf8cb9482db4027)
* [/etc/init.d/S98exit-emu-1b](https://gist.github.com/DjLeChuck/5f798b0d4af4071a92111bf61703aeb1)
* [/recalbox/share/system/exit-emu-1b](https://gist.github.com/DjLeChuck/446cd415575f03c927627e378979027d)

## Désinstallation

* Ouvrir une [session SSH](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal) et tapez la commande `/recalbox/share/system/exit-emu-1b uninstall`


>**Avertissement :**
>
>Dans la configuration par défaut de RetroArch, le script ferme les émulateurs par force brute en utilisant une commande _**killall**_ qui, selon le noyau utilisé, pourrait causer la perte de certains changements de configuration d'émulateur effectués pendant le jeu.  
>Par exemple, cela se produit avec Mame2003.
>
>Pour éviter cela, j'ai implémenté la fermeture de l'émulateur via une commande réseau pour RetroArch. Maintenant, RetroArch se fermera correctement et vous ne perdrez pas les changements de configuration dans les émulateurs.
{.is-danger}


>**Note :**
>
>Ce changement ne concerne que RetroArch, bien que cela couvre la plupart des émulateurs du système, les émulateurs comme **Fb2x, Scummvm** ou **mupen64plus** sont toujours fermés par force brute, jusqu'à ce que je trouve un autre moyen de l'appliquer.
{.is-info}

## Trucs et astuces

* Si, à tout moment, vous devez assigner la fonction de fermeture de l'émulateur à un autre bouton, il vous suffit de relancer l'installateur par la commande `/recalbox/share/system/exit-emu-1b install` et de mettre dans l'installation le nouveau numéro de port que vous souhaitez.
* Si vous modifiez la configuration de votre émulateur et que vous quittez avec le bouton assigné dans l'installation, ceux-ci sont perdus. Assurez-vous qu'ils soient dans le fichier :`/recalbox/share/system/configs/retroarch/retroarchcustom.cfg` Ou dans le fichier de configuration personnalisé RetroArch où vous utilisez le paramètre `Network_cmd_enable` a la valeur`= "true"`.
* Si, pour une raison quelconque, le script cesse de fonctionner et que le bouton perd sa fonction de fermeture de l'émulateur, vous pouvez récupérer son fonctionnement au moyen de la commande :  `/etc/init.d/S98exit-emu-1b restart` vous devrez le saisir à l'intérieur d'une [session SSH](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal)

