---
title: Jogue com seu controle original usando Gamecon
---

# Jogue com seu controle original usando Gamecon

## 1 - Intro <a id="1-intro"></a>

**O driver** foi projetado **para uso** com controles de jogos retro **conectados aos GPIOs** do Raspberry Pi. **Até 4 controles** podem ser usados **​​ao mesmo tempo** se forem do seguinte tipo:

* Controle NES
* Controle SNES
* Controle PSX / PS2
* Controle N64
* Controle Gamecube


>**O driver é baseado no driver Gamecon**, mas usa **diferentes parâmetros e pinagens**. Logo, **não há garantia de que funcionará**, portanto, **faça isso por sua conta e risco**!
{.is-danger}

## 2 - Conecte os controles <a id="2-conecte-os-controles"></a>

**Os PINS P1-01 e P1-06** são usados ​​para a **alimentação de 3,3V** e **o terra**. Eles são **comuns** a todos os controles **conectados ao GPIO**. Embora os **controles SNES / NES** sejam classificados em **5V**, **eles deveriam funcionar em 3,3V**. Portanto, **não há necessidade de usar um conversor** nos PINS de dados. A **intensidade máxima** \(50mA\) do Raspberry deve ser suficiente **para alimentar 4 controladores no GPIO**. No entanto, você deve **usar uma fonte de alimentação Raspberry de alto desempenho** \(tipo 2.1A\) para evitar qualquer **queda de tensão indesejada.**

**Os PINs de dados P1-03, 05, 07, 26** \(GPIO0, GPIO1, GPIO4 e GPIO7\) são **independentes um do outro** e **cada controle** usa um **PIN exclusivo**.


>**Informação:**
>
>* **Os PINS P1-03 e P1-05** correspondem a **GPIO2 e GPIO3** nas **placas rev.2.** Isso deve ser levado em consideração ao carregar o módulo, conforme explicado na **seção 3**. 
>* **PINS P1-19 e P1-23** \(GPIO10 e 11\) são **PINs de sinal comuns** a todos os controles **NES/SNES.**
>* **PINS P1-08, P1-10 e P1-12** \(GPIO14, 15 e 18\) são **PINS de sinal comuns** a todos os controles **PSX/PS2.**
{.is-info}

​

### 2.1 Controles NES / SNES <a id="2-1-controles-nes-snes"></a>

| PIN RASPBERRY | PIN controle SNES | PIN controle NES |
| :---: | :---: | :---: |
| P1-01 \(3.3V\) | 1 \(power - 5V\) | 1 \(power - 5V\) |
| GPIO10 | 2 \(clock\) | 5 \(clock\) |
| GPIO11 | 3 \(latch\) | 6 \(latch\) |
| GPIOXX | 4 \(data\) | 7 \(data\) |
| P1-06 \(GND\) | 7 \(ground\) | 4 \(ground\) |

 **PINAGEM NES e SNES**

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Ly12cOjJDyhW9cGp7Mt%2F-Ly13ct-lbBNlcPB5c54%2F68747470733a2f2f692e7761726f73752e6f72672f646174612f76722f696d672f303032372f32322f313434343135303236343635322e706e67.png?alt=media&token=a116d987-374d-4cb8-926c-f7334c6cdbe2)

Os **GPIOXXs** são **PINs de dados independentes**. Consulte a **seção 3** para selecionar o **GPIO correto** a ser usado.

​

### 2.2 Controles N64​ <a id="2-2-controles-n-64"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDqTCN9r2xAaAtGh2wb%2F-MDqWClO5IkPkFB9aT0b%2F993slmdi.bmp?alt=media&token=19b202af-888d-4eeb-bc2c-ad4049c429c3)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDqTCN9r2xAaAtGh2wb%2F-MDqXq8EVy-uQb3JtQgd%2Fn64_pinouts.png?alt=media&token=4ebb157b-1cef-4c4e-b291-ebd7831101f4)

### 2.3 Controles Gamecube <a id="2-3-controles-gamecube"></a>

| PIN RASPBERRY | PIN controle GAMECUBE |
| :---: | :---: |
| P1-01 \(3.3V\) | 6 \(power/3.43V\) |
| GPIOXX | 3 \(data\) |
| P1-06 \(GND\) | 2&5 \(gnd\) |

 Os **GPIOXXs** são **PINs de dados independentes**. Consulte a **seção 3** para selecionar o **GPIO correto** a ser usado.

​

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDw-HeGvJLeeBwP6W2C%2F-MDw-ZjkI6ByZRMtRnej%2Fgcpad.png?alt=media&token=d996e413-79a4-4deb-abf9-188ee95dae9e)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDqTCN9r2xAaAtGh2wb%2F-MDqXrfiIaTP0ZeICxgf%2Fgc_pinouts.png?alt=media&token=d489aa27-ec65-4eda-8b76-fcfcd3568234)

### ​2.4 Controles PSX / PS2 <a id="2-4-controles-psx-ps2"></a>

| PIN RASPBERRY | PIN controle PSX / PS2 |
| :---: | :---: |
| P1-01 \(3.3V\) | 5 \(VCC\) |
| GPIO14 | 2 \(Command\) |
| GPIO15 | 6 \(ATT\) |
| GPIO18 | 7 \(CLK\) |
| GPIOXX | 1 \(Data\) |
| P1-06 \(GND\) | 4 \(ground\) |

Os **GPIOXXs** são **PINs de dados independentes**. Consulte a **seção 3** para selecionar o **GPIO correto** a ser usado.

![](http://www.geocities.ws/digitan000/Hardware/22/pinout.gif)

## 3 Configurar o driver <a id="3-configurar-o-driver"></a>

### 3.1 Configurar os controles <a id="3-1-configurar-os-controles"></a>

* **Ative o driver Gamecon** no arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) **colocando**`controllers.gamecon.enabled=1` \(se existir, modifique-o. Caso contrário, crie-o\).
* **Use o seguinte índice do controle** para definir a configuração.`controllers.gamecon.args` : `map=<pad1/GPIO0>,<pad2/GPIO1>,<pad3/GPIO4>,<pad4/GPIO7>,<pad5/GPIO2>,<pad6/GPIO3>`

Onde é o número que define o tipo de controle:

* 0 = sem conexão
* 1 = controle SNES
* 2 = controle NES
* 3 = controle Gamecube
* 6 = controle N64
* 7 = controle PSX/PS2
* 8 = controle PSX DDR
* 9 = mouse SNES

Por exemplo, se um **controle SNES** estiver conectado ao **GPIO4** e um **controle N64** ao **GPIO7**, o **mapeamento será**`map=0,0,1,6`.


>Informação:
>
>* **pad1 e pad2** são usados ​​apenas com uma **placa rev.1**
>* **pad5 e pad6** são usados ​​apenas com uma **placa rev.2**
>* **Os controles PSX / PS2** requerem **um resistor de pullup.** **Pad5 \(GPIO2\) e pad6 \(GPIO3\)** possuem esse **resistor embutido.**
{.is-info}

Portanto, se você tiver **uma placa rev.2, o pad1 e o pad2** devem ser **definidos como 0**.

**O índice final do controle** \(usado pelos programas\) é atribuído sequencialmente para os controles conectados, **começando com 0.** Portanto, no exemplo anterior, **o controle SNES** teria um índice **igual a 0** e o **controle N64** teria um índice **igual a 1**.

* **Use o seguinte comando** para verificar se **o módulo foi carregado com sucesso:** `tail /var/log/kern.log`

​

### 3.2 Teste os controles <a id="3-2-teste-os-controles"></a>

**​**[**Teste** seu joystick usando o jtest](https://recalbox.gitbook.io/tutorials/v/portugues/obsoletos/teste-seu-joystick-com-o-jstest)​

​

### 3.3 Calibre o eixo analógico de um controle N64 <a id="3-3-calibre-o-eixo-analogico-de-um-controle-n64"></a>

Para **cada controle N64**, **execute o seguinte comando:**

```text
jscal -s 4,1,0,0,0,6972137,6972137,1,0,0,0,6547006,6468127,1,0,0,0,536854528,536854528,1,0,0,0,536854528,536854528 /dev/input/jsX
```

​

### 3.4 Configurar o tempo de resposta para os controladores PSX <a id="3-4-configurar-o-tempo-de-resposta-para-os-controladores-psx"></a>

**O tempo de resposta** para os controladores **PSX é de 10µs**, o que **minimiza o atraso** induzido pelo driver. No entanto, em **alguns casos raros**, isso não é suficiente **para ter uma entrada estável**. **Se você tiver problemas** de leitura **com os controles PSX**, **aumente o atraso** seguindo o parâmetro **"extra modbprobe": "psx\_delay ="**, em que **"delay"** é o valor em µs **entre 1 e 50.**

## 4 Para ir além <a id="4-para-ir-alem"></a>

**Somente em inglês** =&gt; Driver de gamepad para vários console para GPIO: [https://www.raspberrypi.org/forums/viewtopic.php?f=78&t=15787](https://www.raspberrypi.org/forums/viewtopic.php?f=78&t=15787)​

Obrigado a "**marqs**" pelo driver e por nos permitir usar o "**README**" no Recalbox WIKI.

