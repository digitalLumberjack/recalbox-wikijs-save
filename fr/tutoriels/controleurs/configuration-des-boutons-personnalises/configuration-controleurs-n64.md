---
title: Configuration controleurs N64
---

# Configuration controleurs N64

Vous devez utiliser `sdl2-jstest` pour paramétrer les contrôleurs N64.

Au cas où votre bouton 0 quitterait l'émulateur \(comme le ferait la touche de raccourci\), vous devrez modifier le fichier suivant : `~/configs/mupen64/mupen64plus.cfg` =&gt; Changez le paramètre **Joy Mapping Stop = "J1B0"** en **Joy Mapping Stop = ""** 

### A - Ajoutez la configuration de votre contrôleur au système :

Pour configurer votre contrôleur, vous aurez besoin d'informations dessus. Connectez-vous en tant que [root](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal), et utilisez la commande [jstest](/v/francais/tutoriels/obsoletes/testez-votre-joystick-avec-jstest) :

`jstest /dev/input/js0`

ou

`sdl2-jstest -l`

Dans mon cas, j'obtiens :

```text
Joystick (Broadcom Bluetooth Wireless  Joystick                        ) has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (Trigger, ThumbBtn, ThumbBtn2, TopBtn, TopBtn2, PinkieBtn, BaseBtn, BaseBtn2, BaseBtn3, BaseBtn4, BaseBtn5, BaseBtn6).
```

Une fois le nom du contrôleur et chaque bouton identifié, vous devez modifier ce fichier :`/usr/share/mupen64plus/InputAutoCfg.ini`

Utilisez cette commande :

`nano /usr/share/mupen64plus/InputAutoCfg.ini`

Maintenant, à la fin du fichier, ajoutez les informations de configuration, comme ceci :

_Ce modèle est un exemple, avec des informations sur mon propre contrôleur \(nom du contrôleur, numéro de bouton etc...\). Vous devrez l'adapter avec les informations de votre propre contrôleur._

```text
[Broadcom Bluetooth Wireless  Joystick                        ]
plugged = True
plugin = 2
mouse = False
AnalogDeadzone = 4096,4096
AnalogPeak = 32768,32768
DPad R = hat(0 Right)
DPad L = hat(0 Left)
DPad D = hat(0 Down)
DPad U = hat(0 Up)
Start = button(9)
Z Trig = button(7)
B Button = button(2)
A Button = button(1)
C Button R = axis(3+)
C Button L = axis(3-)
C Button D = axis(2+)
C Button U = axis(2-)
R Trig = button(5)
L Trig = button(4)
Mempak switch = button(6)
Rumblepak switch = 
X Axis = axis(0-,0+)
Y Axis = axis(1-,1+)
```

Une fois que votre configuration est correcte, faites `Ctrl+x` pour quitter nano, acceptez d'écraser le fichier avec `y` et appuyez sur `Entrée` pour quitter. Vous pouvez maintenant démarrer un jeu N64, et tester votre configuration.

Votre configuration est correcte, vous l'aimez ? Super ^^ Mais, il y a un "problème". Lorsque vous mettez à jour votre Recalbox, tous ces fichiers de configuration sont également mis à jour. Ils seront donc réinitialisés.  
Si vous ne voulez pas le faire après chaque mise à jour, faites une sauvegarde de votre fichier `InputAutoCfg.ini`  
Vous pouvez également ajouter votre configuration à Recalbox. Vous devez consulter ce point, et poster votre propre configuration en commentaire.

Nous l'ajouterons ensuite au système lors d'une prochaine mise à jour de Recalbox.

### B - Ajouter des commandes spéciales

Mupen64plus ne supporte pas les combinaisons de boutons, comme les émulateurs RetroArch, pour lancer une commande spéciale.  
Mais vous pouvez affecter les boutons inutilisés à une commande spécifique, comme _sauvegarder/charger une savestate, changer les emplacements de sauvegarde_, etc...

Pour ce faire, dans un premier temps, vous devez identifier tous les boutons inutilisés dans votre configuration.  
Donc, comme vu précédemment, allez en [accès root](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal) et utilisez la [commande jstest](/v/francais/tutoriels/obsoletes/testez-votre-joystick-avec-jstest), puis notez le numéro de code de vos boutons inutilisés.

Maintenant, toujours en accès root, modifiez votre fichier `mupen64plus.cfg` avec cette commande :

`nano /recalbox/configs/mupen64/mupen64plus.cfg`

Ensuite, allez dans la section intitulée `[CoreEvents]`. La bonne section, c'est celle-là :

```text
# Joystick event string for stopping the emulator
Joy Mapping Stop = ""
# Joystick event string for switching between fullscreen/windowed modes
Joy Mapping Fullscreen = ""
# Joystick event string for saving the emulator state
Joy Mapping Save State = ""
# Joystick event string for loading the emulator state
Joy Mapping Load State = ""
# Joystick event string for advancing the save state slot
Joy Mapping Increment Slot = ""
# Joystick event string for taking a screenshot
Joy Mapping Screenshot = ""
# Joystick event string for pausing the emulator
Joy Mapping Pause = ""
# Joystick event string for muting/unmuting the sound
Joy Mapping Mute = ""
# Joystick event string for increasing the volume
Joy Mapping Increase Volume = ""
# Joystick event string for decreasing the volume
Joy Mapping Decrease Volume = ""
# Joystick event string for fast-forward
Joy Mapping Fast Forward = ""
# Joystick event string for pressing the game shark button
Joy Mapping Gameshark = ""
```

Il faut garder à l'esprit que Mupen64plus identifie `player 1` en tant que `J0`, `player 2` en `J1` etc...  
Ainsi par exemple, si vous voulez ajouter le bouton numéro 10 du joueur 1 à la commande "_save savestates_", vous devez éditer votre fichier comme ceci :  
`Joy Mapping Save State = "J0B10"`

Et si vous voulez ajouter le bouton 5 du joueur 2 à la commande "_load savestates_", vous devez éditer votre fichier comme ceci:  
`Joy Mapping Load State = "J1B5"`

Une fois que votre configuration est correcte, faites `Ctrl+x` pour quitter nano, acceptez d'écraser le fichier avec `y` et appuyez sur `Entrée` pour quitter.

