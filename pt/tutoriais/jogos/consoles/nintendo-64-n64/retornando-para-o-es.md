---
title: Retornando para o ES
---

# Retornando para o ES

O Mupen64plus não é configurado automaticamente pelo Recalbox como outros emuladores. Então você tem que fazer isso manualmente.

O modo de vídeo do N64 é definido em seu arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf). Por padrão, usamos o modo de vídeo: `n64.videomode=DMT 4 HDMI`

Este modo exibe uma resolução de **640x480**. Definimos esta resolução como padrão, porque o Raspberry Pi 2 não pode emular o N64 em uma resolução mais alta com uma boa taxa de atualização. Portanto, **640x480** é a resolução máxima a ser usada no Recalbox.


>**Atenção:** se sua tela não puder mudar a resolução \(por exemplo: tela de toque oficial do Pi\), você terá bordas pretas ao redor da imagem porque ela não será esticada para caber na tela.
{.is-danger}

* Neste caso, você deve definir `n64.videomode=default` e modificar`/recalbox/share/system/configs/mupen64/mupen64plus.cfg` para alterar a resolução de saída para a nativa de sua tela \(aqui **800x480**\) :

  ```text
  [Video-General]
  # Use fullscreen mode if True, or windowed mode if False
  Fullscreen = False
  # Width of output window or fullscreen width
  ScreenWidth = 800
  # Height of output window or fullscreen height
  ScreenHeight = 480
  ```

Porém, nem todos os monitores têm a mesma compatibilidade de modo de vídeo. Portanto, quando você tenta iniciar um jogo do N64, pode aparecer uma tela preta e retornar para o Emulationstation. Nesse caso, você precisa determinar quais modos de vídeo são compatíveis com o seu próprio monitor.

Use o [acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) e digite estes 2 comandos:

`tvservice -m DMT`

e

`tvservice -m CEA`

Os comandos retornarão algo assim:

```text
[root@RECALBOX ~]# tvservice -m DMT
Group DMT has 16 modes:
           mode 4: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 5: 640x480 @ 72Hz 4:3, clock:31MHz progressive 
           mode 6: 640x480 @ 75Hz 4:3, clock:31MHz progressive 
           mode 8: 800x600 @ 56Hz 4:3, clock:36MHz progressive 
           mode 9: 800x600 @ 60Hz 4:3, clock:40MHz progressive 
           mode 10: 800x600 @ 72Hz 4:3, clock:50MHz progressive 
           mode 11: 800x600 @ 75Hz 4:3, clock:49MHz progressive 
           mode 16: 1024x768 @ 60Hz 4:3, clock:65MHz progressive 
           mode 17: 1024x768 @ 70Hz 4:3, clock:75MHz progressive 
           mode 18: 1024x768 @ 75Hz 4:3, clock:78MHz progressive 
           mode 21: 1152x864 @ 75Hz 4:3, clock:108MHz progressive 
           mode 32: 1280x960 @ 60Hz 4:3, clock:108MHz progressive 
           mode 35: 1280x1024 @ 60Hz 5:4, clock:108MHz progressive 
           mode 36: 1280x1024 @ 75Hz 5:4, clock:135MHz progressive 
  (prefer) mode 57: 1680x1050 @ 60Hz 16:10, clock:119MHz progressive 
           mode 58: 1680x1050 @ 60Hz 16:10, clock:146MHz progressive 
```

e

```text
[root@RECALBOX ~]# tvservice -m CEA
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive 
           mode 2: 720x480 @ 60Hz 4:3, clock:27MHz progressive 
           mode 3: 720x480 @ 60Hz 16:9, clock:27MHz progressive 
  (native) mode 4: 1280x720 @ 60Hz 16:9, clock:74MHz progressive 
           mode 16: 1920x1080 @ 60Hz 16:9, clock:148MHz progressive 
```

Ok, agora temos todos os modos de vídeo que podem ser usados ​​neste monitor. Você tem que encontrar um modo de vídeo, com resolução igual ou inferior a 640x480, e definir este modo no arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf).

Se eu escolher este modo de vídeo:

```text
Group CEA has 5 modes:
           mode 1: 640x480 @ 60Hz 4:3, clock:25MHz progressive
```

O arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) deve ser alterado da seguinte forma:

* modo de vídeo padrão:`n64.videomode=DMT 4 HDMI`
* novo modo de vídeo:`n64.videomode=CEA 1 HDMI`

## Caso especial: tela CRT <a id="cas-particulier-ecran-crt"></a>

Se você estiver usando uma tela CRT, será necessário alterar o modo de vídeo da seguinte forma: `n64.videomode=default`

