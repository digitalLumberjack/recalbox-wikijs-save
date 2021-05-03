---
title: Retroachievements
---

# Retroachievements

## **Challenge/Succès avec retroarch :** <a id="challenge-succes-avec-retroarch"></a>

Le site internet [retroachievements.org](http://www.retroachievements.org/) propose **des challenges/succès/trophées** sur les plateformes tels NES, SNES, GB, GBC, GBA, Megadrive/Genenis, PCengine, prochainement FBA libretro, N64, GameGear.

## **Création d'un compte** : <a id="creation-dun-compte"></a>

* **Vous devez** [créer un compte](http://retroachievements.org/createaccount.php) sur le site [retroachievements.org](http://www.retroachievements.org/). 
* **Noter votre pseudonyme** \(_Username_\) et **votre mot de passe** \(_password_\) dans un coin car ils vont servir à **configurer Retroachievements dans retroarch.**

## **Activation du compte dans Emulationstation sous recalboxOS**  <a id="activation-du-compte-dans-emulationstation-sous-recalboxos"></a>

* **Ouvrir le menu** d'Emulationstation \(START\) 
* Aller dans **Options des jeux** 
* Puis **Options de Retroachievements**

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/menu_es_retroachievements1.png)

* **Éditer** comme ceci : `Retroachievements > ON`  `Nom Utilisateur > mettre votre pseudonyme`  `Mot de passe > votre mot de passe`

## **Activation du compte manuellement sous Recalbox** <a id="activation-du-compte-manuellement-sous-recalboxos"></a>

Vous devez **éditer** le fichier **recalbox.conf :**

* **Via ssh** avec putty et le commande nano `nano /recalbox/share/system/recalbox.conf`  ou  [winscp](/fr/tutoriels/systeme/acces/acces-reseau-via-winscp) avec l'éditeur Notepad++ ​
* **Ajout ses 3 lignes** en remplaçant pseudonyme et motdepasse par ceux créer lors de votre inscription.

```text
## Enable retroarchievements (0,1)
## Set your www.retroachievements.org username/password
## Escape your special chars (# ; $) with a backslash : $ => \$
global.retroachievements=1
global.retroachievements.hardcore=0
global.retroachievements.username=
global.retroachievements.password=
```


>_**Information :**_
>
>**Le mode** hardcore **désactive les fonctions** de rewind, crédit illimité etc...
{.is-info}

* **Sauvegarder** votre **recalbox.conf** 
* **Rebooter** votre Recalbox.

## **Les émulateurs/cores compatibles avec Retroachievements.** <a id="configuration-des-emulateurs-core-compatible-avec-retroachievements"></a>


>_**Remarques :**_
>
>**Tous les cores** Libretro **ne sont pas compatibles** avec **Retroachievements.**
{.is-warning}



Voici la **liste des emulateurs/core** qui fonctionnent avec **Retroarch/Retoachievements** :

* **Afficher le menu** d'Emulationstation \( bouton START\)
  * **puis** `Options jeux > advanced >`
* NES &gt; EMULATEUR LIBRETRO &gt; CORES QUICKNES / FCEUMM 
* SNES &gt; EMULATEUR LIBRETRO &gt; CORE SNES9X\_NEXT 
* GB/GBC/GBA &gt; DEFAULT 
* MEGADRIVE &gt; DEFAULT \(picodrive\) 
* PCENGINE &gt;DEFAULT \(pour le moment ce n'est pas supporté par le core libretro\) 
* FBA Libtreto / Neogeo FBA Libretro &gt; DEFAULT \(soon vers 2018.x.x\) 
* GameGear &gt; Genesis \(Default\) \(soon vers 2018.x.x\) 
* N64 &gt; Emulateur \(Libretro\) , Glupen64 \(core\) \(soon vers 2018.x.x\)




>_**Informations :**_
>
>​Pour **visionner les challenges/trophées** dans **Retroach** , il suffit d'**activer le menu retroarch** \(Hotkey+B\)   
>`Quick Menu > Achievements list`
>
>La **liste des jeux compatibles** sont disponibles sur [cette page](http://retroachievements.org/gameList.php)
{.is-info}

## **Quelles roms sont compatibles ?**  <a id="quelles-roms-sont-compatibles"></a>

En général, les **roms No-Intro en version USA** fonctionnent mieux pour les **Retroachievements,** à quelques rares exceptions où l'**on peut avoir aussi quelques roms européennes.**  
  
Vous pouvez trouver **une liste de roms avec leurs HASHES \(MD5\)** autrement dit **leur signature numérique** en vous rendant **sur la page du jeu** et en **cliquant sur le lien à droite** :`HASHES LINKED TO THIS GAME` .

Vous verrez **une liste de signatures de roms compatible** avec ses Retroachievements.

