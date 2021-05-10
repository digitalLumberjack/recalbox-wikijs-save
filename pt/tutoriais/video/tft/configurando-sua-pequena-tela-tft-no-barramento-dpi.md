---
title: Configurando sua pequena tela TFT no barramento DPI
---

# Configurando sua pequena tela TFT no barramento DPI

## DPI \(Display Parallel Interface / Tela de Interface Paralela\) <a id="dpi-display-parallel-interface-tela-de-interface-paralela"></a>

Fonte : [https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md](https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md)​

Uma interface RGB paralela de até 24 bits está disponível em todas as placas Raspberry Pi com cabeçalho de 40 canais \(A+, B+, Pi2, Pi3, Zero\) e o módulo de cálculo. Essa interface permite que telas RGB paralelas sejam conectadas ao Raspberry Pi GPIO em RGB24 \(8 bits para vermelho, verde e azul\) ou RGB666 \(6 bits por cor\) ou RGB565 \(5 bits vermelho, 6 verde e 5 azul\).

Essa interface é controlada pelo firmware da GPU e pode ser programada por um usuário através de parâmetros especiais no config.txt, e ativando a sobreposição \(_overlay_\) correta da árvore de dispositivos Linux.

Ao enviar dados por essa interface paralela, você não tem problemas com a largura de banda do barramento e a velocidade de exibição \(FPS\). Mas isso usa quase todos os pinos GPIO.

Este modo é muito útil, você pode ajustar seus parâmetros de exibição: tempos, resoluções, etc.

Esse modo vem com novas sobreposições \(_overlays_\), que permitem produzir um sinal RGB graças ao VGA666 \(obtenha o adaptador VGA 666 passivo para Raspberry-Pi B+: [https://github.com/fenlogic/vga666](https://github.com/fenlogic/vga666)\) \([http://www.banggood.com/VGA-666-Adapter-Board-For-Raspberry-Pi-3-Model-B-2B-B-A-p-1071309.html](http://www.banggood.com/VGA-666-Adapter-Board-For-Raspberry-Pi-3-Model-B-2B-B-A-p-1071309.html)\).

```text
dtoverlay=vga666
```

Você poderá usar as telas Adafruit TFT de 5"\([http://www.adafruit.com/products/1596](http://www.adafruit.com/products/1596)\), e 7" \([http://www.adafruit.com/products/2354](http://www.adafruit.com/products/2354)\), graças ao painel TFT Kippah DPI da Adafruit para Raspberry Pi com suporte a toque \(_touch screen_\) \([https://www.adafruit.com/products/2453](https://www.adafruit.com/products/2453)​\)

```text
dtoverlay=dpi24
```

Em seguida, conecte-se ao Recalbox via [ssh](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) E monte a partição no modo leitura e gravação

 `mount -o remount, rw /boot`


>**IMPORTANTE :**
>
>Se você estiver usando a versão 4.0.x, o arquivo`dpi24.dtbo` existe, e pode ser encontrado na pasta`/boot/overlays`. Você precisa renomeá-lo para`dpi24.dtb` para a tela funcionar. No Recalbox 4.1, nada é necessário.
{.is-warning}

Vá até a pasta `/boot/overlays` e renomeie o arquivo dtbo \(Recalbox 4.0.x\)

```text
cd /boot/overlays
mv dpi24.dtbo dpi24.dtb
```

Agora você pode usar

```text
dtoverlay=dpi24
```

## Tela 3.5" TFT Geekwrom HD 800x480 para Raspberry Pi 3B 2B <a id="tela-3-5-tft-geekwrom-hd-800-x480-para-raspberry-pi-3-b-2-b"></a>

Essa tela é pequena e oferece uma resolução de 800x480. Suas especificações são muito boas:

![hd-tftScreen](https://camo.githubusercontent.com/8680157a6e810c62eae94925088b302873fdaff7/687474703a2f2f696d616765732e6d6f726572652e65752f68642d74667453637265656e2e706e67)

Encontrei essa tela incrível no site chinês: [http://www.banggood.com/Geekwrom-HD-3\_5-Inch-TFT-Display-Shield-800x480-For-Raspberry-Pi-3B-2B-With-2-Keys-And-Remote-IR-p-1069730.html](http://www.banggood.com/Geekwrom-HD-3_5-Inch-TFT-Display-Shield-800x480-For-Raspberry-Pi-3B-2B-With-2-Keys-And-Remote-IR-p-1069730.html) por menos de 40€.

Pode ser usado como está, sem o programa fbcp. O Fbcp também não é necessário porque o modo DPI usa a GPU diretamente.

Para obter suporte para essa tela, basta adicionar as seguintes linhas ao seu **/boot/config.txt**.

Você precisa de uma [conexão SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) no Raspberry Pi para executar/verificar as seguintes etapas.

Alterne o sistema de arquivos para o modo Leitura/Gravação para poder fazer alterações:

```text
mount -o remount, rw /boot
mount -o remount, rw /
```

Edite o arquivo /boot/config.txt com nano ou vim e adicione:

```text
#3.5 HD tft screen 800x480
dtoverlay=dpi24
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0

​#Banggood
framebuffer_width=800
framebuffer_height=480
dtparam=spi=off
dtparam=i2c_arm=off

enable_dpi_lcd=1
display_default_lcd=1
dpi_output_format=0x6f015
dpi_group=2
dpi_mode=87
hdmi_timings=480 0 16 16 24 800 0 4 2 2 0 0 0 60 0 32000000 6
display_rotate=3
```

Salve o arquivo e reinicie o Recalbox... isso deve ser suficiente, agora você pode ver as incríveis imagens exibidas nesta tela...

![Tela 3,5&quot; TFT Geekwrom HD 800x480](https://camo.githubusercontent.com/e139870fc5e1e6ae285d64e46e6a00f9823f4071/687474703a2f2f696d672e796f75747562652e636f6d2f76692f714b6449744e737059564d2f302e6a7067)



## Telas de 5" e 7" TFT da Adafruit <a id="telas-de-5-e-7-tft-da-adafruit"></a>

Para usar essas telas \([https://www.adafruit.com/product/2353](https://www.adafruit.com/product/2353), [https://www.adafruit.com/products/1596](https://www.adafruit.com/products/1596)\), você precisará do painel TIP Kippah DPI da Adafruit para Raspberry Pi com suporte a toque \(_touch screen_\) \([https://www.adafruit.com/products/2453](https://www.adafruit.com/products/2453)\) para operá-las.

Elas também usam o modo DPI. A configuração do arquivo config.txt é a seguinte:

```text
#3.5 HD tft screen 800x480
dtoverlay=dpi24
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0

#Adafruit
framebuffer_width=800
framebuffer_height=480
dtparam=spi=off
dtparam=i2c_arm=off

enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
dpi_output_format=0x6f005
hdmi_timings=800 0 40 48 88 480 0 13 3 32 0 0 0 60 0 32000000 6
display_rotate=3
```

## Tela 4.0" HyperPixel <a id="tela-4-0-hyperpixel"></a>

Obrigado @glook por este tutorial : [https://forum.recalbox.com/topic/17854/ecran-hyperpixel-4-pouces/4](https://forum.recalbox.com/topic/17854/ecran-hyperpixel-4-pouces/4)​

Esta tela está disponível neste endereço: [https://shop.pimoroni.com/products/hyperpixel-4](https://shop.pimoroni.com/products/hyperpixel-4) com ou sem _touch screen_.

Comece lendo o Github aqui: [https://github.com/pimoroni/hyperpixel4](https://github.com/pimoroni/hyperpixel4)​

Você precisará:

* compilar hyperpixel4.dts em hyperpixel4.dtbo ou encontrá-lo pronto na internet :

  `dtc` [`[email protected]`](https://recalbox.gitbook.io/cdn-cgi/l/email-protection) `-I dts -O dtb -o hyperpixel4.dtbo hyperpixel4.dts`

* copiar `hyperpixel4.dtbo` para `/boot/overlays/`
* adicionar a configuração ao arquivo config.txt:

```
# Paramètres de l'écran LCD HyperPixel
dtoverlay=hyperpixel4
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0
framebuffer_width=800
framebuffer_height=480
enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
dpi_output_format=0x7f216
display_rotate=3
hdmi_timings=480 0 10 16 59 800 0 15 113 15 0 0 0 60 0 32000000 6
```

Tenha certeza que o i2c e o spinnaker estão desativados:

```text
dtparam=i2c_arm=off
dtparam=spi=off
```

* Monte a partição : `mount -o remount,rw /`
* Copie hyperpixel4-init localizado na pasta `/dist` para `/usr/bin/` no Recalbox
* Finalmente, certifique-se de executar este programa na inicialização do Recalbox, adicionando`hyperpixel4-init` na linha de comandos em um dos scripts init em `/etc/init.d`

