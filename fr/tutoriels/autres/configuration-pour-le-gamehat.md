---
title: Configuration pour le GameHat
---

# Configuration pour le GameHat


>**Information :**
>
>Le guide d'installation officiel du GameHat pour Recalbox est **uniquement** pour les versions de Recalbox antérieures à la 6.x.  
>Ce mode d'emploi reflète les instructions à jour pour la version 6.0 de Recalbox !
{.is-info}

## Configuration

Pour tous ceux qui veulent utiliser Recalbox 6.0 avec le GameHat, voici comment faire :

* Flashez l'image de Recalbox 6.0 sur votre carte-SD.
* Depuis un PC/Mac :
  * Branchez la carte-SD
  * Ajoutez ces paramètres au fichier "_config.txt_" à la racine de la carte :
    * **hdmi\_force\_hotplug=1**
    * **avoid\_warnings=1**
    * **max\_usb\_current=1**
    * **hdmi\_group=2**
    * **hdmi\_mode=1**
    * **hdmi\_mode=87**
    * **hdmi\_cvt 640 480 60 6 0 0 0**
    * **hdmi\_drive=2**
    * **display\_rotate=0**
* Connectez une manette de jeu \(filaire\) et renseignez les paramètres wifi.
* Lorsque vous êtes connecté sur votre réseau, via l'interface web \(ou SSH\)
  * Éditez le fichier  "_recalbox.conf_" comme ceci :
    * Changez la commande **controllers.gpio.enabled=0** en : **controllers.gpio.enabled=1**
    * Changez la commande **controllers.gpio.args=map=1,2** en : **controllers.gpio.args=map=5 gpio=5,6,13,19,21,4,26,12,23,20,16,18,-1**
* Débranchez la manette et redémarrez la Recalbox.
* Après le redémarrage, appuyez sur un bouton et configurez !

## Lien extérieur

* **Lien vers le Wiki du GameHat :** [https://www.waveshare.com/wiki/Game\_HAT](https://www.waveshare.com/wiki/Game_HAT) \(Anglais\)

