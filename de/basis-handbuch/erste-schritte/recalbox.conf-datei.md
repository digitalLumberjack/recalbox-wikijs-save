---
title: Recalbox.conf-Datei
---

# Recalbox.conf-Datei

## Introduction <a id="introduction"></a>

Recalbox à un fichier de configuration avancée nommé`recalbox.conf` permettant de modifier des paramètres non accessibles depuis EmulationStation.

Il est possible d'éditer le fichier de plusieurs manières :

* Le webmanager \(le plus simple\), pour atteibndre le Webmanager:
  1. * Sous Windows: entrez `http://recalbox/` ou l'adresse IP de votre recalbox dans un navigateur.
     * Sous Linux ou MacOS: entrez `http://recalbox/` ou l'adresse IP de votre recalbox dans un navigateur.
  2. Accédez au menu `recalbox.conf` sur la gauche
* Utiliser les dossiers partagés de Recalbox. Le fichier est disponible dans le dossier nommé `system` 
* Vous pouvez vous connecter via un terminal, et éditer le fichier situé à l'emplacement `recalbox/share/system/recalbox.conf`


>**Pour les utilisateurs de Windows** : Si vous ne passez pas par le Webmanager, il est préférable d'utiliser un éditeur de texte comme **NotePad++**. Par défaut, l'éditeur de texte inclus dans Windows génère des mauvais caractères.
{.is-warning}


>Un point-virgule en début de ligne signifie que cette dernière est désactivée, enlever ce point-virgule permet d'activer la ligne en question.
{.is-info}

## I - Options disponibles <a id="i-available-options"></a>

* **A - System Options**
  * set system power switch option
  * set splash screen duration
  * enable / disable fbcp \(framebuffer for TFT screens on gpio/spi\)
  * enable / disable recalbox-manager auto start
  * set recalbox-manager version
  * enable / disable security
  * set emulationstation video mode
  * set menu style for emulationstation
  * set emulationstation boot/display options
  * set emulators special keys
  * hide kodi in emulationstation
  * start kodi on system startup
  * avoid x button to start kodi
  * set kodi video mode
  * set kodi network delay
* **B - Network**
  * set hostname
  * set wifi ssid and key
  * set up to 3 different wifi networks \(system will use the first that works\)
  * enable / disable samba
  * enable / disable virtual-gamepads
  * enable / disable ssh
* **C - Audio**
  * set output device
  * set audio volume
  * enable / disable background music in es
* **D - Controllers**
  * enable bluetooth controllers
  * enable steam controllers
  * select ps3 driver
  * enable / disable controllers on gpio
  * enable / disable controllers on marqs DB9
  * enable / disable controllers on marqs gamecon
  * enable / disable controllers xarcade
* **F - Language and keyboard**
  * set language
  * set keyboard layout
  * set time zone
* **G - UPDATES**
  * enable / disable update checking
  * set update type
* **H - EMULATOR CONFIGURATION - detailed below**
* \*\*I - EMULATORS CHOICES
* **J - NETPLAY CONFIGURATION**

## II - Configuration de l'émulateur <a id="ii-emulator-configuration"></a>

### 1 - Configuration globale <a id="1-global-configuration"></a>

Il est possible de régler les émulateurs dans le recalbox.conf. la variable nommée `global` défini les préférences par défaut pour l'ensemble des émulateurs.

**Variables disponibles :**

* **videomode** : défini le mode vidéo \(la commande tvservice permet de voir les valeurs compatibles\). Utiliser la valeur _default_ empêche le changement de mode vidéo au lancement de l'émulateur \(utile pour un écran crt\)

  exemple : `global.videomode=CEA 4 HDMI`

* **shaderset** : défini le shader utilisé \(none, retro, scanlines\), voir \[\[shaders configuration\|Shaders-configuration-\(EN\)\]\]

  exemple : `global.shaderset=retro`

* **integerscale** : active la mise à l'échelle par un facteur entier pour conserver l'aspect des pixels en jeu.

  exemple : `global.integerscale=0`

* **shaders** : défini le chemin absolu vers un shader \(glsl or glslp\)

  exemple : `global.shaders=/recalbox/share_init/shaders/scanline.glslp`

* **ratio** : défini l'aspect ratio pour les jeux \(_16/9_, _4/3_, _16/10_, _auto_ or _custom_\)

  exemple : `global.ratio=16/9`

* **smooth** : lisse ou non l'affichage des jeux

  exemple : `global.smooth=0`

* **rewind** : active le rembobinage dans les jeux \(peut entraîner une perte de performances en jeu\)

  exemple : `global.rewind=1`

* **autosave** : Permet d'activer la sauvegarde/chargement rapide lors du lancement ou de la sortie d'un jeu exemple : `global.autosave=0`
* **retroachievements** : Active les retroachievements en jeu exemple : `global.retroachievements=0`
* **retroachievements hardcore mode** : active le mode "hardcore" des retroachievements en jeu \(désactive des fonctions facilitant le jeu, telles que les savestates ou le rewind\)

  exemple : `global.retroachievements.hardcore=0`

* **retroachievements username** : permet d'entrer son nom d'utilisateur du site des retroachievements  example : `global.retroachievements.username=`
* **retroachievements password** : permet d'entrer son mot de passe d'utilisateur du site des retroachievements 

  example : `global.retroachievements.password=`

* **inputdriver** : force les pilotes d'entrées de Retroarch \(auto, sdl2, udev\)

  example : `global.inputdriver=auto`

La configuration par défaut :

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

Si vous souhaitez activer le lissage pour tous les émulateurs, utilisez :`global.smooth=1`.  
Si vous voulez activer les Scanline pour tous les émulateurs, utilisez :`global.shaders=/recalbox/share_init/shaders/scanline.glslp`.

### 2 - Configuration d'un émulateur spécifique <a id="2-specific-emulator-configuration"></a>

Chaque émulateur peut être configuré ici, utilisez juste le nom du système suivi de la variable souhaitée.

**Systèmes disponibles :**

_snes_ _, nes_ _, n64_ _, gba_ _, gb_ _, gbc_ _, fds_ _, gamecube_ _, wii_ _, virtualboy_ _, sg1000_ _, mastersystem_ _, megadrive_ _, gamegear_ _, sega32x_ _, segacd_ _, dreamcast_ _, neogeo_ _, mame_ _, fba_ _, fba\_libretro_ _, ngp_ _, ngpc_ _, gw_ _, vectrex_ _, lynx_ _, lutro_ _, wswan_ _, wswanc_ _, pcengine_ _, pcenginecd_ _, supergrafx_ _, atari2600_ _, atari7800_ _, atarist_ _, apple2_ _, amstradcpc_ _, c64_ _, colecovision_ _, msx_ _, msx1_ _, msx2_ _, dos_ _, scummvm_ _, o2em_ _, zxspectrum_ _, zx81_ _, prboom_ _, cavestory_ _, psx_ _, psp_ _, moonlight_

**Cores libretro disponibles :**

* **snes :** pocketsnes - snes9x\_next - catsfc - snes9x
* **nes / fds :** fceumm - fceunext - nestopia
* **n64 :** mupen64plus - glupen64
* **gamecube / wii :** dolphin
* **gb / gbc :** gambatte - tgbdual
* **gba :** gpsp - mgba - meteor
* **virtualboy :** vb
* **megadrive / mastersystem / gamegear / sega32x / segacd / sg1000 :** genesisplusgx - picodrive
* **dreamcast :** reicast
* **neogeo :** imame4all - mame2003 - mame2010 - fba
* **mame :** imame4all - mame2003 - mame2010
* **fba\_libretro :** fba
* **ngp / ngpc :** mednafen\_ngp
* **gw :** gw
* **vectrex :** vecx
* **lynx :** handy - mednafen\_lynx
* **lutro :** lutro
* **wswan / wswanc :** mednafen\_wswan
* **pcengine / pcenginecd /supergrafx :** mednafen\_supergrafx - pce
* **atari2600 :** stella
* **atari7800 :** prosystem
* **atarist :** hatari
* **c64 :** vice
* **amstradcpc :** cap32
* **apple2 :** lineapple
* **zx81 :** zx81
* **zxspectrum :** fuse
* **o2em :** o2em
* **colecovision :** bluemsx
* **dos :** dosbox
* **scummvm :** scummvm
* **msx / msx1 / msx2:** bluemsx - fmsx
* **prboom :** prboom
* **psx :** pcsx\_rearmed - mednafen\_psx
* **psp :** ppsspp
* **cavestory :** nxengine
* **moonlight :** moonlight

**Variables disponibles :**

\*\*\*\*

* **videomode** : défini le mode vidéo \(la commande tvservice permet de voir les valeurs compatibles\). Utiliser la valeur _default_ empêche le changement de mode vidéo au lancement de l'émulateur \(utile pour un écran crt\)

  exemple : `snes.videomode=CEA 4 HDMI`

* **integerscale** : active la mise à l'échelle par un facteur entier pour conserver l'aspect des pixels en jeu.

  exemple : `snes.integerscale=0`

* **shaders** : défini le chemin absolu vers un shader \(glsl or glslp\)

  exemple : `snes.shaders=/recalbox/share_init/shaders/scanline.glslp`

* **ratio** : défini l'aspect ratio pour les jeux \(_16/9_, _4/3_, _16/10_, _auto_ or _custom_\)

  exemple : `snes.ratio=4/3`

* **smooth** : lisse ou non l'affichage des jeux

  exemple : `snes.smooth=0`

* **rewind** : active le rembobinage dans les jeux \(peut entraîner une perte de performances en jeu\)

  exemple : `snes.rewind=1`

* **autosave** : Permet d'activer la sauvegarde/chargement rapide lors du lancement ou de la sortie d'un jeu exemple : `snes.autosave=0`
* **core** : permet de choisir le core utilisé par défaut \(les cores libretro sont situés dans /usr/lib/libretro\)

  exemple : `snes.core=snes9x_next`

* **emulator** : permet de choisir l'émulateur par défaut \(les émulateurs sont retroarch, fba2x, mupen64\)

  exemple : `neogeo.emulator=fba2x`

* **configfile** : permet de forcer l'utilisation de votre propre fichier de configuration, Recalbox ne va pas générer lui-même la configuration automatiquement

  exemple : `snes.configfile=/path/to/my/configfile.cfg`

## III - Le contenu par défaut du recalbox.conf sur Raspberry Pi 3 <a id="iii-the-default-recalbox-conf-for-rpi3"></a>

```text
Variable
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
## 1 or 2, depending on the manager version you wish
system.manager.version=2

## Recalbox security
# enforce security
#   samba password required
#   disable virtual gamepads
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
### Disable system view ES will boot and show ONLY the first or selected system (0,1)
emulationstation.hidesystemview=0
### Parse Gamelists only. Show only games listed in gamelist.xml files (0,1)
emulationstation.gamelistonly=0
### Force basicgameList view to be displayed, even if your game systems are scraped (0,1)
emulationstation.forcebasicgamelistview=0

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

# ------------ B - Network ------------ #
## Set system hostname
system.hostname=RECALBOX
## Activate wifi (0,1)
wifi.enabled=0
## Wifi SSID (string)
;wifi.ssid=new ssid
## Wifi KEY (string)
## after rebooting the recalbox, the "new key" is replace by a hidden value "enc:xxxxx"
## you can edit the "enc:xxxxx" value to replace by a clear value, it will be updated again at the following reboot
## Escape your special chars (# ; $) with a backslash : $ => \$
;wifi.key=new key

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

# ------------ D3 - Steam Controllers ------------ #
## Enable steam controller service
controllers.steam.enabled=0

## DB9 Controllers
## Enable DB9 drivers for atari, megadrive, amiga controllers (0,1)
controllers.db9.enabled=0
## db9 arguments
controllers.db9.args=map=1

## Gamecon controllers
## Enable gamecon controllers, for nes, snes psx (0,1) 
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
## (string)
global.videomode=CEA 4 HDMI

## Shader set 
## Automatically select shaders for all systems
## (none, retro, scanlines)
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

# ------------ I - EMULATORS CHOICES ----------- #
## You can override the global configuration here
## Here is the snes example
;snes.videomode=CEA 4 HDMI
;snes.core=snes9x_next
;snes.shaders=/recalbox/share/shaders/shaders_glsl/mysnesshader.gplsp
;snes.ratio=16/9
;snes.smooth=0
;snes.rewind=1
;snes.autosave=0
;snes.emulator=libretro
;snes.integerscale=0
## If you do not want recalboxOS to generate the configuration for the emulator : 
;snes.configfile=/path/to/my/configfile.cfg

## Default cores for RPi3
snes.core=snes9x_next
gba.core=mgba
mame.core=mame078
nes.core=fceunext

## NeoGeo emulator 
## You can use pifba or a libretro core (fba2x,libretro)
neogeo.emulator=libretro
## If you set libretro as neogeo.emulator, the line below sets the retroarch core (fba,imame4all)
neogeo.core=fba

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


# ------------ J - NETPLAY PARAMETERS ----------- #
## All the valuez here are handled by Recalbox itself
global.netplay=1
global.netplay.nickname=test
global.netplay.port=55430
global.netplay.relay=
global.netplay.systems=fba_libretro,mame,mastersystem,megadrive,neogeo,nes,pcengine,sega32x,sg1000,snes,supergrafx
global.netplay.lobby=http://lobby.libretro.com/list/




## Configurations generated by Recalbox
```

