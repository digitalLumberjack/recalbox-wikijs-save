---
title: Connectez votre Recalbox à un écran cathodique avec HDMI et SCART
---

# Connectez votre Recalbox à un écran cathodique avec HDMI et SCART

## Principes

### Câblage

Dans un premier temps, vous devrez créer le super-câble pour convertir le VGA en Péritel.  
Merci à @ian57 pour [ce message](https://forum.recalbox.com/topic/3475/recalbox-sur-tv-crt-en-rgb/745) !

![](https://s3-eu-west-1.amazonaws.com/forums.recalbox.com/ac9ba3d3-29fc-4ff2-8644-aee71b62f043.png)

J'ai utilisé cela \(câble HDMI VGA péritel\) sur une borne avec une Tv 36 cm et une Recalbox 6.1.1, il n'y avait pas de soucis particulier.

Voici le schéma de mon câblage à la sortie du convertisseur VGA.

Ensuite pour les configurations, c'est très différent du VGA666 / pi2scart / rgbPi \(ils utilisent tous les 3 le DPI en mode 18 bits \(6 bits/couleur\)\) :

Dans le fichier /boot/config.txt, on configure comme si on avait un écran 1920x240 :

```text
hdmi_cvt=1920 240 60 1 1 0 0
hdmi_disable_edid=0xa5000080 #Enables the ignoring of EDID/display data if your display doesn't have an accurate EDID.

hdmi_pixel_encoding=2 #Force the pixel encoding mode. By default it will use the mode requested from edid so shouldn't need changing. 
avoid_safe_mode=1
disable_overscan=0 #oversan enabled
hdmi_drive=2
hdmi_group=1
hdmi_mode=6
hdmi_force=1
```

Dans le fichier recalbox.conf, on force EmulationStation à s'afficher en 480 entrelacé \(ça pique un peut les yeux\) ; sinon on utiliser les CEA 8 HDMI un 240 non entrelacé, mais il faudra un thème adapté à cette faible résolution.

```text
system.es.videomode=CEA 6 HDMI
 
#global.videomode=CEA 4 HDMI
global.videomode=DMT 87 HDMI
```

Ensuite, il faut dire à Libretro pour chaque émulateur de n'utiliser d'une partie de la fenêtre 1920x240.  
Pour cela, il faut [créer un fichier](https://forum.recalbox.com/topic/18927/recalbox-6-1-sur-%C3%A9cran-crt/9) de config pour chaque émulateur à placer dans `/share/system/configs/retroarch`

Par exemple, mon `megadrive.cfg`

```text
aspect_ratio_index = "23"
custom_viewport_width = "1792"
custom_viewport_height = "224"
custom_viewport_x = "104"
custom_viewport_y = "16"
```

Il faut adapter les 4 dernières lignes en fonction de la géométrie de l'écran. Il est possible de trouver les valeurs en réglant depuis le menu de RetroArch.

Si cela n'est pas fait, l'image de l'émulateur sera complètement écrasée au milieu de l'écran.

## Liens utiles pour la configuration du noyau RetroArch

[Ce lien](https://surchargeur-ra-rb.netlify.app/) vous permet de générer simplement les fichiers de configuration pour la RetroArch à partir d'une interface web.

La suite arrive bientôt =\)

