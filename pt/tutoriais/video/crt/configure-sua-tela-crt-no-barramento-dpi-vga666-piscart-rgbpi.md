---
title: Configure sua tela CRT no barramento DPI \(VGA666 / PiScart / RGBPi\)
---

# Configure sua tela CRT no barramento DPI \(VGA666 / PiScart / RGBPi\)

## O que é barramento DPI <a id="o-que-e-barramento-dpi"></a>

A descrição completa pode ser encontrada no seguinte endereço: [https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md](https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md).

Uma interface RGB paralela de até 24 bits está disponível em todas as placas Raspberry Pi com o cabeçalho de 40 canais \(A+, B+, Pi2, Pi3, Zero\) e o "Módulo de computação". Essa interface permite conectar telas RGB paralelas ao Raspberry Pi GPIO, seja em RGB24 \(8 bits para vermelho, verde e azul\), seja em RGB666 \(6 bits por cor\) ou em RGB565 \(5 bits para o vermelho, 6 para verde e 5 para azul\).

Essa interface é controlada pelo firmware da GPU e pode ser programada por um usuário através de parâmetros especiais no arquivo `config.txt` e permitindo a sobreposição correta da árvore de dispositivos Linux.

Observe que existem diferentes maneiras de representar os valores de cores nos pinos de saída DPI nos modos 565, 666 ou 24 bits \(consulte a tabela a seguir e a parte `output_format` do parâmetro `dpi_output_format` abaixo\) :

![GPIOs usados &#x200B;&#x200B;dependendo do modo usado](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lzvgq0Nce-kRqnZQ42V%2F-LzviJlKzqqcI4x_96cQ%2Fimage.png?alt=media&token=0386d23a-0aad-4a2c-904a-24e5f4e4cf31)



Observe que todos os outros dispositivos de sobreposição periférica que usam pinos GPIO conflitantes devem ser desativados. No arquivo `config.txt`, certifique-se de comentar ou reverter qualquer configuração de dtp que habilite I2C ou SPI:

```text
dtparam=i2c_arm=off
dtparam=spi=off
```

## O Gert VGA666 <a id="o-gert-vga666"></a>

O Gert VGA 666 \(6 bits por canal de cor, portanto 666\) é uma placa de expansão/complemento para o Raspberry Pi Modelo B+ \(não funcionará com o Modelo A/B, pois são necessários pinos adicionais do Modelo B+ GPIO \) Esta é uma criação de hardware de código aberto recentemente divulgada ao público por Gert van Loo, um dos engenheiros de hardware que contribuiu para o design inicial do Raspberry Pi original \(também um dos arquitetos do chip BCM2835 no núcleo do Raspberry Pi\) e alguém com quem muitos de vocês já conversaram no Raspberry Jams ou nos fóruns do Raspberry Pi.

Esse é um método limpo e muito útil de usar uma tela/monitor VGA com o seu Raspberry Pi e é muito mais barato que um adaptador HDMI para VGA ou semelhante. A conexão VGA é conduzida nativamente no hardware pelos pinos GPIO \(usando uma interface paralela\) e usa aproximadamente a mesma carga de CPU que a conexão HDMI integrada. É capaz de exibir vídeos VGA 1080p60 sem carga da CPU.

Também é possível gerenciar essa interface ao mesmo tempo que a conexão HDMI, para que também seja possível uma configuração de tela dupla. Esse complemento não foi possível nos modelos A e B do Raspberry Pi, pois todos os pinos necessários não foram colocados no cabeçalho GPIO. Mais uma grande melhoria que o Modelo B + tornou possível!

![O m&#xF3;dulo Gert VGA666](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-Kg3CVViTFwXRr4XFa%2F-M-KgH6dbc0ROi2A3I_1%2FgertVGA666.png?alt=media&token=5be3b72b-18e9-4bde-a478-58b5cd229fd4)



​Primeiro precisamos editar o arquivo `/boot/config.txt` . Precisamos remontar a partição no modo de leitura e gravação:

`mount -o remount, rw /boot`

Use o nano para editar o arquivo `/boot/config.txt`

Comando: `nano /boot/config.txt`

Observe que, para que o Gert VGA 666 funcione corretamente, você deve desativar o SPI e o I2C. Em seguida, adicione essas linhas na parte inferior do arquivo:

```text
dtparam=spi=off
dtparam=i2c_arm=off
dtoverlay=vga666
enable_dpi_lcd=1
display_default_lcd=1 
```

Você também deve especificar a resolução da sua tela \(e não a de uma televisão\). Após as linhas adicionadas acima, você também precisará adicionar uma das seguintes configurações:

```text
#For 1920x1080 60Hz
dpi_group=2
dpi_mode=82
#For 1280x1024 60Hz
dpi_group=2
dpi_mode=35
#For 1024x768 60Hz
dpi_group=2
dpi_mode=16
#For 800x600 60Hz
dpi_group=2
dpi_mode=9
```

![VGA666 em um monitor de PC](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-L1fSbaZId_VZnWiJs%2F-M-L1pOs7optiSxRpJ30%2FDSC_1528.JPG?alt=media&token=c5cb8532-b833-427a-953d-2d1558e5a929)

Se a resolução que você está procurando não estiver entre essas, consulte o seguinte link: [https://www.raspberrypi.org/documentation/configuration/config-txt/video.md](https://www.raspberrypi.org/documentation/configuration/config-txt/video.md)​

Para telas de TV, a configuração será diferente. Precisamos usar o dpi\_mode personalizado 87 e corrigir hdmi\_timings para configurar o modo personalizado de 15KHz. Este modo personalizado será aplicado à interface do EmulationStation. Podem ser usados vários hdmi\_timings diferentes.

```text
dtparam=i2c_arm=off
dtparam=spi=off
 
# Enable VGA666
dtoverlay=vga666
enable_dpi_lcd=1
display_default_lcd=1
 
dpi_group=2
dpi_mode=87
 
#hdmi_timings=506 1 8 48 56 240 1 3 10 6 0 0 0 60 0 9600000 1
#hdmi_timings=512 1 16 48 64 288 1 3 5 6 0 0 0 50 0 9600000 1
 
# Custom 15kHz mode
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
#hdmi_timings=320 1 17 33 34 224 1 14 8 18 0 0 0 60 0 6400000 1
#hdmi_timings=960 0 173 8 0 160 0 40 10 0 0 0 0 60 0 19200000 8
#hdmi_timings=320 1 25 30 30 240 1 9 3 10 0 0 0 60 0 6400000 1
#hdmi_timings=1920 1 52 208 260 240 1 6 10 6 0 0 0 60 0 38400000 1
```

Vários hdmi\_timings diferentes podem ser usados. Aqui está uma lista de timings utilizáveis ​​testados pela **ironic**. Isso economizará tempo para sua configuração.

```text
OK
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=336 1 10 30 34 252 1 15 3 42 0 0 0 50 0 6400000 1 #with borders
hdmi_timings 480 1 29 35 66 234 1 4 10 18 0 0 0 60 0 9600000 1
hdmi_timings=990 1 22 94 116 240 1 6 10 6 0 0 0 60 0 19200000 1
hdmi_timings=820 1 42 260 100 240 1 6 10 6 0 0 0 60 0 19200000 1
Perfect
hdmi_timings=320 1 12 32 44 240 1 6 10 6 0 0 0 60 0 6400000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=1920 1 52 208 260 240 1 6 10 6 0 0 0 60 0 38400000 1
hdmi_timings=512 1 16 48 64 288 1 3 5 6 0 0 0 50 0 9600000 1
OK
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=336 1 10 30 34 252 1 15 3 42 0 0 0 50 0 6400000 1 #with borders
hdmi_timings 480 1 29 35 66 234 1 4 10 18 0 0 0 60 0 9600000 1
hdmi_timings=990 1 22 94 116 240 1 6 10 6 0 0 0 60 0 19200000 1
hdmi_timings=820 1 42 260 100 240 1 6 10 6 0 0 0 60 0 19200000 1
Perfect
hdmi_timings=320 1 12 32 44 240 1 6 10 6 0 0 0 60 0 6400000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=1920 1 52 208 260 240 1 6 10 6 0 0 0 60 0 38400000 1
hdmi_timings=512 1 16 48 64 288 1 3 5 6 0 0 0 50 0 9600000 1
OK
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=336 1 10 30 34 252 1 15 3 42 0 0 0 50 0 6400000 1 #with borders
hdmi_timings 480 1 29 35 66 234 1 4 10 18 0 0 0 60 0 9600000 1
hdmi_timings=990 1 22 94 116 240 1 6 10 6 0 0 0 60 0 19200000 1
hdmi_timings=820 1 42 260 100 240 1 6 10 6 0 0 0 60 0 19200000 1
Perfect
hdmi_timings=320 1 12 32 44 240 1 6 10 6 0 0 0 60 0 6400000 1
hdmi_timings=506 1 8 44 52 240 1 6 10 6 0 0 0 60 0 9600000 1
hdmi_timings=996 1 24 96 120 240 1 3 10 6 0 0 0 60 0 19200000 1
hdmi_timings=1920 1 52 208 260 240 1 6 10 6 0 0 0 60 0 38400000 1
hdmi_timings=512 1 16 48 64 288 1 3 5 6 0 0 0 50 0 9600000 1
```

Em seguida, precisamos informar ao Recalbox como exibir o EmulationStation e a resolução padrão para emuladores. No arquivo[`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) :

```text
global.videomode=DMT 87 HDMI
```

![VGA666 em uma pequena tela de TV](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-KqnBEwIH18MSzC0hr%2F-M-KuuXQ26NWg083B4u6%2FDSC_1531.JPG?alt=media&token=6cf8c976-eb5a-49ce-a1de-e910915893e7)

O Retroarch permite configuração básica específica para saída de vídeo. Nós podemos criar um arquivo de configuração por núcleo. Para fazer isso, você deve criar os arquivos de configuração no diretório`/share/system/configs/retroarch`.

Usamos a proporção "23" custom/personalizada para modificar a aparência do Retroarch.

 para o snes \| snes.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

para o megadrive \| megadrive.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

para o nes \| nes.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

para o fba \| fba\_libretro.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

para o mame \| mame.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

![Detalhes da imagem](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-L4gFcNhWrkASCSCra%2F-M-L4va4kGZyDkAsaAR7%2FDSC_1535.JPG?alt=media&token=7578bd5c-ba61-4235-b3b5-9e0ffaf29f29)



![Detalhes da imagem](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-L4gFcNhWrkASCSCra%2F-M-L53_A6Q0tG2msIIy4%2FDSC_1538.JPG?alt=media&token=a827b677-6358-48b9-8ee9-b4600c297b95)

Nos emuladores, você provavelmente precisará ajustar manualmente as variáveis ​​de viewport personalizadas. Para isso, você deve iniciar o menu Retroarch pressionando `Hotkey + B`. Antes disso, você precisa ajustar o estilo do menu Retroarch ao antigo `rgui` porque por padrão com uma tela de televisão, a interface `ozone` não será utilizável.

Edite os arquivos `retroarchcustom.cfg` e `retroarchcustom.cfg.original` na pasta `/recalbox/share/system/configs/retroarch/` \(ou `\recalbox\share\system\configs\retroarch` via rede no windows\) e substitua a linha `menu_driver = ozone` por`menu_driver = rgui`. Salve e reinicie.

## RGBPi : cabo Scart para televisões CRT <a id="rgbpi-cabo-scart-para-televisoes-crt"></a>

Aprecie a simplicidade de um cabo plug-and-play para sua TV CRT e RaspberryPi com nosso sistema operacional personalizado em resoluções RGB e PixelPerfect para todos os jogos, com som estéreo aprimorado e um novo recurso compatível com comutação automática, compatível com os modelos 2B, 3B, 3B + até o momento...

Nova função de comutação automática para canal AV em 4: 3, RGB de 18 bits sem conversões e sinal CSync limpo gerado na PCB no scart, oferecendo a melhor qualidade de sinal possível e a menor perda, dois canais de áudio filtrados aprimorados, tudo pré-configurado em nosso sistema operacional baseado em Retropie.

![Adaptador RGB-Pi](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-KgOFMeodNnnIVg_Um%2F-M-Kit6W7vpAV5mjRXkF%2Frgbpi.jpg?alt=media&token=02d46b62-c04b-4d07-87b3-667f1cdc49e2)

![Detalhes do adaptador RGB-Pi](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-KgOFMeodNnnIVg_Um%2F-M-Kig0eyw4dUu8IX36y%2Frgbpi2.jpg?alt=media&token=06529a40-dc84-4250-be2a-8e4d99e77d34)

Se você quiser usá-lo com o Recalbox, poderá usar o mesmo procedimento que no caso do VGA666, com algumas pequenas modificações. Aqui está o arquivo`config.txt` :

```text
hdmi_timings=320 1 10 30 40 240 1 3 4 6 0 0 0 60 0 6400000 1

## RGB-Pi Custom Configuration
## IMPORTANT! hdmi_timings must be always in the first line
## hdmi_timings=<h_active_pixels> <h_sync_polarity <h_front_porch> <h_sync_pulse
> <h_back_porch> <v_active_lines> <v_sync_polarity> <v_front_porch> <v_sync_puls
e> <v_back_porch> <v_sync_offset_a> <v_sync_offset_b> <pixel_rep> <frame_rate> <
interlaced> <pixel_freq> <aspect_ratio>
## Usable Pixel clock are : 4800000 - 6400000 - 9600000 - 19200000 and anything 
over 38400000

disable_overscan=1
hdmi_force_hotplug=1
config_hdmi_boost=0
dtparam=audio=on
display_rotate=0
audio_pwm_mode=2
disable_audio_dither=1
hdmi_drive=2
boot_delay=3
disable_splash=1
avoid_safe_mode=1
dtoverlay=pwm-2chan,pin=18,func=2,pin2=19,func2=2
framebuffer_depth=32
framebuffer_ignore_alpha=1
#dtoverlay=rgb-pi
#dpi24 is equal to rgb-pi
dtoverlay=dpi24
enable_dpi_lcd=1
display_default_lcd=1
dpi_output_format=6
dpi_group=2
dpi_mode=87
kernel=zImage
overscan_scale=0
avoid_warnings=1
gpu_mem_256=64
gpu_mem_512=128
gpu_mem_1024=256
dtparam=i2c_vc=on
dtoverlay=i2c-gpio,i2c_gpio_sda=10,i2c_gpio_scl=11
```

## Pi2Scart <a id="pi-2-scart"></a>

O Pi2SCART é um circuito impresso que permite adicionar ao seu Raspberry Pi uma saída de áudio / vídeo de 15Khz em um soquete Scart. O PI2SCART se conecta de maneira muito simples à interface GPIO do Raspberry. Enquanto isso, o som é captado do fone de ouvido por meio de um cabo de áudio. O PI2SCART não precisa de energia adicional para operar.

![M&#xF3;dulo Pi2Scart conectado a um Pi](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M-Kj14ynToc3f0ORLfF%2F-M-KqAyeP5Q6_8kLtVtn%2Fpi2scart.jpg?alt=media&token=aab7e6b0-13af-45f0-bdc3-963ff87de871)

Como os dois sistemas anteriores, o Pi2Scart usa o barramento DPI e as portas GPIO para operar. Ele usa a sobreposição VGA66 e o ​​dpi\_mode 87. Para fazê-lo funcionar, você precisa editar o arquivo`/boot/config.txt` e adicionar as seguintes linhas:

```text
disable_audio_dither=1
dtparam=audio=on
dtoverlay=vga666
enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
hdmi_timings=320 1 16 30 34 240 1 2 3 22 0 0 0 60 0 6400000 1 #240p
```


>**AVISO:**  
>Essa configuração de resolução corresponde a uma resolução comum a todos os emuladores que pode não ser perfeitamente adequada ao seu monitor CRT. Cabe a você ajustar sua tela \(menu de fábrica, potenciômetro\) ou via RECALBOX \(overscan ou via retroarch\). No último caso \(retroarch\), você pode substituir a configuração básica para definir uma resolução de vídeo específica.
{.is-warning}


>**ATENÇÃO:**
>
>No caso de testes em um terminal ou bartop, não se esqueça de modificar a opção **controllers.gpio.enabled** que habilita os comandos GPIO alterando o valor de 1 para 0.
{.is-danger}

​O Retroarch permite configuração básica específica para saída de vídeo. Nós podemos criar um arquivo de configuração por núcleo. Para fazer isso, você deve criar os arquivos de configuração no diretório`/share/system/configs/retroarch`.

Usamos a proporção "23" custom/personalizada para modificar a aparência do Retroarch.

 para o snes \| snes.cfg

```text
aspect_ratio_index = "23"
custom_viewport_width = "900"
custom_viewport_height = "224"
custom_viewport_x = "58"
custom_viewport_y = "13"
```

​

