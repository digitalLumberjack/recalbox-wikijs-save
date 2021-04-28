---
title: Hyperion sur Recalbox
---

# Hyperion sur Recalbox

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJOZB8uJ0fcgdF-EvJd%2F-MJOZhKdagsWxYakHpGF%2Fimage.png?alt=media&token=ab8fd4a7-0d94-4606-967a-cf03c9d930a3)

## Faites briller votre Recalbox avec Hyperion!

**Hyperion** \([https://github.com/hyperion-project/hyperion](https://github.com/hyperion-project/hyperion)\) est un projet libre et open source pour transformer votre RaspberryPi en système **Ambilight** !

Avec Hyperion et recalbox, vous allez transformer votre système de retrogaming et multimedia system en une magnifique experience immersive !

## I - Description

Tout d’abord, nous ne parlons pas d’utiliser Hyperion avec une partie de votre Recalbox comme **Kodi**.  
Vous serez capable d’utiliser les fonctions d’Hyperion dans **CHACUN DES JEUX RETRO** auquel vous jouez sur Recalbox !

![Hyperion avec recalbox](https://www.recalbox.com/images/blog/2017-11-10-hyperion/pukerainbow.gif)

L’image que vous voyez sur votre TV \(LCD ou CRT\) sera **dynamiquement étendu** sur le mur avec des leds RGB.

A quoi ça ressemble? Regardez avec Sonic 3 sur Sega Megadrive/Genesis

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJOZB8uJ0fcgdF-EvJd%2F-MJOaV7eraR9ljK9sRcC%2Fimage.png?alt=media&token=423b0f17-08ff-407d-ae42-4618d897926c)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJOZB8uJ0fcgdF-EvJd%2F-MJOaioELMcO_qq6VJe4%2Fimage.png?alt=media&token=a37f7b58-defc-43c3-b738-71a045403ef2)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJOZB8uJ0fcgdF-EvJd%2F-MJOaqiWT2nhT1bA634s%2Fimage.png?alt=media&token=81a44bd8-cd89-48e7-a6de-c4fde7b2b6c6)

Et en vidéo:

[https://youtu.be/z1QblkdO6bs](https://youtu.be/z1QblkdO6bs)

## II - Materiel

Hyperion supporte de nombreuses bandes de LED \(voir [https://hyperion-project.org/wiki/Supported-hardware](https://hyperion-project.org/wiki/Supported-hardware)\) avec différents protocoles:

* **SPI**: LPD6803, LPD8806, APA102, WS2812b, and WS2801
* **USB**: AdaLight et SEDU
* **PWM**: WS2812b

Les tests ont été faits sur **WS2812b** avec PWM et SPI. Je n’ai jamais réussi à faire fonctionner PWM correctement, nous allons donc décrire comment faire votre installation recalbox/hyperion avec le mode **WS2812b en SPI**.  
Cette section est absente du wiki Hyperion, nous allons donc expliquer comment l’utiliser ici \(et mettre à jour le wiki Hyperion avec ces informations\).

La prise en charge de **WS2812b** avec un fil sur SPI a été ajoutée par [penfold42](https://github.com/penfold42) avec [ce commit](https://github.com/hyperion-project/hyperion/commit/a960894d140405e29edb413685e700d2f1714212). Merci.

Le tutoriel suivant utilise un fer à souder. Si vous en possedez déjà un, le reste du matériel est plutôt bon marché.  
Mais si vous souhaitez faire quelque chose sans soudure, voir le tutoriel ici : [https://hyperion-project.org/threads/raspberry-pi-3-mediacenter-hyperion-ambilight-no-soldering.77/](https://hyperion-project.org/threads/raspberry-pi-3-mediacenter-hyperion-ambilight-no-soldering.77/)

### Les éléments necessaires

Vous aurez besoin de:

* Votre Recalbox
* Une bande de led WS2812b
* Une resistance de 330 Ohms à mettre sur le pin data
* Quelque chose pour couper la bande
* Un fer à souder
* Des files ou connecteurs pour connecter la bande de leds
* Un level shifter pour passer le voltage de data à 5V , ou un regulateur de tension pour réduire le VCC des leds.
* Des jumpers dupont pour connecter facilement les fils sur le RaspberryPi
* Une alimentation de 4A \(min\) 5v

N’hésitez pas à visiter le [![](https://www.recalbox.com/images/shared/recalstore.png)](https://www.recalbox.com/shop) pour trouver tout ce dont vous avez besoin.

Bien sûr si vous voulez économiser vous pouvez :

* Souder directement \(pas de connecteurs ni dupont\)
* Utilisez une alimentation 3A. J’ai testé ma bande de 220 led hyperion avec une Aukru 5V 3A et ça fonctionnait presque bien, mais quand toutes les leds sont blanches, la fin de la bande est un peu jaune…

## III - Câblage

### **Leds**

Mesurez les bords de votre TV et coupez 1 bande par bord selon cette mesure.

Soudez les bandes ensemble OU soudez des connecteurs sur les bandes. Suivez les flêches sur la bande pour savoir quel connecteur utiliser \(IN ou OUT\).

Voici un aperçu du résultat

![connectors](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJOZB8uJ0fcgdF-EvJd%2F-MJO_M6dQYQjey65OWvS%2Fimage.png?alt=media&token=689f2670-a143-42d5-babf-db3184703769)

![solder](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJOZB8uJ0fcgdF-EvJd%2F-MJO_GnsxTQxVoujLjIu%2Fimage.png?alt=media&token=82ca351e-5d60-4f8d-ac96-baf731bf729a)

### **Le système**

Pour autoriser le Rpi à envoyer des données aux LEDs, vous avez le choix:

* Baisser le voltage LED à 4.7V avec un convertisseur
* Redresser le signal du GPIO à 5V

#### **A - Régulateur de tension**

![Circuit voltage regulator](https://www.recalbox.com/images/blog/2017-11-10-hyperion/wiring-regulator.png)

\(image originale du [wiki hyperion](https://hyperion-project.org/wiki/3-Wire-PWM)\)

Si vous êtes sur RPI2 ou 3, vous avez plus de GPIO mais le placement reste le même.

Le RPi est connecté sur sa propre alimentation et sur la masse de l’alimentation des LEDs.

Le RPi envoie les données à travers le SPI MOSI GPIO vers le câble données des LEDs.

Le régulateur est connecté entre les LEDs et leur alimentation.

#### **B - Level shifter \(non testé\)**

Si vous choisissez de réguler le voltage des GPIO, utilisez le schéma au dessus, enlevez le régulateur et connectez le level shifter entre le GPIO MOSI et le câble données des LEDs.

## IV - Configuration

**Hypercon** est une interface graphique qui vous permet de configurer votre installation Hyperion et créer le fichier de configuration a placer sur la Recalbox.

### Téléchargement et démarrage

* Téléchargez et démarrez **Hypercon** en suivant le tutoriel officiel: [https://hyperion-project.org/wiki/HyperCon-Information](https://hyperion-project.org/wiki/HyperCon-Information)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJOZB8uJ0fcgdF-EvJd%2F-MJO_1HkQUXpWc1uWUwn%2Fimage.png?alt=media&token=7c07bd76-2497-45fd-b8f1-399a1fd4c403)

Vous trouverez de nombreuses ressources sur la configuration d’Hypercon sur le wiki Hyperion: [https://hyperion-project.org/wiki/HyperCon-Guide](https://hyperion-project.org/wiki/HyperCon-Guide)

### Configuration pour Recalbox

Voici comment configurer Hypercon pour votre Recalbox et le **WS2812b en mode spi**:

* **Hardware**
  * Type -&gt; WS281X-SPI
  * RGB Byte Order -&gt; GRB
  * Construction and Image Process -&gt; configure depending of your installation
  * Blackborder Detection -&gt; Enabled
    * Threshold -&gt; 5
    * mode -&gt; osd
* **Process**
  * _Smoothing_
    * Enabled -&gt; True
    * Time -&gt; 200ms
    * Update Freq -&gt; 20
    * Update Delay -&gt; 0
* **Grabber**
  * _Internal Frame Grabber_
    * Enabled -&gt; True
    * Width -&gt; 64
    * Height -&gt; 64
    * Interval -&gt; 200
    * Priority Channel -&gt; 890
  * _GrabberV4L2_
    * Enabled -&gt; False
* External
  * Booteffect / Static Color -&gt; configure the boot effect you like here!



* Cliquez ensuite sur le bouton **Create Hyperion Configuration**
  * Sauvegardez le fichier json en `hyperion.config.json`.
* Copiez ce fichier sur votre recalbox dans
  * En ssh :  `/recalbox/share/system/config/hyperion/hyperion.config.json` 
  * Depuis le réseau : `config/hyperion/hyperion.config.json`

\*\*\*\*

#### **Activer le service Hyperion dans recalbox.conf**

* Activez simplement Hyperion dans recalbox.conf \(voir [le wiki](https://github.com/recalbox/recalbox-os/wiki/recalbox.conf-%28EN%29)\):
  * Changez la ligne `hyperion.enabled=0` en `hyperion.enabled=1`
* Modifiez le fichier config.txt sur la partition boot et ajoutez la ligne `dtparam=spi=on`:

```text
mount -o remount,rw /boot && echo 'dtparam=spi=on' >> /boot/config.txt
```

* Redémarrez la Recalbox.

## V - Profitez de l’arc en ciel

Vous avez un système ambilight totalement fonctionnel!  
Testez des jeux retro, des films et animes avec Kodi et laissez la beauté des couleurs améliorer votre expérience multimédia!

![](https://www.recalbox.com/images/blog/2017-11-10-hyperion/nyan.jpg)



