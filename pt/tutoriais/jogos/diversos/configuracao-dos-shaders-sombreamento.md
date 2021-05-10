---
title: Configuração dos shaders \(sombreamento\)
---

# Configuração dos shaders \(sombreamento\)

## Introdução​ <a id="introducao"></a>

Os shaders são filtros que podem alterar a imagem que você obtém ao usar seus emuladores. É freqüentemente usado para obter uma imagem "retro", próxima à imagem em que reproduzimos na época.

Os diferentes arquivos que você possui no Recalbox são:

*  **glsl** : o próprio shader
*  **glslp** : o shader predefinido. Pode combinar vários shaders.
* /recalbox/share\_init/system/configs/shadersets/**xxx.cfg** : arquivos de configuração do pack de shaders

O arquivo de configuração do pack de shader \(.cfg\) refere-se a uma predefinição de shader \(glslp\) para cada sistema no Recalbox. Cada arquivo glslp refere-se a um ou mais shaders \(glsl\).

## Pack de shaders <a id="pack-de-shaders"></a>

​Com o pacotes de shader, você pode configurar shaders para todos os seus sistemas em uma opção. Os pacotes são criados pela comunidade e são otimizados a cada nova versão do Recalbox. Pacotes disponíveis:

* **scanlines** : ativar linhas de verificação \(_scanlines_\) em todos os emuladores
* **retro** :selecione os "melhores" shaders para cada sistema, escolhido pela comunidade, o que proporcionará a experiência de jogo mais próxima do original.
* **none** : sem shaders

Você pode definir o shader pack que deseja ativar no menu "CONFIGURAÇÕES DE JOGO" do EmulationStation ou diretamente no [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) com a opção `global.shaderset`.

## Shaders personalizados <a id="shaders-personalizados"></a>

Você pode combinar o poder dos pacotes de shader com a profunda personalização do [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf). O `global.shaderset` pode definir um shader de base para cada emulador. Você pode alterar a predefinição de shader de um sistema com a opção `systemname.shader`. As predefinições de shader padrão são definidas em `/recalbox/share_init/shaders/`

Por exemplo, se eu quero os melhores shaders em todos os emuladores, mas não há shaders para o meu gameboy, uma predefinição de shader já existente para megadrive e uma predefinição de shader personalizada para minhas snes:

```text
# Set the retro shader set for all emulators, now i know that i have the best selection
global.shaderset=retro
# But my gameboy seem better for me with no shaders
gb.shaders=
# We use the already existing 4xbr_retro.glslp shader for megadrive
megadrive.shaders=/recalbox/share_init/shaders/4xbr_retro.glslp
# And i want to apply my own shader preset on snes
snes.shaders=/recalbox/share/shaders/custom/snes.glslp
```

Você também pode alterar os shaders durante o jogo usando seu controle. Use os comandos especiais Hotkey + R2 ou Hotkey + L2 para selecionar o shader seguinte ou anterior.

## Capturas de tela <a id="capturas-de-tela"></a>

## ​**Sem** shader: <a id="sem-shader"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lko7NXwWuq6o_JbyMiN%2F-LkoAc09tMdSbcRo-zYm%2Fimage.png?alt=media&token=7405b2a7-c30b-402c-b242-1c87c8f5c871)

​Com o **conjunto retro** ativado:

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lko7NXwWuq6o_JbyMiN%2F-LkoAh6LO-z5waVpIwto%2Fimage.png?alt=media&token=907375ea-ea6b-4f9e-ae00-9ff2bb1f358b)

