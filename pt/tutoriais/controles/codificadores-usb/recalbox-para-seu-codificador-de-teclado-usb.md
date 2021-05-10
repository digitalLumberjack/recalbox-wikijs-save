---
title: Recalbox para seu codificador de teclado USB
---

# Recalbox para seu codificador de teclado USB

## Introdução​ <a id="introducao"></a>

Este tutorial é para Recalbox 4.0.0 Beta 2 ou superior.

Xarcade2jstick foi corrigido para suportar codificadores de teclado. Você pode precisar reconfigurar algumas chaves em seu codificador, pois infelizmente os dispositivos Xarcade do X-gaming não foram mapeados como controles comuns do MAME.

## Adicionando seu codificador de teclado​ <a id="adicionando-seu-codificador-de-teclado"></a>

Até agora, apenas a primeira geração do IPAC foi incluída. Se você tiver outro codificador de teclado, siga estas etapas:

* Conecte-se ao seu Recalbox localmente ou via SSH
* Encontre o nome do dispositivo do seu codificador com`ls /dev/input/by-id`. Normalmente, o resultado é seguido por um kbd. Por exemplo: _usb-Ultimarc\_IPAC\_2\_Ultimarc\_IPAC\_2\_9-if01-event-kbd_


>**NOTA:** Um único codificador pode ter vários nomes possíveis, então tente todos eles, por exemplo:
>
>* usb-Cypress\_I-PAC\_Arcade\_Control\_Interface-event-kbd -&gt; functiona
>* usb-Cypress\_I-PAC\_Arcade\_Control\_Interface-if01-event-kbd -&gt; não funciona
{.is-info}

* Agora remonte em modo de gravação `mount -o remount,rw /`
* Crie um arquivo vazio com o mesmo nome do seu dispositivo de teclado encontrado 2 etapas acima`touch /recalbox/share_init/system/configs/xarcade2jstick/devicename`.

  No exemplo anterior:`touch /recalbox/share_init/system/configs/xarcade2jstick/usb-Ultimarc_IPAC_2_Ultimarc_IPAC_2_9-if01-event-kbd`

* Edite [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) e defina como:`controllers.xarcade.enabled=1`
* Reinicie digitando `reboot`

O Recalbox agora está configurado para esses dispositivos.

## Mapeamento das teclas​ <a id="mapeamento-das-teclas"></a>

### v4.0.0 - beta4 : <a id="v-4-0-0-beta4"></a>

| Tecla | Jogador 1 | Jogador 2 |
| :--- | :--- | :--- |
| CIMA | Tecla Cima ou Tecla 8 do teclado numérico | Tecla R |
| BAIXO | Tecla Baixo ou Tecla 2 do teclado numérico | Tecla F |
| ESQUERDA | Tecla Esquerda ou Tecla 4 do teclado numérico | Tecla D |
| DIREITA | Tecla Direita ou Tecla 6 do teclado numérico | Tecla G |
| A | Tecla Z | Tecla E |
| B | Tecla SHIFT esquerda | Tecla W |
| X | Tecla ALT esquerda | Tecla S |
| Y | Tecla CTRL esquerda | Tecla A |
| START | Tecla 1 do teclado numérico | Tecla 2 do teclado numérico |
| SELECT | Tecla 5 do teclado numérico | Tecla 6 do teclado numérico |
| L1 | Barra de Espaço | Tecla Q |
| R1 | Tecla X | Tecla \[ ou Tecla K |
| HOTKEY | Tecla 3 do teclado numérico ou Tecla V | Tecla 4 do teclado numérico ou Tecla L |

### ​v4.0.0 - beta2 : <a id="v-4-0-0-beta2"></a>

| Tecla | Jogador 1 | Jogador 2 |
| :--- | :--- | :--- |
| CIMA | Tecla Cima ou Tecla 8 do teclado numérico | Tecla R |
| BAIXO | Tecla Baixo ou Tecla 2 do teclado numérico | Tecla F |
| ESQUERDA | Tecla Esquerda ou Tecla 4 do teclado numérico | Tecla D |
| DIREITA | Tecla Direita ou Tecla 6 do teclado numérico | Tecla G |
| A | Tecla Z | Tecla E |
| B | Tecla SHIFT esquerda | Tecla W |
| X | Tecla ALT esquerda | Tecla S |
| Y | Tecla CTRL esquerda | Tecla A |
| START | Tecla 1 do teclado numérico | Tecla 2 do teclado numérico |
| SELECT | Tecla 3 do teclado numérico | Tecla 4 do teclado numérico |
| L1 | Barra de Espaço | Tecla Q |
| R1 | Tecla X | Tecla \[ |
| HOTKEY | Tecla C | Tecla \] |

###  <a id="v-4-0-0-beta2"></a>

