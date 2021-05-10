---
title: Odroid XU4 : Tela OGST TFT
---

# Odroid XU4 : Tela OGST TFT

## O que é uma tela OGST TFT? <a id="o-que-e-uma-tela-ogst-tft"></a>

{% embed url="https://www.hardkernel.com/shop/ogst-gaming-console-kit-for-xu4/" caption="Suporte de tela TFT OGST no Recalbox" %}

## Instalação <a id="instalacao"></a>

Pré-requisitos:

* Um ODROID XU4 \(Q\) com o kit de console de jogos OGST.
* Recalbox instalado \(testado na versão estável 18.07.13, 2018 christmas beta, v6 0 e v6.1\)
* Recalbox conectado na Internet.

O script de instalação será executado da seguinte maneira:

* Baixe o pacote
* Instale o script `/recalbox/share/system/custom.sh`
* Extraia o pacote do logotipo para`/recalbox/share/system/tft_logos`
* Substitua o `/usr/bin/ffmpeg` binário com um novo \(o existente é muito antigo e com erros para operações de loop de vídeo\)
* Modifique e recompile`/usr/lib/python2.7/site-packages/configgen/emulatorlauncher.py`
* Reinicie o sistema

Procedimento de instalação:

* Faça acesso root via terminal
* Copie e cole no seu terminal e execute a seguinte linha de comando para **Recalbox 2018**:

```text
wget https://www.dropbox.com/s/jp85fh6j4lkoz8m/install.sh && chmod +x install.sh && ./install.sh
```

* Copie e cole no seu terminal e execute a seguinte linha de comando para o **Recalbox v6.0**:

```text
wget https://www.dropbox.com/s/1c63n1kakkpylbw/install_6x.sh && chmod +x install_6x.sh && ./install_6x.sh
```

* Copie e cole no seu terminal e execute a seguinte linha de comando para o **Recalbox v6.1**:

```text
curl -sL https://www.dropbox.com/s/9bhrq0bta8aah8o/install_6.1.sh | bash
```

Isso é tudo, pessoal! Aproveite!


>**Nota**
>
>Após atualizar o sistema Recalbox, talvez seja necessário reinstalá-lo. Se você fez alterações \(consulte a seção "Personalização"\), faça um backup do seu arquivo custom.sh e da pasta tft\_logos antes. Em seguida, restaure-os após a instalação.
>
>O script `custom.sh` foi atualizado para a v6.1. Se você fez um script`custom.sh` para uma versão antiga, você precisará recriá-la com base no novo script "oficial", para usá-lo na v6.1.
{.is-info}

**​**

## Algumas informações sobre como funciona <a id="algumas-informacoes-sobre-como-funciona"></a>

* Ao iniciar o sistema, o script `/recalbox/share/system/custom.sh` será executado \(através do script de inicialização `/etc/init.d/S99custom` com o parâmetro de inicialização para inicializar a tela TFT e exibir o logotipo padrão\).
* Quando um jogo \(ou Kodi\) é iniciado, o _launcher_ do emulador modificado`/usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc` executará o script`custom.sh` com o nome do _launcher_ do emulador como argumento, exibindo o logotipo correspondente na tela TFT.
* O script `custom.sh` continua a ser executado silenciosamente em segundo plano enquanto o emulador está sendo executado \(enquanto o processo python / emulatorlauncher existe\), aguardando e monitorando o desligamento do processo.
* Depois que o emulador é parado, o script `custom.sh` exibe o logotipo padrão novamente.

## Customização <a id="customizacao"></a>

* Todos os logotipos \(imagens estáticas ou videoclipes\) são armazenados em `/recalbox/share/system/tft_logos`.
* Você pode adicionar, modificar, excluir, etc ... logotipos conforme desejar, mas, consequentemente, pode ser necessário modificar o script`/recalbox/share/system/custom.sh`, para que algumas alterações entrem em vigor \(o caminho dos arquivos de logotipo é armazenado lá, bem como o parâmetro loop, se você deseja repetir um clipe de vídeo\). Certifique-se de manter a integridade da estrutura do script.
* Se você acidentalmente corrompeu o script `custom.sh` , faça um backup da sua pasta tft\_logos se você tiver feito alterações, refaça o procedimento de instalação e restaure sua pasta tft\_logos, se necessário.
* Para serem exibidas corretamente, todas as imagens ou videoclipes dos logotipos devem ter 320 x 240 pixels \(a resolução da tela TFT\).
* Funciona com arquivos _.mp4, .jpg, .png_ e _.gif_. Todos os arquivos suportados pelo ffmpeg devem funcionar. Apenas experimente!

## Contribuições <a id="contribuicoes"></a>

### Alguns testes com vídeos de introdução específicos ao Recalbox <a id="alguns-testes-com-videos-de-introducao-especificos-ao-recalbox"></a>

​[Tópico relacionado no Fórum Recalbox \(Em Francês\)](https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case)​

{% embed url="https://www.youtube.com/watch?v=ZXZSbX--2xg&feature=emb\_title&ab\_channel=YannMORERE" %}



### Alguns vídeos no formato 320x240 <a id="alguns-videos-no-formato-320-x240"></a>

Faça o download deste arquivo e substitua o valor padrão pelo que você quiser :\) [https://mega.nz/\#!Kp8BkYoD!SAeq9xcDUX4po\_Xmhed\_KypmycQ8iQRS1SZI9vBRb3Q](https://mega.nz/#!Kp8BkYoD!SAeq9xcDUX4po_Xmhed_KypmycQ8iQRS1SZI9vBRb3Q)​

Retirado de: [https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case/97](https://forum.recalbox.com/topic/14391/ogst-odroid-n64-case/97)   
Obrigado a @kevinnash!  
Basta baixar o pacote aqui: [https://uptobox.com/gsic8c6h72fq](https://uptobox.com/gsic8c6h72fq)​

