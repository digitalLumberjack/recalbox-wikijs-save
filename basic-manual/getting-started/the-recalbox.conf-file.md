# The recalbox.conf file

## Introduction <a id="introduction"></a>

The recalbox has an advanced configuration tool named `recalbox.conf` that allows you to modify some options not available in emulationstation.

You can edit the file by either :

* The webmanager \(the easiest way\). The webmanager can be reached as follows:

  Windows: `http://recalbox/` or enter the IP address.

  Linux/Mac: `http://recalbox.local/` or enter the IP address.

  Now go on the left side to `recalbox.conf`

* Using the network shared folders on the recalbox. The file is available in a directory named `system` that contains `recalbox.conf`
* You can \[\[connect as root\|Root-access-on-terminal-\(EN\)\]\] and edit the file on the system at `/recalbox/share/system/recalbox.conf`


>**For Windows users** : If you dont use the option via the webmanager, you must use a real text editor software program, like **NotePad++**. The default windows text editor inserts bad characters in the file.
>{% endhint %}
>
>{% hint style="info" %}
>The **;** at line start means the line is disabled. Remove the **;** to enable the line.
>
{.is-warning}

## I - Available options <a id="i-available-options"></a>

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

## II - Emulator configuration <a id="ii-emulator-configuration"></a>

### 1 - Global configuration <a id="1-global-configuration"></a>

You can fine tune emulators in recalbox.conf. The `global` variable set the preferences for all emulators.

**Available variables :**

* **videomode** : set videomode \(use tvservice to get compatible values\). Use _default_ to disable videomode switch \(for crt\)

  example : `global.videomode=CEA 4 HDMI`

* **shaderset** : set the shader set for all emulators \(none, retro, scanlines\) see \[\[shaders configuration\|Shaders-configuration-\(EN\)\]\]

  example : `global.shaderset=retro`

* **integerscale** : enable integerscale "pixel perfect" in games

  example : `global.integerscale=0`

* **shaders** : set the absolute path to the shader or shader preset \(glsl or glslp\)

  example : `global.shaders=/recalbox/share_init/shaders/scanline.glslp`

* **ratio** : set the ratio for games \(_16/9_, _4/3_, _16/10_, _auto_ or _custom_\)

  example : `global.ratio=16/9`

* **smooth** : smooth games

  example : `global.smooth=0`

* **rewind** : enable rewind in games \(can slow down emulators\)

  example : `global.rewind=1`

* **autosave** : enable autosave/load in games during game's exit/start

  example : `global.autosave=0`

* **retroachievements** : enable retroachievements in games

  example : `global.retroachievements=0`

* **retroachievements hardcore mode** : enable retroachievements hardcore mode in games \(disable rewind and savestates\)

  example : `global.retroachievements.hardcore=0`

* **retroachievements username** : set your retroachievements username

  example : `global.retroachievements.username=`

* **retroachievements password** : set your retroachievements password

  example : `global.retroachievements.password=`

* **inputdriver** : force input drivers for retroarch \(auto, sdl2, udev\)

  example : `global.inputdriver=auto`

The default configuration :

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

If you want to enable smoothing for all emulators, set `global.smooth=1`. If you want to add a scanline shader for all emulators, set `global.shaders=/recalbox/share_init/shaders/scanline.glslp`.

### 2 - Specific emulator configuration <a id="2-specific-emulator-configuration"></a>

Each emulator can be configured here. Just use the name of the system and set variables.

**Available systems :**

_snes_ _, nes_ _, n64_ _, gba_ _, gb_ _, gbc_ _, fds_ _, gamecube_ _, wii_ _, virtualboy_ _, sg1000_ _, mastersystem_ _, megadrive_ _, gamegear_ _, sega32x_ _, segacd_ _, dreamcast_ _, neogeo_ _, mame_ _, fba_ _, fba\_libretro_ _, ngp_ _, ngpc_ _, gw_ _, vectrex_ _, lynx_ _, lutro_ _, wswan_ _, wswanc_ _, pcengine_ _, pcenginecd_ _, supergrafx_ _, atari2600_ _, atari7800_ _, atarist_ _, apple2_ _, amstradcpc_ _, c64_ _, colecovision_ _, msx_ _, msx1_ _, msx2_ _, dos_ _, scummvm_ _, o2em_ _, zxspectrum_ _, zx81_ _, prboom_ _, cavestory_ _, psx_ _, psp_ _, moonlight_

**Available libretro cores :**

* **snes :** pocketsnes - snes9x\_next - catsfc - snes9x
* **nes / fds :** fceumm - fceunext - nestopia
* **n64 :** mupen64plus - glupen64
* **gamecube / wii :** dolphin
* **gb / gbc :** gambatte - tgbdual
* **gba :** gpsp - mgba - meteor
* **virtualboy :** vb
* **megadrive / mastersystem / gamegear / sega32x / segacd / sg1000 :** genesisplusgx - picodrive
* **dreamcast :** reicast
* **neogeo :** imame4all - mame2003 - mame2010 - fbneo
* **neogeo CD** : fbneo
* **mame :** imame4all - mame2003 - mame2010
* **fba\_libretro :** fbneo
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
* **naomi** : flycast
* **Intellvision** :   freeintv
* **pc98** : np2kai
* **pc88** :  quasi88
* **x68000** : px68k
* **x1** : x1



**Available variables :**

* **videomode** : set videomode \(use tvservice to get compatible values\).

  example : `snes.videomode=CEA 4 HDMI`

* **integerscale** : enable integerscale "pixel perfect" in games**.**

  example : `snes.integerscale=0`

* **shaders** : set the absolute path to the shader or shader preset \(glsl or glslp\).

  example : `snes.shaders=/recalbox/share_init/shaders/scanline.glslp`

* **ratio** : set the ratio for games \(_16/9_, _4/3_, _auto\_or \_custom_\)

  example : `snes.ratio=4/3`

* **smooth** : smooth games

  example : `snes.smooth=0`

* **rewind** : enable rewind in games \(can slow down emulators\)

  example : `snes.rewind=1`

* **autosave** : enable autosave/load in games during game's exit/start

  example : `snes.autosave=0`

* **core** : select the core for the emulation \(libretrocores are located in /usr/lib/libretro\)

  example : `snes.core=snes9x_next`

* **emulator** : select the emulator for the emulation \(emulators are retroarch, fba2x, mupen64\)

  example : `neogeo.emulator=fba2x`

* **configfile** : force your own configuration file to be loaded. The recalbox will not automatize emulator configuration

  example : `snes.configfile=/path/to/my/configfile.cfg`



## III - The default recalbox.conf for rpi3Variable <a id="iii-the-default-recalbox-conf-for-rpi3"></a>

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
# defaults to dhcp. uncomment for static ip
;wifi2.ip=manual ip address
;wifi2.gateway=new gateway
;wifi2.netmask=new netmask

# third wifi (not configurable via the user interface)
;wifi3.ssid=new ssid
;wifi3.key=new key
# defaults to dhcp. uncomment for static ip
;wifi3.ip=manual ip address
;wifi3.gateway=new gateway
;wifi3.netmask=new netmask

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

