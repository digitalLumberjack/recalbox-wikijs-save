---
title: Configurer un écran externe \(x86/x86\_64\)
---

# Configurer un écran externe \(x86/x86\_64\)


>**Information :**
>
>Depuis la **version 7.0**, la configuration des écrans externe ce fait depuis le fichier  `recalbox.conf`.
{.is-info}

## Connaître les sorties vidéo disponible

* Connecté vous a votre Recalbox en [ssh](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal)
* Dans votre terminal **ssh**, tapez la commande suivante : `xrandr`

Ce qui vous donne comme résultat **les sorties vidéo disponible et leur résolutions.**

**Exemple :**

```text
eDP-1 connected primary 1366x768+0+0 (normal left inverted right x axis y axis) 344mm x 193mm
   1366x768      60.06*+
   1360x768      59.80    59.96  
   1280x720      60.00    59.99    59.86    59.74  
   1024x768      60.04    60.00  
   960x720       60.00  
   928x696       60.05  
   896x672       60.01  
   1024x576      59.95    59.96    59.90    59.82  
   960x600       59.93    60.00   
VGA-1 disconnected (normal left inverted right x axis y axis)
HDMI-1 disconnected (normal left inverted right x axis y axis)
DP-1 disconnected (normal left inverted right x axis y axis)
```

## Configuration

* Ouvrez le fichier **recalbox.conf** situé dans le dossier : `/recalbox/share/system` 
* Une fois la sortie sectionné, renseignez-la dans cette partie du fichier **recalbox.conf** :

```text
## Prefered external screen retrieved from ssh : xrandr
system.externalscreen.prefered=HDMI-1
## Force selected external screen to resolution ex : 1920x1080
system.externalscreen.forceresolution=1920x1080
```


>**Prenez note**
>
>Le signe **;** se trouvera par défaut devant les 2 lignes que vous modifiez. Vous devrez supprimer ce caractère devant chacune des 2 lignes pour activer vos modifications.
{.is-info}

## Plus d'info

[https://doc.ubuntu-fr.org/xrandr](https://doc.ubuntu-fr.org/xrandr)

