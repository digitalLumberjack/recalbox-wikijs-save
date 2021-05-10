---
title: Configure um monitor externo em x86 / x86\_64
---

# Configure um monitor externo em x86 / x86\_64

## Configuração <a id="configuracao"></a>

Desde a versão 7.0, a configuração de monitores externos é feita no [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)​

Abra o arquivo recalbox.conf, localizado na pasta: `/recalbox/share/system`

## Conheça as saídas de vídeo disponíveis <a id="conheca-as-saidas-de-video-disponiveis"></a>

* Conecte-se ao seu recalbox em [ssh](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)​
* No terminal ssh, digite: `xrandr`

Isso dará como resultado **as saídas de vídeo disponíveis e suas resoluções**. Exemplo:

```text
eDP-1 connected primary 1366x768+0+0 (normal left inverted right x axis y axis) 344mm x 193mm
   1366x768      60.06*+
   1360x768      59.80    59.96  
   1280x720      60.00    59.99    59.86    59.74  
   1024x768      60.04    60.00  
   960x720       60.00  
   928x696       60.05  
   896x672       60.01  
   1024x576      59.95    59.96    59.90    59.82  
   960x600       59.93    60.00   
VGA-1 disconnected (normal left inverted right x axis y axis)
HDMI-1 disconnected (normal left inverted right x axis y axis)
DP-1 disconnected (normal left inverted right x axis y axis)
```

Após escolher a saída, insira-a nesta parte do recalbox.conf:

```text
## Prefered external screen retrieved from ssh : xrandr
system.externalscreen.prefered=HDMI-1
## Force selected external screen to resolution ex : 1920x1080
system.externalscreen.forceresolution=1920x1080
```

## Mais informações: <a id="mais-informacoes"></a>

​[https://doc.ubuntu-fr.org/xrandr](https://doc.ubuntu-fr.org/xrandr)​

