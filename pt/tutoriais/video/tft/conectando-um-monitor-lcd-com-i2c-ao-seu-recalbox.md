---
title: Conectando um monitor LCD com I2C ao seu recalbox
---

# Conectando um monitor LCD com I2C ao seu recalbox

## Pré-requisitos <a id="pre-requisitos"></a>

Uma tela **LCD I2c** como o modelo Hd44780 na versão **A00** \(suporte ascii + caracteres japoneses\) ou **A02** \(suporte ascii + caracteres europeus\)

​![](http://i.imgur.com/YrDDhwUm.jpg)​

## Instalação <a id="instalacao"></a>

### Conexão do I2C ao GPIO do Raspberry Pi 3 <a id="conexao-do-i-2-c-ao-gpio-do-raspberry-pi-3"></a>

![](http://i.imgur.com/NKswbgr.png)

### ​Ativação do I2C no Recalbox <a id="ativacao-do-i-2-c-no-recalbox"></a>

* **Edite** o arquivo `/etc/modules.conf`.

  * **Adicione as seguintes linhas no final** do arquivo:

  ```text
  i2c-bcm2708
  i2c-dev
  ```

* **Edite** o arquivo `/boot/config.txt`.
  * **Adicione as seguintes linhas no final**:

```text
#Activate I2Cdt
param=i2c1=ondt
param=i2c_arm=on
```

* **Edite** o arquivo `/boot/cmdline.txt`.
  * **Adicione as seguintes linhas no final** do arquivo:

```text
bcm2708.vc_i2c_override=1
```

* **Reinicie o** Recalbox

### Descubra o endereço do I2C <a id="descubra-o-endereco-do-i-2-c"></a>

Você precisará **saber o endereço do seu I2C** para executar alguns **scripts de exibição.** Normalmente, o endereço é `0x27` ou `0x3f`.

* Execute o próximo comando; e vá relaxar, pois pode demorar um pouco!

  * nos modelos muito antigos de Raspberry: `i2cdetect -y 0`
  * nos modelos atuais de Raspberry \(ft3, ft2\) : `i2cdetect -y 1`

  ```text

       0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
  00:          -- -- -- -- -- -- -- -- -- -- -- -- --
  10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
  20: -- -- -- -- -- -- -- 27 -- -- -- -- -- -- -- --
  30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
  40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
  50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
  60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
  ```

O **endereço** retornado pela ordem na tabela nos diz: `0x27`

## Script da Tela disponível para Recalbox <a id="script-da-tela-disponivel-para-recalbox"></a>

​[https://forum.recalbox.com/topic/8689/script-clcd-display-on-recalbox](https://forum.recalbox.com/topic/8689/script-clcd-display-on-recalbox)​

![](http://i.imgur.com/fsXfArEm.jpg)

