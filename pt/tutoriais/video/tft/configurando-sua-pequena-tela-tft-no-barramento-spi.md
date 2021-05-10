---
title: Configurando sua pequena tela TFT no barramento SPI
---

# Configurando sua pequena tela TFT no barramento SPI

## Configurando sua tela TFT capacitiva/resistiva Adafruit de 2,8 " <a id="configurando-sua-tela-tft-capacitiva-resistiva-adafruit-de-2-8"></a>

Essa tela pode ser encontrada em: [https://www.adafruit.com/product/1601](https://www.adafruit.com/product/1601). Como já existem _overlays_ \(sobreposições\) para esta tela na pasta `/boot/overlays` , será suportado com uma configuração simples.

```text
pitft28-capacitive.dtbo
pitft28-resistive.dtbo
```

Verifique se você possui a versão capacitiva ou resistiva da tela e ajuste a linha dt-overlay em`/boot/config.txt`.

Esta tela usa o barramento SPI para ser controlada. Sua baixa resolução nos permite obter uma boa taxa de quadros nas frequências de emulação. Não é realmente 60fps, mas, é mais do que o mínimo de 30fps, graças ao programa `fcbp` modificado \([https://recalbox.gitbook.io/tutorials/v/portugues/video/tft/tutorial-do-fbcp-usando-o-fbcp-para-pequenas-telas-tft](tutorial-do-fbcp-usando-o-fbcp-para-pequenas-telas-tft.md)\).

Para fazer isso, você deve obter acesso de gravação ao sistema:

```text
mount -o remount, rw /boot
mount -o remount, rw /
```

### Modificando o arquivo /boot/config.txt para corresponder à resolução da tela

Para que esta tela funcione, você deve ter essas linhas no arquivo `/boot/config.txt`:

```text
#overclocking extreme
arm_freq=1100
core_freq=550
sdram_freq=600
over_voltage=8
over_voltage_sdram=6
force_turbo=1

dtparam=spi=on
dtparam=i2c1=on
dtparam=i2c_arm=on
#forcing HDMI output at TFT screen resolution to be able to make the FB copy
#resolution configuration
hdmi_force_hotplug=1
hdmi_cvt=320 240 60 1 0 0 0
hdmi_group=2
hdmi_mode=87
# working config for speed
# 900 Mhz -> 48000000
# 1Ghz -> 35000000
#modification of the speed   
dtoverlay=pitft28-resistive,rotate=90,speed=22000000,fps=60
```

A parte de overclock não é necessária e está configurada para um Pi1.

A velocidade do barramento SPI precisa ser ajustada se você fizer um overclock no seu Raspberry Pi para obter uma boa imagem. Essas configurações foram testadas em um Raspberry P1 em 1.1Ghz.

Para começar, você pode tentar:

```text
dtoverlay=pitft28-resistive,rotate=90,speed=32000000,fps=20
```

No caso de uma tela capacitiva, basta substituir por:

```text
dtoverlay=pitft28-capacitive,rotate=90,speed=32000000,fps=20
```

Ao reiniciar, a tela deve começar com uma tela branca e, após alguns segundos, deve ficar preta. Isso é um sinal de que a tela agora é suportada. Mas você não terá nenhuma imagem até executar `fbcp`.

Agora você deve usar uma conexão SSH no seu Raspberry Pi para executar / verificar as seguintes etapas \(consulte [https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)\)

### Ativando o fbcp no arquivo recalbox.conf

No [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), basta ativar o suporte ao `fbcp` e reiniciar.


>**Cuidado:**  
>Certifique-se de desativar os controladores GPIO
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

Ou altere a configuração do pino GPIO usando os plugues 4 ou 5 para definir o pino usado, evitando os pinos usados pelo seu monitor. Leia [https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controladores-gpio](https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controladores-gpio) para mais detalhes.

```text
## fbcp FrameBuffer Copy Program
## For small TFT screen on GPIO and SPI
## See https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29 for details
## Needed for Waveshare 3.2" 3.5" TFT screen, 2.8" Adafruit screen
## See https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29
## for support and configuration details needed by /boot/config.txt
system.fbcp.enabled=1
```

Edite o arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) da seguinte maneira:

```text
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=4/3
```

Salve o arquivo e reinicie. A tela agora deve funcionar perfeitamente. Se você encontrar problemas, verifique primeiro se o programa `fbcp` funciona com:

```text
ps aux | grep fbcp
```

Essa tela de 2,8 "funciona bem, mas pode ser muito pequena e muito cara \(35 €\) para clones chineses. Então, agora vamos configurar uma tela TFT Waveshare de 3,2" encontrada na Banggood por menos de 15 €.

## Configurando sua tela capacitiva/resistiva TFT de 3,2" Waveshare

É um módulo de tela TFT LCD de 3,2", _touch screen_, para o Raspberry Pi B +, B, A +. Sua resolução é igual à de 2,8": 320x240. Na verdade, é uma tela Waveshare [http://www.waveshare.com/3.2inch-rpi-lcd-b.htm](http://www.waveshare.com/3.2inch-rpi-lcd-b.htm).

Esta tela não é suportada por padrão pelos sistemas de arquivos do kernel. Teremos que adicionar mais telas para a tela funcionar.

Esses arquivos podem ser encontrados em [https://github.com/swkim01/waveshare-dtoverlays](https://github.com/swkim01/waveshare-dtoverlays).

Consiga os arquivos `waveshare35a-overlay.dtb` e `waveshare32b-overlay.dtb` para a tela WaveShare de 3,2" 320x240 e a tela WaveShare de 3,5" 320x480, respectivamente. Para os novos kernels na versão 4.4, precisamos renomear os arquivos dtb para arquivos dtbo para corresponder ao novo nome da árvore de sobreposição \(_overlay_\). Renomeie `waveshare35a-overlay.dtb` para `waveshare35a.dtbo` e `waveshare32b-overlay.dtb` para `waveshare32b.dtbo` e copie eles para a pasta `/boot/overlays`.

Agora modificamos o arquivo `/boot/config.txt` para suportar a nova tela:

```text
#tft screen

#Waveshare 3.2 TFT Screen
#same resolution for hdmi and tft
hdmi_force_hotplug=1
hdmi_cvt=320 240 60 1 0 0 0
hdmi_group=2                
hdmi_mode=1                 
hdmi_mode=87                

dtparam=spi=on              
dtoverlay=waveshare32b:rotate=270,speed=82000000
```

### Ativando o fbcp no arquivo recalbox.conf

No [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), basta ativar o suporte ao `fbcp` e reiniciar.


>**Cuidado:**  
>Certifique-se de desativar os controladores GPIO
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

Ou altere a configuração do pino GPIO usando os plugues 4 ou 5 para definir o pino usado, evitando os pinos usados pelo seu monitor. Leia [https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controladores-gpio](https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controladores-gpio) para mais detalhes.

```text
## fbcp FrameBuffer Copy Program
## For small TFT screen on GPIO and SPI
## See https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29 for details
## Needed for Waveshare 3.2" 3.5" TFT screen, 2.8" Adafruit screen
## See https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29
## for support and configuration details needed by /boot/config.txt
system.fbcp.enabled=1
```

Edite o arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) da seguinte maneira:

```text
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=4/3
```

Salve o arquivo e reinicie. A tela agora deve funcionar perfeitamente. Se você encontrar problemas, verifique primeiro se o programa `fbcp` funciona com:

Uma tela funcional em vídeo:

{% embed url="https://www.youtube.com/watch?v=hcFk\_vjQLVo&feature=emb\_title&ab\_channel=YannMORERE" %}



## Por que o monitor TFT capacitivo/resistivo de 3,5 "do Waveshare não pode ser usado com o Recalbox?

Esta tela não pode ser usada para jogos de arcade com Recalbox. O barramento SPI não tem largura de banda suficiente para lidar com essa resolução mais alta de 480x320. Se você aumentar a velocidade do barramento, a tela ficará instável \(cores, tremulações\). Durante meus testes, eu só conseguia 20-25 FPS. Essa tela pode ser usada com um servidor X com uma taxa de quadros lenta, mas não no modo arcade, o que requer uma taxa de quadros mais alta.

Conforme descrito em [https://learn.adafruit.com/](https://learn.adafruit.com/), não é recomendável usar essa tela para jogos. &lt;&lt; Com o dobro do número de pixels para pressionar na tela, o PiTFT de 3,5 "é significativamente mais lento que seus irmãos mais compactos e é altamente recomendável em jogos &gt;&gt;. Agora você sabe!

Mas se você quiser fazê-lo funcionar, faça o seguinte:

### Modificando o arquivo /boot/config.txt para corresponder à resolução da tela

Consiga os arquivos `waveshare35a-overlay.dtb` e `waveshare32b-overlay.dtb` para a tela WaveShare de 3,2" 320x240 e a tela WaveShare de 3,5" 320x480, respectivamente. Para os novos kernels na versão 4.4, precisamos renomear os arquivos dtb para arquivos dtbo para corresponder ao novo nome da árvore de sobreposição \(_overlay_\). Renomeie `waveshare35a-overlay.dtb` para `waveshare35a.dtbo` e `waveshare32b-overlay.dtb` para `waveshare32b.dtbo` e copie eles para a pasta `/boot/overlays`.

Agora modificamos o arquivo `/boot/config.txt` para suportar a nova tela:

```text
#tft screen
#Waveshare 3.5 TFT Screen
#same resolution for hdmi and tft
hdmi_force_hotplug=1
hdmi_cvt=480 320 60 1 0 0 0
hdmi_group=2
hdmi_mode=1
hdmi_mode=87

dtparam=spi=on
dtoverlay=waveshare35a:rotate=270,speed=27000000
# speed=41000000,fps=60 for better FPS, but the colors will look a little weird.
```

### Ativando o fbcp no arquivo recalbox.conf

No [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), basta ativar o suporte ao `fbcp` e reiniciar.


>**Cuidado:**  
>Certifique-se de desativar os controladores GPIO
{.is-danger}

```text
## enable controllers on GPIO with mk_arcarde_joystick_rpi (0,1)
controllers.gpio.enabled=0
```

Ou altere a configuração do pino GPIO usando os plugues 4 ou 5 para definir o pino usado, evitando os pinos usados pelo seu monitor. Leia [https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controladores-gpio](https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controladores-gpio) para mais detalhes.

```text
fbcp FrameBuffer Copy Program
## For small TFT screen on GPIO and SPI
## See https://github.com/recalbox/recalbox-os/wiki/Utility---Use-of-fbcp-for-small-TFT-screen-%28EN%29 for details
## Needed for Waveshare 3.2" 3.5" TFT screen, 2.8" Adafruit screen
## See https://github.com/recalbox/recalbox-os/wiki/TFT-Screen-SPI-Bus-%28EN%29
## for support and configuration details needed by /boot/config.txt
system.fbcp.enabled=1
```

Edite o arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) da seguinte maneira:

```text
#global.videomode=DMT 87 HDMI
global.videomode=default

#global.ratio=auto
global.ratio=3/2
```

Salve o arquivo e reinicie. A tela agora deve funcionar perfeitamente. Se você encontrar problemas, verifique primeiro se o programa `fbcp` funciona com:

```text
ps aux | grep fbcp
```

Uma tela funcional de 3,5 polegadas com problemas de vídeo FPS:

{% embed url="https://youtu.be/HJXQAEaVhKE" %}

Trabalhando com uma velocidade = 410000, fps = 60; é claramente arriscado, algumas telas darão resultados estranhos. Funcionará em algumas telas, dependendo do controlador do chip incorporado.

Na minha humilde opinião, se você tiver o [https://www.waveshare.com/3.5inch-RPi-LCD-C.htm](https://www.waveshare.com/3.5inch-RPi-LCD-C.htm) LCD de 3,5 "\(C\) para Raspberry Pi \(480x320; 125Mhz\), ele deve funcionar, mas com [https://www.waveshare.com/3.5inch-RPi-LCD-B.htm](https://www.waveshare.com/3.5inch-RPi-LCD-B.htm) LCD de 3,5 "\(B\) para Raspberry Pi \(480x320; IPS\), você não conseguirá 60fps!

{% embed url="https://www.youtube.com/watch?v=cgznOcvRRqQ&feature=emb\_title&ab\_channel=ClipesDiarios" %}



## Faça com que TFT resistiva de 3,5" Waveshare trabalhe a toda velocidade!

Em breve. Isto é para os corajosos: [https://github.com/juj/fbcp-ili9341](https://github.com/juj/fbcp-ili9341)​

