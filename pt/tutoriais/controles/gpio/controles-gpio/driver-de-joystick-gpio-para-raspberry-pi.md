---
title: Driver de joystick GPIO para Raspberry Pi
---

# Driver de joystick GPIO para Raspberry Pi

O mk\_arcade\_joystick\_rpi está totalmente integrado na distribuição do Recalbox: consulte [http://www.recalbox.com​](https://www.recalbox.com/pt-br/)​

**A ramificação Hotkeybtn agora suporta um botão adicional por jogador, em vez do suporte MCP23017**

## Introdução <a id="introducao"></a>

O Raspberry Pi é uma ferramenta incrível que eu descobri há um mês. O projeto RetroPie me fez querer construir minha própria máquina de fliperama com simples botões e joysticks.

Então comecei a conectar meus joysticks e botões ao Raspberry Pi e escrevi a primeira metade desse driver para conectar meus joysticks e botões diretamente às portas GPIO dele.

No entanto, o Raspberry Pi B Rev 2 tem no máximo 21 portas GPIO utilizáveis, o que não é suficiente para conectar todos os 28 switches \(2 joysticks e 20 botões\) exigidos por um painel padrão.

ATUALIZAÇÃO 0.1.5: adicionada personalização do GPIO

ATUALIZAÇÃO 0.1.4: Compatibilidade com o Raspberry Pi 2

ATUALIZAÇÃO 0.1.3: Compatibilidade com 3.18.3:

A instalação do driver agora funciona com o kernel 3.18.3, lançado com o firmware mais recente.

ATUALIZAÇÃO 0.1.2: feito o _downgrade_ para 3.12.28+:

Como o módulo não carrega um kernel e cabeçalhos recentes, estamos adicionando a capacidade de fazer o _downgrade_ do seu firmware para uma versão compatível, até encontrarmos uma solução.

ATUALIZAÇÃO 0.1.1: versão do Raspberry Pi B +:

A nova revisão do Raspberry Pi B + nos trouxe 9 portas GPIO adicionais, por isso agora podemos conectar 2 joysticks e 12 botões diretamente às portas GPIO. Atualizei o driver para suportar os 2 joysticks na configuração das portas GPIO.

#### ​ <a id="undefined"></a>

#### Ainda mais joysticks <a id="undefined-1"></a>

Um pequeno chip barato chamado MCP23017 permite adicionar 16 GPIOs externos e aceita apenas duas portas GPIO no Raspberry Pi. O chip permite usar os GPIOs como entrada ou saída; a entrada é o que estamos procurando, se queremos ainda mais joysticks.

Se você deseja usar mais de um chip, o protocolo i2c permite escolher endereços diferentes para o dispositivo conectado, mas todos eles usam o mesmo SDA e SCL GPIO.

Em teoria, você pode conectar até 8 chips, portanto 8 joysticks.

## O software <a id="o-software"></a>

O driver do joystick é baseado no driver gamecon\_gpio\_rpi de [marqs](https://github.com/marqs85).

Ele é escrito para 4 joysticks direcionais e 8 botões por jogador. O uso de um MCP23017 estende os números de entrada para 16: 4 direções e 12 botões.

Ele pode reconhecer joysticks + botões conectados nas portas GPIO do Raspberry Pi \(dois joysticks na revisão RPi B+\) e até 5 outros joysticks + botões provenientes dos chips MCP23017. É necessário um MCP23017 para cada joystick.

Ele usa pull-ups internos do Raspeberry Pi e MCP23017, portanto todos os switches devem ser conectados diretamente ao seu GPIO e terra \(GROUND\) correspondentes.

## Casos comuns: Joysticks conectados às portas GPIO <a id="casos-comuns-joysticks-conectados-as-portas-gpio"></a>

#### ​Pinagem <a id="undefined-1-1"></a>

Considere um painel de controle de 6 botões com esta ordem de botão:

```text
 ↑   Ⓨ Ⓧ Ⓛ  
← →	 Ⓑ Ⓐ Ⓡ  
 ↓  
```

Onde:  
R = TR  
L = TL

Aqui está o resumo da pinagem das portas GPIO rev B:​[​​](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOs.png)​

![](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOs.png)

Se você tem um Raspberry Pi Rev B + 1 ou 2:​[​​](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOsb+.png)​

![](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOsb+.png)

Obviamente, o terra pode ser comum a todos os interruptores.

## Instalação <a id="instalacao"></a>

#### ​Script de instalação <a id="undefined-2"></a>

Baixe o script de instalação:

```text
mkdir mkjoystick
cd mkjoystick
wget https://github.com/recalbox/mk_arcade_joystick_rpi/releases/download/v0.1.4/install.sh
```

Atualize seu sistema:

```text
sudo sh ./install.sh updatesystem
sudo reboot
```

Lembre-se de reiniciar \(ou a próxima parte não funcionará\) e reiniciar o script sem argumentos:

```text
sudo sh ./install.sh
```

Agora vá para ~~_**Carregando o driver**_~~

### ​Instalação manual <a id="instalacao-manual"></a>

Atualização do sistema:

```text
sudo apt-get update
sudo apt-get upgrade
sudo rpi-update
```

1 - Instale tudo o que você precisa:

```text
sudo apt-get install -y --force-yes dkms cpp-4.7 gcc-4.7 git joystick
```

2 - Instale os cabeçalhos mais recentes do kernel:

```text
sudo apt-get install -y --force-yes raspberrypi-kernel-headers
```

3.a - Instale a versão do driver \(de preferência\):

```text
wget https://github.com/recalbox/mk_arcade_joystick_rpi/releases/download/v0.1.4/mk-arcade-joystick-rpi-0.1.4.deb
sudo dpkg -i mk-arcade-joystick-rpi-0.1.4.deb
```

3.b - Ou compile e instale com dkms:

3.b.1 - Baixe os arquivos:

```text
git clone https://github.com/pinuct/mk_arcade_joystick_rpi/tree/customgpio
```

3.b.2 - Crie uma pasta em "/usr/src/_module_-_module-version_/"

```text
mkdir /usr/src/mk_arcade_joystick_rpi-0.1.5/
```

3.b.3 - Copie os arquivos para a pasta:

```text
cd mk_arcade_joystick_rpi/
cp -a * /usr/src/mk_arcade_joystick_rpi-0.1.5/
```

3.b.4 - Compile e instale o módulo:

```text
dkms build -m mk_arcade_joystick_rpi -v 0.1.5
dkms install -m mk_arcade_joystick_rpi -v 0.1.5
```

## Carregando o driver <a id="carregando-o-driver"></a>

O driver é carregado com o comando modprobe e recebe um parâmetro chamado "map" representando os joysticks conectados. Quando você precisar carregar o driver, precisará passar uma lista de parâmetros que representam a lista de joysticks conectados. O primeiro parâmetro será o joystick mapeado para /dev/input/js0, o segundo para js1, etc.

Se você conectou um joystick às portas GPIO do Raspberry Pi \(joystick 1 na imagem da pinagem\), deve passar "map=1" como parâmetro. Se você está na revisão B+ e conectou 2 joysticks, deve passar map="1,2" como parâmetro.

Se você tiver um joystick conectado à sua versão do Raspberry Pi B ou B +, será necessário executar o seguinte comando:

```text
sudo modprobe mk_arcade_joystick_rpi map=1
```

Se você tiver dois joysticks conectados na sua versão do Raspberry Pi B ou B +, será necessário executar o seguinte comando:

```text
sudo modprobe mk_arcade_joystick_rpi map=1,2
```

Se você tiver uma tela TFT conectada ao seu Raspberry Pi B +, não poderá usar todas as portas GPIO. Você pode executar o seguinte comando para usar apenas os GPIOs não usados ​​pela tela TFT \(Observe que nem todas as telas TFT usam os mesmos pinos. Os GPIOs usados ​​com esta placa são: 21, 13, 26, 19 , 5, 6, 22, 4, 20, 17, 27, 16\):

```text
sudo modprobe mk_arcade_joystick_rpi map=4
```

Se você não deseja usar todos os pinos ou se deseja usar um cartão com **GPIO personalizado**:

```text
sudo modprobe mk_arcade_joystick_rpi map=5 gpio=pin1,pin2,pin3,.....,pin12
```

Onde _pinx_ é o número da porta GPIO que você deseja. Existem 12 GPIOs possíveis com **controle de botão: Y-, Y +, X-, X +, start, select, a, b, tr, y, x, tl**. Use -1 para pinos não utilizados. por exemplo `gpio=21,13,26,19,-1,-1,22,24,-1,-1,-1,-1,-1` usa as portas GPIO 21, 13, 26, 19 para os eixos e as portas 22 e 24 para os botões A e B, o restante dos botões não é utilizado.

As ações do joystick 1 serão relatadas ao arquivo "/dev/input/js0" e as ações do joystick 2 serão relatadas ao arquivo "/dev/input/js1".

#### ​ <a id="undefined-4"></a>

### Carregamento automático na inicialização <a id="carregamento-automatico-na-inicializacao"></a>

Abra `/etc/modules` :

```text
sudo nano /etc/modules
```

e adicione a linha que você usa para carregar o driver:

```text
mk_arcade_joystick_rpi
```

Em seguida, crie o arquivo `/etc/modprobe.d/mk_arcade_joystick.conf` :

```text
sudo nano /etc/modprobe.d/mk_arcade_joystick.conf
```

e adicione a configuração do módulo:

```text
options mk_arcade_joystick_rpi map=1,2
```

​

### Teste <a id="teste"></a>

Use o seguinte comando para testar as ações dos joysticks:

```text
jstest /dev/input/js0
```

​

### Outros casos de joysticks: MCP23017 <a id="outros-casos-de-joysticks-mcp23017"></a>

Aqui está o resumo da pinagem MCP23017:​[​​](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_mcp23017.png)​

![](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_mcp23017.png)

#### ​ <a id="undefined-5"></a>

#### Preparando o Raspberry Pi para o MCP23017 <a id="preparando-o-raspberry-pi-para-o-mcp23017"></a>

Siga as instruções de instalação dos padrões.

Ative o i2c no seu Pi:

```text
sudo nano /etc/modules
```

Adicione as seguintes linhas para carregar automaticamente os módulos i2c:

```text
i2c-bcm2708 
i2c-dev
```

E se o arquivo `/etc/modprobe.d/raspi-blacklist.conf` existir :

```text
sudo nano /etc/modprobe.d/raspi-blacklist.conf
```

Verifique se você tem uma linha com:

```text
i2c-bcm2708 
```

e adicione um \# \(hashtag\) no início da linha para remover a lista negra

Reinicie ou carregue os dois módulos:

```text
modprobe i2c-bcm2708 i2c-dev
```

​

### Preparação do chip MCP23017 <a id="preparation-de-la-puce-mcp23017"></a>

Você precisa definir os pinos A0, A1 e A2 como 0 ou 1 para definir o endereço i2c do chip.

Se você tiver apenas um chip, conecte todos os 3 pinos ao terra. Basta conectar um dos pinos a 3,3V para definir seu estado como 1 e alterar o endereço i2c do MCP23017.

Você também precisa conectar o pino RESET a 3,3V.

​

### Configuração <a id="configuracao"></a>

Quando você deseja carregar o driver, precisa verificar uma lista de parâmetros que representam a lista de joysticks conectados. O primeiro parâmetro será o joystick mapeado para /dev/input/js0, o segundo para js1, etc.

Se você conectou um joystick aos GPIOs do Pi, deve inserir "1" como parâmetro.

Se você conectou um ou mais joysticks ao chip MCP23017, deverá inserir o endereço dos dispositivos I2C conectados, o que poderá obter com o comando:

```text
sudo i2cdetect -y 1
```

A configuração de cada MCP23017 é feita definindo os pads A0, A1 e A2 para 0 ou 1.

 Se você configurou seu MCP23017 com A0, A1 e A2 conectado ao terra, o endereço retornado pelo i2cdetect deve ser 0x20

Portanto, se você tiver um joystick conectado aos GPIOs no Pi e um joystick em um chip MCP23017 com o endereço 0x20, para carregar o driver, execute o seguinte comando:

```text
sudo modprobe mk_arcade_joystick_rpi map=1,0x20
```

As ações do joystick no GPIO serão relatadas no arquivo "/dev/input/js0" e as ações do joystick no chip MCP23017 serão relatadas no arquivo "/dev/input/js1".

Eu testei até 3 joysticks; um nas portas GPIO, um no MCP23017 no endereço 0x20, um no MCP23017 no endereço 0x24:

```text
sudo modprobe mk_arcade_joystick_rpi map=1,0x20,0x24
```

## Bugs conhecidos <a id="bugs-conhecidos"></a>

Se você tentar ler ou gravar no i2c com uma ferramenta como o i2cget ou o i2cset quando o driver estiver carregado, será muito difícil...

Se você tentar o i2cdetect quando o driver estiver em execução, ele mostrará alguns endereços estranhos do dispositivo...

A versão de 256 MB do Raspberry Pi Modelo B não é suportada pelo driver atual. Se você deseja que o driver funcione no seu Pi antigo, será necessário alterar o endereço de BSC1\_BASE para \(BCM2708\_PERI\_BASE + 0x205000\) para usar o endereço i2c correto, e recompilar.

