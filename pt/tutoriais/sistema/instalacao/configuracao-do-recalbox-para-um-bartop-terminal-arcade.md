---
title: Configuração do Recalbox para um Bartop/Terminal Arcade
---

# Configuração do Recalbox para um Bartop/Terminal Arcade

Se você quiser usar um Raspberry Pi com Recalbox para criar um "**Bartop**" ou uma **máquina Arcade/Fliperama**. Você pode configurar facilmente o Recalbox para atender às suas necessidades.

## A - GPIO​ <a id="a-gpio"></a>

Você pode **configurar o driver GPIO do** Recalbox no arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf). Este driver **cria dois joysticks no sistema** e é controlado diretamente pelos **PINOS GPIO** do Raspberry Pi.

Para isso você **não precisa de um hub USB**, pois você **conectará seus botões** diretamente aos [GPIOs](https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controles-gpio).

## B - Configuração de vídeo​ <a id="b-configuracao-de-video"></a>

Muitos "bartops" usam uma tela LCD antiga ou telas de televisão CRT que usam uma das seguintes conexões:

* **Tela VGA**: você precisará de um conversor HDMI / VGA \(conversor ativo\) que custa cerca de 10 €. Se você estiver em uma tela 4/3, você precisará alterar o modo de vídeo para `global.videomode=default` para todos os seus emuladores no arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf).
* **Tela DVI**: você precisará de um adaptador HDMI / DVI \(conversor passivo\). Você provavelmente precisará editar seu arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), com base [neste tutorial](https://recalbox.gitbook.io/tutorials/v/portugues/video/lcd/conectando-o-recalbox-a-um-monitor-dvi).
* **Tela CRT** : você precisará de um conector para RCA com um cabo de vídeo. Você deve alterar o modo de vídeo para defini-lo como `global.videomode=default` para todos os seus jogos no arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), e, modificar os parâmetros descritos [neste tutorial](https://recalbox.gitbook.io/tutorials/v/portugues/video/crt/conectando-seu-recalbox-a-um-crt-via-cabo-composto).

## C - Configuração de áudio​ <a id="c-configuracao-de-audio"></a>

Você pode selecionar o **dispositivo de saída de áudio** no arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf):

* Utilize `audio.device=jack` se quiser forçar a saída de áudio para o conector de áudio 3,5mm \(_jack_\).
* Utilize `audio.device=hdmi` se quiser forçar a saída de áudio para HDMI.

Você pode **desativar o Kodi** no arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), **definindo o seguinte parâmetro**:`kodi.enable=0`para **remover o atalho atribuído ao botão "X".** Isso também **removerá a entrada Kodi** do menu do **Emulationstation**.

Você também pode **alterar as configurações do menu:**

* **Para o ES**:
  * Definindo como: `system.es.menu=bartop`, você terá **acesso a um mínimo de opções** ao pressionar o **botão "Start" no Emulationstation.**
  * Definindo como: `system.es.menu=none`, **apenas o menu de seleção de jogos** \(botão Select\) estará disponível.
* **Para os emuladores:**
  * Definindo como: `system.emulators.specialkey` como `nomenu`, você **desativará os menus nos emuladores**.
  * Definindo como: `system.emulators.specialkey` como `none` , **você desabilitará menus** e todas as **funções especiais em emuladores**. \(Exceto a combinação para sair de um jogo, é claro\).​

## Relacionado:​ <a id="relacionado"></a>

​[Ative o botão GPIO para fechar o emulador pressionando um único botão](https://recalbox.gitbook.io/tutorials/v/portugues/controles/gpio/controles-gpio/ative-o-botao-gpio-para-fechar-o-emulador-pressionando-um-unico-botao)​

