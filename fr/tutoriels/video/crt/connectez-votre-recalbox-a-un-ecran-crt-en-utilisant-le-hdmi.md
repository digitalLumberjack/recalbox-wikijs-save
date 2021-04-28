---
title: Connectez votre recalbox à un écran CRT en utilisant le HDMI
---

# Connectez votre recalbox à un écran CRT en utilisant le HDMI

Pour jouer à sa Recalbox sur **un écran CRT connecté en HDMI**, plusieurs choix sont possibles, **selon les connectiques de son écran.**

* Connexion via la prise **HDMI** à l'aide d'**un adaptateur HDMI / VGA ==&gt; VGA / BNC** 
* Connexion via la prise **HDMI** à l'aide d'**un adaptateur HDMI / VGA ==&gt; VGA / PERITEL**

## Hardware <a id="hardware"></a>

### Connecter sa Recalbox sur un écran CRT disposant d'entrée RGB en BNC, via HDMI <a id="connecter-sa-recalbox-sur-un-ecran-crt-disposant-dentree-rgb-en-bnc-via-hdmi"></a>

Beaucoup **d'écrans CRT professionnels** disposent **d'entrée RGB en BNC**, comme sur cette image **en Line 3 \(Input\).**

* Nous aurons donc **3 fils pour les 3 couleurs** \(Rouge, Vert, Bleu\), ainsi que **2 fils pour la synchronisation** \(verticale et horizontale\)

![](http://www.auschoice.com/images/ebay_images/garage_sale_images_dv/sonytrini-1387169360-8160.jpg)

####  <a id="connectiques"></a>

### Connectiques

* Vous aurez besoin **d'un adaptateur** comme [celui ci](https://www.amazon.fr/dp/B00NBUTHJG/).​

![Adaptateur HDMI VGA](http://i.imgur.com/WTRfCo6.png)

* Une fois **connecté au port HDMI** de votre Recalbox, vous aurez **une prise VGA en sortie**, et **un jack audio.**


>**Attention :**
>
>Vous aurez besoin d'une alimentation externe micro-usb, 1A devrait suffire.
{.is-danger}

* Il vous faudra ensuite **un adaptateur VGA ==&gt; BNC** comme [celui-ci](https://www.amazon.fr/dp/B0033AF5Y0/).​

![Adaptateur VGA BNC](http://i.imgur.com/UAuajvZ.png)

* N'ayant pas trouvé **d'adaptateur VGA / BNC avec sortie BNC femelle**, j'ai dû utiliser **5 connecteurs BNC mâle / mâle**, trouvable en boutique spécialisée d'électronique.

![BNC male male](http://i.imgur.com/UEXCmCR.png)

## Software <a id="software"></a>

### Configuration du boot de la Recalbox <a id="configuration-du-boot-de-la-recalbox"></a>

Les **résolutions acceptées** par ce type d'écran sont **différentes selon le modèle**, mais en général, nous voulons :

* **Du 480i pour EmulationStation** \(mon écran ne supporte pas le 480p, et les textes sont illisibles en 240p\) 
* **Du 240p pour les jeux** \(résolution de sortie pour quasiment toutes les consoles de cette époque\)

Voila à quoi devrait **ressembler votre fichier** `/boot/config.txt`

```text
#Définition de la résolution du mode custom DMT 87 HDMI pour la résolution des jeux
hdmi_cvt=1920 240 60 1 1 0 0
#Ignore le EDID de votre TV (le CRT peut envoyer de mauvaises informations)
hdmi_ignore_edid=0xa5000080
#Force le mode d'encodage des pixels, 2 correspond à Full RGB
hdmi_pixel_encoding=2
#Désactive le safe mode au boot du raspberry pi
avoid_safe_mode=1
#Ne pas désactiver l'overscan
disable_overscan=0
#Evite les interférences de l'adaptateur en boostant le signal HDMI
config_hdmi_boost=4
#Force le son sur HDMI
hdmi_drive=2
#Selectionne le groupe HDMI CEA
hdmi_group=1
#Résolution CEA 6 = 480 interlaced
hdmi_mode=6

#Kernel utilisé
kernel=zImage
#Utiliser le mode HDMI même si aucun câble n'est connecté
hdmi_force_hotplug=1
#paramètres mémoire
gpu_mem_256=128
gpu_mem_512=256
gpu_mem_1024=512

#Paramètre lié à l'audio
dtparam=audio=on
#Permet de temporiser le boot
boot_delay=3
```


>**Informations :**
>
>* Pour **éditer ce fichier,** il faut modifier ****[**la partition de boot en écriture**](/v/francais/tutoriels/systeme/acces/acceder-a-une-partition-en-ecriture). 
>* **Pour y accéder** par Winscp, suivre[ ce tutorial](/v/francais/tutoriels/systeme/acces/acces-reseau-via-winscp).
{.is-info}

**Quelques explications :**

* Le Raspberry pi **démarrera en mode** `hdmi_group=1 hdmi_mode=6`, ce qui correspond à du **480i \(interlaced\)**.
* **Si le boot** s'effectue directement en **240p**, les textes des menus et des jeux **seraient illisibles.**
* **La ligne** `hdmi_cvt=1920 240 60 1 1 0 0` **spécifie** une résolution de **1920 x 240 x 60 Hz**, qui ne **servira pas pour le boot**, mais sera **enregistrée en tant que mode** `DMT 87 HDMI`, que nous utiliserons ultérieurement pour **le lancement des jeux.**

Voici un peu **plus d'explication** sur cette ligne :

```text
hdmi_cvt=<width> <height> <framerate> <aspect> <margins> <interlace> <rb>
width        width in pixels
height       height in pixels
framerate    framerate in Hz
aspect       aspect ratio 1=4:3, 2=14:9, 3=16:9, 4=5:4, 5=16:10, 6=15:9
margins      0=margins disabled, 1=margins enabled
interlace    0=progressive, 1=interlaced
rb           0=normal, 1=reduced blanking
```

### Configuration du fichier recalbox.conf <a id="configuration-du-fichier-recalbox-conf"></a>

Bien que le Raspberry Pi **boot en mode vidéo CEA 6** \(via le config.txt\) j'ai préféré **forcer cette configuration** pour **EmulationStation:**

```text
system.es.videomode=CEA 6 HDMI
```

* Nous devons ensuite préciser la **résolution de boot** pour nos émulateurs, **de façon globale :**

```text
global.videomode=DMT 87 HDMI
```

**Tous les émulateurs** seront donc lancé en **mode DMT 87 HDMI** \(mode "custom"\) contenant via **le hdmi\_cvt** du fichier **config.txt**, la résolution **1920 x 240x 60Hz.**


>**Information :**
>
>Petite explication pour les **1920 pixels de large :**
>
>* Pour faire court, **un écran CRT** n'a besoin que **d'un nombre de pixels vertical** \(240 ici\) et **d'un taux de rafraîchissement vertical** \(60 Hz ici\).
>* Nous spécifions donc **1920 pixels de large**, car **1920 est un multiple de** 160, 320, 384... qui sont des résolutions **souvent rencontrées**.
>* Pour les résolutions **n'étant pas des multiples**, nous devrons **calculer avec retroarch l'overscan**, c'est-à-dire **les bandes noires** nécessaires **autour de l'écran** pour garder **le ratio original.**
{.is-info}


>Tout passe chez moi dans cette résolution.   
>Mais vous pouvez **spécifier une résolution différente** par console, avec **la ligne suivante :**
{.is-info}

```
dreamcast.videomode=hdmi_cvt 320 240 60 1 1 0 0
```

### Configuration du viewport Retro**A**rch \(garder le ratio d'origine et caler l'image sur son écran\) <a id="configuration-du-viewport-retroarch-garder-le-ratio-dorigine-et-caler-limage-sur-son-ecran"></a>

#### Configuration par système <a id="configuration-par-systeme"></a>

Lors du **lancement d'un jeu**, celui-ci doit donc démarrer dans une **résolution de 320 x 240 x 60 Hz pixels.**   
Nous pouvons **spécifier** pour chaque système, **la taille d'affichage réelle** et **le décalage** si besoin.

**Ces fichiers de configuration** sont **à créer** dans votre **dossier partagé :**`/system/configs/retroarch/`   
Ils devront **contenir le nom du système** \(le même que dans le dossier roms\), **par exemple :**`nes.cfg`, ou `mastersystem.cfg`

Voici le **contenu de mon fichier** `nes.cfg`

```text
aspect_ratio_index = "22"
video_smooth = "false"
video_scale_integer = "false"
video_threaded = "false"
custom_viewport_width = "1680"
custom_viewport_height = "224"
custom_viewport_x = "118"
custom_viewport_y = "17"
```

* Pour régler le positionnement de l'écran, il suffit de changer la valeur **custom\_viewport\_x** et **y**, directement en jeu via le menu RetroArch \(touche **Hotkey + B**\), puis de recopier ces valeurs dans le _fichier .cfg_ du système. 
* Voici les **viewports width** et **height** que j'ai configuré pour mon **CRT :**

```text
nes.cfg
custom_viewport_width = "1680"
custom_viewport_height = "224"
        
snes.cfg
custom_viewport_width = "1792"
custom_viewport_height = "224"

gb.cfg gbc.cfg gamegear.cfg
custom_viewport_width = "960"
custom_viewport_height = "144"

gba.cfg
custom_viewport_width = "1440"
custom_viewport_height = "160"

megadrive.cfg neogeo.cfg segacd.cfg sega32x.cfg fba_libretro.cfg
custom_viewport_width = "1920"
custom_viewport_height = "224"

mastersystem.cfg
custom_viewport_width = "1536"
custom_viewport_height = "192"

psx.cfg n64.cfg
custom_viewport_width = "1920"
custom_viewport_height = "240"

pcenginecd.cfg
custom_viewport_width = "1760"
custom_viewport_height = "240"
```

#### Configuration par jeux

Pour l'**arcade**, j'utilise **fba\_libretro**. Chaque jeu ou presque ayant une résolution différente, j'ai défini un fichier par jeu \(pour garder le ratio original\).

Même manipulation que par système, sauf que les fichiers se situent dans votre dossier partagé : `/system/configs/retroarch/fba_libretro/`

Le contenu du fichier est identique à la configuration par système. Le nom du fichier doit être sous la forme **rom.zip.cfg**  
Donc par exemple : **1944.zip.cfg**

### Cas particuliers <a id="cas-particuliers"></a>

#### Nintendo 64 <a id="nintendo-64"></a>

Pour **gérer les viewports** sur l'émulateur **Nintendo 64**, nous devons **sélectionner le core** RetroArch `glupen64`.  
Ensuite, de la **même façon** que pour les autres systèmes, **la configuration** se trouvera dans **un fichier** `n64.cfg`

#### AdvanceMame <a id="advancemame"></a>

Pour les jeux arcade **Mame**, le core **AdvanceMame** à la particularité de **calculer automatiquement la résolution de chaque jeu**, en l'adaptant à **votre résolution d'écran.**

Ainsi, nous nous passons d'effectuer **une configuration par jeu** \(comme c'est le cas pour fba\_libretro\).


>## _Cette partie reste à compléter **!**_
{.is-danger}

### Thèmes EmulationStation <a id="themes-emulation-station"></a>

**Le thème** doit être réalisé en **4/3** pour avoir **une image bien cadrée**, je vous propose [**un thème**](https://forum.recalbox.com/topic/6580/release-wip-theme-recalbox-multi-help-needed) crée par Supernature2K.​

Ce thème est **configurable**, et s'adapte parfaitement **aux CRT.**

![Th&#xE8;me Recalbox Multi](http://i.imgur.com/6hQFlPO.png)

