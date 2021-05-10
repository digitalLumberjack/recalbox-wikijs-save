---
title: Conectando o Recalbox a um monitor CRT com HDMI e SCART
---

# Conectando o Recalbox a um monitor CRT com HDMI e SCART

## Princípios <a id="principios"></a>

### Cabeamento <a id="cabeamento"></a>

Primeiro, você precisará criar o super cabo para converter VGA em Scart. A propósito, obrigado a @ian57 por este post!

​[https://forum.recalbox.com/topic/3475/recalbox-sur-tv-crt-en-rgb/745](https://forum.recalbox.com/topic/3475/recalbox-sur-tv-crt-en-rgb/745)​

![](https://s3-eu-west-1.amazonaws.com/forums.recalbox.com/ac9ba3d3-29fc-4ff2-8644-aee71b62f043.png)

​

Usei isso \(cabo Scart HDMI VGA\) em um terminal com uma TV de 36 cm e um Recalbox 6.1.1, não houve problemas específicos.

Aqui está o esquema da minha fiação na saída do conversor VGA.

Então, para as configurações, é muito diferente do VGA666 / pi2scart / rgbPi \(todos os três usam DPI no modo de 18 bits \(6 bits / cor\):

No arquivo `config.txt`, configuramos como se tivéssemos uma tela 1920x240:

```text
hdmi_cvt=1920 240 60 1 1 0 0
hdmi_disable_edid=0xa5000080 #Enables the ignoring of EDID/display data if your display doesn't have an accurate EDID.

hdmi_pixel_encoding=2 #Force the pixel encoding mode. By default it will use the mode requested from edid so shouldn't need changing. 
avoid_safe_mode=1
disable_overscan=0 #oversan enabled
hdmi_drive=2
hdmi_group=1
hdmi_mode=6
hdmi_force=1
```

No arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), forçamos o EmulationStation a ser exibido em 480 entrelaçados \(dói um pouco os olhos\); caso contrário, usamos o CEA 8 HDMI a 240 não entrelaçado, mas precisaremos de um tema adaptado a esta baixa resolução.

```text
system.es.videomode=CEA 6 HDMI

#global.videomode=CEA 4
HDMIglobal.videomode=DMT 87 HDMI
```

Então, você deve informar ao libretro para cada emulador para usar apenas parte da janela 1920x240. Para fazer isso, você precisa criar um arquivo de configuração para cada emulador: [https://forum.recalbox.com/topic/18927/recalbox-6-1-sur-écran-crt/9](https://forum.recalbox.com/topic/18927/recalbox-6-1-sur-%C3%A9cran-crt/9) para ser colocado em `/share/system/configs/retroarch`

Por exemplo, meu`megadrive.cfg`

```text
aspect_ratio_index = "23"
custom_viewport_width = "1792"
custom_viewport_height = "224"
custom_viewport_x = "104"
custom_viewport_y = "16"
```

 As últimas 4 linhas devem ser adaptadas à geometria da tela. Os valores podem ser encontrados ajustando-se no menu Retroarch.

Se isso não for feito, a imagem do emulador será completamente substituída no meio da tela.

## Links úteis para a configuração do núcleo do Retroarch <a id="useful-links-for-retroarch-kernel-configuration"></a>

Esse link permite que você simplesmente gere os arquivos de configuração para o retroarch a partir de uma interface web.

​[https://surchargeur-ra-rb.netlify.com/](https://surchargeur-ra-rb.netlify.com/)​

Mais em breve =\)

