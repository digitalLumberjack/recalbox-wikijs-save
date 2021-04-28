---
title: Le fichier recalbox.conf
---

# Le fichier recalbox.conf

## I - Introduction

**Recalbox** possède un **outil de configuration avancée** nommé `recalbox.conf`qui vous permet de **modifier des options qui ne sont pas disponibles** dans **emulationstation.**

**Pour l'éditer** vous pouvez utiliser soit :

* **Le moyen le plus simple** est d'utiliser [le web manager](https://www.youtube.com/watch?v=pxq_8RXSRjg).  
  Il faut rafraichir la page manuellement derrière, sinon vous verrez la version sans les modifs \(Section - recalbox.conf\).  
  Ce dernier est **accessible via** :

  * **Windows: `http://recalbox/`** ou **saisissez votre adresse IP.**
  * **Linux/Mac: `http://recalbox.local/`** ou **saisissez votre adresse IP.**

  Dans le **menu de gauche**, **allez** maintenant dans **`recalbox.conf`**  

* Les **dossiers de recalbox partagés sur le réseau local.** Le fichier **`recalbox.conf`** est disponible dans le répertoire nommé **`system`**. 
* Un[ accès root via Terminal ](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal)et **éditer le fichier** présent dans le système à l'emplacement **`/recalbox/share/system/recalbox.conf`.**


>**Information :**  
>Le `;` **au début d'une ligne**, signifie que celle-ci est **désactivée**.  
>**Retirez** le `;` pour **activer l'option** associée à la ligne.
>
>**Pour les utilisateurs de Windows :**  
>Si vous n'utilisez pas l'option via le webmanager, vous devez utiliser un vrai éditeur de texte, comme [**Notepad++**](https://notepad-plus-plus.org/downloads/).  
>L'éditeur de texte **présent par défaut** dans Windows **insert de mauvais caractères** dans le fichier, **le rendant illisible par le système.**
{.is-info}

## II - Options disponibles <a id="i-options-disponibles"></a>

* **A - Options Système**
  * définir la gestion d'alimentation
  * activer / désactiver fbcp \(framebuffer utilisé pour les écrans gpio/spi\)
  * définir le temps des vidéos de démarrage
  * activer / désactiver le démarrage automatique de recalbox-manager
  * définir la version du recalbox-manager utilisée
  * activer / désactiver l'option sécurité
  * activer / désactiver l'Api Recalbox
  * définir le mode vidéo de Emulationstation
  * définir le style de menu pour Emulationstation
  * définir les options de démarrage / affichage de Emulationstation
  * définir les options et votre compte ScreenScrapers
  * définir la gestion des raccourcis spéciaux en jeu
  * cacher Kodi dans Emulationstation
  * lancer Kodi au démarrage du système
  * définir le mode vidéo de Kodi
  * attribuer le bouton X au démarrage de Kodi
  * définir le délai réseau de Kodi
  * activer / désactiver Hyperion 
* **B - Réseau**
  * définir le "hostname"
  * définir la region du wifi 
  * saisir la clé et SSID du wifi
  * définir une "ip static" en wifi 
  * définir jusqu'à 3 réseaux wifi \(le system se connectera au premier qui sera disponible\)
  * activer / désactiver le partage samba
  * activer / désactiver le virtual-gamepads
  * activer / désactiver le ssh 
* **C - Audio**
  * définir la sortie audio
  * définir le volume audio
  * activer / désactiver la musique en arrière plan dans Emulationstation 
* **D - Manettes**
  * activer / désactiver les contrôleurs Bluetooth
  * activer /désactiver les contrôleur PS3
  * sélectionner le driver pour les manettes PS3
  * activer / désactiver les contrôleurs sur Gpio
  * définir le nombre de contrôleurs Gpio
  * activer / désactiver Steam Controleurs
  * activer / désactiver les contrôleurs via le pilote DB9
  * activer / désactiver le contrôleurs Gamecon 
  * activer / désactiver les contrôleurs Xarcade 
* **F - Langue et clavier**
  * définir la langue
  * définir l'agencement du clavier
  * définir le fuseau horaire 
* **G - Mises à jour**
  * activer / désactiver de contrôle de présence des mises à jour
  * définir le type de mises à jour 
* **H - Configuration globale émulateurs**
  * définir la résolution en jeu
  * définir des shaders automatique
  * activer / désactiver le pixel perfect 
  * définir un ratio pour tout les émulateurs
  * activer / désactiver l'effet smooth en jeu
  * acitver /désactiver le rembobinage 
  * activer / désactiver l'auto sauvegarde 
  * définir et activer votre compte Retroachievement 
  * definir le driver des entrées pour retroarch 
  * definir les platformes disponible en mode demo
  * definir la durée de passage d'un jeu en mode demo
  * definir la durée de l'ecran d'information du mode demo 
  * activer / désactiver la Traduction automatique 
  * activer / désactiver l'option Arcade system dans Emulationstation 
* **I - Configuration des émulateurs par Core** 
* **J - Configuration Netplay**
  * activer / désactiver le netplay
  * définir le surnom afficher dans le lobby Netplay
  * définir le port réseau
  * activer / désactiver le MITM



### 1 - Variables disponibles

* **videomode** : défini le **mode vidéo** \(utilisez **tvservice** pour **obtenir les valeurs compatibles**\). Utilisez _**default**_ pour **désactiver le switch videomode** \(pour les écrans crt\)

  exemple : `global.videomode=CEA 4 HDMI`

* **shaderset** : défini le **set de shaders pour tous les émulateurs** \(none, retro, scanlines\) voir [Configuration des shaders](/v/francais/tutoriels/jeux/generalite/configuration-des-shaders)

  exemple : `global.shaderset=retro`

* **integerscale** : active / desactive **l'option integerscale "pixel perfect" dans les jeux**

  exemple : `global.integerscale=0`

* **shaders** : défini le **chemin vers le "shader"** ou le **"shader preset"** \(glsl ou glslp\)

  exemple : `global.shaders=/recalbox/share_init/shaders/scanline.glslp`

* **ratio** : défini le **ratio utilisé pour les jeux** \(_16/9_, _4/3_, _16/10_, _auto_ ou _custom_\)

  exemple : `global.ratio=16/9`

* **smooth** : **lissage** des jeux

  exemple : `global.smooth=0`

* **rewind** : active / désactive le **rembobinage en jeu** \(peut ralentir l'émulation\)

  exemple : `global.rewind=1`

* **autosave** : active / désactive **l'option permettant de sauvegarder / charger** automatiquement lors du lancement / fermeture d'un jeu

  exemple : `global.autosave=0`

* **retroachievements** : active / désactive les **retroachievements** en jeu

  exemple : `global.retroachievements=0`

* **retroachievements hardcore mode** : active / désactive le **mode hardcore** de retroachievements en jeu \(désactivation du rembobinage et des savestates\)

  exemple : `global.retroachievements.hardcore=0`

* **retroachievements username** : défini votre nom d'utilisateur retroachievements

  exemple : `global.retroachievements.username=`

* **retroachievements password** : défini votre **mot de passe retroachievements**

  exemple : `global.retroachievements.password=`

* **inputdriver** : **force le pilote** "input" utilisé **dans retroarch** \(auto, sdl2, udev\)

  exemple : `global.inputdriver=auto`



### **2 - La configuration par défaut :**

```text
global.videomode=CEA 4 HDMI
global.shaderset=none
global.integerscale=0
global.shaders=
global.ratio=auto
global.smooth=1
global.rewind=1
global.autosave=0
global.retroachievements=0
global.retroachievements.hardcore=0
global.retroachievements.username=
global.retroachievements.password=
global.inputdriver=auto
```

* Si vous souhaitez **activer le lissage des jeux** pour tous les émulateurs, **définissez** `global.smooth=1`.
* Si vous souhaitez **ajouter des scanlines** pour tous les émulateurs, **définissez** `global.shaders=/recalbox/share_init/shaders/scanline.glslp`.

## III - Configuration spécifique pour chaque émulateur

Chaque émulateur peut être **configuré de manière indépendante,** utilisez le nom du système et définissez les variables.

### 1 - Systèmes disponibles :

_3do_ _, amstradcpc_ _, apple2_ _, atari2600_ _, atari5200_ _, atari7800_ _, atarist , atomiswave , c64_ _, cavestory_ _, channelf_ _, colecovision_ _, dreamcast_ _, dos_ _, fba_ _, fba\_libretro_ _, fds_ _, gamegear_ _, gba_ _, gb_ _, gbc_ _, gw_ _, jaguar_ _, lutro_ _, lynx_ _, mame_ _, mastersystem_ _, megadrive_ _, moonlight_ _, msx_ _, msx1_ _, msx2_ _, n64_ _, nds_ _, naomi , nes_ _, neogeo_ _, neogeocd_ _, ngp_ _, ngpc_ _, o2em_ _, pcengine_ _, pcenginecd_ _, prboom_ _, psx_ _, satellaview_ _, scummvm_ _, sega32x_ _, segacd_ _, sg1000_ _, snes_ _, supergrafx_ _, vectrex_ _, virtualboy_ _, wswan_ _, wswanc_ _, zx81_ _, zxspectrum_ _, x68000_

### 2 - Liste des cores libretro de chaque système :

* **3d0 panasonic :** 4d0
* **amstradcpc :** cap32
* **atari800 :** atari800
* **atari2600 :** stella
* **atari5200 :** atari800
* **atari7800 :** prosystem
* **atarist :** hatari
* **atomiswave** : flycast
* **c64 :** vice
* **cavestory :** nxengine
* **colecovision :** bluemsx
* **fairchild :** freechaf
* **fba\_libretro :** fba\_alpha
* **gb / gbc :** gambatte - tgbdual -mgba
* **gba :** gpsp - mgba - meteor
* **gw :** gw
* **intellivision :** freeintv
* **jaguar:** virtualjaguar
* **lynx :** handy - mednafen\_lynx
* **lutro :** lutro
* **msx / msx1 / msx2:** bluemsx - fmsx
* **mame :** imame4all - mame2003 - mame2010 - mame2003-plus - mame2015
* **megadrive / mastersystem / gamegear / sega32x / segacd / sg1000 :** genesisplusgx - picodrive
* **n64 :** mupen64plus - glupen64
* **naomi** : flycast
* **nds :** desmume - melonds
* **neogeo :** imame4all - mame2003 - mame2010 - fba\_alpha
* **neogeocd:** fba\_alpha
* **nes / fds :** fceumm - fceunext - nestopia
* **ngp / ngpc :** mednafen\_ngp
* **o2em :** o2em
* **pc98 :** np2kai
* **pcengine / pcenginecd /supergrafx :** mednafen\_supergrafx - pce
* **pokémon mini :** pokemini
* **prboom :** prboom
* **psx :** pcsx\_rearmed - mednafen\_psx - mednafen\_psx\_hw
* **scummvm :** scummvm
* **sharp x68000 :** px68k
* **sinclair zx spectrum /sinclair zx81:** fuse
* **snes / satellaview /sufami turbo :** snes9x2005 - snes9x2010 - snes9x
* **thomson :** theodore
* **videopack :** o2em
* **virtualboy :** vb
* **vectrex :** vecx
* **wswan / wswanc :** mednafen\_wswan
* **zx81 :** zx81
* **zxspectrum :** fuse

### 3 - Variables disponibles :

* **videomode** : défini **le mode vidéo** \(utilisez tvservice pour obtenir les valeurs compatibles\).

  exemple : `snes.videomode=CEA 4 HDMI`

* **integerscale** : active / désactive **integerscale "pixel perfect"** dans les jeux

  exemple : \`snes.integerscale=0

* **shaders** : défini le **chemin vers le "shader"** ou le **"shader preset"** \(glsl ou glslp\)

  exemple : `snes.shaders=/recalbox/share_init/shaders/scanline.glslp`

* **ratio** : défini le **ratio utilisé pour les jeux** \(_16/9_, _4/3_, _16/10_, _auto_ ou _custom_\)

  exemple : `snes.ratio=4/3`

* **smooth** : **lissage des jeux**

  exemple : `snes.smooth=0`

* **rewind** : active / désactive le **rembobinage en jeu** \(peut ralentir l'émulation\)

  exemple : `snes.rewind=1`

* **autosave** : active / désactive **l'option permettant de sauvegarder / charger** automatiquement lors du lancement / fermeture d'un jeu

  exemple : `global.autosave=0`

* **core** : défini **le core utilisé pour l'émulation** \(les cores libretro sont localisés dans /usr/lib/libretro\)

  exemple : `snes.core=snes9x_next`

* **emulator** : défini **l'émulateur utilisé pour l'émulation** \(les émulateurs sont : retorarch, fba2x, mupen64\)

  exemple : `neogeo.emulator=fba2x`

* **configfile** : ****force le chargement ****de **votre propre fichier de configuration**.  
  Recalbox **n'automatisera pas** la configuration de l'émulateur.

  exemple : `snes.configfile=/path/to/my/configfile.cfg`

## IV - Le fichier recalbox.conf par défaut <a id="iii-le-fichier-recalbox-conf-par-defaut-pour-rpi3"></a>

Voici les liens des **recalbox.conf** par **default** pour le [Rpi1](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/rpi1/recalbox.conf), [Rpi2](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/rpi2/recalbox.conf), [Rpi3](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/rpi3/recalbox.conf), [X86](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/x86/recalbox.conf), [X86-64](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/x86_64/recalbox.conf) et [Xu4](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/xu4/recalbox.conf).

####  **Exemple du recalbox.conf du Rpi3 :**

```text
# System Variable
# You can configure your recalbox from here
# To set a variable, remove the first ; on the line



# ------------ A - System Options ----------- #
#    Uncomment the system.power.switch you use
;system.power.switch=ATX_RASPI_R2_6      # http://lowpowerlab.com/atxraspi/#installation
;system.power.switch=MAUSBERRY           # http://mausberry-circuits.myshopify.com/pages/setup
;system.power.switch=REMOTEPIBOARD_2003  # http://www.msldigital.com/pages/support-for-remotepi-board-2013
;system.power.switch=REMOTEPIBOARD_2005  # http://www.msldigital.com/pages/support-for-remotepi-board-plus-2015
;system.power.switch=WITTYPI             # http://www.uugear.com/witty-pi-realtime-clock-power-management-for-raspberry-pi
;system.power.switch=PIN56ONOFF          # https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-(EN)
;system.power.switch=PIN56PUSH           # https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-(EN)
;system.power.switch=PIN356ONOFFRESET    # https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-(EN)
;system.power.switch=PIN356PUSHRESET     # https://github.com/recalbox/recalbox-os/wiki/Add-a-start-stop-button-to-your-recalbox-(EN)

## fbcp FrameBuffer Copy Program
## For small TFT screen on GPIO and SPI
## See https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29 for details
## Needed for Waveshare 3.2" 3.5" TFT screen, 2.8" Adafruit screen
## See https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29
## for support and configuration details needed by /boot/config.txt
system.fbcp.enabled=0

## Splash screen duration
## 0: Video will be played for 20 seconds (default)
## -1: All the video will be played (it won't be stopped automatically)
## >0 : Time before the video will be stopped (in seconds)
system.splash.length=0

## Recalbox Manager (http manager)
system.manager.enabled=1
## Currently, only version 2 is available
system.manager.version=2

## Recalbox security
# enforce security
# samba password required
# disable virtual gamepads
system.security.enabled=0

## Recalbox API (REST)
system.api.enabled=0

## Allow a specific resolution for ES only from the command : tvservice -m [MODE]
## Leave commented for the default usual behaviour
;system.es.videomode=CEA 4 HDMI

## EmulationStation
### menu style
### default -> default all options menu
### none -> no menu except the game search menu
### bartop -> less menu, only needed for bartops
emulationstation.menu=default
### Select a system to show on boot (use rom directory name) (string)
emulationstation.selectedsystem=favorites
### Show the gamelist of the first or selected system on boot (0,1)
emulationstation.bootongamelist=0
### Disable system view. ES will boot and show ONLY the first or selected system (0,1)
emulationstation.hidesystemview=0
### Parse Gamelists only. Show only games listed in gamelist.xml files (0,1)
emulationstation.gamelistonly=0
### Force basicgameList view to be displayed, even if your game systems are scraped (0,1)
emulationstation.forcebasicgamelistview=0

## Videosnaps
### Delay before videosnaps start, in millisecond. Default: 2s
;emulationstation.videosnaps.delay=2000
### Video loop times. 0 = no video. 1 or more = the video loops x times before fading out
;emulationstation.videosnaps.loop=1

## Scrapers
### ScreenScraper.fr
### Force media region - if not defined, region is taken from system.language. Default: us
;scraper.screenscraper.region=eu
### Force text language - if not defined, region is taken from system.language. Default: en
;scraper.screenscraper.language=fr
### Choose the media to download among:
### screenshot: game screenshot
### title     : game title screenshot
### box2d     : Front case
### box3d     : 3D rendered case
### mixv1     : Recalbox special mix image V1 (default)
### mixv2     : Recalbox special mix image V2
;scraper.screenscraper.media=mixv1
### ScreenScraper account
;scraper.screenscraper.user=
;scraper.screenscraper.password=

## Emulator special keys
## default -> default all special keys
## nomenu -> cannot popup the emulator menu
## none -> no special keys in emulators
system.emulators.specialkeys=default

## Show or hide kodi in emulationstation (0,1)
kodi.enabled=1
## Start kodi at launch (0,1)
kodi.atstartup=0
## set x button shortcut (0,1)
kodi.xbutton=1

## Allow a specific resolution for Kodi only from the command : tvservice -m [MODE]
## By default is using the default resolution of your screen
kodi.videomode=default

## Kodi can wait for a network component before starting
## waithost is the ip or hostname that must answer to a ping to validate the availability
## waittime is the maximum time waited when kodi boots
## if waitmode is required, kodi will not start if the component is not available
## if waitmode is wish, kodi will start if the component is not available
## if waitmode is not set or has another value, kodi will start immediately
;kodi.network.waitmode=required
;kodi.network.waittime=10
;kodi.network.waithost=192.168.0.50

## Hyperion
## Hyperion allows you to use an ambilight like led system on your recalbox
## Use hypercon to create your configuration file, and copy it in /recalbox/share/system/configs/hyperion/hyperion.config.json
hyperion.enabled=0


# ------------ B - Network ------------ #
## Set system hostname
system.hostname=RECALBOX
## Activate wifi (0,1)
wifi.enabled=0
## Set wifi region
## More info here: https://github.com/recalbox/recalbox-os/wiki/Wifi-country-code-(EN)
wifi.region=US
## Wifi SSID (string)
;wifi.ssid=new ssid
## Wifi KEY (string)
## after rebooting the recalbox, the "new key" is replace by a hidden value "enc:xxxxx"
## you can edit the "enc:xxxxx" value to replace by a clear value, it will be updated again at the following reboot
## Escape your special chars (# ; $) with a backslash : $ => \$
;wifi.key=new key

## Wifi - static IP
## if you want a static IP address, you must set all 3 values (ip, gateway, and netmask)
## if any value is missing or all lines are commented out, it will fall back to the
## default of DHCP
;wifi.ip=manual ip address
;wifi.gateway=new gateway
;wifi.netmask=new netmask

# secondary wifi (not configurable via the user interface)
;wifi2.ssid=new ssid
;wifi2.key=new key

# third wifi (not configurable via the user interface)
;wifi3.ssid=new ssid
;wifi3.key=new key

## Samba share
system.samba.enabled=1
### Virtual Gamepads
system.virtual-gamepads.enabled=1
### SSH
system.ssh.enabled=1

# ------------ C - Audio ------------ #
## Set the audio device (auto, hdmi, jack)
audio.device=auto
## Set system volume (0..100)
audio.volume=90
## Enable or disable system sounds in ES (0,1)
audio.bgmusic=1



# -------------- D - Controllers ----------------- #
# Enable support for standard bluetooth controllers
controllers.bluetooth.enabled=1
# Enable ERTM
controllers.bluetooth.ertm=0


## Please enable only one of these
# -------------- D1 - PS3 Controllers ------------ #
##Enable PS3 controllers support
controllers.ps3.enabled=1
## Choose a driver between bluez, official and shanwan
## bluez -> bluez 5 + kernel drivers, support official and shanwan sisaxis
## official -> sixad drivers, support official and gasia sisaxis
## shanwan -> shanwan drivers, support official and shanwan sisaxis
controllers.ps3.driver=bluez


# ------------ D2 - GPIO Controllers ------------ #
## GPIO Controllers
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
## mk_gpio arguments, map=1 for one controller, map=1,2 for 2 (map=1,map=1,2)
controllers.gpio.args=map=1,2
## Custom mk_gpio arguments,
## map=5 gpio1=Y-,Y+,X-,X+,start,select,a,b,tr,y,x,tl,hk  for one controller,
## map=5 gpio1=pin1,pin2,pin3,.....,pin12,pin13
## map=5,6 gpio1=Y-,Y+,X-,X+,start,select,a,b,tr,y,x,tl,hk gpio2=Y-,Y+,X-,X+,start,select,a,b,tr,y,x,tl,hk for 2 (map=5,map=5,6)
## map=5,6 gpio1=gpiox,gpioy,gpioz,.....,gpiou,gpiov gpio2=gpiox,gpioy,gpioz,.....,gpiou,gpiov
# where gpiox,gpioy,gpioz ... are NOT pin numbers on the connector, BUT location gpio numbered as in 
# https://www.raspberrypi-spy.co.uk/wp-content/uploads/2012/06/Raspberry-Pi-GPIO-Layout-Model-B-Plus-rotated-2700x900.png
## Set pin to -1 to disable it
# controllers.gpio.args=map=5,6 gpio=4,17,27,22,10,9,25,24,23,18,15,14,2 gpio2=11,5,6,13,19,26,21,20,16,12,7,8,3
## MCP configuration : GPIO and MCP can be used together. You can mix them.
## map=0x20,0x21 for 2 mcp23017 on i2c bus
#controllers.gpio.args=map=0x20,0x21,5,6 gpio=4,17,27,22,10,9,25,24,23,18,15,14,-1 gpio2=11,5,6,13,19,26,21,20,16,12,7,8,-1



# ------------ D3 - Steam Controllers ------------ #
## Enable steam controller service
controllers.steam.enabled=0


## DB9 Controllers
## Enable DB9 drivers for atari, megadrive, amiga controllers (0,1)
controllers.db9.enabled=0
## db9 arguments
controllers.db9.args=map=1

## Gamecon controllers
## Enable gamecon controllers, for nes, snes, psx (0,1) 
controllers.gamecon.enabled=0
## gamecon_args
controllers.gamecon.args=map=1

## XGaming's XArcade Tankstik and other compatible devices
controllers.xarcade.enabled=1



# ------------ F - Language and keyboard ------------ #
## Set the language of the system (fr_FR,en_US,en_GB,de_DE,pt_BR,es_ES,it_IT,eu_ES,tr_TR,zh_CN)
system.language=en_US
## set the keyboard layout (fr,en,de,us,es)
;system.kblayout=us
## Set you local time
## Select your timezone from : ls /usr/share/zoneinfo/ (string)
;system.timezone=Europe/Paris



# ------------ G - UPDATES ------------ #
## Automatically check for updates at start (0,1)
updates.enabled=1
# Update type : default to stable
updates.type=stable


# ------------ H - HERE IT IS - GLOBAL EMULATOR CONFIGURATION ------------ #
## The global value will be used for all emulators, except if the value
## is redefined in the emulator

## Set game resolution for emulators
## select your mode from the command : tvservice -m [MODE]
## CEA 5 HDMI : 1920x1080 @ 60Hz 16:9, clock:74MHz interlaced 
## CEA 4 HDMI : 1280x720 @ 60Hz 16:9, clock:74MHz progressive
## use 'default' for using the default resolution
## use 'auto' : switches to CEA 4 HDMI if supported, else keep the current resolution
## (string)
global.videomode=CEA 4 HDMI

## Shader set 
## Automatically select shaders for all systems
## (none, retro, scanlines)
global.shaderset=none

## Once enabled, your screen will be cropped, and you will have a pixel perfect image (0,1)
global.integerscale=0

## Set gpslp shader for all emulators (prefer shadersets above). Absolute path (string)
global.shaders=

## Set ratio for all emulators (auto,4/3,16/9,16/10,custom)
global.ratio=auto

## Set smooth for all emulators (0,1)
global.smooth=1

## Set rewind for all emulators (0,1)
global.rewind=1

## Set autosave/load savestate for all emulators (0,1)
global.autosave=0

## Enable retroarchievements (0,1)
## Set your www.retroachievements.org username/password
## Escape your special chars (# ; $) with a backslash : $ => \$
global.retroachievements=0
global.retroachievements.hardcore=0
global.retroachievements.username=
global.retroachievements.password=

## Set retroarch input driver (auto, udev, sdl2)
## If you don't have issues with your controllers, let auto
global.inputdriver=auto

## If you do not want recalboxOS to generate the configuration for all emulators (string)
;global.configfile=/path/to/my/configfile.cfg

## Demo screensaver parameters
## Set the system list from which ES will run random games.
## Empty list or unexisting key means all available systems
global.demo.systemlist=3do,amigacd32,atari2600,atari5200,atari7800,daphne,fba_libretro,fds,gamegear,gba,lynx,mame,mastersystem,megadrive,neogeo,nes,ngpc,pcengine,sega32x,sg1000,snes
## Default demo game sessions last 90s. Change this value if you want shorter or longer sessions
;global.demo.duration=90
## Default game info screen duration lasts 6s. Change this value if you want shorter or longer info screens.
;global.demo.infoscreenduration=6

## Retroarch AI Translation service
## Comment out or set to 0 the following key if you don't want the AI service
global.translate=1
## Set the source and the target languages.
## Allowed language list: EN, ES, FR, IT, DE, JP, NL, CS, DA, SV, HR, KO, ZH_CN, ZH_TW, CA, BG, BN, EU, AZ, AR, SQ,
##                        AF, EO, ET, TL, FI, GL, KA, EL, GU, HT, IW, HI, HU, IS, ID, GA, KN, LA, LV, LT, MK, MS,
##                        MT, NO, FA, PL, PT, RO, RU, SR, SK, SL, SW, TA, TE, TH, TR, UK, UR, VI, CY, YI
## Setting the translate.from key to a specified language may speed up or give more accurate results
## If translate.to key is commented, the default value is extracted from system.language or, if system.language is
## undefined, set to auto (=EN).
global.translate.from=auto
global.translate.to=auto
## zTranslate API Key
## go to https://ztranslate.net and create an account.
## validate your account, then log in and go to the settngs page
## Look for the API Key at the bottom of the page, then uncomment the following key and paste your API Key:
;global.translate.apikey=YOUR_API_KEY_HERE
## Other translation service
## If you want to use another translation service or a custom API call, use this key to
## specify the url to call. If the key is not empty, it is used instead of zTranslation's API Key
;global.translate.url=

## Arcade metasystem
## Activate the Arcade metasystem to group all games from piFBA, FBN (libretro), MAME and optionally Neogeo
## into a single "Arcade" system.
;global.arcade=1
## You may want to specify its position in the system list. (Default: 0)
## Negatives values may be used to tart from the end (-1 = last position)
;global.arcade.position=0
## Include NeoGeo or not (default: 1)
;global.arcade.includeneogeo=1
## Hide included system or leave them in the system list (default: 1)
;global.arcade.hideoriginals=1


# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configurations here
## Here is the snes example
;snes.videomode=CEA 4 HDMI
;snes.core=snes9x2010
;snes.shaders=/recalbox/share/shaders/shaders_glsl/mysnesshader.gplsp
;snes.ratio=16/9
;snes.smooth=0
;snes.rewind=1
;snes.autosave=0
;snes.emulator=libretro
;snes.integerscale=0
## If you do not want recalboxOS to generate the configuration for the emulator: 
;snes.configfile=/path/to/my/configfile.cfg

## Default cores for RPi3
snes.core=snes9x2010

## NeoGeo emulator 
## You can use pifba or a libretro core (fba2x,libretro)
neogeo.emulator=libretro
## If you set libretro as neogeo.emulator, the line below sets the retroarch core (fbneo, mame2000)
neogeo.core=fbneo

## N64 emulator is configured to display a screen with a 640x480 resolution (native n64 resolution)
## So you must use one of these video modes (DMT 4 HDMI,CEA 1 HDMI).
## If your screen is not compatible with one of these video modes, please check the recalbox's wiki.
n64.videomode=DMT 4 HDMI
## If you are using a CRT screen, please change the setting above with this one : 
# n64.videomode=default

## Dreamcast emulator
## Like N64, such a CPU intensive emulator needs a small resolution
## Consider DMT 4 HDMI (640*480) or DMT 9 HDMI (800*600). If you have a black screen on dreamcast, try DMT 9 HDMI here
dreamcast.videomode=DMT 4 HDMI

## Demo screensaver parameters
## Include or exclude a particular system from the demo screensaver
## You may change the global.demo.systemlist key or include/exclude every single system
;snes.demo.include=0
## Set the session duration for a particular system
;snes.demo.duration=90

# ------------ J - NETPLAY PARAMETERS ----------- #
## All these values are handled by Recalbox itself
global.netplay=1
global.netplay.nickname=
global.netplay.port=55435
global.netplay.relay=
global.netplay.systems=fba_libretro,mame,mastersystem,megadrive,neogeo,nes,pcengine,sega32x,sg1000,snes,supergrafx
global.netplay.lobby=http://lobby.libretro.com/list/

## Configurations generated by Recalbox
```

