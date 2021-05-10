---
title: Retroarch: Configurar sobreposições \(overlays\) \[4.1\]
---

# Retroarch: Configurar sobreposições \(overlays\) \[4.1\]

## Sobreposições por jogo:​ <a id="sobreposicoes-por-jogo"></a>

O que você precisa :

* Criar uma pasta `overlays` + subpasta com o mesmo nome do sistema
* Adicione o seu `.png`, um `romName.cfg` + `romName.zip.cfg`

**Então, aqui estão as informações básicas por meio de um exemplo**

* Sistema: MAME
* Rom: Double Dragon \(ddragon.zip\)

Pasta: /recalbox/share/overlays/**mame** Arquivos :

* /recalbox/share/overlays/mame/ddragon.zip.cfg:

```text
input_overlay = "/recalbox/share/overlays/mame/ddragon.cfg"
```

* /recalbox/share/overlays/mame/**ddragon**.cfg:

```text
overlays = "1"
overlay0_overlay = "ddragon.png"
overlay0_full_screen = "true"
overlay0_descs = "0"
```

Veja o link: Recalbox irá pesquisar `overlays//.cfg` que se refere a outro .cfg \(o arquivo não precisa ser nomeado como rom, você pode personalizar o parâmetro input\_overlay\).

O mesmo vale para o nome da sobreposição. Esses são os requisitos mínimos. Você pode, é claro, adicionar algumas configurações personalizadas do Retroarch para`ddragon.zip.cfg` Na maioria das vezes, você deve forçar as janelas de exibição \(_viewports\)_.​

## Sobreposições por sistema:​ <a id="sobreposicoes-por-sistema"></a>

O que você precisa :

* Crie a pasta`overlays`
* Adicione o seu `.png` + `systemName_overlay.cfg` na pasta`/recalbox/share/system/configs/retroarch/overlays`
* Adicione o seu `systemName.cfg` na pasta`/recalbox/share/system/configs/retroarch`
* `systemName.cfg` é nomeado como o nome da pasta em`/recalbox/share/roms/...`. Por exemplo, o arquivo do Sega 32X é chamado `sega32x.cfg`. Há uma exceção para Odyssey2. O arquivo deve ser chamado `odyssey2.cfg` \(portanto, não o2em.cfg\).

**Então, aqui estão as informações básicas por meio de um exemplo**

* Sistema: PSW

Pasta: /recalbox/share/system/configs/retroarch Arquivo: /recalbox/share/system/configs/retroarch/**psx.cfg**

```text
input_overlay = "/recalbox/share/system/configs/retroarch/overlays/psx_overlay.cfg"
```

Pasta: /recalbox/share/system/configs/retroarch/overlays Arquivo: /recalbox/share/system/configs/retroarch/overlays/**psx\_overlay.cfg** :

```text
overlays = "1"
overlay0_overlay = "psx.png"
overlay0_full_screen = "true"
overlay0_descs = "0"
```

Portanto, consulte o link: Recalbox procurará `retroarch/.cfg` que se refere a outro .cfg \(o arquivo não precisa ser nomeado como `nomedosistema_overlay`, é você quem decide o parâmetro input\_overlay\). O mesmo vale para o nome da sobreposição.

Esses são os requisitos mínimos. É claro que você pode adicionar algumas configurações personalizadas do Retroarch em `psx_overlay.cfg`. Na maioria das vezes, você deve forçar as janelas de exibição.

## Janelas de visualização _\(Viewports_\) personalizadas:​ <a id="janelas-de-visualizacao-viewports-personalizadas"></a>

Agora que as sobreposições por sistema estão definidas, para exibir adequadamente o jogo dentro da sobreposição, definiremos janelas de exibição personalizadas para cada sistema.

Usando como exemplo o Gamegear :

* Defina a proporção nas opções da Emulationstation como `custom`. `OPÇÕES DE JOGOS / PROPORÇÃO DO JOGO = PERSONALIZADO`

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/overlays/overlays_2.png)

* Inicie um jogo Gamegear e abra o menu Retroarch com `Hotkey+B`.
* Ative a opção de exibir sobreposições no menu Retroarch. Vá para o menu `settings/onscreen_display/onscreen_overlay`, em seguida, ative esta opção:`hide_overlay_in_menu = on` -&gt; `off`
* Vá para `menu settings/ menu vidEo` :
  * definir proporção de aspecto para `custom`
  * Defina `custom aspect ratio width` e`custom aspect ratio height` para exibir perfeitamente o jogo dentro da sobreposição.
  * Observe esses 2 valores.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/overlays/overlays_1.png)

​

* Saia do menu Retroarch e do jogo **sem salvar nenhuma configuração**.
* Edite o arquivo`/recalbox/share/system/configs/retroarch/gamegear.cfg` criado anteriormente.
  * adicione os valores definidos na etapa anterior:

    ```text
    custom_viewport_width = "992"
    custom_viewport_height = "720"
    aspect_ratio_index = "22"
    ```

Nosso arquivo contém esta informação:

```text
input_overlay = "/recalbox/share/system/configs/retroarch/overlays/gamegear.cfg"
custom_viewport_width = "992"
custom_viewport_height = "720"
aspect_ratio_index = "22"
```

Se você deseja exibir uma proporção predefinida, aqui estão os códigos de proporção:

```text
0: 4:3
1: 16:9
2: 16:10
3: 16:15
4: 1:1
5: 2:1
6: 3:2
7: 3:4
8: 4:1
9: 4:4
10: 5:4
11: 6:5
12: 7:9
13: 8:3
14: 8:7
15: 19:12
16: 19:14
17: 30:17
18: 32:9
19: config (video_aspect_ratio setting)
20: 10:9 (1:1 PAR)
21: Core Provided
22: Custom
```

Portanto, para forçar, por exemplo, uma proporção de aspecto de 4: 3, você deve gravar no arquivo:`aspect_ratio_index = "0"`

* Salve seu arquivo e saia.
* Inicie um jogo para testar.
* Divirta-se

### Adicionado molduras do The Bezel Project: <a id="adicionado-molduras-do-the-bezel-project"></a>

Vá para The Bezel Project e baixe o zip para o seu sistema: [https://github.com/thebezelproject?tab=repositories](https://github.com/thebezelproject?tab=repositories)​

Neste exemplo, estarei usando o Atari7800. Como no exemplo do início, crie a pasta atari7800:`/recalbox/share/overlays/atari7800/` E então uma pasta de moldura dentro:`/recalbox/share/overlays/atari7800/bezel`

Descompacte seu **bezelproject-Atari7800-master.zip** e copie todos os arquivos .png e .cfg:`bezelproject-Atari7800-master\retroarch\overlay\GameBezels\Atari7800` em `/recalbox/share/overlays/atari7800/bezel`

Agora edite todos os arquivos .cfg \(use o **Notepad ++** para isso\). No Notepad ++, use a função substituir e substituir: `/opt/retropie/configs/all/retroarch/overlay/GameBezels/Atari7800/` sem mais nada e pressione a função Substituir em todos os documentos.

Os arquivos devem ter a seguinte aparência:

_overlays = 1 overlay0\_overlay = "Alien Brigade \(USA\).png" overlay0\_full\_screen = true overlay0\_descs = 0_

Agora faça uma cópia de todos os arquivos .cfg e cole-os nesta pasta:`/recalbox/share/overlays/atari7800`

Edite-os todos no Recalbox: substituindo`overlays = 1` par rien du tout.

Substitua: `overlay0_overlay = "` por `input_overlay = "/recalbox/share/overlays/atari7800/arcade-artwork/`

Substitua:**.png"** por **.cfg"**

Substitua:`overlay0_full_screen = true` por `input_overlay_enable = true`

Substitua: `overlay0_descs = 0` por `input_overlay_opacity = 0.900000`

Adicione esta linha: `input_overlay_scale = 1.000000`

O arquivo agora deve se parecer com este: **input\_overlay = "/recalbox/share/overlays/atari7800/arcade-artwork/Alien Brigade \(USA\).cfg" input\_overlay\_enable = true input\_overlay\_opacity = 0.900000 input\_overlay\_scale = 1.000000**

Agora você pode iniciar um jogo e testar o resultado.

