---
title: Sobrecargas do Retroarch
---

# Sobrecargas do Retroarch

Aqui está uma lista não exaustiva de chaves que podem ser alteradas em um arquivo de sobrecarga do tipo .retroarch.cfg, essas modificações só podem ser feitas se o emulador for um retroarca de núcleo.


>Um \* após o valor significa que o parâmetro também pode ser sobrecarregado por meio de um .recalbox.conf
{.is-info}

## Áudio <a id="audio"></a>

* **`audio_enable = "true"`** _Ativa ou desativa o áudio_
* **`audio_volume = "0.000000"`** _Ajusta o aumento de volume, 0 = volume padrão padrão_
* **`quick_menu_show_save_content_dir_overrides = "false"`** _Exibe ou oculta a opção de substituição de configuração para a pasta_
* **`quick_menu_show_save_core_overrides = "false"`** _Exibe ou oculta a opção de substituição de configuração para o núcleo_
* **`quick_menu_show_save_game_overrides = "false"`** _Exibe ou oculta a opção de substituição de configuração para o jogo_


>Substituições de configuração são um recurso do Retroarch, semelhante a sobrecargas, mas retêm muitas informações, no contexto do Recalbox, é melhor preferenciar sobrecargas, sempre que possível
{.is-info}

## Depuração <a id="depuracao"></a>

* **`fps_show = "true"`** _Mostrar FPS no jogo_
* **`menu_driver = "ozone"`** " _Escolha o menu retroarch, base "ozone", exceto na carcaça GPi, onde rgui é usado_
* **`menu_enable_widgets = "true"`** _Activa os pop-ups no jogo, se definido como falso, exibirá notificações como texto amarelo_

## Pastas <a id="pastas"></a>

* **`recording_output_directory = ""`** _Pasta para onde vão as gravações de vídeo_
* **`savefile_directory = ""`** _Onde salvar / carregar os saves_
* **`savestate_directory = ""`** _Onde salvar / carregar savestates_
* **`screenshot_directory = ""`** _Pasta para onde vão as imagens_

## Serviço de tradução <a id="servico-de-traducao"></a>

* **`ai_service_enable = "true"`** **\*** _Ative ou desative o serviço de tradução_
* **`ai_service_mode = "0"`** _Modo de serviço de tradução, 0: imagem, 1: voz_
* **`ai_service_source_lang = "0"`** **\*** _Idioma a ser lido para o serviço de tradução, 0 = não especificado_
* **`ai_service_target_lang = "1"`** \* _Idioma para o qual traduzir, 1 = Inglês, 3 = Francês, 48=Português \(Portugal\)_
* **`ai_service_url =`** **\*** _Link da Internet do serviço a ser usado_

## Sobreposições/Overlays <a id="sobreposicoes-overlays"></a>

* **`aspect_ratio_index = "23"`** **\*** _Índice de proporção, 23 = personalizado_
* **`input_overlay = ""`** _Link para o arquivo de configuração de sobreposição/overlay_
* **`input_overlay_enable = "true"`** _Ativação da sobreposição/overlay_
* **`input_overlay_hide_in_menu = "true"`** _Overlay/Sobreposição oculta no menu Retroarch_

_Coordenadas a serem definidas com a sobreposição/Overlay:_

* **`custom_viewport_height = ""`**
* **`custom_viewport_width = ""`**
* **`custom_viewport_x = ""`**
* **`custom_viewport_y = ""`**
* **`video_message_pos_x = "0.050000"`**
* **`video_message_pos_y = "0.050000"`**

## Netplay/Jogo em rede <a id="netplay-jogo-em-rede"></a>

* **`netplay_nickname = ""`** \* _Apelido netplay_

​

## Rotação da tela

* **`video_rotation = "1"`** _Gire a renderização do vídeo, 0=normal, 1=90 °, 2=180 °, 3=270 °, preste atenção à proporção_

## Joystick e controle direcional <a id="joystick-e-controle-direcional"></a>

_dissociar / associar o direcional a um dos joysticks_

* **`input_player1_analog_dpad_mode = "0"`** _dissociar_
  * _**=**_ **"1"** _associado ao joystick esquerdo_
  * **= "2"** _associado ao joystick direito_

## Remapeando teclas de atalho <a id="remapeando-teclas-de-atalho"></a>


>As configurações para alterar as teclas de atalho dependem do mapeamento do controle no Recalbox, portanto, se o controlador for alterado, a configuração sobrecarregada com essas linhas pode não funcionar mais.
{.is-warning}

Para obter o valor numérico de cada chave em seu controlador, procure no arquivo _system/configs/retroarch/retroarchcustom.cfg_ o valor da chave desejada de acordo com esta tabela:

{% tabs %}
{% tab title="Esconder" %}
Clique na aba "Mostrar" para mostrar as chaves de cada botão
{% endtab %}

{% tab title="Mostrar" %}
| Nome do botão | Chave em questão cujo valor deve ser alterado |
| :---: | :--- |
| A | input\_player1\_a\_btn |
| B | input\_player1\_b\_btn |
| X | input\_player1\_x\_btn |
| Y | input\_player1\_y\_btn |
| Alto | input\_player1\_up\_btn |
| Baixo | input\_player1\_down\_btn |
| Esquerda | input\_player1\_left\_btn |
| Direita | input\_player1\_right\_btn |
| Select | input\_player1\_select\_btn |
| Start | input\_player1\_start\_btn |
| L | input\_player1\_l\_btn |
| L2 | input\_player1\_l2\_btn |
| L3 | input\_player1\_l3\_btn |
| R | input\_player1\_r\_btn |
| R2 | input\_player1\_r2\_btn |
| R3 | input\_player1\_r3\_btn |
| Eixo L para Cima | input\_player1\_l\_y\_minus\_axis |
| Eixo L para Baixo | input\_player1\_l\_y\_plus\_axis |
| Eixo L para Esquerda | input\_player1\_l\_x\_minus\_axis |
| Eixo L para Direita | input\_player1\_l\_x\_plus\_axis |
| Eixo R para Cima | input\_player1\_r\_y\_minus\_axis |
| Eixo R para Baixo | input\_player1\_r\_y\_plus\_axis |
| Eixo R para Esquerda | input\_player1\_r\_x\_minus\_axis |
| Eixo R para Direita | input\_player1\_r\_x\_plus\_axis |
{% endtab %}
{% endtabs %}


>As modificações a serem feitas nos seguintes valores devem ser feitas no arquivo de sobrecarga.
>
>O arquivo anterior é usado apenas para observar o mapeamento atual.
{.is-warning}

* **`input_enable_hotkey_btn =`** _Botão hotkey_
* **`input_screenshot_btn =`** _Botão que faz uma captura de Tela_
* **`input_exit_emulator_btn =`** _Botão que sai do jogo_
* **`input_load_state_btn =`** _Botão para carregar um jogo salvo_
* **`input_save_state_btn =`** _Botão para salvar um savestate_
* **`input_menu_toggle_btn =`** _Botão para abrir o menu Retroarch_
* **`input_reset_btn =`** _Botão para resetar o jogo_
* **`input_ai_service_btn =`** _Botão para traduzir a tela atual_

_Por exemplo, **The legend of Zelda: Link's Awakening** no Game Boy requer o uso de `Start + Select + A + B` para salvar, se o seu controle não tiver um botão **home** e, portanto, **Hotkey** estiver em `Select`, salvar normalmente no jogo será impossível, então, coloque também o botão **`input_enable_hotkey_btn`** no botão `R` do seu controle, como substituição exclusivamente para esse jogo. Se, para o seu controle, no botão `R`, o valor da chave **`input_player1_r_btn`** for `4`, você precisará inserir_**`input_enable_hotkey_btn = 4`**.

