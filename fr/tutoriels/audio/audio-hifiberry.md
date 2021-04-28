---
title: Audio HiFiBerry
---

# Audio HiFiBerry

## Informations générales <a id="general"></a>


>Pour obtenir un **signal audio de qualité sur Pi**, une solution consiste à utiliser un **HiFiBerry DAC** \(Digital - Analog Converter = CNA : Convertisseur Numérique-Analogique\). 
{.is-info}

Ces **DAC** existent en plusieurs versions :

### **Raspberry Pi A+, B+, 2 et 3**

* DAC+ Light
* DAC+ Standard RCA
* DAC+ Standard Phone
* DAC+ Pro

### **Raspberry Pi A et B**

* DAC Standard version with RCA connectors

Les caractéristiques des différentes cartes peuvent être comparées sur [**hifiberry.com**](http://www.hifiberry.com/).  
**Les cartes DAC+** peuvent être connectées **directement sur le GPIO du Pi.**  
Les broches **non utilisées** par le DAC **peuvent être réutilisées** pour d'autres utilisations, auquel cas il faut **souder des broches additionnelles à la carte DAC+**.

  
**Ci-dessous** le schéma de câblage d'un DAC+ HifiBerry : hifiberry

![](https://cloud.githubusercontent.com/assets/17233889/16976447/3755fcc8-4e4f-11e6-847b-1233d687ffd7.png)


>La version pour **Raspberry A et B** doit être installée sur la **broche 5**. Cela requiert **quelques manipulations supplémentaires** notamment.  
>Une fois la carte installée, il reste quelques étapes de configuration logicielle pour que tout fonctionne
{.is-info}

## Arborescence et configuration des appareils <a id="device-tree-and-config"></a>

* Sur recalbox, il suffit **d'ajouter** dans `/boot/config.txt` le bon **DTB**, à paramétrer selon votre carte :
  * **DAC/DAC+ Light** `dtoverlay=hifiberry-dac`
  * **DAC+ Standard/Pro** `dtoverlay=hifiberry-dacplus`    
* Ensuite il faut **sélectionner la carte son par défaut.** **Il faut alors éditer** _/etc/asound.conf_ \(le créer s'il n'existe pas\) **avec le contenu suivant** :
  * `pcm.!default {` `type hw card 0` `}` `ctl.!default {` `type hw card 0` `}`
* **Rebootez** à présent votre Pi.

A présent vous devriez **entendre le son** par votre carte **HiFiBerry**.


>**IMPORTANT:**  
>Vous ne pouvez pas changer le volume du son dans EmulationStation seulement par _Alsamixer/Amixer_.
{.is-info}

## Alsamixer/Amixer <a id="alsamixer-amixer"></a>

**Les cartes son ALSA** \(et c'est le cas des HiFiBerry\) peuvent être contrôlées par **Alsamixer.**  
Ce dernier est une i**nterface graphique**, alors que **Amixer** fonctionne en mode texte, notamment pour **des scripts.**

Puisque **alsa-utils** est installé sur Recalbox, HifiBerry fonctionnera **sans utilitaires supplémentaire.**


>**IMPORTANT:**  
>Les DAC+ Light et l'ancienne DAC **n'ont pas** de réglages possible dans ALSA.
{.is-danger}

  
Avec la **commande** `amixer` vous aurez une version textes des **différents réglages du DAC.**  
La **meilleure façon** de changer le volume est de modifier le **"Overall volume"**. Son nom peut **différer** selon la carte : ‘PCM’, ‘Digital’, ‘Master’, à vous d'essayer.

Les **commandes** suivantes vous permettent de **changer le volume par le terminal** :

* `amixer sset ‘Master’ -- 90%` \(déconseillé car l'échelle est logarithmique\)
* `amixer sset ‘Master’ -- -3dB` \(en décibels, réglage recommandé\)
* `amixer sset ‘Master’ – 2000` \(unité empirique, déconseillé\)


>Vous pouvez utiliser Google pour découvrir **le reste des commandes possibles** avec les mots clé : **amixer**, **alsamixer**.
{.is-info}

**Voici un exemple** en python pour gérer le volume.

Tout d'abord, importez la commande du sous-processus :

```python
from subprocess import call


call(["amixer", "sset", "Digital", "--", str(YourDesiredVolume)+"dB"])
```

**Ce script** peut notamment être utilisé pour **changer le volume** par l'utilisation du **GPIO**.

**Ci-dessous un récapitulatif de quelques commandes :**

* `amixer sset 'PCM' 70%` \(pourcentage\)
* `amixer sset 'Master' 3dB` \(Decibel\)
* `amixer sset 'Mic' 4` \(valeurs matérielles\)
* `amixer sset 'PCM' 10%+` \(augmentation de la valeur en cours. L'unité peut être des % ou des dB\)
* `amixer sset 'Line' cap` \(Recording on/off: cap, nocap\)
* `amixer sset 'Mic' mute` \(Playback on/off: mute, unmute\)
* `amixer sset 'Master' off` \(On/Off: on/off\)
* `amixer sset 'Mic Select' 'Mic1'` \(Nom du périphérique\)

Source : [**wiki.ubuntuusers.de/amixer**](https://wiki.ubuntuusers.de/amixer/)

