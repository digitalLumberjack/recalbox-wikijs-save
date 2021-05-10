---
title: Ative o botão GPIO para fechar o emulador pressionando um único botão
---

# Ative o botão GPIO para fechar o emulador pressionando um único botão

Esse script python para Raspberry Pi permite que um botão seja usado para fechar o emulador pressionando um único botão GPIO. É compatível com qualquer outra função ou script atribuído anteriormente aos botões.

O botão selecionado por padrão é o **botão Start do Player 1**; pode ser alterado durante a instalação por qualquer outro, porque não remove nenhuma função anterior. O emulador fecha após pressionar o botão por pelo menos 0,5 s. O tempo de ativação do botão também pode ser alterado.

## Necessário: <a id="necessario"></a>

* Um Recalbox no Raspberry Pi que usa comandos GPIO \(não é necessário ter um botão livre\).
* O Raspberry Pi deve ter acesso à Internet:
  * Você pode ativar e configurar o wifi e o nome do host, obter o IP recalbox, o SSID da sua rede e a chave de rede com um teclado. Depois de validado, o wifi é ativado. Existe um bug conhecido que não permite que você insira todos os caracteres necessários para o SSID ou a chave. Você pode configurá-lo diretamente do seu wifi usando [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf).
* Um computador no qual você pode realizar um [acesso root SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) no Rapsberry \(no Windows ou Mac, pode ser necessário um programa como o PuTTY\).

## Instalação: <a id="instalacao"></a>

* Abra uma sessão ssh do seu computador para o Raspberry.
* Uma vez logado, copie e cole este comando na sessão ssh:

`wget --quiet --show-progress -O /recalbox/share/system/exit-emu-1b https://gist.githubusercontent.com/DjLeChuck/446cd415575f03c927627e378979027d/raw/9ebe3a5e178ff047b536220afd513981095fb41d/exit-emu-1b-installer && chmod 755 /recalbox/share/system/exit-emu-1b && /recalbox/share/system/exit-emu-1b install`

O instalador exibirá uma lista de possíveis mapas da porta GPIO correspondentes ao mapa GPIO para Recalbox, correspondendo à seguinte imagem:

![Mapeamento das portas GPIO](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M1pg9d9WjOYChpb5hus%2F-M1pzARovpy60-nqM0ZG%2FgaU6t.png?alt=media&token=89aed639-da21-4c6c-afe6-590fe47e423e)

* Depois de selecionar a porta do botão à qual você deseja atribuir o script, o instalador solicitará o atraso para sair do emulador, você precisará digitar o atraso desejado em segundos. \(É importante responder às duas perguntas, caso contrário, o instalador falhará\)
* Após alguns segundos, se o resultado for uma mensagem na tela dizendo "botão Iniciar", tudo correu bem e agora temos o script do botão instalado e funcionando.

## Arquivos instalados: <a id="arquivos-instalados"></a>

* [/recalbox/scripts/rpi-exit-emu-1b.py](https://gist.github.com/DjLeChuck/445ce3d37f41f12d5bf8cb9482db4027)
* [/etc/init.d/S98exit-emu-1b](https://gist.github.com/DjLeChuck/5f798b0d4af4071a92111bf61703aeb1)
* [/recalbox/share/system/exit-emu-1b](https://gist.github.com/DjLeChuck/446cd415575f03c927627e378979027d)

## Desinstalação: <a id="desinstalacao"></a>

* Inicie uma [sessão ssh](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp)
* digite `/recalbox/share/system/exit-emu-1b uninstall`

\*\*\*\*


>**Aviso:**
>
>Na configuração padrão do Retroarch, o script encerra os emuladores por força bruta, usando um comando **`killall`** que, dependendo do núcleo usado, pode causar a perda de algumas alterações na configuração do emulador feitas durante o jogo.  
>Por exemplo, isso acontece com o Mame2003.
>
>  
>Para evitar isso, implementei o fechamento do emulador por meio de um comando de rede para a Retroarch. Agora o Retroarch fechará corretamente e você não perderá as alterações de configuração nos emuladores.
{.is-danger}


>**Nota:**
>
>Essa alteração é apenas para o Retroarch, embora abranja a maioria dos emuladores no sistema, emuladores como **Fb2x**, **scummvm** ou **mupen64plus** ainda são desativados por força bruta, até encontrar outra maneira de aplicá-lo.
{.is-info}

## Dicas e truques: <a id="dicas-e-truques"></a>

* Se a qualquer momento você precisar atribuir a função de fechamento do emulador a outro botão, basta reiniciar o instalador com o comando `/recalbox/share/system/exit-emu-1b install`

  e coloque na instalação o novo número de porta que você deseja.

* Se você alterar a configuração do seu emulador e sair com o botão atribuído na instalação, essas alterações serão perdidas. Verifique se elas estão no arquivo: `/recalbox/share/system/configs/retroarch/retroarchcustom.cfg` Ou no arquivo de configuração personalizado do Retroarch em que você usa o parâmetro `Network_cmd_enable` para `= "true"`.
* Se, por algum motivo, o script parar de funcionar e o botão perder a função de fechar o emulador, você poderá fazê-lo funcionar novamente com o comando: `/etc/init.d/S98exit-emu-1b restart` você precisará inseri-lo em uma [sessão SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)​

