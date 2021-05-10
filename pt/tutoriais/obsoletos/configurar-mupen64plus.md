---
title: Configurar Mupen64plus
---

# Configurar Mupen64plus

O Mupen64plus não é configurado automaticamente pelo Recalbox como outros emuladores. Você tem que fazer isso manualmente.


>**Informação:**
>
>_O botão **Hotkey** será automaticamente atribuído à **função de saída** do emulador._
{.is-info}

## _​_A - Adicione sua configuração de controle ao sistema:​ <a id="a-adicione-sua-configuracao-de-controle-ao-sistema"></a>

Para configurar seu controle, você precisa de algumas informações sobre ele.

* Obtenha [**acesso** **root**](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) 
* E use o [**comando jstest**](https://recalbox.gitbook.io/tutorials/v/portugues/obsoletos/teste-seu-joystick-com-o-jstest)

`jstest /dev/input/js0`

 **Exemplo:**

```text
Joystick (Broadcom Bluetooth Wireless  Joystick                        ) has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (Trigger, ThumbBtn, ThumbBtn2, TopBtn, TopBtn2, PinkieBtn, BaseBtn, BaseBtn2, BaseBtn3, BaseBtn4, BaseBtn5, BaseBtn6).
```

* Assim que o nome do controle e cada botão forem identificados, você precisará editar este arquivo`/usr/share/mupen64plus/InputAutoCfg.ini`
* Use este comando:`nano /usr/share/mupen64plus/InputAutoCfg.ini`
* Agora, no final do arquivo, adicione as informações de configuração, assim:

_Este é um exemplo, com informações provenientes de um controle \(nome do controle, número do botão, etc.\). Você deve adaptá-lo com as configurações do seu controle_

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

* Assim que a configuração estiver concluída, pressione `Ctrl+x` para sair do nano, concorde em editar o arquivo com `y` e pressione `Enter` para sair.

Agora você pode iniciar um jogo de N64 e testar sua configuração.


>**Notas:**
>
>Sua configuração é boa, gostou??  
>Perfeito ^^ Mas há um "problema".  
>Quando você atualiza seu Recalbox, todos esses arquivos de configuração são atualizados também. Haverá, portanto, uma reinicialização.  
>Se não quiser que isso aconteça a cada atualização, faça um backup do seu arquivo InputAutoCfg.ini.
{.is-warning}

## B - Adicionar comandos especiais <a id="b-adicionar-comandos-especiais"></a>

O Mupen64plus não suporta combinação de botões, como emuladores Retroarch, para iniciar comandos especiais. Mas você pode atribuir botões não usados ​​a comandos específicos, como _salvar/carregar um save_, _alternar um slot de save, etc..._

* Para fazer isso, em primeiro lugar, você deve **identificar todos os botões não utilizados** em sua configuração. Como vimos antes, obtenha [**acesso** **root**](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)​
* E use o [**comando jstest**](https://recalbox.gitbook.io/tutorials/v/portugues/obsoletos/teste-seu-joystick-com-o-jstest) , e **anote os códigos dos botões não usados.**
* Agora, **ainda no acesso root, edite** seu arquivo '**mupen64plus.cfg**' com este **comando:**`nano /recalbox/configs/mupen64/mupen64plus.cfg`
* Em seguida, **vá para a seção** chamada `[CoreEvents]` . **A parte útil é:**

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

Você deve ter em mente que Mupen64plus identifica o jogador 1 como 'J0', jogador 2 como 'J1', etc...

**Exemplo:** Se você deseja **adicionar o botão 10 ao jogador 1**, para o comando _**"salvar savestates"**_, você deve **editar o arquivo** assim: `Joy Mapping Save State = "J0B10"`

E se você quiser **adicionar o botão 5 do jogador 2** ao comando _**"carregar savestates"**_, você deve **editar o arquivo** assim: `Joy Mapping Load State = "J1B5"`

* Uma vez **configurado**, **pressione** `Ctrl+x`para **sair do nano, concorde em modificar** o arquivo com `y` e **pressione** `Enter` para **sair.**

