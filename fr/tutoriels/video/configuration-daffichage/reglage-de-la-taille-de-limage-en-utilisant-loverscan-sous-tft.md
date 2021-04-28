---
title: Réglage de la taille de l'image en utilisant l'overscan sous TFT
---

# Réglage de la taille de l'image en utilisant l'overscan sous TFT


>**Information :**
>
>L'option _**overscan**_ peut être activée si vous avez des bordures noires sur l'image ou si votre image est recadrée.
{.is-info}

## Activer l'option _overscan_

* Menu EmulationStation
* Paramètres de l'interface 
* Activer l'option **Overscan**


>**Remarque :**
>
>Vous devez redémarrer le Raspberry Pi après avoir modifié cette option.
{.is-warning}

## Configuration


>**Information :**
>
>Les options d'overscan sont définies par Noobs lors de la première installation.
{.is-info}

* Si elle ne correspond pas à votre écran, vous pouvez modifier les paramètres de chaque bordure dans votre fichier [config.txt](/v/francais/tutoriels/systeme/modification/editer-le-fichier-config.txt) :

```text
disable_overscan=0
overscan_left=24
overscan_right=24
overscan_top=24
overscan_bottom=24
```

La valeur précise le nombre de pixels à ignorer sur le bord de l'écran. **Augmentez** cette valeur _si l'image_ _sort_ du bord de l'écran ; **diminuez**-la s'il y a une _bordure noire_ entre le bord de l'écran et l'image.

* Si ces paramètres ne sont pas appliqués correctement dans les émulateurs ou EmulationStation, essayez d'ajouter ceci :

```text
overscan_scale=1
```

