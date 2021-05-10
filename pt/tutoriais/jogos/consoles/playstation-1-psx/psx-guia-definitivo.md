---
title: PSX - Guia Definitivo
---

# PSX - Guia Definitivo

## Multidiscos <a id="multidiscos"></a>

Em primeiro lugar, veremos as diferentes possibilidades que o Recalbox oferece para a troca de discos.

​

### ​Modo PSP <a id="modo-psp"></a>

Combine todos os discos em um único arquivo eboot.pbp. Você pode alterar os discos no menu Retroarch.

#### Vantagens: <a id="avantages"></a>

* Os atalhos do controle podem ser usados ​​para trocar os discos.
* Existe um arquivo de save para todos os discos.

#### Desvantagens: <a id="inconvenients"></a>

* Os arquivos .Sbi não podem ser usados ​​em jogos com multidisco.
* Não permite a troca para um disco com patch \(com correção de proteção LibCrypt\).
* Demora um pouco para alterar todos os jogos multidiscos no eboot.pbp.

​

### Modo PCSX-reARMed <a id="modo-pcsx-rearmed"></a>

O disco a seguir é procurado no menu Retroarch pelo sistema de arquivos.

#### Vantagens: <a id="avantages-1"></a>

* Seus jogos estão no formato .bin /.cue.

#### Desvantagens: <a id="inconvenients-1"></a>

* Isso não está funcionando no momento.
* É feio e lento.
* Os arquivos de save não são compartilhados entre os discos.
* Os atalhos do controle não podem ser usados ​​para alterar as unidades.

Portanto, os jogos com proteção LibCrypt e multidiscos são um verdadeiro incômodo nesses dois modos.

## ​Modo definitivo <a id="modo-definitivo"></a>

Para este modo, é necessário adicionar a extensão .m3u à parte PSX em`/recalbox/share_init/system/.emulationstation/es_systems.cfg` \(os desenvolvedores devem adicioná-la na próxima versão, obrigado\). Para isso, você pode usar uma máquina virtual com Ubuntu \(por exemplo\) e conectar o cartão SD para editar o arquivo.

A linha modificada ficaria assim:

`.m3u .img .IMG .pbp .PBP .bin .BIN .cue .CUE .iso .ISO`

Em seguida, basta criar um arquivo .m3u para cada jogo com vários discos. Este arquivo conterá os nomes dos arquivos .cue. Por exemplo :

![m3u](https://camo.githubusercontent.com/226ac7a2b8e6e9a79ae38a69973509493272c39f/68747470733a2f2f692e696d6775722e636f6d2f497339315132372e706e67)

O último aspecto deve ser o seguinte:

![Pasta do PSX](https://camo.githubusercontent.com/614395aa32769188757678ecdb0dcc34651a632e/68747470733a2f2f692e696d6775722e636f6d2f516c4d6e4a416d2e706e67)

Como você pode ver, existem .cue /.bin /.sbi por disco e um .m3u por jogo multidisco.

#### Vantagens: <a id="avantages-2"></a>

* Seus jogos estão no formato .bin /.cue.
* Os atalhos do controle podem ser usados ​​para trocar os discos.
* Arquivos .Sbi podem ser usados.
* Existe um arquivo de save para todos os discos.

#### Desvantagens: <a id="inconvenients-2"></a>

* Você precisa editar o arquivo es\_systems.cfg \(apenas uma vez\).
* Você precisa ocultar os arquivos .cue no menu Recalbox.

### Defina os atalhos do controle para alterar entre CDs <a id="defina-os-atalhos-do-controle-para-alterar-entre-cds"></a>

* No jogo, acesse o menu Retroarch \(Hotkey+B\).
* Pressione A para acessar o menu principal.
* Vá para Configurações&gt; Entradas&gt; Vinculação de tecla de atalho
* Configure as funções de ejetar disco, próximo disco e disco anterior com os botões que desejar \(e que ainda não possuam nenhuma função especial atribuída\).
* Exemplo: ejeção do disco \(analógico da direita para cima\), Próximo disco \(analógico da direita para a direita\) e anterior \(analógico da direita para a esquerda\).
* Agora no jogo, você pode pressionar `Hotkey + "a tecla configurada"` para ejetar o disco, trocar o disco e inserir um disco \(e reiniciar o jogo se necessário\).

### Jogos multifaixas <a id="jogos-multifaixas"></a>

Alguns jogos possuem várias faixas por disco. Isso significa que o arquivo .cue requer várias entradas \(uma por faixa\).

Exemple de .cue multifaixa:

![.cue com v&#xE1;rias faixas](https://camo.githubusercontent.com/ab378b532b3cf6c821afbff21997a6e7b09ff480/68747470733a2f2f692e696d6775722e636f6d2f6265556e5637512e706e67)

O último aspecto deve ser o seguinte:

![Jogo Multifaixa](https://camo.githubusercontent.com/64940efef21e347115f420cceebd89d8d708e952/68747470733a2f2f692e696d6775722e636f6d2f4347704b4555622e706e67)

## Perguntas frequentes \(FAQ\) <a id="faq"></a>

Você tem que descompactá-los. Veja esse [guia](https://www.epforums.org/showthread.php?57757-ECM-And-APE-Guide).

### ​Como posso ativar o Dualshock \(análogicos\)? <a id="como-posso-ativar-o-dualshock-analogicos"></a>

No jogo, vá para o menu RetroArch \(Hotkey + A\) e no menu rápido vá para Opções. Lá, selecione _Analógico_ na opção Tipo do controle 1 \(o mesmos para todos os controles que você deseja alterar\). Se o menu Ape Escape \(versão PAL\) não funcionar, verifique o arquivo .sbi.

##  Glossário <a id="glossario"></a>

* .ape: arquivo compactado para o arquivo .wav.
* .bin: dados do jogo e faixas de música.
* .ccd/.img/.sub : clonagem de arquivo de CD. Você deve transformá-los em .cue / .bin \(com IsoBuster, por exemplo\).
* .cue: arquivo no qual as faixas do disco são definidas. Um por arquivos .bin.
* .ecm: arquivo compactado para o arquivo .bin.
* .pbp: Arquivo PSP para jogos PSX.
* .ppf: arquivo de patch para jogos com proteção LibCrypt.
* .sbi: arquivo que contém informações de proteção e que é necessário para rodar jogos protegidos em emuladores. Eles devem ter o mesmo nome do arquivo .cue.
* .wav: arquivo de faixa de música. Você deve renomeá-lo para .bin.

## Links úteis <a id="links-uteis"></a>

* [Guia ECM-APE](https://www.epforums.org/showthread.php?57757-ECM-And-APE-Guide)
* [Lista dos jogos PSX](https://psxdatacenter.com/pal_list.html)
* [Arquivos .sbi](http://psxdatacenter.com/sbifiles.html)
* [Gerador de arquivos .cue](http://nielsbuus.dk/pg/psx_cue_maker/)

​

