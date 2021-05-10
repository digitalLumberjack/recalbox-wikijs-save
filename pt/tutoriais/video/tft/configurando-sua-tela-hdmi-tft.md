---
title: Configurando sua tela HDMI TFT
---

# Configurando sua tela HDMI TFT

## Configurando sua Tela HDMI 5" TFT <a id="configurando-sua-tela-hdmi-5-tft"></a>


>Você pode encontrar essa tela no seguinte endereço: [http://www.banggood.com/5-Inch-800-x-480-HDMI-TFT-LCD-Touch-Screen-For-Raspberry-PI-2-Model-B-B-A-B-p-1023438.html](http://www.banggood.com/5-Inch-800-x-480-HDMI-TFT-LCD-Touch-Screen-For-Raspberry-PI-2-Model-B-B-A-B-p-1023438.html).
>
>É equivalente ao dispositivo Adafruit: [https://learn.adafruit.com/adafruit-5-800x480-tft-hdmi-monitor-touchscreen-backpack/overview](https://learn.adafruit.com/adafruit-5-800x480-tft-hdmi-monitor-touchscreen-backpack/overview).
{.is-success}

Você pode fazê-la funcionar no Recalbox configurando o arquivo `/boot/config.txt`

Não esqueça que o driver TFP401 não possui um redimensionador de vídeo! Se você não alimentar exatamente 800 × 480 pixels, a imagem não será esticada / encolhida para caber!

Portanto, temos que configurar a resolução no arquivo config.txt Conecte-se ao seu Pi \( seja [via SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) ou em TTY local\).

Faça `/boot` gravável para modificar o necessário:

```text
mount -o remount, rw /boot
```

Edite o arquivo `/boot/config.txt` com nano ou vim e adicione:

```text
# uncomment if hdmi display is not detected and composite is being output
hdmi_force_hotplug=1
 
# uncomment to force a specific HDMI mode (here we are forcing 800x480!)
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
hdmi_cvt=800 480 60 6 0 0 0
 
max_usb_current=1
```

A linha `max_usb_current=1` aumenta a corrente máxima de saída USB do Pi. Dessa forma, seu Pi fornecerá energia suficiente à sua tela. Verifique se a fonte de alimentação principal é poderosa o suficiente para todos os seus dispositivos \(5V-3A\).

Se a imagem não tiver a resolução correta ao emular, você precisará modificar o arquivo [`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) e alterar o `global.videomode`:

```text
global.videomode=default
```

para usar a configuração padrão no arquivo `config.txt`.

Verifique este post para ver isso com imagens: [https://forum.recalbox.com/topic/4539/how-to-config-portable-5-inch-screen-pics-inside](https://forum.recalbox.com/topic/4539/how-to-config-portable-5-inch-screen-pics-inside)​

## Configurando sua Tela HDMI 7" TFT <a id="configurando-sua-tela-hdmi-7-tft"></a>

Você pode encontrá-las por um preço justo:

* [https://www.waveshare.com/7inch-HDMI-LCD-C.htm](https://www.waveshare.com/7inch-HDMI-LCD-C.htm)
* [https://www.waveshare.com/wiki/7inch\_HDMI\_LCD\_\(C\)](https://www.waveshare.com/wiki/7inch_HDMI_LCD_%28C%29)

Você pode fazê-la funcionar no Recalbox configurando o arquivo `/boot/config.txt`.

Não esqueça que o driver TFP401 não possui um redimensionador de vídeo! Se você não alimentar exatamente 800 × 480 pixels, a imagem não será esticada / encolhida para caber!

Portanto, temos que configurar a resolução no arquivo config.txt Conecte-se ao seu Pi \( seja [via SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) ou em TTY local\).

Faça `/boot` gravável para modificar o necessário:

```text
mount -o remount, rw /boot
```

Edite o arquivo `/boot/config.txt` com nano ou vim e adicione:

```text
# uncomment if hdmi display is not detected and composite is being output
hdmi_force_hotplug=1
config_hdmi_boost=7
hdmi_max_current=1
# uncomment to force a specific HDMI mode (here we are forcing 2014x600!)
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
hdmi_cvt=1024 600 60 6 0 0 0
display_rotate=0
max_usb_current=1
hdmi_drive=1
hdmi_ignore_edid=0xa5000080
```

A linha `max_usb_current=1` aumenta a corrente máxima de saída USB do Pi se a tela for alimentada por USB. Use`hdmi_max_current=1` se a tela for alimentada por HDMI. Dessa forma, seu Pi fornecerá energia suficiente para a sua tela. Verifique se a fonte de alimentação principal é potente o suficiente para todos os seus dispositivos \(5V-3A\). Para uma tela maior \(10" e superior\), certifique-se de usar uma fonte de alimentação externa.

Se a imagem não tiver a resolução correta ao emular, você precisará modificar o arquivo [`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) e alterar o `global.videomode`:

```text
global.videomode=default
```

Você pode definir o modo personalizado com a ajuda fornecida nesta página: [https://www.raspberrypi.org/documentation/configuration/config-txt/video.md](https://www.raspberrypi.org/documentation/configuration/config-txt/video.md)​

```text
hdmi_cvt=<width> <height> <framerate> <aspect> <margins> <interlace> <rb>

Value 	Default 	Description
width 	(required) 	width in pixels
height 	(required) 	height in pixels
framerate 	(required) 	framerate in Hz
aspect 	3 	aspect ratio 1=4:3, 2=14:9, 3=16:9, 4=5:4, 5=16:10, 6=15:9
margins 	0 	0=margins disabled, 1=margins enabled
interlace 	0 	0=progressive, 1=interlaced
rb 	0 	0=normal, 1=reduced blanking
```

