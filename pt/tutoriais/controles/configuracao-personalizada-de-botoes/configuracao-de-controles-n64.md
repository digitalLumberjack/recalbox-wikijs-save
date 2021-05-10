---
title: Configuração de controles N64
---

# Configuração de controles N64

## EDITAR: <a id="editar"></a>

Por padrão, **/usr/share/mupen64plus** é somente leitura, por isso não funcionará a menos que você habilite o modo de leitura e gravação usando este comando `mount -o remount, rw /`​

## EDITAR PARA A VERSÃO DE RECALBOX&gt; V4.1 <a id="editar-para-a-versao-de-recalbox-greater-than-v-4-1"></a>

jstest não existe mais -&gt; use sdl2-jstest

Caso seu botão 0 saia do emulador \(como a tecla de atalho\), você precisará editar o seguinte arquivo:`~/configs/mupen64/mupen64plus.cfg` =&gt; Altere a configuração **`Joy Mapping Stop = "J1B0"`** para **`Joy Mapping Stop = ""`**

## Para mais informações sobre os controles N64, veja também: <a id="para-mais-informacoes-sobre-os-controles-n-64-veja-tambem"></a>

​[https://forum.recalbox.com/topic/9016/a-lire-manettes-n64](https://forum.recalbox.com/topic/9016/a-lire-manettes-n64)​[https://forum.recalbox.com/topic/21051/utilizar-dois-emuladores-n64-recalbox-pc\_x64/5](https://forum.recalbox.com/topic/21051/utilizar-dois-emuladores-n64-recalbox-pc_x64/5)​

## RECALBOX V3.3.0 UNICAMENTE <a id="recalbox-v-3-3-0-unicamente"></a>

O Mupen64plus não é configurado automaticamente pelo Recalbox como outros emuladores. Então você tem que fazer isso manualmente.

_Para informação: o botão de_ _**Hotkey**_ _será automaticamente atribuído à função de saída do emulador._

### A - Adicione a configuração do seu controlador ao sistema: <a id="a-adicione-a-configuracao-do-seu-controlador-ao-sistema"></a>

Além disso, você precisa saber mais sobre o assunto. Para configurar seu controlador, você precisará de informações sobre ele. [Entre como root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal), e use o comando [jstest:](https://recalbox.gitbook.io/tutorials/v/portugues/obsoletos/teste-seu-joystick-com-o-jstest)​

`jstest /dev/input/js0`

ou

`sdl2-jstest -l`

No meu caso, recebo:

```text
Joystick (Broadcom Bluetooth Wireless  Joystick                        ) has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (Trigger, ThumbBtn, ThumbBtn2, TopBtn, TopBtn2, PinkieBtn, BaseBtn, BaseBtn2, BaseBtn3, BaseBtn4, BaseBtn5, BaseBtn6).
```

Assim que o nome do controle e cada botão forem identificados, você deve modificar este arquivo: `/usr/share/mupen64plus/InputAutoCfg.ini`

Use este comando:

`nano /usr/share/mupen64plus/InputAutoCfg.ini`

Agora, no final do arquivo, adicione as informações de configuração, assim:

_Este modelo é um exemplo, com informações sobre o meu próprio controle \(nome do controle, número do botão etc ...\). Você precisará adaptá-lo com as informações de seu próprio controle._

```text
[Broadcom Bluetooth Wireless  Joystick                        ]
plugged = True
plugin = 2
mouse = False
AnalogDeadzone = 4096,4096
AnalogPeak = 32768,32768
DPad R = hat(0 Right)
DPad L = hat(0 Left)
DPad D = hat(0 Down)
DPad U = hat(0 Up)
Start = button(9)
Z Trig = button(7)
B Button = button(2)
A Button = button(1)
C Button R = axis(3+)
C Button L = axis(3-)
C Button D = axis(2+)
C Button U = axis(2-)
R Trig = button(5)
L Trig = button(4)
Mempak switch = button(6)
Rumblepak switch = 
X Axis = axis(0-,0+)
Y Axis = axis(1-,1+)
```

Assim que sua configuração estiver correta, pressione `Ctrl + x` para sair do nano, concorde em sobrescrever o arquivo com `y` e pressione `Enter` para sair. Agora você pode iniciar um jogo N64 e testar sua configuração.

Sua configuração está correta, gostou? Ótimo ^^ Mas há um "problema". Quando você atualiza seu Recalbox, todos esses arquivos de configuração também são atualizados. Portanto, eles serão redefinidos. Se você não quiser fazer isso após cada atualização, faça um backup do arquivo `InputAutoCfg.ini`. Você também pode adicionar sua configuração ao Recalbox. Você deve consultar este ponto e postar sua própria configuração no comentário.

Em seguida, o adicionaremos ao sistema durante uma atualização futura do Recalbox \(não é mais necessário porque um configgen está integrado desde a versão 4.0.0 do Recalbox\).

### B - Adicionar os comandos especiais <a id="b-adicionar-os-comandos-especiais"></a>

O Mupen64plus não suporta combinações de botões, como emuladores Retroarch, para iniciar um comando especial. Mas você pode atribuir botões não utilizados a um comando específico, como _salvar / carregar um estado de salvamento, alterar locais de salvamento, etc._

Para fazer isso, como primeira etapa, você deve identificar todos os botões não utilizados em sua configuração. Como visto antes, vá para o [acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) e use o comando [jstest](https://recalbox.gitbook.io/tutorials/v/portugues/obsoletos/teste-seu-joystick-com-o-jstest), depois anote o número do código dos botões não usados.

Agora, ainda no acesso root, edite seu arquivo `mupen64plus.cfg` com este comando:

`nano /recalbox/configs/mupen64/mupen64plus.cfg`

Em seguida, vá para a seção chamada `[CoreEvents]`. A seção correta é esta:

```text
# Joystick event string for stopping the emulator
Joy Mapping Stop = ""
# Joystick event string for switching between fullscreen/windowed modes
Joy Mapping Fullscreen = ""
# Joystick event string for saving the emulator state
Joy Mapping Save State = ""
# Joystick event string for loading the emulator state
Joy Mapping Load State = ""
# Joystick event string for advancing the save state slot
Joy Mapping Increment Slot = ""
# Joystick event string for taking a screenshot
Joy Mapping Screenshot = ""
# Joystick event string for pausing the emulator
Joy Mapping Pause = ""
# Joystick event string for muting/unmuting the sound
Joy Mapping Mute = ""
# Joystick event string for increasing the volume
Joy Mapping Increase Volume = ""
# Joystick event string for decreasing the volume
Joy Mapping Decrease Volume = ""
# Joystick event string for fast-forward
Joy Mapping Fast Forward = ""
# Joystick event string for pressing the game shark button
Joy Mapping Gameshark = ""
```

Tenha em mente que Mupen64plus identifica o `player 1` como `J0`, o `player 2` como `J1`etc... Então, por exemplo, se você quiser adicionar o botão número 10 do jogador 1 ao comando "salvar savestates", você deve edite seu arquivo como este: `Joy Mapping Save State = "J0B10"`

E se você quiser adicionar o botão 5 do jogador 2 ao comando "_load savestates_", você deve editar seu arquivo assim: `Joy Mapping Load State = "J1B5"`

Assim que sua configuração estiver correta, pressione `Ctrl+x` para sair do nano, concorde em sobrescrever o arquivo com `y` e pressione `Enter` para sair.

## ​ <a id="undefined"></a>

