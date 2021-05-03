---
title: Configurez votre petit écran TFT sur le bus DPI
---

# Configurez votre petit écran TFT sur le bus DPI

## Configurez votre petit écran TFT sur DPI <a id="configure-your-small-tft-screen-on-dpi"></a>

### DPI \(INTERFACE D'AFFICHAGE PARALLÈLE\)

Source : [https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md](https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md)

Une interface RGB parallèle jusqu'à 24 bits est disponible sur toutes les cartes Raspberry Pi avec l'en-tête à 40 voies \(A+, B+, Pi2, Pi3, Zero\) et le module de calcul. Cette interface permet de connecter des écrans RGB parallèles au GPIO Raspberry Pi soit en RGB24 \(8 bits pour le rouge, le vert et le bleu\) ou RGB666 \(6 bits par couleur\) ou RGB565 \(5 bits rouge, 6 vert et 5 bleu\).

Cette interface est contrôlée par le micrologiciel GPU et peut être programmée par un utilisateur via des paramètres config.txt spéciaux et en activant la bonne superposition de l'arbre de périphériques Linux.

En envoyant les données via cette interface parallèle, vous n'avez aucun problème avec la bande passante du bus et la vitesse d'affichage \(FPS\). Mais il utilise presque toutes les broches GPIO.

Ce mode est très utile, vous pouvez régler très finement vos paramètres d'affichage : timings, résolutions, etc.

Ce mode s'accompagne de nouveaux overlays, qui permettent de produire un signal RGB grâce au VGA666 \(Obtenez l'adaptateur VGA passif 666 pour Raspberry-Pi B+ : [code](https://github.com/fenlogic/vga666) et [matériel](https://www.banggood.com/VGA-666-Adapter-Board-For-Raspberry-Pi-3-Model-B-2B-B-A-p-1071309.html)\).

```text
dtoverlay=vga666
```

Vous pourrez utiliser l'écran TFT [5"](https://www.adafruit.com/product/1596) ou [7"](https://www.adafruit.com/product/2354) d'Adafruit grâce au [panneau TFT Kippah DPI d'Adafruit pour Raspberry Pi avec support tactile](https://www.adafruit.com/product/2453).

```text
dtoverlay=dpi24
```

Alors connectez-vous à Recalbox via [ssh](/fr/tutoriels/systeme/acces/acces-root-via-terminal) et remonter la partition en lecture-écriture :

 `mount -o remount, rw /boot`


>**IMPORTANT :**
>
>Si vous utilisez la version 4.0.x, le fichier `dpi24.dtbo` est présent et se trouve dans le répertoire `/boot/overlays`. Vous devez le renommer `dpi24.dtb` pour que l'écran fonctionne. Sur Recalbox 4.1, rien à faire.
{.is-warning}

Allez dans le répertoire `/boot/overlays` et renommez le fichier dtbo pour Recalbox 4.0.x

```text
cd /boot/overlays
mv dpi24.dtbo dpi24.dtb
```

Vous pouvez maintenant utiliser la directive

```text
dtoverlay=dpi24
```

### Écran TFT Geekwrom HD 3,5 pouces 800x480 pour le Raspberry Pi 3B 2B

Cet écran est de petite taille et offre une résolution de 800x480. Ses spécifications sont assez bonnes :

![hd-tftScreen.png](https://camo.githubusercontent.com/8680157a6e810c62eae94925088b302873fdaff7/687474703a2f2f696d616765732e6d6f726572652e65752f68642d74667453637265656e2e706e67)

J'ai trouvé cet écran étonnant sur [ce site chinois](https://www.banggood.com/Geekwrom-HD-3_5-Inch-TFT-Display-Shield-800x480-For-Raspberry-Pi-3B-2B-With-2-Keys-And-Remote-IR-p-1069730.html) pour un prix inférieur à 50€.

Il peut être utilisé tel quel, sans le programme fbcp. Fbcp n'est pas plus nécessaire car le mode DPI utilise directement le GPU.

Pour obtenir le support de cet écran, il suffit d'ajouter les lignes suivantes à votre **/boot/config.txt**.

Vous devez maintenant utiliser une [connexion SSH](/fr/tutoriels/systeme/acces/acces-root-via-terminal) vers votre Raspebrry Pi pour effectuer/vérifier les étapes suivantes.

Passez le système de fichiers en mode Lecture-Ecriture pour pouvoir effectuer les modifications :

```text
mount -o remount, rw /boot
mount -o remount, rw /
```

Editez le fichier **/boot/config.txt** avec nano ou vim et ajoutez :

```text
#3.5 HD tft screen 800x480
dtoverlay=dpi24
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0

​#Banggood
framebuffer_width=800
framebuffer_height=480
dtparam=spi=off
dtparam=i2c_arm=off

enable_dpi_lcd=1
display_default_lcd=1
dpi_output_format=0x6f015
dpi_group=2
dpi_mode=87
hdmi_timings=480 0 16 16 24 800 0 4 2 2 0 0 0 60 0 32000000 6
display_rotate=3
```

Sauvegardez le fichier et redémarrez Recalbox... cela devrait suffire, vous pouvez maintenant visionner les incroyables images affichées sur cet écran.

![&#xC9;cran TFT Geekwrom HD 3,5 pouces 800x480](https://camo.githubusercontent.com/e139870fc5e1e6ae285d64e46e6a00f9823f4071/687474703a2f2f696d672e796f75747562652e636f6d2f76692f714b6449744e737059564d2f302e6a7067)

### Écran TFT 5" et 7" d'Adafruit

Pour utiliser ces écrans de [5"](https://www.adafruit.com/product/1596) et [7"](https://www.adafruit.com/product/2353), vous aurez besoin du [panneau TFT Kippah DPI d'Adafruit pour Raspberry Pi avec support tactile](https://www.adafruit.com/product/2453) pour les faire fonctionner.

Ils utilisent également le mode DPI. La configuration du fichier config.txt est la suivante :

```text
#3.5 HD tft screen 800x480
dtoverlay=dpi24
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0

#Adafruit
framebuffer_width=800
framebuffer_height=480
dtparam=spi=off
dtparam=i2c_arm=off

enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
dpi_output_format=0x6f005
hdmi_timings=800 0 40 48 88 480 0 13 3 32 0 0 0 60 0 32000000 6
display_rotate=3
```

### Ecran 4.0" HyperPixel

Merci glook pour ce tuto : [https://forum.recalbox.com/topic/17854/ecran-hyperpixel-4-pouces/4](https://forum.recalbox.com/topic/17854/ecran-hyperpixel-4-pouces/4)

Cet écran est disponible [ici](https://shop.pimoroni.com/products/hyperpixel-4?variant=12569539706963) avec ou sans écran tactile.

Commencez par lire le Github [ici](https://github.com/pimoroni/hyperpixel4) **\[anglais\]**. Vous aurez besoin de :

* compiler hyperpixel4.dts en hyperpixel4.dtbo ou le trouver sur le web :`dtc -@ -I dts –O dtb –o hyperpixel4.dtbo hyperpixel4.dts`
* copier hyperpixel4.dtbo dans **/boot/overlays/**
* ajouter la configuration au fichier config.txt :

```text
# Paramètres de l'écran LCD HyperPixel
dtoverlay=hyperpixel4
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0
framebuffer_width=800
framebuffer_height=480
enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
dpi_output_format=0x7f216
display_rotate=3
hdmi_timings=480 0 10 16 59 800 0 15 113 15 0 0 0 60 0 32000000 6
```

Assurez-vous que l'i2c et le spi sont désactivés :

```text
dtparam=i2c_arm=off
dtparam=spi=off
```

Monter la partition : `mount -o remount,rw /`

* copier hyperpixel4-init situé dans le répertoire _/dist_ vers _/usr/bin/_ sur Recalbox
* enfin, assurez-vous d'exécuter ce programme au démarrage dans Recalbox, en ajoutant `hyperpixel4-init` en ligne de commande dans l'un des scripts d'init du fichier **/etc/init.d**

