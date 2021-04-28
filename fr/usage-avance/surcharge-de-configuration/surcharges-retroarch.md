---
title: Surcharges Retroarch
description: Exemples de clefs pour surcharger la configuration retroarch.
---

# Surcharges Retroarch

Voici une liste non exhaustive des clefs pouvant être altérées dans un fichier de surcharge de type .retroarch.cfg, ces modifications ne s'effectue que si l'émulateur est un core retroarch.


>Un \* après la valeur signifie que le paramètre peut être surchargé également via un .recalbox.conf
{.is-info}

## Audio

* **`audio_enable = "true"`**  _Activer ou desactiver l'audio_
* **`audio_volume = "0.000000"`** _Régler le gain du volume, 0= volume par défaut par défaut_

## Menu Retroarch

* **`quick_menu_show_save_content_dir_overrides = "false"`** _Montrer ou cacher l'option Remplacement de configuration pour le répertoire_  
* **`quick_menu_show_save_core_overrides = "false"`** _Montrer ou cacher l'option Remplacement de configuration pour le core_
* **`quick_menu_show_save_game_overrides = "false"`** _Montrer ou cacher l'option Remplacement de configuration pour le jeu_


>Les Remplacements de configuration sont une fonctionnalité de Retroarch, similaire aux surcharges, mais qui retiennent beaucoup d'informations, dans le contexte de recalbox, mieux vaut préférer les surcharge si possible
{.is-info}

## Debug

* **`fps_show = "true"`** _Montrer les FPS en jeu_
* **`menu_driver = "ozone"`** _Choisir le menu retroarch, de base ozone, sauf sur GPi Case, où rgui est utilisé_
* **`menu_enable_widgets = "true"`** _Activer les popups en jeu, si mit à false, affichera les notifications en tant que texte jaune_

## Dossiers

* **`recording_output_directory = ""`** _Dossier où vont les enregistrements vidéos_
* **`savefile_directory = ""`** _Où enregistrer/charger les sauvegardes_
* **`savestate_directory = ""`** _Où enregistrer/charger les savestates_
* **`screenshot_directory = ""`** _Dossier où vont les captures d'écran_

## Service de traduction

* **`ai_service_enable = "true"` \*** _Activer ou desactiver le service de traduction_
* **`ai_service_mode = "0"`** _Mode du service de traduction, 0: image, 1: voix_
* **`ai_service_source_lang = "0"` \*** _Langue à lire pour le service de traduction, 0 = non spécifié_
* **`ai_service_target_lang = "1"`**  __\* _Langue dans laquelle traduire, 1= Anglais, 3= Français_
* **`ai_service_url =`  \*** _Lien internet du service à utiliser_

## Overlays

* **`aspect_ratio_index = "23"` \*** _Index du ratio, 23 = Custom_
* **`input_overlay = ""`** _Lien vers le fichier de configuration de l'overlay_
* **`input_overlay_enable = "true"`**  _Activation de l'overlay_ ****
* **`input_overlay_hide_in_menu = "true"`** _Overlay masqué dans le menu Retroarch_

_Coordonnées à définir avec l'overlay:_

* **`custom_viewport_height = ""`** 
* **`custom_viewport_width = ""`** 
* **`custom_viewport_x = ""`** 
* **`custom_viewport_y = ""`**
* **`video_message_pos_x = "0.050000"`**
* **`video_message_pos_y = "0.050000"`**

## Netplay

* **`netplay_nickname = ""`** \* _Pseudo netplay_



## Rotation de l'écran

* **`video_rotation = "1"`**  _Pivote le rendu vidéo, 0= normal, 1=90°, 2=180°, 3=270°, attention à l'aspect ratio_

## Joystick et Pad directionnel

_dissocie/associe le Pad directionnel a un des joysticks_ 

* **`input_player1_analog_dpad_mode = "0"`**  _dissocie_ 
  * _**=**_ **"1"** _associe au joystick gauche_
  * **= "2"** _associe au joystick droite  ****_

## Remapping des hotkeys


>Les réglages pour changer les hotkeys sont dépendant du mapping de la manette dans Recalbox, aussi si la manette change, la configuration surchargée grâce à ces lignes peut ne plus marcher.
{.is-warning}

Pour avoir la valeur numérique pour chaque touche de votre manette, il faut regarder dans le fichier _system/configs/retroarch/retroarchcustom.cfg_ la valeur de la clef voulue suivant ce tableau :

{% tabs %}
{% tab title="Masquer" %}
Cliquez sur l'onglet "Afficher" pour montrer les clefs pour chaque touche
{% endtab %}

{% tab title="Afficher" %}
| Nom de la touche | Clé concernée dont il faut prendre la valeur |
| :--- | :--- |
| A | input\_player1\_a\_btn |
| B | input\_player1\_b\_btn |
| X | input\_player1\_x\_btn |
| Y | input\_player1\_y\_btn |
| Haut | input\_player1\_up\_btn |
| Bas | input\_player1\_down\_btn |
| Gauche | input\_player1\_left\_btn |
| Droite | input\_player1\_right\_btn |
| Select | input\_player1\_select\_btn |
| Start | input\_player1\_start\_btn |
| L | input\_player1\_l\_btn |
| L2 | input\_player1\_l2\_btn |
| L3 | input\_player1\_l3\_btn |
| R | input\_player1\_r\_btn |
| R2 | input\_player1\_r2\_btn |
| R3 | input\_player1\_r3\_btn |
| Axe L en Haut | input\_player1\_l\_y\_minus\_axis |
| Axe L en Bas | input\_player1\_l\_y\_plus\_axis |
| Axe L à Gauche | input\_player1\_l\_x\_minus\_axis |
| Axe L à Droite | input\_player1\_l\_x\_plus\_axis |
| Axe R en Haut | input\_player1\_r\_y\_minus\_axis |
| Axe R en Bas | input\_player1\_r\_y\_plus\_axis |
| Axe R à Gauche | input\_player1\_r\_x\_minus\_axis |
| Axe R à Droite | input\_player1\_r\_x\_plus\_axis |
{% endtab %}
{% endtabs %}


>Les modifications à faire aux valeurs qui suivent sont à faire dans le fichier de surcharge.
>
>Le fichier précédent ne sert qu'a observer le mapping actuel.
{.is-warning}

* **`input_enable_hotkey_btn =`**  _Touche hotkey_
* **`input_screenshot_btn =`** _Touche pour faire une capture d'écran_
* **`input_exit_emulator_btn =`** _Touche pour quitter le jeu_
* **`input_load_state_btn =`** _Touche pour charger une save state_
* **`input_save_state_btn =`** `` _Touche pour Faire une save state_
* **`input_menu_toggle_btn =`**  _Touche pour accéder au menu Retroarch_
* **`input_reset_btn =`**  _Touche pour redémarrer le jeu_
* **`input_ai_service_btn =`** _Touche pour traduire l'écran actuel_

_Par exemple, The legend of Zelda: Link's Awakening sur Game Boy nécessite d'utiliser Start+Select+A+B pour sauvegarder, si votre manette n'a pas de bouton home, et donc que la hotkey est sur select, la sauvegarde naturelle du jeu sera impossible, aussi mettre la touche **input\_enable\_hotkey\_btn** sur la touche R de votre manette pour ce jeu uniquement peut se tenir. Si pour votre contrôleur, La touche R, donc la valeur de la clef_ **input\_player1\_r\_btn** _vaut 4, alors il vous faudra entrer_ **`input_enable_hotkey_btn = 4`**.

