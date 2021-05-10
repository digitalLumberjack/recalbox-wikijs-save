---
title: Conectando seu recalbox a um monitor CRT usando HDMI
---

# Conectando seu recalbox a um monitor CRT usando HDMI


>CUIDADO
>
>É **IMPERATIVO** ter a versão **4.1 STABLE do Recalbox** para que essas modificações funcionem.
>
>**Para reproduzir seu Recalbox em uma tela CRT conectada em HDMI**, várias opções são possíveis, dependendo das conexões da sua tela.
>
>* Conexão via soquete HDMI usando um **adaptador HDMI / VGA ==&gt; VGA / BNC**
>* Conexão via tomada HDMI usando um **adaptador HDMI / VGA ==&gt; VGA / SCART**
{.is-danger}

## Hardware <a id="hardware"></a>

Muitos monitores CRT profissionais têm entradas RGB no BNC, como nesta imagem abaixo:

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDR_6t9mW0aapQKpTn8%2F-MDRfYSaz7TTyP9aoASG%2Fhje1ge2n.bmp?alt=media&token=c5f72041-6d05-4648-b53e-bba410d13fcc)

* Portanto, teremos 3 fios para as 3 cores \(vermelho, verde, azul\), bem como 2 fios para a sincronização \(vertical e horizontal\).

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDR_6t9mW0aapQKpTn8%2F-MDRgjxvZh6Zerw0sO-_%2F2ip78tl5.bmp?alt=media&token=a1d21fe3-b401-48e1-9456-9a2b76e02378)

#### ​Conectores <a id="connectiques"></a>

Você precisará de um adaptador como este:​ [https://www.amazon.fr/UGREEN-Adaptateur-Rasberry-Chromebook-Ordinateur/dp/B00NBUTHJG/ref=sr\_1\_5?ie=UTF8&qid=1489225116&sr=8-5&keywords=vga+hdmi](https://www.amazon.fr/UGREEN-Adaptateur-Rasberry-Chromebook-Ordinateur/dp/B00NBUTHJG/ref=sr_1_5?ie=UTF8&qid=1489225116&sr=8-5&keywords=vga+hdmi)​

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDR_6t9mW0aapQKpTn8%2F-MDRjSQznH5D_LvZl4OI%2Fhdmi%20vga.jpg?alt=media&token=709703b6-e34e-4bec-8fab-16b79d555a36)

* Uma vez conectado à porta HDMI do seu Recalbox, você terá um conector de saída VGA e um conector de áudio.

Você precisará de uma fonte de alimentação micro-usb externa, 1A deve ser suficiente.

* Então você precisará de um adaptador VGA ==&gt; BNC como este:

​ [https://www.amazon.fr/gp/product/B0033AF5Y0/ref=oh\_aui\_detailpage\_o01\_s00?ie=UTF8&psc=1](https://www.amazon.fr/gp/product/B0033AF5Y0/ref=oh_aui_detailpage_o01_s00?ie=UTF8&psc=1)​

![Adaptador &#x200B;VGA-BNC](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDR_6t9mW0aapQKpTn8%2F-MDRhDxvHf_JWHvR_tin%2Fy3r01qi5.bmp?alt=media&token=29105963-bde2-40d5-92e7-32873622883b)



* Não tendo encontrado um adaptador VGA-BNC com saída BNC fêmea, tive que usar 5 conectores BNC macho-macho, encontrados em lojas especializadas em eletrônicos.

​

![Conector BNC macho-macho](http://i.imgur.com/UEXCmCR.png)



## Software <a id="software"></a>

### ​Configuração de inicialização do Recalbox <a id="configuracao-de-inicializacao-do-recalbox"></a>

As resoluções aceitas por esse tipo de tela são diferentes, dependendo do modelo; mas em geral você vai querer:

* **480i para o EmulationStation** \(minha tela não suporta 480p e os textos são ilegíveis em 240p\)
* **240p para jogar** \(resolução de saída para quase todos os consoles daquela época\)

É assim que o seu arquivo `/boot/config.txt`deve ficar

```text
#Resolution of the mode custom DMT 87 HDMI for the games resolution
hdmi_cvt=1920 240 60 1 1 0 0
#Ignore the EDID of your TV (the CRT can send wrong informations)
hdmi_ignore_edid=0xa5000080
#Force the pixel encoding mode where 2 correspond to Full RGB
hdmi_pixel_encoding=2
#Desactivate the safe boot mode
avoid_safe_mode=1
#Allow overscan
disable_overscan=0
#avoid interférences by boosting the HDMI signal
config_hdmi_boost=4
#Force the sound on HDMI
hdmi_drive=2
#Select the HDMI CEA group
hdmi_group=1
#Define resolution to CEA 6 = 480 interlaced
hdmi_mode=6

#Kernel
kernel=zImage
#Use the HDMI even if no cable is connected
hdmi_force_hotplug=1
#Memory config
gpu_mem_256=128
gpu_mem_512=256
gpu_mem_1024=512

#Audio config
dtparam=audio=on
#Delay boot
boot_delay=3
```


>* Para editar este arquivo, você deve tornar a partição de inicialização gravável seguindo este tutorial: [https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesse-uma-particao-em-modo-gravacao](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesse-uma-particao-em-modo-gravacao) 
>* Para acessá-lo via Winscp, siga este tutorial: [https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp)
{.is-info}

​Algumas explicações: O Raspberry pi começará em hdmi\_group = 1 hdmi\_mode = 6, que corresponde a 480i \(entrelaçado\). Se a inicialização for feita diretamente em 240p, os textos dos menus e jogos serão ilegíveis.

A linha `hdmi_cvt=1920 240 60 1 1 0 0` especifica uma resolução de 1920 x 240 x 60 Hz, que não será usada para a inicialização, mas será registrada como o modo DMT 87 HDMI, que usaremos posteriormente para o lançamento de jogos. Aqui está um pouco mais de explicação nesta linha:

```text
hdmi_cvt=<width> <height> <framerate> <aspect> <margins> <interlace> <rb>
width        width in pixels
height       height in pixels
framerate    framerate in Hz
aspect       aspect ratio 1=4:3, 2=14:9, 3=16:9, 4=5:4, 5=16:10, 6=15:9
margins      0=margins disabled, 1=margins enabled
interlace    0=progressive, 1=interlaced
rb           0=normal, 1=reduced blanking
```

### ​Configuração do arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)​ <a id="configuracao-do-arquivo-recalbox-conf"></a>

Embora o **Raspberry Pi inicialize no modo de vídeo CEA 6** \(via config.txt\), preferi forçar essa configuração para o EmulationStation:

```text
system.es.videomode=CEA 6 HDMI
```

* Em seguida, devemos especificar a resolução de inicialização para nossos emuladores, de uma maneira global:

```text
global.videomode=DMT 87 HDMI
```

Todos os emuladores serão, portanto, iniciados no modo HDMI DMT 87 \(modo "personalizado"\), que contém, por meio do hdmi\_cvt do arquivo config.txt, a resolução 1920 x 240x 60Hz.


>**Pequena explicação para a largura de 1920 pixels:** Para encurtar, um monitor CRT precisa apenas de um número vertical de pixels \(240 aqui\) e uma taxa de atualização vertical \(60 Hz aqui\).
>
>Portanto, especificamos 1920 pixels de largura, porque 1920 é um múltiplo de 160, 320, 384 ... que geralmente são encontrados em resoluções.  
>  
>Para as outras resoluções, calcularemos o overscan com retroarch, ou seja, as faixas pretas necessárias na tela para manter a proporção original.
{.is-info}

Tudo corre bem para mim nesta resolução. Mas você pode especificar uma resolução diferente por console \(dreamcast, por exemplo\), com a seguinte linha:

```text
dreamcast.videomode=hdmi_cvt 320 240 60 1 1 0 0
```

### ​Configuração da viewport do Retroarch \(mantenha a proporção original e defina a imagem na tela\) <a id="configuracao-da-viewport-do-retroarch-mantenha-a-proporcao-original-e-defina-a-imagem-na-tela"></a>

#### Configuração por sistema <a id="configuration-per-system"></a>

Ao iniciar um jogo, ele deve começar com uma resolução de 320 x 240 x 60 Hz pixels. Podemos especificar para cada sistema, o tamanho real da exibição e o deslocamento, se necessário.

Esses arquivos de configuração devem ser criados na sua pasta compartilhada: `/system/configs/retroarch/` Eles devem conter o nome do sistema \(o mesmo da pasta roms\), por exemplo, ser criado na sua pasta compartilhada:: `nes.cfg`, ou `mastersystem.cfg`.

Aqui está o conteúdo do meu arquivo nes.cfg

```text
aspect_ratio_index = "22"
video_smooth = "false"
video_scale_integer = "false"
video_threaded = "false"
custom_viewport_width = "1680"
custom_viewport_height = "224"
custom_viewport_x = "118"
custom_viewport_y = "17"
```

* Para ajustar o posicionamento da tela, simplesmente altere os valores de custom\_viewport\_x e y diretamente no jogo através do menu do retroarch \(**Hotkey + B**\), e copie esses valores no arquivo _\* .cfg_ do sistema.
* Aqui estão as **larguras e alturas das viewports** que eu configurei para o meu CRT:

  ```text
  nes.cfg
  custom_viewport_width = "1680"
  custom_viewport_height = "224"
        
  snes.cfg
  custom_viewport_width = "1792"
  custom_viewport_height = "224"

  gb.cfg gbc.cfg gamegear.cfg
  custom_viewport_width = "960"
  custom_viewport_height = "144"

  gba.cfg
  custom_viewport_width = "1440"
  custom_viewport_height = "160"

  megadrive.cfg neogeo.cfg segacd.cfg sega32x.cfg fba_libretro.cfg
  custom_viewport_width = "1920"
  custom_viewport_height = "224"

  mastersystem.cfg
  custom_viewport_width = "1536"
  custom_viewport_height = "192"

  psx.cfg n64.cfg
  custom_viewport_width = "1920"
  custom_viewport_height = "240"

  pcenginecd.cfg
  custom_viewport_width = "1760"
  custom_viewport_height = "240"
  ```

#### Configuração por jogo <a id="configuration-par-jeux"></a>

**​**Para o **arcade**, eu uso **fba\_libretro**. Como quase todo jogo tem uma resolução diferente, eu defini um arquivo por jogo \(para manter a proporção original\). A mesma manipulação do sistema, exceto que os arquivos estão localizados na sua pasta compartilhada:`/system/configs/retroarch/fba_libretro/`

O conteúdo do arquivo é idêntico à configuração do sistema. O nome do arquivo deve estar no formato _rom.zip.cfg._ Então, por exemplo: _1944.zip.cfg_

### Casos Especiais <a id="casos-especiais"></a>

#### Nintendo 64 <a id="nintendo-64"></a>

​Para **lidar com as viewports** no emulador do **Nintendo 64**, precisamos **selecionar o núcleo** retroarch `glupen64`. Então, assim como em outros sistemas, a configuração estará em um arquivo `n64.cfg`.

#### AdvanceMame <a id="advancemame"></a>

Para jogos de arcade do **Mame**, o núcleo **AdvanceMame** tem a particularidade de **calcular automaticamente a resolução de cada jogo**, adaptando-a à sua resolução de tela.

Dessa forma, **não precisamos fazer uma configuração por jogo** \(como é o caso do fba\_libretro\).


>**Esta parte precisa ser concluída!**
{.is-danger}

### Temas do ​EmulationStation <a id="temas-do-emulationstation"></a>

O tema **deve estar no formato 4/3** para ter uma imagem bem enquadrada.

Proponho a você um tema criado por Supernature2K: [https://forum.recalbox.com/topic/6580/release-wip-theme-recalbox-multi-help-needed](https://forum.recalbox.com/topic/6580/release-wip-theme-recalbox-multi-help-needed)​

Este tema é configurável e se adapta perfeitamente aos CRTs.

​

![Tema Recalbox Multi](http://i.imgur.com/6hQFlPO.png)



