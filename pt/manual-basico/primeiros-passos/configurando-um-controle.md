---
title: Configurando um controle
---

# Configurando um controle

## Adicionando e configurando um controle USB

Você pode adicionar controles USB no Recalbox. A maioria dos modelos é compatível \(consulte a [lista de compatibilidade](/compatibility/compatible-devices/controller)\).

* Após conectar um controle USB \(ou parear um controle Bluetooth\), pressione **START** no controle a ser configurado \(ou **ENTER** no teclado\)
* Selecione **"CONFIGURAÇÕES DOS CONTROLES"** e **siga as instruções**.

Os nomes dos botões são baseados no layout do controle do Super Nintendo: ​

![Controle de Super Nintendo \(SNES\)](/migration-images/manual-basico/primeiros-passos/1000px-snes_cont.jpg)


>Os botões L1, R1, L2, R2, L3 e R3 são baseados no controle do Playstation.
{.is-info}

O último botão a ser configurado, **HOTKEY \("tecla de atalho"\),** será utilizado para enviar [**comandos especiais**](/v/portugues/manual-basico/primeiras-nocoes/durante-o-jogo#comandos-especiais) dentro do emulador :

* Para controles de Xbox 360 e Xbox One, o _Hotkey_ está atribuído ao botão _HOME._
* Para controles de Ps3 e PS4, o _Hotkey_ está atribuído ao botão _PS._
* Em casos onde não há um botão dedicado ou um botão não está atribuído, é recomendado que o botão _HOTKEY_ seja configurado no botão _Select_ ou _L3_ \(Clique com a alavanca esquerda\).


>Para ignorar a configuração de um botão \(exceto _Hotkey_\), pressione e segure momentaneamente _Baixo_ para ir para o próximo botão.
{.is-info}

Ao terminar a configuração de controle, você poderá atribuir de forma fixa o controle para um jogador.   
  
Seu controle está configurado.

## Atribuindo botões

* Para controles de 6 botões \(SNES, arcade, ...\) os botões são mapeados de acordo com o controle do SNES \(veja acima\).
* Para controles de 2 botões \(NES, PC Engine, Gameboy, ...\) apenas os botões A e B serão utilizados.

## Usando um teclado

Se você não conseguir configurar seu controlador, pode conectar um teclado USB com fio ao Recalbox para configurá-lo.

* **START** = _ENTER_
* **SELECT** = _ESPAÇO_
* **Voltar** = _S_
* **Confirmar** = _A_

## Controles de PS3

Para **parear** um ****controle de PS3:

* Conecte o controle na porta USB \(usando um cabo adequado\) 
* Aguarde 10 segundos.
* Passados os 10 segundos, desconecte o controle.
* Pressione o botão **PS** para iniciar a conexão sem fio.


>**Nota:**  
>Para cópias asiáticas do PS3 Dualshock 3 \(como GASIA ou SHANWAN\), você precisará ajustar algumas configurações. Consulte [Drivers dos controles PS3](https://recalbox.gitbook.io/tutorials/v/portugues/controles/controles/os-drivers-dos-controles-ps3).
{.is-warning}


>**Atenção:**  
>Em caso de dúvida sobre a fonte de alimentação e o consumo de energia, é melhor evitar carregar o controle PS3 no Raspberry Pi, pois isso pode causar problemas de estabilidade.
>
>Conecte o controle ao Pi apenas para emparelhar o controle com o Recalbox.
{.is-danger}

Se você entende os parâmetros envolvidos ou deseja usar o controlador com uma conexão USB:

* você deve desabilitar o driver bluetooth PS3 em [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) definindo`controllers.ps3.enabled=0`

Lembre-se que a configuração dos controles é sempre baseado no layout do SNES:

| Controle de PS3 | Controle de SNES |
| :---: | :---: |
| X | B |
| ◯ | A |
| ⬜ | Y |
| △ | X |


>**Information:**
>
>Por padrão, a **HOTKEY** está associada ao botão **PS** \(aquele no meio do controle\). Para informações adicionais acesse a página de [Comandos Especiais](/v/portugues/manual-basico/primeiras-nocoes/durante-o-jogo#comandos-especiais).
{.is-info}

## Controles de Xbox 360 


>**Nota:  
>Os controles sem fio de** **Xbox 360** necessitam de um **receptor\(dongle\) específico** pois não funcionam através de bluetooth.
{.is-warning}

Lembre-se que a configuração dos controles é sempre baseado no layout do SNES:

| Controle de Xbox 360 | Controle de SNES |
| :---: | :---: |
| A | B |
| B | A |
| X | Y |
| Y | X |


>**Informação:**  
>Por padrão a **HOTKEY** está associada ao botão **HOME** \(aquele no meio do controle\). Para informações adicionais acesse a página de [Comandos Especiais](/v/portugues/manual-basico/primeiras-nocoes/durante-o-jogo#comandos-especiais).
{.is-info}

## Adicionar um controle Bluetooth

Para parear um controle Bluetooth:

* Coloque o controle em modo de _pareamento_. 
* Pressione **START**, e selecione "_CONFIGURAÇÕES DOS CONTROLES_"
* Em seguida, "_PAREAR CONTROLE BLUETOOTH_".

Uma **lista de controles** detectados aparecerá:

* Basta selecionar o seu controle que ele será pareado. 
* Agora você pode configurá-lo \(se ainda não for compatível com o Recalbox\).


>**Informação:**  
>Para os controles **8bitdo**, veja [8bitdo no Recalbox](https://recalbox.gitbook.io/tutorials/v/portugues/controles/controles/8bitdo)
{.is-info}

## Controles GPIO

* Você pode conectar botões e Joysticks diretamente na GPIO do Raspberry Pi \(Veja [**Controles GPIO**](https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controles-gpio)\)
* Você pode também conectar diretamente controles originais de PSOne, Nes Snes, Megadrive, ... \(Veja [**Controles Gamecom**](https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/jogue-com-seu-controle-original-usando-gamecon)\). 

## Controles Virtual

 Com os [Controles Virtuais Miroof](https://github.com/jehervy/node-virtual-gamepads) você pode adicionar até 4 controles através de smartphones e/ou tablets!

* Abra o navegador web em seu smartphone
* Coloque o endereço IP do seu Recalbox na barra de endereços seguido de \(port=8080\)


>**Informação:**  
>Você pode obter o endereço IP do seu Recalbox acessando o menu e indo em **CONFIGURAÇÕES DE REDE**
{.is-info}

![zonas de mapeamento de bot&#xF5;es do controle virtual](/migration-images/manual-basico/primeiros-passos/virutalgamepad_touch_zones.png)

