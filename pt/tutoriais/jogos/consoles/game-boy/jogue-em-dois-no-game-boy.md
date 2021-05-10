---
title: Jogue em dois no Game Boy
---

# Jogue em dois no Game Boy

É possível jogar dois jogadores com dois GameBoys no Recalbox.

Existem 3 métodos para fazer isso.


>Embora possa ser tentador, o Recalbox não suporta netplay neste modo.
>
>Além disso, no modo jogar em dois no Game Boy, não há suporte para salvamentos no segundo Game Boy, ao contrário [do modo dois jogos dois Game Boys](https://recalbox.gitbook.io/tutorials/v/portugues/jogos/consoles/game-boy/jogue-em-dois-no-game-boy/jogue-dois-jogos-diferentes-no-modo-gamelink), novamente, o netplay não é compatível.
{.is-warning}

## O método "sem edição" <a id="o-metodo-sem-edicao"></a>

1. **Ligue** o recalbox
2. Uma vez no EmulationStation, selecione **Game Boy** ou **Game Boy Color**.
3. **Na lista de jogos**, posicione-se no **jogo desejado** e **pressione** **`START`**.
4. **Selecione** "Editar dados do jogo": 1. **Emulador:** selecione "libretro" em vez de "Padrão \(Libretro\)" 2. **Núcleo**: selecione "TGBDUAL"
5. **Salve**
6. **Inicie o jogo**
7. Quando o jogo **começar**, **vá para o menu RetroArch** apertando `"HotKey + B"`
8. Settings/Configuration -&gt; coloque "salvar configuração" em "ON"
9. Ainda **no menu RetroArch,** menu rápido/Opções **Defina** "habilitar link GB \(reiniciar\)" para "habilitar"

Você pode redefinir "Salvar configuração ao sair" para DESLIGADO após reiniciar o jogo.

## Editando o Recalbox.conf <a id="editando-o-recalbox-conf"></a>

* **Edite** o arquivo [`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) para **substituir** o emulador GameBoy por`tgbdual`

  ```text
  # ------------ I - EMULATORS CHOICES ----------- #
  ## You can override the global configuration here
  gb.core=tgbdual ;GameBoy
  gb.ratio=custom
  gbc.core=tgbdual ;GameBoyColor
  gbc.ratio=custom
  ```

* **Salve e reinicie** o Recalbox corretamente.
* **Comece um jogo GameBoy** como Ballon Kid, por exemplo.
* **Abra o menu Retroarch** com `Hotkey + B`.
* **Altere** as seguintes configurações:

```text
Setting / Configuration / Save Configuration On Exit : ON
Quick menu / Core Options / GB Link Enable (restart) : enabled
Quick menu / Core Options / Screen placement (restart) : horizontal
Quick menu / Core Options / Switch player screens : normal ; joueur 1 à gauche et joueur 2 à droite
Quick menu / Core Options / Show player screens : both players
Settings / Video / Aspect Ratio Index : 20:9 (1:1 PAR) ; 100% conforme ratio GB
Quick menu / Restart Content
```

* Você pode **redefinir** "Salvar configuração ao sair" para **DESLIGADO** após **reiniciar o jogo.**


>Lembre-se de que se a sua TV não estiver configurada para **16/9** - se o menu Recalbox não ocupar a tela inteira - a proporção não será boa.
>
>Observe também que **os jogos para um jogador** também serão duplicados. Dois GB lado a lado, é bom para um duelo de velocidade, caso contrário, inútil.
>
>Para evitar muita manipulação, você pode aplicar todos esses parâmetros apenas no GB ou apenas no GBC.
{.is-warning}

## Usando arquivos de sobrecarga \(para usuários avançados\) <a id="usando-arquivos-de-sobrecarga-para-usuarios-avancados"></a>

Sobrecargas de configuração são uma forma de forçar as configurações de um jogo, uma subpasta ou um sistema inteiro.

No caso que nos interessa, vamos precisar de um arquivo nomedojogo.extensão.recalbox.conf \(por exemplo: **Pac-Man \(Europe\) .zip.recalbox.conf**\) contendo as seguintes linhas:

```text
gb.core=tgbdual
gbc.core=tgbdual
```


>Aqui, forçamos o núcleo TGBDual para o jogo.
{.is-info}

Um nome de nomedojogo.extensão.core.cfg \(por exemplo: **Pac-Man \(Europe\) .zip.core.cfg**\) contendo:

```text
tgbdual_audio_output = "Game Boy #1"
tgbdual_gblink_enable = "enabled"
tgbdual_screen_placement = "left-right"
tgbdual_single_screen_mp = "both players"
tgbdual_switch_screens = "normal"
```


>Configuramos o TGBDual para usar o som do Game Boy \# 1, ativar o GameLink, exibir dois game boys lado a lado, um à esquerda e um à direita, e o GameBoy do jogador \# 1 à esquerda.
{.is-info}

E um último arquivo chamado nomedojogo.extensão.retroarch.cfg \(por exemplo: **Pac-Man \(Europe\) .zip.retroarch.cfg**\) contendo:

```text
aspect_ratio_index = "22"
input_overlay_enable = "false"
```


>Forçamos a proporção da tela para o modo 22: Core Provided \(Fornecida pelo núcleo\), enquanto desabilitamos os overlays \(sobreposições\).
{.is-info}

Esses arquivos devem ser colocados no mesmo local do jogo desejado \(no exemplo acima, no mesmo local do jogo **Pac-Man \(Europe\).zip**\).


>Se os arquivos de sobrecarga forem nomeados apenas **.recalbox.conf**, **.retroarch.cfg** e **.core.cfg**, eles se aplicarão a toda a pasta em que foram colocados, bem como às subpastas, se houver.
{.is-info}


>Os arquivos de sobrecarga não são afetados pela configuração da interface Recalbox, e têm precedência sobre a última, é imperativo poder acessar esses arquivos para fazer uma modificação subsequente nos parâmetros que eles afetam.
{.is-warning}

