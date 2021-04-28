---
title: Comment personnaliser mapping manette
---

# Comment personnaliser mapping manette


>Ceci concerne ceux qui veulent changer le mapping des boutons suivant les émulateurs du core RetroArch.
{.is-info}

* **Lancez un jeu** dudit émulateur, 
* **Dans le menu de RetroArch** \(Hotkey + B\), **allez** dans **« Settings »,** puis **« Input user 1 binds »** 
* **Reconfigurez les touches**, pensez à avoir un **clavier sous la main**, car à un moment ça peut coincer, **donc finir au clavier** \("w" et "x" pour valider et revenir en arrière\) 
* **Allez** ensuite dans **"Input hotkey binds"** et **reconfigurez les touches** comme vous le souhaitez 
* **Revenez au premier menu de RetroArch** et **faire « Save new config »** \(normalement le nom de la configuration est **nom\_du\_core.cfg**, par exemple **catsfc.cfg** si vous êtes sur **snes + catsfc**\) 
* **Se connecter en SSH** à Recalbox, et **modifiez le nom du fichier de configuration** pour quelques chose de plus parlant.  Exemple pour l'**émulateur Neogeo** :

`mv /recalbox/share/system/configs/retroarch/catsfc.cfg /recalbox/share/system/configs/retroarch/inputs/neogeocustom.cfg`

* **Modifiez** le fichier **recalbox.conf** en **ajoutant la ligne suivante** pour prendre en compte la nouvelle configuration : `neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeocustom.cfg`


>**Attention :** 
>
>Tous les autres paramètres sont ceux **par défaut**, donc **pas de shader, cheat, ou autre.**
{.is-danger}

