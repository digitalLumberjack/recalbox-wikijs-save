---
title: Conectando seu Recalbox a um CRT via cabo composto
---

# Conectando seu Recalbox a um CRT via cabo composto

Se você deseja **conectar seu Recalbox a um CRT**, precisará de um **mini-jack para RCA** como este:

![Soquete de &#xE1;udio/v&#xED;deo RPi](https://image.ibb.co/mQCKDJ/rpi_AV_socket.jpg)




>Cuidado, nos **cabos de câmeras de vídeo, a saída de vídeo pode estar na entrada de áudio direita** \(vermelha\).
>
>Além disso, o tipo de cabo necessário não é realmente comum. É preferível testar com um multímetro, para garantir que o cabo que você planeja usar corresponda ao diagrama proposto acima \(uma inversão de terra e vídeo no conector leva a uma imagem em preto e branco saltitante, sinal de cabo inadequado\).
{.is-danger}


>No **Recalbox 4.0.0**, você deve tornar a partição gravável.
{.is-warning}

* ​[Edite seu /boot/config.txt​](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/modificacao/editar-o-arquivo-config.txt)​

  **Comente** cada linha começando com `hdmi_` **usando** `#`, e **adicionando o sdtv\_mode suportado:**

  ```text
  sdtv_mode=0    Normal NTSC   
  sdtv_mode=1    Japanese version of NTSC – no pedestal  
  sdtv_mode=2    Normal PAL   
  sdtv_mode=3    Brazilian version of PAL – 525/60 rather than 625/50, different subcarrier
  ```

* Para obter um **som melhor através da saída composta**, ative o driver de áudio experimental para o Raspberry pi


>**Cuidado**, este modo pode criar uma lentidão no Recalbox.
{.is-danger}

* Se for esse o caso, comente a linha anterior e force a saída de áudio ao conector

```text
#audio_pwm_mode=2
hdmi_drive=1
```

* Finalmente, **adicione**`hdmi_ignore_hotplug=1` para **forçar a saída composta**.

Se você estiver no Recalbox OS 4.0 ou superior, o sistema de arquivos é somente leitura. Leia [este link](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/modificacao/editar-o-arquivo-config.txt).

Seu **config.txt** deve se parecer como abaixo:

```text
sdtv_mode=2
hdmi_ignore_hotplug=1
audio_pwm_mode=2
```

* **Edite** o arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) e altere`global.videomode` para `default`

```
global.videomode=default
```

* Se você estiver usando o **emulador n64**, comente também esta linha:

```text
n64.videomode=DMT 9 HDMI
```

* e deixe essa linha sem comentar:

```text
n64.videomode=default
```

* Por fim, desative a suavização de jogos e todos os shaders no menu EmulationStation \(START -&gt; OPÇÕES DE JOGOS\), o que permitirá que você tenha a renderização original em todos os sistemas!

## Tudo está lento no modo composto <a id="everythings-slow-in-composite-mode"></a>

`audio_pwm_mode=2` melhora o som, mas pode diminuir a velocidade do sistema no modo composto, especialmente no Pi zero. Nesse caso, use o seguinte modo:

```text
audio_pwm_mode=0
```

