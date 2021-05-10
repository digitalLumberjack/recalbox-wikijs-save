---
title: O projeto Recalbox
---

# O projeto Recalbox

## Introdução <a id="introduction"></a>

 Um **console de retrogaming de código aberto**! O Recalbox.

**O Recalbox** permite reproduzir uma variedade de consoles e plataformas em sua sala, com facilidade!

O **RecalboxOS** é o **sistema operacional do projeto Recalbox**, um console de emulação **pronto para uso** baseado no **Raspberry Pi**, totalmente **gratuito e de código aberto**, e foi especialmente projetado para que **você possa criar o seu próprio em pouco tempo**.

O Recalbox oferece uma **ampla seleção de consoles e sistemas**, desde os primeiros terminais de arcade até plataformas como Playstation, passando pelo Nes e o Megadrive.

**RecalboOS** usa vários elementos que já existem, como ​[EmulationStation2](https://github.com/Aloshi/EmulationStation) como interface, [piFBA](https://github.com/digitalLumberjack/pifba) e [RetroArch](https://github.com/libretro/RetroArch) como emuladores, [Raspberry Pi NOOBS](https://github.com/raspberrypi/noobs) como sistema de instalação/recuperação \(_recovery_\).

O **RecalboxOS** pode ser descrito com uma palavra: **FÁCIL**. Queremos fornecer um sistema que seja o mais amigável e intuitivo possível. Não é necessário modificar uma infinidade de arquivos de configuração ou conectar-se no SSH. Basta instalar o sistema e jogar. A configuração do sistema operacional é feita através de um único arquivo chamado `recalbox.conf`. Ele permite uma configuração precisa de todos os emuladores!

Mas para **usuários avançados** que desejam uma **configuração mais avançada**, demos a eles a possibilidade de fazer um sistema à sua vontade **com** _**overloads**_ \(modifique somente se tiver certeza do resultado\).

## Dezenas de softwares de código aberto... reunidos em um único sistema operacional. <a id="dezenas-de-softwares-de-codigo-aberto-reunidos-em-um-unico-sistema-operacional"></a>

O **RecalboxOS** é baseado no sistema **GNU/Linux**. Ele inclui centenas de software de código aberto, desde o menor utilitário até seus emuladores e o _frontend_ \(interface\) do EmulationStation.

Desfrute de dezenas de emuladores do retroarch/libretro, o famoso Kodi Media Player e o _frontend_ personalizado do EmulationStation!

![](https://www.recalbox.com/images/opensource/opensource.png)

​

### Com homebrews e hacks. Descubra jogos nunca antes lançados em um console!

Homebrews são jogos criados do zero pelos desenvolvedores. Muitos são ótimas surpresas e farão com que você se divirta muito.

Hacks são modificações de jogos existentes. Eles pegam todo ou parte dos gráficos e jogabilidade de um jogo e divergem na história, na dificuldade e na atmosfera. Alguns são considerados sequências completas dos jogos originais, como Super Mario Bros 4 \(hack do Super Mario World\) ou Legend Of Zelda - Parallels Worlds \(hack de Legend Of Zelda - A link to the past\).

![](https://gblobscdn.gitbook.com/assets%2F-Ly_yBeDH04LSxQatRyA%2F-LyaJHLtvlytQLosKe8u%2F-LyaK3YeCNXzrqMjb1Ko%2Fimage.png?alt=media&token=a1f74c4a-d236-4ae3-9b8b-b6c8caa72897)

### 

### Media Center

Garantido pelo **Kodi**, o Recalbox também funciona como um **Media Center.** Ao conectá-lo à rede doméstica, você poderá reproduzir vídeos de qualquer dispositivo compatível \(roteador, computador\).

## Características <a id="caracteristicas"></a>

* Sistema :
  * [​](/fr/compatibilite/cartes-compatibles)[Os sistemas suportados](/fr/compatibilite/cartes-compatibles)
  * **Versão de FBA otimizada com suporte de 4 jogadores.**
  * **Compilado com buildroot :** O que significa que o sistema de ficheiro root só tem 150MB comprimido.
  * **O sistema de backup é baseado no NOOBS :**

    Possibilidade de instalar o sistema diretamente em um cartão SD, ou conseguindo a ultima versão na internet.

  * **Línguas suportadas pelo sistema :** Francês, Inglês, Espanhol, Alemão, Italiano, Português e outras se você quer participar!
  * **Interface :** Interface baseada no EmulationStation2 desenvolvida por Aloshi.
  * **Músicas de fundo na interface.**
  * **Gestão dos favoritos.**
* Rede :
  * **Acesso pela rede :** As pastas roms, capturas de tela e saves dos jogos.
  * **Suporte wifi e RJ45**
  * **Atualização via rede.**
* Controles :
  * Configuração dos controles diretamente da interface: uma vez a configuração feita, ela será compatível com todos os emuladores.
  * **Suporte integrado dos controles PS3, Xbox360, 8BitDo e Bluetooth :** Associe um deles e jogue!
  * **Presencia dos drivers GPIO :** Para utilizar comandos arcade ou os vossos comandos originais Nes, Snes, Megadrive, PSX.
  * Suporte dos comandos Xin-Mo 2 jogadores.
  * **Suporte de gamepad virtual** [Miroof's Virtual Gamepad](https://github.com/miroof/node-virtual-gamepads) : Use o seu smartphone como controle.
* **Funcionalidades** :
  * **Kodi Media Center :**
  * **Moonlight :** Transmite jogos em streaming na sua rede local ou pela Internet
  * **Netplay retrogaming :** Jogue em rede
  * **Retroarch AI :** Tradução dos textos em jogos.
  * **Scraper interno e externo.** Insira uma imagem, um vídeo e uma descrição para cada jogo.
  * **Vídeos instantâneos:** Apresentação de vídeo do jogo nos scrapes.

