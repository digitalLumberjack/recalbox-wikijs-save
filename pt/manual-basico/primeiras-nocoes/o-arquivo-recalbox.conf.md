---
title: O arquivo recalbox.conf
---

# O arquivo recalbox.conf

## I - Introdução <a id="i-introducao"></a>

**Recalbox** possui uma **ferramenta de configuração avançada** chamada `recalbox.conf`que permite **alterar opções que não estão disponíveis** no **emulationstation.**

**Para editá-lo**, você pode usar:

* **A maneira mais fácil** é usar [o web manager](https://www.youtube.com/watch?v=pxq_8RXSRjg).  
  Você precisa atualizar a página manualmente, caso contrário, verá a versão sem as modificações \(Seção - recalbox.conf\).  
  O último é **acessível via**:

  * **Windows:** **`http://recalbox/`** ou **digite seu endereço IP.**
  * **Linux/Mac:** **`http://recalbox.local/`** ou **digite seu endereço IP.**

  No menu esquerdo, agora vá para **`recalbox.conf`**  

* As pastas do Recalbox compartilhadas na rede local. O arquivo**`recalbox.conf`**está disponível no diretório chamado **`system`**. 
* Faça [acesso root via Terminal](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) e edite o arquivo em _system_ no local**`/recalbox/share/system/recalbox.conf`.**


>**Information :**  
>O **`;`** **no início de uma linha**, significa que esta está **desativada**.  
>**Remova`;`** para **ativar a opção** associada à linha.
>
>**Para usuários do Windows:**  
>Se você não usar a opção pelo gerenciador da web, deverá usar um editor de texto real, como [**Notepad++**](https://notepad-plus-plus.org/downloads/).  
>O editor de texto **padrão** no Windows **insere caracteres incorretos** no arquivo, **tornando-o ilegível pelo sistema**.
{.is-info}

## II - Opções disponíveis <a id="ii-opcoes-disponiveis"></a>

* **A - Opções do sistema**
  * definir gerenciamento de energia
  * ativar / desativar o fbcp \(framebuffer usado para telas gpio / spi\)
  * definir tempo para vídeos de inicialização
  * ativar / desativar o início automático do recalbox-manager
  * defina a versão do recalbox-manager usado
  * ativar / desativar a opção de segurança
  * ativar / desativar a API Recalbox
  * definir o modo de vídeo do Emulationstation
  * definir estilo de menu para o Emulationstation
  * definir opções de inicialização / exibição do Emulationstation
  * definir opções e sua conta do ScreenScrapers
  * definir o gerenciamento de atalhos especiais no jogo
  * esconder Kodi no Emulationstation
  * iniciar o Kodi na inicialização do sistema
  * definir o modo de vídeo kodi
  * atribua o botão X ao iniciar o Kodi
  * definir atraso de rede Kodi
  * ativar / desativar Hyperion 
* **B - Rede**
  * definir o "hostname
  * definir a região wifi
  * digitar a chave wifi e SSID
  * definir um "ip estático" no wifi
  * definir até 3 redes wifi \(o sistema se conectará à primeira disponível\)
  * ativar / desativar o compartilhamento de samba
  * ativar / desativar gamepads virtuais
  * ativar / desativar ssh 
* **C - Áudio**
  * definir saída de áudio
  * definir o volume do áudio
  * ativar / desativar a música de fundo no Emulationstation 
* **D - Controles**
  * ativar / desativar controles bluetooth
  * ativar / desativar controles PS3
  * selecione o driver para os controles PS3
  * ativar / desativar controles no Gpio
  * definir o número de controles Gpio
  * ativar / desativar os controles Steam
  * ativar / desativar controles via driver DB9
  * ativar / desativar controles Gamecon
  * ativar / desativar controles Xarcade 
* **F - Idioma e teclado**
  * definir idioma
  * definir o layout do teclado
  * definir o fuso horário 
* **G - Atualizações**
  * ativar / desativar a verificação de presença de atualização
  * definir o tipo de atualizações 
* **H - Configurações globais de emuladores**
  * definir resolução no jogo
  * definir shaders/sombreadores automáticos
  * ativar / desativar pixel perfeito
  * defina uma proporção para todos os emuladores
  * ativar / desativar o efeito smooth/suavização no jogo
  * ativar / desativar rewind/rebobinar
  * ativar / desativar o salvamento automático
  * defina e ative sua conta de Retroachievement/Conquistas
  * defina o driver de entrada para o Retroarch
  * definir as plataformas disponíveis no modo de demonstração
  * define a duração da passagem de um jogo no modo de demonstração
  * definir a duração da tela de informações do modo de demonstração
  * ativar / desativar a tradução automática
  * ativar / desativar a opção do sistema Arcade no Emulationstation 
* **I - Configuração de emuladores por Núcleo** 
* **J - Configuração Netplay/Jogo em rede**
  * ativar / desativar netplay
  * definir o apelido a ser exibido no lobby do Netplay
  * definir porta de rede
  * ativar / desativar MITM

### 1 - Variáveis ​​disponíveis <a id="1-variaveis-disponiveis"></a>

* **videomode** : defina o modo de vídeo \(use o tvservice para obter valores compatíveis\). Use o padrão para desativar a opção de modo de vídeo \(para telas CRT\) exemplo: `global.videomode=CEA 4 HDMI`
* **shaderset** : defina o conjunto de shaders/sombreamento para todos os emuladores \(nenhum, retro, linhas de verificação\), consulte a [configuração de shaders](https://app.gitbook.com/@recalbox/s/tutorials/v/portugues/jogos/generalidade/configuracao-dos-shaders-sombreamento)

  exemplo:`global.shaderset=retro`

* **integerscale** : ativar / desativar a opção de escala inteira "pixel perfeito" nos jogos

  exemplo : `global.integerscale=0`

* **shaders** : defina o caminho para o "shader" ou a "predefinição de shader" \(glsl ou glslp\)

  exemplo : `global.shaders=/recalbox/share_init/shaders/scanline.glslp`

* **ratio** : defina a proporção usada para jogos \(_16/9_, _4/3_, _16/10_, _auto_ ou _custom_\)

  exemplo : `global.ratio=16/9`

* **smooth** : suavização dos jogos

  exemplo : `global.smooth=0`

* **rewind** : ativar / desativar o rebobinamento \(_rewind_\) no jogo \(pode diminuir a velocidade de emulação\)

  exemplo : `global.rewind=1`

* **autosave** :ativar / desativar a opção para salvar / carregar automaticamente ao iniciar / fechar um jogo

  exemplo : `global.autosave=0`

* **retroachievements** :ativar / desativar as conquistas nos jogos

  exemplo : `global.retroachievements=0`

* **retroachievements hardcore mode** : ativar / desativar o modo de conquista hardcore nos jogos \(desativando rebobinar e savestates\)

  exemplo : `global.retroachievements.hardcore=0`

* **retroachievements username** : defina seu nome de usuário das conquistas

  exemplo : `global.retroachievements.username=`

* **retroachievements password** : defina sua senha das conquistas

  exemplo : `global.retroachievements.password=`

* **inputdriver** : forçar o driver "input" usado no **retroarch** \(auto, sdl2, udev\)

  exemplo : `global.inputdriver=auto`

​

### **2 -** A configuração padrão: <a id="2-a-configuracao-padrao"></a>

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

* Se você deseja ativar a suavização de jogos para todos os emuladores, defina`global.smooth=1`.
* Se você deseja adicionar o shader _scanlines_ para todos os emuladores, defina`global.shaders=/recalbox/share_init/shaders/scanline.glslp`.

## III - Configuração específica para cada emulador <a id="iii-configuracao-especifica-para-cada-emulador"></a>

Cada emulador pode ser **configurado independentemente**, use o nome do sistema e defina as variáveis.

​

### 1 - Sistemas disponíveis: <a id="1-sistemas-disponiveis"></a>

_, 3do_ _, amstradcpc_ _, apple2_ _, atari2600_ _, atari5200_ _, atari7800_ _, atarist , atomiswave , c64_ _, cavestory_ _, channelf_ _, colecovision_ _, dreamcast_ _, dos_ _, fba_ _, fba\_libretro_ _, fds_ _, gamegear_ _, gba_ _, gb_ _, gbc_ _, gw_ _, jaguar_ _, lutro_ _, lynx_ _, mame_ _, mastersystem_ _, megadrive_ _, moonlight_ _, msx_ _, msx1_ _, msx2_ _, n64_ _, nds_ _, naomi , nes_ _, neogeo_ _, neogeocd_ _, ngp_ _, ngpc_ _, o2em_ _, pcengine_ _, pcenginecd_ _, prboom_ _, psx_ _, satellaview_ _, scummvm_ _, sega32x_ _, segacd_ _, sg1000_ _, snes_ _, supergrafx_ _, vectrex_ _, virtualboy_ _, wswan_ _, wswanc_ _, zx81_ _, zxspectrum_ _, x68000_

​

### 2 - Lista de núcleos libretro para cada sistema: <a id="2-lista-de-nucleos-libretro-para-cada-sistema"></a>

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

​

### 3 - Variáveis ​​disponíveis: <a id="3-variaveis-disponiveis"></a>

* **videomode** : defina o modo de vídeo \(use o tvservice para obter valores compatíveis\). 

  exemplo : `snes.videomode=CEA 4 HDMI`

* **integerscale** : ativar / desativar a opção de escala inteira "pixel perfeito" nos jogos

  exemplo : snes.integerscale=0

* **shaders** : defina o caminho para o "shader" ou a "predefinição de shader" \(glsl ou glslp\)

  exemplo : `snes.shaders=/recalbox/share_init/shaders/scanline.glslp`

* **ratio** : defina a proporção usada para jogos \(_16/9_, _4/3_, _16/10_, _auto_ ou _custom_\)

  exemplo : `snes.ratio=4/3`

* **smooth** : suavização dos jogos

  exemplo : `snes.smooth=0`

* **rewind** : ativar / desativar o rebobinamento \(_rewind_\) no jogo \(pode diminuir a velocidade de emulação\)

  exemplo : `snes.rewind=1`

* **autosave** : ativar / desativar a opção para salvar / carregar automaticamente ao iniciar / fechar um jogo

  exemplo : `global.autosave=0`

* **core** : defina o núcleo usado para emulação \(os núcleos do libretro estão localizados em /usr/lib/libretro\)

  exemplo : `snes.core=snes9x_next`

* **emulator** : defina o emulador usado para emulação \(os emuladores são: retroarch, fba2x, mupen64\)

  exemplo : `neogeo.emulator=fba2x`

* **configfile** : força o seu próprio arquivo de configuração a carregar. Recalbox não automatizará a configuração do emulador.

  exemplo : `snes.configfile=/path/to/my/configfile.cfg`

## IV - O arquivo recalbox.conf padrão <a id="iv-o-arquivo-recalbox-conf-padrao"></a>

Aqui estão os links do **recalbox.conf padrão** para o [Rpi1](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/rpi1/recalbox.conf), [Rpi2](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/rpi2/recalbox.conf), [Rpi3](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/rpi3/recalbox.conf), [X86](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/x86/recalbox.conf), [X86-64](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/x86_64/recalbox.conf) e [Xu4](https://gitlab.com/recalbox/recalbox/blob/master/package/recalbox-system/xu4/recalbox.conf).

​

####  **Exemplo do recalbox.conf do Rpi3 :** <a id="exemple-du-recalbox-conf-du-rpi3"></a>

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



