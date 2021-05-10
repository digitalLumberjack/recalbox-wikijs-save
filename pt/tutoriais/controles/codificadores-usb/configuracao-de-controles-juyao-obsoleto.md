---
title: Configuração de controles Juyao \(obsoleto?!\)
---

# Configuração de controles Juyao \(obsoleto?!\)

## Pinagem​ <a id="pinagem"></a>

Esta placa é uma das que permite conectar **a maioria dos botões** e gerenciar **dois jogadores**. Siga a seguinte fiação:

![Chaves de mapeamento Juyao](http://image.dhgate.com/0x0/f2/albu/g2/M00/F2/A5/rBVaGlZhCQWAUlMrAAD1xDQpwYk580.jpg)


>**Atenção:  
>Em algumas placas**, J1 e J2 estão **invertidos**, recomendamos que você **teste** seus manípulos **antes de conectar tudo**.  
>O risco seria que seu J1 estivesse à direita e seu J2 à esquerda.
{.is-danger}

​

## Configuração​ <a id="configuracao"></a>

​

**As Interfaces USB Juyao** requerem algumas **configurações antes de serem reconhecidas** pelo Recalbox 4.0.0

**Na versão 4.1**, as configurações a seguir **serão descontinuadas**.

* Comece conectando em SSH com WINSCP e PuTTY, conforme mostrado [AQUI](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp)​
* [Acesse sua partição em modo gravação](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesse-uma-particao-em-modo-gravacao)
* Em seguida, edite o arquivo localizado em `/boot/cmdline.txt` via notepad ++ \(no windows\) ou via ssh`nano /boot/cmdline.txt`

1 . **Adicione** no final da linha com um espaço após as últimas palavras

`usbhid.quirks=0x314:0x328:0x040`

2 . **Salve** a modificação \(Cltr+X no _nano_ e depois Y para sair ou simplesmente Ctrl+S e Alt+F4\)

* **Reinicie** o Raspberry Pi via **sua interface** ou via **ssh** com o comando `reboot`
* **Vá** para a **interface do EmulationStation** e **configure apenas as "opções do controle" do jogador 1** com o diagrama de um joystick Snes.
* **Atribuia o J1**
* **Inicie um jogo para 2 jogadores** e **teste** seus joysticks. \(exemplo: via Street Fighter\)


>**Atenção:**  
>Insistimos no fato de que basta fazer **apenas** a configuração do jogador 1 diretamente **no Emulationstation**.  
>A configuração do **jogador 2** deve funcionar se o **mapeamento for o mesmo.** **Não tente** configurar o jogador 2, isso **sobrescreverá a configuração do jogador 1**.
{.is-danger}

​

