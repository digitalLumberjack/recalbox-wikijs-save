---
title: Converta roms PSX .BIN em .ISO
---

# Converta roms PSX .BIN em .ISO

## Introdução​ <a id="introducao"></a>

Aqui, vamos desenvolver uma solução para obter **um único arquivo** por jogo, no **formato .ISO**. Todos os jogos funcionarão neste modelo, **desde que** os **arquivos .BIN** baixados **também funcionem**.


>Um problema comum com roms para PSX é que os arquivos estão **mais frequentemente** nos formatos **.BIN e .CUE** do que em **.ISO**, e às vezes ainda roms no formato **.BIN.ECM**
>
>Uma das desvantagens desses arquivos é que geralmente são vários, 2 ou 3 arquivos ou, às vezes, dezenas.  
>Isso pode **distorcer a qualidade da apresentação** na interface do **EmulationStation** \(você pode acabar com vários arquivos por jogo e, de repente, o número total de jogos para este sistema também é distorcido\).
>
>**Este problema de exibição** no EmulationStation ocorre:
>
>* Se você não fizer o **scrappe das suas roms.**
>* Se você configurou incorretamente seu software de **scrap**.
>
>No entanto, roms nos formatos .BIN e .CUE também são funcionais.
{.is-info}

Em primeiro lugar, o arquivo ISO é uma imagem binária de disco, é o formato que nos interessa porque o jogo inteiro cabe em um arquivo.

### O arquivo BIN <a id="o-arquivo-bin"></a>

O arquivo **.BIN** também é uma **imagem de disco**, é um formato muito próximo ao **ISO A desvantagem** é que os arquivos BIN podem ser **vários**, ou às vezes até muito grandes, e geralmente vêm **com outro arquivo no formato CUE**.

​

### O arquivo CUE <a id="o-arquivo-cue"></a>

O arquivo **.CUE** é um **pequeno arquivo de texto** que acompanha os **.BIN.** Pode ser aberto **com qualquer editor de texto**, sua única finalidade é **ajudar a indexar os arquivos BIN** que acompanha. **Para indicar** ao emulador **que vai lê-lo**, **onde estão os arquivos BIN, quais são seus nomes, a ordem** e, às vezes, **as diferentes faixas de áudio** contidas.

​

### O arquivo .BIN.ECM <a id="o-arquivo-bin-ecm"></a>

O arquivo **.BIN.ECM** é mais raro, é o resultado de um **arquivo BIN compactado.** Veremos na última parte **como descompactá-lo**.

A primeira observação é que geralmente um jogo consiste em **um arquivo BIN acompanhado de um arquivo CUE**. Neste caso, o **arquivo CUE** \(texto\), que tem a função **de indexar os diversos arquivos BIN** que o acompanham, **não tem mais utilidade**. Os usuários entenderam bem, aliás neste caso basta **deletar o arquivo CUE**, e aí **o arquivo BIN é autônomo** \(como um ISO\), pode deixar como está, **que já funciona**.


>**Atenção:**
>
>Nem sempre é tão simples: veja o exemplo 4b deste tutorial, existem **arquivos CUE que são inúteis**, outros são **mais completos e, portanto, importantes**.
{.is-danger}

Você pode **aprender a fazer a diferença** consultando-os sistematicamente, você também tem a possibilidade de **converter todas as suas ROMs** sem problemas\).

A segunda observação é **nunca renomear os arquivos BIN** que acabamos de ver. Na verdade, se você **abrir um arquivo CUE** com um editor de texto, verá que ele **lista todos os arquivos .BIN** que o acompanha. **Se você renomear** os arquivos BIN, eles **não corresponderão mais**.

Nesse caso, você pode **renomear todos os BINs no arquivo CUE**, mas essa é uma etapa mais fácil de evitar ao **não renomear os arquivos**. Depois de **obter um arquivo ISO**, você estará livre para **renomeá-lo** como desejar.

## Conversão de BIN em ISO​ <a id="conversao-de-bin-em-iso"></a>

**1-** Vamos agora discutir **a conversão de arquivos BIN para ISO.** Para isso, utilize o software [IsoBuster](https://www.isobuster.com/) \(para Windows, compatível com Windows 10\), gratuito na versão demo.

* **Abra** o [IsoBuster](https://www.isobuster.com/)
* **Arquivo&gt; Abrir arquivo de imagem**
* **Encontre** onde está o jogo no formato BIN / CUE.
* Como você **não pode selecionar vários arquivos BIN para incorporar** no IsoBuster, **o truque** é usar o **arquivo CUE**, que **indexa todos os BINs** que compõem o jogo. Este exemplo não é interessante porque há apenas 1 arquivo BIN, mas o **princípio seria o mesmo com 3 ou 30 arquivos BIN**: usamos o .CUE

Se a sua rom **está em 1 arquivo BIN** e você **excluiu o .CUE**, não há problema, ele funciona **selecionando diretamente o .BIN**


>**Nota:**
>
>Exceto que acabei de ter **outro caso com Rayman,** composto de **Rayman.bin** e **Rayman.cue**  
>Como você pode ver na imagem abaixo, o **arquivo .cue é muito mais completo e, adicionalmente, indexa as faixas de áudio do jogo**.  
>Nem todos os arquivos **.CUE** são **igualmente completos**, mas é um **bom hábito** trabalhar **sempre com .cue**
{.is-warning}


>Aqui está **um arquivo** contendo **os arquivos CUE** para todas as roms **PSX:** [cue\_and\_sbis](https://www.google.fr/#q=cue_and_sbis)
{.is-info}

* Na **coluna à esquerda, clique com o botão direito na raiz** \[CD\], em **Extrair CD&gt; Dados brutos \(.BIN, .ISO\)**
* Você **dá um nome** ao arquivo de exportação, **o nome do jogo desejado**. Normalmente **nesta fase** dos programas, se você **não colocar uma extensão** de arquivo \(.ISO\), **mas verificar** que ela está selecionada **.ISO abaixo**, seu arquivo chega em **.iso Com IsoBuster** não é **se você não anotá-lo**, seu arquivo **não terá extensão de arquivo**. Você pode **adicioná-lo mais tarde**, mas também **pode se perder**, é mais fácil **colocar a extensão .iso no nome do arquivo:**
* **A conversão** leva alguns segundos:
* Se você **selecionou um .CUE,** você **clica em não**, de qualquer forma, sendo usado no programa, **ele não pode ser substituído.**

Você **obteve seu jogo** no formato **ISO**, que terá sido **extraído junto com os arquivos BIN e CUE originais.**

## BIN compactado \(BIN.ECM\)​ <a id="bin-compactado-bin-ecm"></a>

E terminaremos com o caso mais raro do **BIN compactado,** no formato **.BIN.ECM** Remover a extensão **.ECM** para obter um **.BIN não funciona**, é necessário passar por um **programa de descompressão**.

Existem **vários métodos** que você pode tentar:

* Por meio do **navegador Chrome** neste site \(botão Adicionar\)
* **Para Linux e OSX:** Existem métodos de **linha de comando**, onde o método é **arrastar os arquivos para o terminal.** Você encontrará **tutoriais adequados** pesquisando os termos **"BIN.ECM" e "Un-ECM" + o nome do seu sistema operacional**.
* **Para Windows** :
  * Baixe o programa **Un-ECM.exe** \(24Kb\) [nesta página](https://archive.org/details/ECMToolsV1.0).
  * **Extraia o programa** Un-ECM.exe em **uma pasta de mesmo nome** entre **seus programas** e **mantenha seu caminho** de instalação.
  * Clique com o **botão direito** em um arquivo **.BIN.ECM** e clique em **"Abrir com"**.
  * Na **lista de programas** propostos, role para baixo e **clique** em "**Procurar outro aplicativo neste PC**" e **abra-o com o** programa **Un-ECM.exe.**
  * Você pode **marcar** a caixa "**sempre abrir com este aplicativo"**, portanto, no futuro, **clicar duas vezes** em um arquivo **.BIN.ECM** descompactará **automaticamente** o arquivo **BIN** nessa **mesma pasta**.

O arquivo **BIN** resultante pode, portanto, **ser usado como está** ou você também pode **convertê-lo para ISO** como vimos anteriormente.

