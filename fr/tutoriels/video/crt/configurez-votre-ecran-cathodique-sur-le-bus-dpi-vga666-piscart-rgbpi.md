---
title: Configurez votre écran cathodique sur le bus DPI \(VGA666/PiScart/RGBPi\)
---

# Configurez votre écran cathodique sur le bus DPI \(VGA666/PiScart/RGBPi\)

## Qu'est-ce que le bus DPI ?

La description complète peut être consultée [ici](https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md).

Une interface RGB parallèle jusqu'à 24 bits est disponible sur toutes les cartes Raspberry Pi avec l'en-tête 40 voies \(A+, B+, Pi2, Pi3, Zero\) et le "Compute Module". Cette interface permet de connecter des écrans RGB parallèles au GPIO du Raspberry Pi, soit en RGB24 \(8 bits pour le rouge, le vert et le bleu\), soit en RGB666 \(6 bits par couleur\), soit en RGB565 \(5 bits pour le rouge, 6 pour le vert et 5 pour le bleu\).

Cette interface est contrôlée par le micrologiciel GPU et peut être programmée par un utilisateur via des paramètres config.txt spéciaux et en activant la bonne superposition de l'arbre de périphériques Linux.

Notez qu'il existe différentes façons de représenter les valeurs des couleurs sur les broches de sortie DPI en mode 565, 666 ou 24 bits \(voir le tableau suivant et la partie `output_format` du paramètre `dpi_output_format` ci-dessous\) :

![GPIOs utilis&#xE9;s selon le mode utilis&#xE9;](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lzvgq0Nce-kRqnZQ42V%2F-LzviJlKzqqcI4x_96cQ%2Fimage.png?alt=media&token=0386d23a-0aad-4a2c-904a-24e5f4e4cf31)

Notez que tous les autres dispositifs de superposition périphérique qui utilisent des broches GPIO conflictuelles doivent être désactivés. Dans le fichier config.txt, veillez à commenter ou à inverser tout paramètre dtp qui active I2C ou SPI :

```text
dtparam=i2c_arm=off
dtparam=spi=off
```

## Le Gert VGA666

Le Gert VGA 666 \(6 bits par canal de couleur, donc 666\) est une carte d'extension/additionnelle pour le modèle B+ de Raspberry Pi \(ne fonctionnera pas avec le modèle A/B car les broches GPIO supplémentaires du modèle B+ sont nécessaires\). Il s'agit d'une création matérielle open source récemment rendue publique par Gert van Loo, l'un des ingénieurs du matériel qui a contribué à la conception initiale du Raspberry Pi original \(également l'un des architectes de la puce BCM2835 au cœur du Raspberry Pi\) et quelqu'un à qui beaucoup d'entre vous ont peut-être parlé lors de Raspberry Jams ou sur les forums du Raspberry Pi.

C'est une méthode propre et très utile pour utiliser un écran/moniteur VGA avec votre Raspberry Pi et elle est bien moins chère qu'un adaptateur HDMI vers VGA ou similaire. La connexion VGA est pilotée nativement dans le matériel par les broches GPIO \(en utilisant une interface parallèle\) et utilise à peu près la même charge CPU que la connexion HDMI à bord. Elle est capable d'afficher des vidéos VGA 1080p60 sans charge CPU.

Il est également possible de piloter cette interface en même temps que la connexion HDMI, de sorte qu'une configuration à double écran est également possible. Cet add-on n'était pas possible sur les modèles A et B des Raspberry Pi, car toutes les broches nécessaires n'avaient pas été placées dans l'en-tête GPIO. Encore une autre amélioration géniale que le modèle B+ a permis de réaliser !

![Le module Gert VGA666](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-Kg3CVViTFwXRr4XFa%2F-M-KgH6dbc0ROi2A3I_1%2FgertVGA666.png?alt=media&token=5be3b72b-18e9-4bde-a478-58b5cd229fd4)

Nous devons d'abord éditer le fichier `/boot/config.txt` . Nous devons remonter la partition en mode lecture-écriture :

`mount -o remount, rw /boot`

Utilisez nano pour éditer le fichier situé à /boot/config.txt  
Commande : `nano /boot/config.txt`

Notez que pour que le Gert VGA 666 fonctionne correctement, vous devez désactiver SPI et I2C. Ajoutez alors ces lignes au bas du fichier

```text
dtparam=spi=off
dtparam=i2c_arm=off
dtoverlay=vga666 
enable_dpi_lcd=1 
display_default_lcd=1 
```

Vous devez également spécifier la résolution de votre écran \(et pas celle d'une télévision\). Après les lignes que vous avez ajoutées ci-dessus, vous devrez également ajouter l'une des configurations suivantes :

```text
#For 1920x1080 60Hz
dpi_group=2
dpi_mode=82
#For 1280x1024 60Hz
dpi_group=2
dpi_mode=35
#For 1024x768 60Hz
dpi_group=2
dpi_mode=16
#For 800x600 60Hz
dpi_group=2
dpi_mode=9
```

![VGA666 sur un &#xE9;cran de PC](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-L1fSbaZId_VZnWiJs%2F-M-L1pOs7optiSxRpJ30%2FDSC_1528.JPG?alt=media&token=c5cb8532-b833-427a-953d-2d1558e5a929)

Si la résolution que vous recherchez n'est pas parmi celles-ci, vous pouvez consulter [ce lien](https://www.raspberrypi.org/documentation/configuration/config-txt/video.md).

Pour les écrans de télévision, la configuration sera différente. Nous devons utiliser le dpi\_mode 87 personnalisé et nous devons corriger la partie hdmi\_timings pour configurer le mode personnalisé 15KHz. Ce mode personnalisé sera appliqué à l'interface d'EmulationStation. Plusieurs hdmi\_timings différents peuvent être utilisés.

```text
dtparam=i2c_arm=off
dtparam=spi=off
 
# Enable VGA666
dtoverlay=vga666
enable_dpi_lcd=1
display_default_lcd=1
 
dpi_group=2
dpi_mode=87
 
#hdmi_timings=506 1 8 48 56 240 1 3 10 6 0 0 0 60 0 9600000 1
#hdmi_timings=512 1 16 48 64 288 1 3 5 6 0 0 0 50 0 9600000 1
 
# Custom 15kHz mode
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
#hdmi_timings=320 1 17 33 34 224 1 14 8 18 0 0 0 60 0 6400000 1
#hdmi_timings=960 0 173 8 0 160 0 40 10 0 0 0 0 60 0 19200000 8
#hdmi_timings=320 1 25 30 30 240 1 9 3 10 0 0 0 60 0 6400000 1
#hdmi_timings=1920 1 52 208 260 240 1 6 10 6 0 0 0 60 0 38400000 1
```

Plusieurs hdmi\_timings différents peuvent être utilisés. Voici une liste de timings utilisables testés par **ironic**, cela vous permettra de gagner du temps pour votre configuration.

```text
OK
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=336 1 10 30 34 252 1 15 3 42 0 0 0 50 0 6400000 1 #with borders
hdmi_timings 480 1 29 35 66 234 1 4 10 18 0 0 0 60 0 9600000 1
hdmi_timings=990 1 22 94 116 240 1 6 10 6 0 0 0 60 0 19200000 1
hdmi_timings=820 1 42 260 100 240 1 6 10 6 0 0 0 60 0 19200000 1
Perfect
hdmi_timings=320 1 12 32 44 240 1 6 10 6 0 0 0 60 0 6400000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=1920 1 52 208 260 240 1 6 10 6 0 0 0 60 0 38400000 1
hdmi_timings=512 1 16 48 64 288 1 3 5 6 0 0 0 50 0 9600000 1
OK
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=336 1 10 30 34 252 1 15 3 42 0 0 0 50 0 6400000 1 #with borders
hdmi_timings 480 1 29 35 66 234 1 4 10 18 0 0 0 60 0 9600000 1
hdmi_timings=990 1 22 94 116 240 1 6 10 6 0 0 0 60 0 19200000 1
hdmi_timings=820 1 42 260 100 240 1 6 10 6 0 0 0 60 0 19200000 1
Perfect
hdmi_timings=320 1 12 32 44 240 1 6 10 6 0 0 0 60 0 6400000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=1920 1 52 208 260 240 1 6 10 6 0 0 0 60 0 38400000 1
hdmi_timings=512 1 16 48 64 288 1 3 5 6 0 0 0 50 0 9600000 1
OK
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=336 1 10 30 34 252 1 15 3 42 0 0 0 50 0 6400000 1 #with borders
hdmi_timings 480 1 29 35 66 234 1 4 10 18 0 0 0 60 0 9600000 1
hdmi_timings=990 1 22 94 116 240 1 6 10 6 0 0 0 60 0 19200000 1
hdmi_timings=820 1 42 260 100 240 1 6 10 6 0 0 0 60 0 19200000 1
Perfect
hdmi_timings=320 1 12 32 44 240 1 6 10 6 0 0 0 60 0 6400000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=1920 1 52 208 260 240 1 6 10 6 0 0 0 60 0 38400000 1
hdmi_timings=512 1 16 48 64 288 1 3 5 6 0 0 0 50 0 9600000 1
```

Ensuite, nous devons indiquer à Recalbox comment afficher EmulationStation et la résolution par défaut des émulateurs. Dans le fichier `recalbox.conf` :

```text
global.videomode=DMT 87 HDMI
```

![VGA666 avec un petit &#xE9;cran de t&#xE9;l&#xE9;vision](/migration-images/tutoriels/video/crt/image%20%28352%29.png)

Retroarch permet une configuration de base spécifique pour la sortie vidéo. On peut faire un fichier de configuration par noyau. Pour ce faire, il faut créer les fichiers de configuration dans le répertoire `/share/system/configs/retroarch`.

Nous utilisons le rapport d'aspect personnalisé "23" pour modifier le visuel de Retroarch.

Pour snes \| snes.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

Pour megadrive \| megadrive.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

Pour nes \| nes.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

Pour fba \| fba\_libretro.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

Pour mame \| mame.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

![D&#xE9;tails de l&apos;image](/migration-images/tutoriels/video/crt/image%20%28157%29.png)

![D&#xE9;tails de l&apos;image](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-L4gFcNhWrkASCSCra%2F-M-L53_A6Q0tG2msIIy4%2FDSC_1538.JPG?alt=media&token=a827b677-6358-48b9-8ee9-b4600c297b95)

Dans les émulateurs, vous devrez probablement ajuster manuellement les variables personnalisées de la fenêtre d'affichage. Pour cela, vous devez lancer le menu Retroarch en appuyant sur le `Hotkey + B`. Avant cela, vous devez ajuster le style du menu Retroarch à l'ancien `rgui` car par défaut avec un écran de télévision, l'interface `ozone` ne sera pas utilisable.

Modifiez les fichiers `retroarchcustom.cfg` et `retroarchcustom.cfg.original` dans le répertoire /recalbox/share/system/configs/retroarch/ \(ou \recalbox\share\system\configs\retroarch via le partage réseau Windows\) et remplacez la ligne `menu_driver = ozone` par cette ligne `menu_driver = rgui` .  
Sauvegardez et redémarrez.

## RGBPi : câble Péritel pour les télévisions CRT

Profitez de la simplicité d'un câble prêt à brancher sur votre téléviseur CRT et votre RaspberryPi grâce à notre système d'exploitation personnalisé en résolutions RGB et PixelPerfect pour tous les jeux, avec un son stéréo amélioré et une nouvelle fonction de commutation automatique, compatible avec les modèles 2B, 3B, 3B+ pour le moment...

Nouvelle fonction de commutation automatique sur le canal AV en 4:3, RVB 18 bits sans conversions et signal CSync propre généré sur le circuit imprimé dans le Péritel offrant la meilleure qualité de signal possible et la plus faible perte, deux canaux audio filtrés améliorés, tous pré configurés.

![Adaptateur RGB-Pi](/migration-images/tutoriels/video/crt/image%20%2864%29.png)

![D&#xE9;tails de l&apos;adaptateur RGB-Pi](/migration-images/tutoriels/video/crt/image%20%28279%29.png)

Si vous voulez l'utiliser avec Recalbox, vous pouvez utiliser la même procédure que dans le cas du VGA666, avec quelques petites modifications. Voici le fichier `config.txt` :

```text
hdmi_timings=320 1 10 30 40 240 1 3 4 6 0 0 0 60 0 6400000 1

## RGB-Pi Custom Configuration
## IMPORTANT! hdmi_timings must be always in the first line
## hdmi_timings=<h_active_pixels> <h_sync_polarity <h_front_porch> <h_sync_pulse
> <h_back_porch> <v_active_lines> <v_sync_polarity> <v_front_porch> <v_sync_puls
e> <v_back_porch> <v_sync_offset_a> <v_sync_offset_b> <pixel_rep> <frame_rate> <
interlaced> <pixel_freq> <aspect_ratio>
## Usable Pixel clock are : 4800000 - 6400000 - 9600000 - 19200000 and anything 
over 38400000

disable_overscan=1
hdmi_force_hotplug=1
config_hdmi_boost=0
dtparam=audio=on
display_rotate=0
audio_pwm_mode=2
disable_audio_dither=1
hdmi_drive=2
boot_delay=3
disable_splash=1
avoid_safe_mode=1
dtoverlay=pwm-2chan,pin=18,func=2,pin2=19,func2=2
framebuffer_depth=32
framebuffer_ignore_alpha=1
#dtoverlay=rgb-pi
#dpi24 is equal to rgb-pi
dtoverlay=dpi24
enable_dpi_lcd=1
display_default_lcd=1
dpi_output_format=6
dpi_group=2
dpi_mode=87
kernel=zImage
overscan_scale=0
avoid_warnings=1
gpu_mem_256=64
gpu_mem_512=128
gpu_mem_1024=256
dtparam=i2c_vc=on
dtoverlay=i2c-gpio,i2c_gpio_sda=10,i2c_gpio_scl=11
```

## Pi2Scart

Le Pi2SCART est un circuit imprimé qui permet d'ajouter à votre Raspberry Pi une sortie audio / vidéo de 15Khz sur une prise Péritel. Le PI2SCART se connecte très simplement à l'interface GPIO du Raspberry. Le son, quant à lui, est capté à partir de la prise casque via un câble audio. Le PI2SCART n'a pas besoin de puissance supplémentaire pour fonctionner.

![Module Pi2Scart branch&#xE9; sur un Pi](/migration-images/tutoriels/video/crt/image%20%28118%29.png)

Comme les deux systèmes précédents, le Pi2Scart utilise le bus DPI et les ports GPIO pour fonctionner. Il utilise l'overlay VGA66 et le dpi\_mode 87. Pour le faire fonctionner, vous devez modifier le fichier `/boot/config.txt` et ajouter les lignes suivantes :

```text
disable_audio_dither=1
dtparam=audio=on
dtoverlay=vga666
enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
hdmi_timings=320 1 16 30 34 240 1 2 3 22 0 0 0 60 0 6400000 1 #240p
```


>**AVERTISSEMENT :**
>
>Ce réglage de résolution correspond à une résolution commune à tous les émulateurs qui peut ne pas être parfaitement adaptée à votre moniteur CRT. C'est à vous de régler soit votre écran \(menu d'usine, potentiomètre\), soit via RECALBOX \(overscan ou via RetroArch\). Dans le dernier cas \(RetroArch\), vous pouvez surcharger la configuration de base pour définir une résolution vidéo spécifique.
{.is-warning}


>**ATTENTION :**
>
>Dans le cas de tests sur un terminal ou un bartop, n'oubliez pas de modifier l'option **controllers.gpio.enabled** qui active les commandes GPIO en changeant la valeur de 1 à 0.
{.is-danger}

RetroArch permet une configuration de base spécifique pour la sortie vidéo. On peut faire un fichier de configuration par noyau. Pour ce faire, il faut créer les fichiers de configuration dans le répertoire `/share/system/configs/retroarch`.

Nous utilisons le rapport d'aspect personnalisé "23" pour modifier le visuel de RetroArch.

 Pour snes \| snes.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

