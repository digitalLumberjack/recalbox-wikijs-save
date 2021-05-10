---
title: Tutorial ClrmamePro
---

# Tutorial ClrmamePro

### **Definições** <a id="definicoes"></a>

* game \(jogo\): indica o nome do jogo
* set : versão de cada jogo
* clone : versão de um jogo diferente do original
* rom : arquivo contido em um set.
* rom set : conjunto de arquivos \(roms\) contidos em um set

## O que é um arquivo dat? <a id="o-que-e-um-arquivo-dat"></a>

Arquivos dat são arquivos de texto com informações sobre jogos emulados com uma versão específica do MAME. Nos arquivos dat, encontramos informações para conjuntos específicos, como: nome da rom \(nome\), ano \(ano\), fabricante \(fabricante\), informações de mesclagem \(mesclagem\), rom pai \(romof\) ou clone de \(cloneof\), tamanho da rom \(tamanho\), CRC para cada rom. O CRC é um algoritmo que permite verificar a integridade de um arquivo, o clrmamepro o utiliza para verificar seus conjuntos de ROM.

O cabeçalho mostra informações como o nome do emulador, uma descrição, a versão e informações sobre o autor.

```markup
<datafile>
    <header>
        <name>MAME</name>
        <description>MAME 0.78</description>
        <category>EMULATION</category>
        <version>0.78</version>
        <date>-not specified-</date>
        <author>AntoPISA</author>
        <email>progettosnaps@gmail.com</email>
        <homepage>http://www.progettosnaps.net/</homepage>
        <url>-not specified-</url>
        <comment>-not specified-</comment>
        <clrmamepro/>
    </header>
```

## **Tabela das versões disponíveis no Recalbox** <a id="tabela-das-versoes-disponiveis-no-recalbox"></a>

Exceto a versão RPI, não mencionei imame4all e piFBA.

​

| Versão | Emulador | Núcleo | Arquivos Dat | Caminho | Bios | Lista de Compatibilidade |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 6.0 | Libretro | imame4all | [mame 0.37b5](https://github.com/recalbox/recalbox-buildroot/blob/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/imame4all/imame4all.dat) | /recalbox/share/roms/mame | Liste |  |
| 6.0 | Libretro | Mame2003 | [mame 0.78 dat](https://github.com/recalbox/recalbox-buildroot/blob/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/mame2003/mame2003.dat) | /recalbox/share/roms/mame | Liste |  |
| 6.0 | Libretro | Mame2003-plus | mame 0.78 + mame 0.188 | /recalbox/share/roms/mame | \[Liste\] |  |
| 6.0 | Libretro | Fba 0.2.97.44 | \[mame 0.189 dat\] | /recalbox/share/roms/fba\_libretro | Liste |  |
| 6.0 | Libretro | FBA 0.2.97.44 neogeo | \[mame 0.189 dat\] | /recalbox/share/roms/neogeo | neogeo.zip |  |
| 6.0 | Libretro | mame2003 neogeo | mame 0.78 dat | /recalbox/share/roms/neogeo | neogeo.zip |  |
| 6.0 | Autônomo | piFBA | [mame 0.114 dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-os/master/wiki/dat/fba_029671_od_release_10_working_roms.dat) | /recalbox/share/roms/neogeo | Liste |  |
| 6.0 | Libretro | FBA 0.2.97.44 | \[mame 0.189 dat\] | /recalbox/share/roms/fba\_libretro | Liste |  |


>Uma rom arcade no formato zip nunca deve ser descompactada ou renomeada
{.is-warning}


>**Nota:** Outros arquivos DAT estão disponíveis no site [progretto-SNAPS Dats](http://www.progettosnaps.net/dats/)
{.is-info}

## **BIOS Arcade** <a id="bios-arcade"></a>

Se você recuperou seu romset, a BIOS de algumas Editoras de jogos estará disponível neste. Aqui está a lista de BIOS presentes no seu romset, necessárias para que algumas ROMs funcionem.​

| Nome | Editora | Nome da BIOS |
| :---: | :---: | :---: |
| Acclaim PSX | Acclaim | acpsx.zip |
| Arcadia System BIOS | Arcadia Systems | ar\_bios.zip |
| Atari PSX | Atari | atpsx.zip |
| Atlus PSX | Atlus | atluspsx.zip |
| Baby Phoenix/GV System | Konami | konamigx.zip |
| Crystal System BIOS | BrezzaSoft | crysbios.zip |
| DECO Cassette System | Data East Corporation | decocass.zip |
| Hyper NeoGeo 64 Bios | SNK | hng64.zip |
| Max-A-Flex | Exidy | maxaflex.zip |
| Mega Play BIOS | Sega | megaplay.zip |
| Mega-Tech | Sega | megatech.zip |
| Multi Amenity Cassette System BIOS | I'Max | macsbios.zip |
| Neo-Geo | SNK | **neogeo.zip** |
| Nintendo Super System BIOS | Nintendo | nss.zip |
| PGM \(Polygame Master\) System BIOS | IGS | **pgm.zip** |
| PlayChoice-10 BIOS | Nintendo of America | **playch10.zip** |
| PS Arcade 95 | Eighting / Raizing | psarc95.zip |
| ST-V Bios | Sega | stvbios |
| Super Kaneko Nova System BIOS | Kaneko | **skns.zip** |
| System GX | Konami | **konamigx.zip** |
| Taito FX1 | Taito | taitofx1.zip |
| Taito GNET | Taito | taitogn.zip |
| TPS | Tecmo | tps.zip |
| ZN1 | Capcom | cpzn1.zip |
| ZN2 | Capcom | cpzn2.zip |

Fonte : [mamedb.com](http://www.mamedb.com/category/BIOS.html)​

**Em negrito : bios necessária**

## ClrmamePro <a id="clrmamepro"></a>

ClrmamePro é uma ferramenta para verificação e reconstrução seus romsets arcade de acordo com um arquivo de informação \(formato XML ou dat\).

**Instalação**

1. Baixe o ClrmamePro para Windows ou MacOS ; no Linux, apenas use o Wine. Nota : o arquivo zip é uma versão portátil.
2. Instale-o.
3. Consiga o arquivo dat correto do emulador arcade
4. Execute o ClrmamePro no modo administrador \(clique com o botão direito &gt; Executar como administrador\)


>**Dica**: No Windows, clique com o botão direito do mouse em cmpro64.exe ou cmpro32.exe e clique em "Propriedades"&gt; guia Compatibilidade&gt; marque a caixa: Executar como administrador. Valide clicando em Ok. O aplicativo agora sempre será executado no modo administrador.
{.is-warning}

## Roms "Pais" \(Parent Roms\) e Roms "Clones" \(Clone Roms\) <a id="roms-pais-parent-roms-e-roms-clones-clone-roms"></a>

Há dois formatos especiais de rom, que chamamos de **Rom Pai \(Parent Rom\) e Rom Clone \(Clone Rom\)**. Uma Rom "Clone" precisa da Rom "Pai" para rodar corretamente..

Exemplo : _Metal Slug 4_

```text
Metal Slug 4 (NGH-2630)  (clone de: mslug4)          mslug4h.zip     
Metal Slug 4 (NGM-2630)                              mslug4.zip
```

mslug4.zip é a rom pai, mslug4h.zip é a rom clone. A rom clone depende da rom pai. O nome das roms clone são geralmente seguidos por uma letra, justamente para diferencia-las dos seus pais.

## Diferença entre Conjunto Não-Mesclado \(Non-Merged set\), Conjunto Dividido \(Split Set\) e Conjunto Mesclado \(Merged-Set\) <a id="diferenca-entre-conjunto-nao-mesclado-non-merged-set-conjunto-dividido-split-set-e-conjunto-mesclado-merged-set"></a>

Existem três métodos de classificação de ROMs usados ​​para gerenciar as diferentes versões de um jogo:

* **Conjunto Não-Mesclado \(Non Merged Sets\)** : cada pai e clone terá seu próprio arquivo zip, contendo as ROMs necessárias. Esse método é de longe o método que ocupa mais espaço no disco rígido, mas você não precisará mais se preocupar se os clones estão com os pais ou não, quando você queima suas ROMs, por exemplo.
* **Conjunto Dividido \(Split Set\)** : o conjunto pai possui um arquivo zip contendo todas as ROMs necessárias. O\(s\) conjunto\(s\) de clones possui um arquivo zip que contém apenas as ROMs diferentes do conjunto pai. No entanto, os conjuntos de clones precisarão de algumas ROMs comuns, contidas no arquivo zip pai, para funcionar. Esta solução ocupa a menor quantidade de espaço em disco rígido, mas se os conjuntos de clones não estiverem no mesmo diretório que os conjuntos pai, eles não funcionarão.
* **Conjunto Mesclado \(Merged-Set\):** os pais e os clones de um jogo estarão contidos em um grande arquivo zip. Em relação ao uso do disco, é uma solução intermediária. Maior que o do conjunto dividido e menor que o não-mesclado. O problema de separação pai / clone também foi resolvido. A única desvantagem é atualizar suas roms se você não estiver interessado em clones.​

<table>
  <thead>
    <tr>
      <th style="text-align:center">Modo</th>
      <th style="text-align:center">Non-Merged (N&#xE3;o-Mesclado)</th>
      <th style="text-align:center">Split-Merged (Dividido)</th>
      <th style="text-align:center">Merged (Mesclado)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">parent (pais)</td>
      <td style="text-align:center">
        <ul>
          <li>rom 1 nom : abcd crc : 1234</li>
          <li>rom 2 nom : azerty crc : 789</li>
        </ul>
      </td>
      <td style="text-align:center">
        <ul>
          <li>rom 1 nom : abcd crc : 1234</li>
          <li>rom 2 nom : azerty crc : 789</li>
        </ul>
      </td>
      <td style="text-align:center">
        <ul>
          <li>rom 1 nom : abcd crc : 1234</li>
          <li>rom 2 nom : azerty crc : 789</li>
          <li>rom 3 nom : bdce crc : 4444</li>
          <li>rom 3&apos; nom : jklm crc : 5555</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:center">clone 1</td>
      <td style="text-align:center">
        <p></p>
        <ul>
          <li>rom 1 nom : abcd crc : 1234</li>
          <li>rom 2 nom : azerty crc : 789</li>
          <li>rom 3 nom : bdce crc : 4444</li>
        </ul>
      </td>
      <td style="text-align:center">
        <ul>
          <li>rom 3 nom : bdce crc : 4444</li>
        </ul>
      </td>
      <td style="text-align:center"></td>
    </tr>
    <tr>
      <td style="text-align:center">clone 2</td>
      <td style="text-align:center">
        <p></p>
        <ul>
          <li>rom 1 nom : abcd crc : 1234</li>
          <li>rom 2 nom : azerty crc : 789</li>
          <li>rom 3 nom : jklm crc : 5555</li>
        </ul>
      </td>
      <td style="text-align:center">
        <ul>
          <li>rom 3 nom : jklm crc : 5555</li>
        </ul>
      </td>
      <td style="text-align:center"></td>
    </tr>
  </tbody>
</table>

Fonte [Tutorial Clrmamepro \(fr\) detalhado](http://clrmamepro.free.fr/merger.php)​

##  Configuração ClrmamePro <a id="configuracao-clrmamepro"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lxs1A-PJIlazZLj0r7W%2F-Lxs5oXHf0GNoe7lqAHj%2Fclrmamepro.png?alt=media&token=d1fd4a80-933b-47cd-b05b-4babb71badda)

1. Criação de Perfil

Clique em "Add DatFile" \(Adicionar arquivo Dat\) para carregar seu arquivo dat

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lxs1A-PJIlazZLj0r7W%2F-Lxs6-70gPqM-ARvrxmS%2Fadd_DatFile.png?alt=media&token=5e7087a1-61a5-4fef-8ac7-53379b3a99f4)

 2. Neste exemplo : mame0.780.dat para o mame2003.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lxs1A-PJIlazZLj0r7W%2F-Lxs6QZRNqBsO51V-rm6%2Fdatfiles.png?alt=media&token=d0b74229-6b37-46b5-935e-a1c83ffb650d)

Clique em **Load/update \(Carregar/atualizar\)**. Clique então em **default \(padrão\)**, espere o escaneamento, e clique em OK TO ALL \(Ok para todos\) para deixar o processo seguir.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lxs1A-PJIlazZLj0r7W%2F-Lxs6_C42RWZ1Z6pOH-O%2Fok.png?alt=media&token=cd8ae580-a2ac-4633-96ff-e2859e7c4c75)

 3. Clique no botão settings \(configurações\). Configure o campo **ROM-Paths** \(1\), que indica o caminho do seu diretório de Roms. Clique no botão **Add... \(adicionar...\)** \(2\) . Clique então em **Save As Def. \(Salvar como padrão\)** \(3\) - Valide sua ação clicando em OK.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwUxzaIbGBvIpUyQI6%2FSettings.png?alt=media&token=b76883cf-7bf1-46d9-ab61-34dae3ea4af6)

Configure também o **Add-Paths**, que indica o caminho para o diretório de destino das suas ROMs. Clique no botão **Add...** \(**Adicionar...**\).

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwV5u7QqP8WsWRUSsv%2Faddpath.png?alt=media&token=ef6f3ceb-29c8-4a97-a67d-cfcf9b182d91)

Feche a Janela.


>**Nota:** você pode adicionar outros caminhos ao diretório de amostras, por exemplo.
{.is-info}

## Função Scanner: Verificando seu romset <a id="funcao-scanner-verificando-seu-romset"></a>

1. Clique no botão "Scanner"
2. Marque **Sets \(Conjuntos\)**, **ROMs** e **Samples \(Exemplos\)** se você configurou os caminhos \(1\)
3. Escolha a opção correta, relacionada ao seu romset \(non merged/não mesclado, split-merge /dividido, ou merged/mesclado\) \(2\)
4. Clique em "New Scan" \(Nova verificação\) \(3\)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwVLAswxuyLKQLq6fW%2FScanner_.png?alt=media&token=8e131ef7-b8e1-4068-8db7-3eb1b18f1509)

## **Função Reconstruir \(Rebuild\):** Construa seu romset. <a id="funcao-reconstruir-rebuild-construa-seu-romset"></a>


>**Conselho**: trabalhe sempre em um romset de backup com esta ferramenta!
{.is-warning}

Exemplo com mslug3

```text
mslug3.zip parent rom
mslug3b6.zip clone of mslug3.zip
mslug3h.zip clone of mslug3.zip
mslug3v.zip clone of mslug3.zip
```

Supondo que você tenha um romset não mesclado, ou seja, ele contém os roms pai com os clones. A função de reconstrução permite alterar o "modo" do seu romset: de um romset non merged/não-mesclado para um romset merged/mesclado ou split/dividido e vice-versa.

1. Clique no botão "Scan", desmarque as amostras \(samples\), chd e escolha Non-Merged Set/Conjunto não mesclado, feche a janela clicando no "X" no canto superior direito.
2. Clique em Reconstruir Indique o caminho da fonte de suas ROMs. Verifique o destino. Escolha Non-Merged Set/Conjunto não mesclado, desmarque "Remove Matched Sourcefiles"/ "Remover arquivos de origem correspondentes". Clique no botão Rebuild/Reconstruir.

![clrmamepro - fun&#xE7;&#xE3;o reconstruir](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwWM_MvnWtCEvCtj28%2FRebuilder_.png?alt=media&token=47abd07d-a6b3-4265-84d1-7051d5929eb5)

Simplesmente faça uma pausa, este passo pode demorar um pouco ... :\)

No recalboxOS, todos os nossos jogos de arcade são divididos em 3 grupos: mame, fba\_libretro e neogeo.

Atenção**:** no Neogeo, por padrão, o emulador usado é fba\_libretro; se você deseja usar o mame 2003, precisará modificar o emulador usado por padrão do sistema. No menu Emulationstation \(botão Start\), depois nas Opções de Jogo&gt; Avançado&gt; neogeo&gt; modifique as opções desejadas.

Para separar as ROMs neogeo contidas no seu romset mame ou fba\_libretro, tudo o que você precisa fazer é iniciar o "Scan" e clicar no botão **Systems**/**Sistemas**.

O número de sistemas pode variar dependendo do arquivo de dados que você carregou.

1.  Clique no botão "AutoAssign"/"Atribuição automática" - os sistemas são atribuídos à sua pasta roms.
2. Clique no botão None/Nenhum para desmarcar todos os sistemas.
3. Marque apenas a caixa de seleção \[Bios\] Neo geo e escolha uma pasta para neogeo.
4. Na caixa Move Set/Mover conjunto para, especifique uma pasta para as suas roms neogeo.

   ​

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwWs6-yB58HMt54ueA%2FSystems%20%26%20assigned%20System-Default-Paths.png?alt=media&token=6ca13fa3-041f-492d-adb8-6857b730e016)

Verifique sua pasta.

## Dividindo um romset completo para obter apenas as roms pai <a id="dividindo-um-romset-completo-para-obter-apenas-as-roms-pai"></a>

Basta criar um profile/perfil com o arquivo dat desejado. Nesse caso, mame2003\_parent\_only.dat \(com ou sem neogeo, você decide\).

* rom-path \(pasta que contém todas as suas roms\)
* adicione o caminho das amostras \(se necessário\)
* Marque a caixa Make backups To Folder, e especifique uma pasta de backup.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwX05Mjm-O9FsHtTtb%2Fbackup_folders.png?alt=media&token=f77eb0dc-8717-4703-b1f5-6ea684a33225)

* Use a função Scanner e configure da seguinte maneira:

  * Clique no botão system/sistemas e clique no botão Auto-assign/Atribuir automaticamente.
  * Marque todas as caixas na seção fix section/correção de verificação.
  * Para acelerar a verificação, desmarque a caixa Ask before fixing/Perguntar antes de corrigir. Uma vez feito, clique em scan.
  * Clique em OK ALL/OK PARA TUDO se a pergunta for feita durante a verificação.

  ​

Aqui está: consulte sua pasta de origem \(rom-path\) e você verá que as ROMs **não indicadas** no seu arquivo dat foram movidas para a sua pasta de backup. A pasta de backup contém:

* na pasta principal \(root\), as ROMs modificadas pela verificação que não estavam no arquivo dat,
* e um subdiretório chamado \_unknown \(\_desconhecido\) com as ROMs não modificadas pela verificação que não estavam no arquivo dat.

## Crie seu arquivo dat: <a id="crie-seu-arquivo-dat"></a>

Você verificou seu romset com clrmamepro através da função Scanner. Para criar um arquivo dat personalizado, você pode usar a função dir2dat disponível no Profile/Perfil. Exemplo: mame0.78\_neogeo\_only.dat

1. Indique a pasta de origem \(1\)
2. Escolha o formato xml \(2\)
3. Preencha o formulário das Entradas de cabeçalho \(3\)
4. Clique no botão Create/Criar \(4\)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwXLJ2VnqUx1vaZrfQ%2FDir2Dat.png?alt=media&token=1a969ad7-65e3-45b6-8753-5326425b4219)

## Atualizando seu romset <a id="atualizando-seu-romset"></a>

### A. Pré-requisitos <a id="a-prerequisite"></a>

* Ter várias versões de romsets arcade completos
* Possivelmente com todos os pacotes de atualização do Mame 0.xxx a 0.xxxx
* Fazer o download do arquivo dat necessário \(veja a tabela acima\)
* Criar um novo perfil com o arquivo dat baixado anteriormente
* Fazer um backup dos seus romsets em um disco rígido externo e sempre trabalhar em um backup do romset para atualizar.

### B. Configuração <a id="b-configuration"></a>

* rom-path \(a pasta de origem das suas roms\)
* add-path \(adicione todas as pastas romsets que você possui, quanto mais, melhor\)
* sample-path \(adicione a pasta de amostras dos seus romsets \(opcional porque alguns conjuntos têm amostras ausentes\)\)
* Configurar uma pasta de backup

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwXXe3PN341MWjQ6zy%2Fbackup_folders.png?alt=media&token=072312e4-54d0-4857-bd1d-7783cb2d0218)

### C. Escanear seu romset <a id="c-scan-your-romset"></a>

* Verifique as seguintes opções como na imagem:

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwXmcXW-qbo2-wyQ-d%2Fscanner_update.png?alt=media&token=c3b71d36-8ee0-4f79-b86a-8af171f27158)

Clique no botão **Systems/Sistemas** , então em **Auto-Assign/Atribuição automática**

E, finalmente, clique no botão **New Scan...** ; e espere um pouco, isso pode levar algum tempo...

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwY-WeeVyrJKAvHdjc%2FSystem-Default-Paths.png?alt=media&token=801c9401-30c1-40e7-a0e4-bf5c0944ac93)

### D. Analise das estatísticas <a id="d-analysis-of-statistics"></a>

O que nos interessa aqui é a parte superior: **Missing/Ausente**. Esta parte **Missing/Ausente** mostra os conjuntos, as ROMs e as amostras ausentes. Basta ler novamente as definições acima, se necessário.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwY8vtgOGP6Ev8TGNQ%2Fsatistic.png?alt=media&token=d7c272b9-197c-4362-bfc4-99c40adc5736)

Valide clicando em OK para fechar a janela; mas quais conjuntos estão faltando? Nas informações do conjunto, você tem a lista de conjuntos e ROMs ausentes.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwYJbWc9edz7bt4yC_%2FScan%20Results.png?alt=media&token=96977294-3d12-406f-907b-8a2b2f3ae316)

Para obter uma lista dos conjuntos ausentes, basta clicar no botão **Miss List....**

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwYa6fO8SVukB1UBbG%2Fmisslist.png?alt=media&token=7603efd4-935b-43ec-a219-5cf584660337)

## Como preencher os sets/conjuntos ausentes: <a id="como-preencher-os-sets-conjuntos-ausentes"></a>

Com o nome escrito no arquivo, você pode procurar os conjuntos ausentes em diferentes mecanismos de pesquisa com as seguintes palavras-chave: mame filename.zip

Exemplo com o jogo Touch & Go \(touchgo.zip\) com esses clones.

```text
touchgo
touchgoe
touchgok
touchgon
```

Provavelmente, você encontrará sites com os arquivos ausentes. Busque-os e coloque-os em uma pasta chamada ausente, por exemplo. Depois que todos os conjuntos ausentes forem recuperados, adicione a pasta na seção `settings > add-path` \(configurações&gt; adicionar caminho\). Reinicie a verificação. Se estiver tudo bem, você deve ter reduzido os conjuntos ausentes. Repita isso quantas vezes for necessário, se ainda estiver faltando algum.

## Preenchendo as ROMs ausentes: <a id="preenchendo-as-roms-ausentes"></a>

Esta é a parte mais longa e entediante de reunir todos os seus romsets. Para maior facilidade, exporte a lista de ROMs ausentes. Análise de uma ROM ausente:

```text
Burger Time (Data East USA) [graphics issues, use parent romset!] [folder: btime3 - parent: btime - size: 56kb]
missing rom: ab03-3.6b [size: 2048] [CRC32: f699d797]
missing rom: ab04-3.9b [size: 4096] [CRC32: 5d90c696]
missing rom: ab05-3.10b [size: 4096] [CRC32: c2b44b7f]
missing rom: ab05a-3.12b [size: 4096] [CRC32: 12e9f58c]
missing rom: ab06-3.13b [size: 4096] [CRC32: e0b993ad]
missing rom: ab07-3.15b [size: 4096] [CRC32: 91986594]
```

**​**

* **Burger Time \(Data East USA\)** : nome do set
* **\[graphics issues, use parent romset!\]** : este é um clone de btime3.zip com problemas gráficos, é aconselhável usar a ROM pai btime.zip.
* **\[folder: btime3 - parent: btime - size: 56kb\]** : lembre-se anteriormente, eu lhe disse que as ROMs clones sempre vinham com um número ou uma letra. Aqui estamos falando de um clone btime3.zip e sua ROM principal é btime.zip.
* **missing rom: ab03-3.6b** : informações sobre o arquivo \(rom\) ausente no arquivo
* **\[size: 2048\] \[CRC32: f699d797\]** : informações sobre o tamanho / peso desse arquivo com a assinatura CRC para identificá-lo

Usando as seguintes informações no seu mecanismo de pesquisa preferido: **ab03-3.6b CRC32: f699d797** É bem possível que você encontre a sua ROM ausente, basta refazer a pesquisa nos outros arquivos. Eles podem ou não estar contidos no arquivo recuperado. Recupere seus arquivos ausentes e coloque-os em uma pasta ausente como antes. Quando terminar, não esqueça de adicionar a pasta em `settings > add-path` \(configurações&gt; adicionar caminho\). Reinicie seu scan quantas vezes quiser.

No final, você deve ter:

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwZFrJP24avHJjH5fW%2Fromsetcomplet.png?alt=media&token=af7b915d-408d-412d-9937-7f3c47efe4b6)

Para obter um arquivo que contém as ROMs ausentes, clique com o botão direito do mouse na janela Definir informações e escolha **Copy to Clipboard &gt; all list sets messages /** Copiar para a área de transferência&gt; todas as mensagens de conjuntos de listas. Abra a área de transferência e cole o resultado.

**Nota:**

Mova `https://github.com/recalbox/recalbox-buildroot/blob/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba_libretro/FBA_libretro_NEOGEO_only.dat` na pasta `/recalbox/share_int/roms/neogeo/date file/FBA_libretro_NEOGEO_only.dat` e adicione a pasta mame2003 neogeo.

Realize um PR com as datas ausentes.

### Trabalho: Opções de definir informações <a id="trabalho-opcoes-de-definir-informacoes"></a>

Após configurar o clrmamepro, comece a verificar o seu romset. Uma janela chamada informações do conjunto é exibida. Clique no botão set information/definir informações. Para criar um arquivo dat contendo apenas roms pai Clique no botão avail.sets Desmarque os clones e pais, se marcados Digite as seguintes informações: `%c=?*` Você notará que apenas os clones estão selecionados Clique no botão invert/inverter; a seleção é invertida e agora as ROMs pai são selecionadas Clique no botão Export/Exportar; dê um nome ao seu arquivo dat \(mame2003\_parent\_only\)

### \[Em desenvolvimento\] Faça o download dos arquivos dat do clrmamepro: www Mode <a id="em-desenvolvimento-faca-o-download-dos-arquivos-dat-do-clrmamepro-www-mode"></a>

O WWW Mode é um gerenciador de downloads para arquivos dat.

* Abra o software clrmamepro
* Não é obrigatório, mas você já pode criar sua pasta para um perfil \(exemplo: mame 2003\) clicando com o botão direito do mouse em \[PROFILES\]&gt; Create folder.
* Clique no botão WWW Mode
* Clique no botão Adicionar site ....
  * URL do Dat : mamedl.esy.es/dats/cmdats/recalbox\_arcade.zip
  * Apelido do Site : Recalbox \(por exemplo\)
* Confirme no OK

  Você obterá uma lista de diferentes dados disponíveis.

![WWW Mode -Clrmamepro \_ lista de arquivos dats](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwZkZ_B6HAyQCl-9LV%2FwwwMode_list.png?alt=media&token=48d70210-6170-49d7-8121-232eb67f1d70)

* Clique com o botão direito do mouse no arquivo, escolha Download File/Baixar arquivo ou clique duas vezes no arquivo ou clique no botão de download.
* Você pode criar uma pasta ou não clicando em Create Dir, se não tiver feito isso antes.
* Selecione sua pasta e clique em OK. Clique em Sim para abrir o perfil com o arquivo dat recém-baixado.
* Clique em Default/Padrão, vá para a configuração \(settings\) do seu perfil.

