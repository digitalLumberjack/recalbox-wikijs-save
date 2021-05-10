---
title: Sobrecargas de Configurações
description: >-
  Descrição das sobrecargas de configuração local aplicadas a jogos específicos
  ou a pastas completas.
---

# Sobrecargas de Configurações


>**Recalbox 7.0 e superior!**
{.is-warning}

## Visão geral das possibilidades <a id="visao-geral-das-possibilidades"></a>

A partir do Recalbox 7.0, você pode substituir a configuração de um jogo ou de uma pasta completa.

Isso significa que, ao adicionar arquivos específicos as suas pastas de roms, você poderá modificar o comportamento do Recalbox, Retroarch ou do emulador para um determinado jogo ou para todos os jogos em uma pasta.

Concretamente, você será capaz de agir sobre:

* A Configuração do Recalbox
* A Configuração geral do Retroarch
* A Configuração dos núcleos do Retroarch

Aliás, você também terá a possibilidade de sobrecarregar as imagens e as descrições dos diretórios roms à medida que são exibidos no EmulationStation, veremos o porquê um pouco mais adiante.

Indefinidamente, poderemos, para um jogo ou conjunto de jogos:

* Definir um emulador ou núcleo específico
* Definir uma resolução de vídeo específica
* Modificar configurações de vídeo Retroarch
* Modificar opções dos núcleo
* etc.

## **Informações gerais** <a id="informacoes-gerais"></a>

As sobrecargas serão aplicadas a um arquivo base. Esses arquivos são os arquivos que são carregados primeiro pelo iniciador Python \(chamado **configgen**\) ao iniciar um jogo:

| Alvo | Arquivo de configuração |
| :--- | :--- |
| **Recalbox** | `/recalbox/share/system/recalbox.conf` |
| **Retroarch** | `/recalbox/share/system/configs/retroarch/retroarchcustom.cfg.origin` |
| **Núcleos** | `/recalbox/share/system/configs/retroarch/cores/retroarch-core-options.cfg` |

Todos os arquivos de configuração que podem ser sobrecarregados são arquivos do tipo chaves/valores. Portanto, poderemos modificar o valor de uma chave da configuração básica ou definir uma chave inexistente.

Podemos até sobrecarregar as sobrecargas! Na verdade, o sistema permite definir uma sobrecarga por nível de pastas. Portanto, ele começará carregando a configuração básica e, em seguida, aplicará sucessivamente todos os arquivos de sobrecarga que encontrar nas pastas, começando pela raiz. Então, no final, tentará aplicar a sobrecarga do jogo, se houver.​

Vamos dar um exemplo, se executarmos o jogo`/recalbox/share/roms/snes/platform/Aladdin (France).zip`, o **configgen** tentará substituir a configuração do Retroarch, carregando na ordem:

1. `Base: /recalbox/share/system/configs/retroarch/retroarchcustom.cfg`
2. `Path: /.retroarch.cfg`
3. `Path: /recalbox/.retroarch.cfg`
4. `Path: /recalbox/share/.retroarch.cfg`
5. `Path: /recalbox/share/roms/.retroarch.cfg`
6. `Path: /recalbox/share/roms/snes/.retroarch.cfg`
7. `Path: /recalbox/share/roms/snes/platform/.retroarch.cfg`
8.    `File: /recalbox/share/roms/snes/platform/Aladdin (France).zip.retroarch.cfg`

Claro, não é realmente aconselhável sobrecarregar a configuração antes de chegar pelo menos a pasta de um sistema.

Você notará que para sobrescrever uma pasta, os arquivos de sobrecarga devem estar **dentro** da pasta, começando com um ponto \(.\), o que os torna invisíveis para o sistema linux.

Por outro lado, a sobrecarga de um jogo deve ser nomeada exatamente como o jogo, **incluindo a extensão do arquivo**, seguida pelo sufixo de sobrecarga, `.retroarch.cfg` no exemplo acima.


>Uma vez que os arquivos de sobrecarga estão localizados dentro da suas pastas de roms, eles não temem uma falha do Recalbox, uma atualização que poderia ter dado errado ou uma falha do seu SD \(desde que você use um armazenamento externo, claro\)
>
>Eles também são portáteis: Leve seu pendrive com você para brincar na casa de um amigo, sua configuração será aplicada sem ter que tocar em nada!
{.is-info}

## Sobrecargas do Recalbox <a id="sobrecargas-do-recalbox"></a>

Sobrecarregar a configuração do Recalbox tem duas vantagens imediatas:

* Ser capaz de selecionar um modo de vídeo específico para um jogo ou conjunto de jogos. Os aficionados por pixel perfeitos em Arcade ficarão maravilhados.
* Ser capaz de escolher núcleo ou um emulador autônomo para um jogo ou conjunto de jogos.

Existem outras possibilidades, e sem dúvida você as encontrará 😉


>Sobrecarregar chaves que não são usadas pelo **configgen** não tem efeito!  
>Não espere modificar o comportamento do EmulationStation \(sobrecarregando as classificações, por exemplo\).
{.is-danger}


>**Lembrete:**
>
>Sobrecarga de pastas:  
>**`/path/to/your/roms/.recalbox.conf`** 
>
>Sobrecarga de rom:  
>**`/path/to/your/roms/file.zip.recalbox.conf`**
{.is-warning}

​

### Exemplo 1: Múltiplas versões do MAME <a id="exemplo-1-multiplas-versoes-do-mame"></a>

Por que se contentar com apenas uma versão do MAME quando poderíamos ter todas elas.

Por exemplo, você poderia ter MAME 2003 Plus e MAME 2010, cada romset em sua própria pasta:

`/recalbox/share/roms/mame/  
 ├── MAME2003Plus  
 └── MAME2010`

​

Em seguida, basta adicionar o arquivo:

```text
/recalbox/share/roms/mame/MAME2003Plus/.recalbox.conf
mame.emulator=libretro
mame.core=mame2003_plus
```

​E o arquivo:

```text
/recalbox/share/roms/mame/MAME2010/.recalbox.conf
mame.emulator=libretro
mame.core=mame2010
```


>E aí está! Isso é tudo. A partir de agora, todos os jogos na pasta MAME2003Plus serão iniciados com o núcleo mame2003\_plus-libretro, e aqueles na pasta MAME2010 com o núcleo mame2010-libretro!
{.is-success}

​

### Exemplo 2: Atribuir um determinado núcleo a um jogo <a id="exemplo-2-atribuir-um-determinado-nucleo-a-um-jogo"></a>

Meu jogo `/recalbox/share/pcengine/1943 Kai (Japan).zip` funciona melhor com o núcleo `mednafen_pce_fast_libretro` do que com o núcleo `mednafen_supergrafx_libretro` padrão \(suposição totalmente arbitrária para o exemplo\).

Até agora, era possível fazer isso via EmulationStation, editando os metadados do jogo, a informação ficava armazenada no arquivo `gamelist.xml`. Um erro ao gravar o arquivo, um scrappe malsucedido e toda a configuração era perdida...

Aqui você só precisa adicionar o arquivo:

```text
/recalbox/share/roms/pcengine/1943Kai(Japan).zip.recalbox.conf
global.emulator=libretro
global.core=mednafen_pce_fast
```


>Desta vez, sem risco de perder a configuração!  
>Claro, a edição de metadados via EmulationStation ainda funciona. Por outro lado, um arquivo de sobrecarga terá prioridade sobre o que está armazenado no `gamelist.xml`.
{.is-success}

​

### Exemplo 3: alterar o modo de vídeo de um jogo <a id="exemplo-3-alterar-o-modo-de-video-de-um-jogo"></a>

No meu Raspberry Pi2, o modo de vídeo padrão é CEA 4 HDMI. Mas no jogo **`Blazing Stars`** no **FinalBurn Neo**, fica um pouco lento. Mudar para 240p certamente ajudaria, além de ser perfeito em pixels! \(novamente, hipótese completamente hipotética, apenas para o exemplo\)

```text
/recalbox/share/roms/fba_libretro/blazstar.zip.recalbox.conf
global.videomode=CEA 8 HDMI
```


>E pronto! Quando eu executo este jogo, minha TV muda para 240p, e posso desfrutar totalmente do Blazing Stars.
{.is-success}

## Sobrecarga Retroarch <a id="sobrecarga-retroarch"></a>

As configurações do Retroarch dizem respeito ao próprio Retroarch \(e as opções de configuração são muito numerosas!\), bem como aos diferentes núcleos, cada um com opções específicas dependendo das máquinas que emulam.


>Já existem mecanismos específicos para Recalbox e Retroarch para substituir a linha de comando que inicia o emulador \(via [Recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)\), ou diretamente as configurações Retroarch/Núcleos \(via menus Retroarch\)
>
>Mas, nenhum desses sistemas permitiu que as sobrecargas fossem aplicadas a diretórios inteiros e/ou manter essas configurações específicas no mesmo lugar que as roms. Isso é particularmente interessante para pessoas que usam compartilhamentos de rede para fornecer roms a vários Recalbox!
{.is-info}

​

### Configuração do Retroarch <a id="configuracao-do-retroarch"></a>

A própria configuração Retroarch é extremamente rica e cobre muitas áreas diferentes.

Não há necessidade de insistir na questão, o melhor é dar uma olhada diretamente no arquivo RetroArch, que é particularmente bem documentado:  
[https://github.com/libretro/RetroArch/blob/master/retroarch.cfg](https://github.com/libretro/RetroArch/blob/master/retroarch.cfg)​

As possibilidades oferecidas pelas sobrecargas locais são enormes, entre as quais podemos contar:

* Configuração de vídeo: proporção, escala, anti-alias, rotação de tela ou até mesmo seleções de sombreamento, etc.
* Ajuste de áudio para alguns jogos desafiadores
* Overlays/Sobreposições
* Algumas opções relativas às entradas: seleção do mouse, sensibilidade, etc.
* Forçar configurações NetPlay específicas
* Alterar diretórios Retroarch \(saves, por exemplo\)
* Definir várias opções: Retroceder, Avançar, etc.
* ...

Assim como as sobrecargas de configuração do Recalbox, poderemos criar arquivos `.retroarch.cfg` para os diretórios e para as roms.


>**Lembrete:**  
>Sobrecarga de diretório:**`/caminho/para/suas/roms/.retroarch.cfg`**  
>Sobrecarga de Rom:**`/caminho/para/suas/roms/arquivo.zip.retroarch.cfg`**
{.is-warning}

**Exemplo 1: Forçar uma configuração de vídeo**

**Exemplo 2: forçar um shader para um diretório completo**

### Configurações dos Núcleos <a id="configuracoes-dos-nucleos"></a>

Sobrecarregar as opções dos núcleos oferece enormes possibilidades, **entre as quais um recurso muito aguardado pelos fãs dos "computosauros": a possibilidade de definir um diretório por subsistema!**


>Sobrecargas de núcleos são adicionadas ao arquivo _share/system/configs/retroarch/cores/retroarch-core-options.cfg_ quando o jogo é iniciado, o que implica que, uma vez que o jogo seja fechado, **elas serão salvas neste mesmo arquivo**, por para evitar surpresas desagradáveis, recomendamos substituir as chaves na pasta com os valores padrão \(por exemplo, `fbneo-frameskip = "0"`\) se você quiser substituir um jogo particular com valores específicos \(por exemplo, `fbneo-frameskip = "2"`\), portanto, você manterá seus valores "básicos" para arquivos que não têm sobrecargas personalizadas.
{.is-danger}

Isso é particularmente interessante para núcleos de várias máquinas, como:

* **theodore**, que cobre Thomson MO5, MO6 e TO7 até TO9+
* **atari800**, que cobre todos os Atari 8bits, desde a primeira série 800, até o XE, através do XL.
* **vice**, que agora emula C64, PET, Vic20, CBM2,...
* **hatari**, que emula do primeiro 520ST ao último Falcons
* e ainda mais...


>**Lembrete:**  
>Sobrecarga de diretório:**`/caminho/para/suas/roms/.retroarch.cfg`**  
>Sobrecarga de Rom:**`/caminho/para/suas/roms/arquivo.zip.retroarch.cfg`**
{.is-warning}

​

#### Exemplo 1: configurar subsistemas Thomson <a id="exemple-1-configurer-des-sous-systemes-thomson"></a>

Os Thomsons, computadores franceses de 8 bits dos anos 80, foram divididos em 2 séries:

* Os MOs, que produziram o primeiro MO5, depois o MO6 com seu teclado mecânico e toca-fitas integrado
* O TO, que deu os primeiros TO7 e TO7-70, depois o TO8 e TO8D, com unidades de disquete, e as séries TO9 e TO9 +, computadores com aparências mais profissionais

Os jogos MO e TO não são todos compatíveis. Dentro da mesma série, há compatibilidade com versões anteriores: Um MO6 irá \(em geral\) rodar os jogos do MO5. Claro, vamos tentar emular cada jogo com a máquina mais próxima da máquina para a qual foi originalmente projetado, a fim de evitar problemas e maximizar as chances de ter uma emulação perfeita.

Se pegarmos os pacotes TOSEC \([http://www.tosec.org](http://www.tosec.org)\), os jogos Thomson foram divididos em 4 subsistemas:

* MO5
* MO6
* TO7 \(TO7-70\)
* TO8, TO8D, TO9 e TO9+

Portanto, criaremos uma árvore semelhante:

`recalbox/share/roms/thomson/  
 ├── MO5  
 ├── MO6  
 ├── TO7  
 └── TO8,TO8D,TO9,TO9+`

Na raiz do sistema, vamos colocar um arquivo de sobrecarga de núcleo, para forçar algumas opções interessantes para todos:

```text
/recalbox/share/roms/thomson/.core.cfg
theodore_rom = "Auto"
theodore_autorun = "enabled"
theodore_floppy_write_protect = "enabled"
theodore_tape_write_protect = "enabled"
```

Se adicionarmos jogos à raiz ou a outra pasta, pedimos ao emulador para tentar encontrar a melhor máquina \(com base no nome do arquivo\). Também protegemos os arquivos roms por padrão e ativamos a mecânica de execução automática, que é útil quando não conhecemos realmente as máquinas originais.

Então, em cada subpasta, adicionaremos uma sobrecarga na chave `theodore_rom` que determina a máquina.

```text
/recalbox/share/roms/thomson/MO5/.core.cfg
theodore_rom = "MO5"
```

```text
/recalbox/share/thomson/MO6/.core.cfg
theodore_rom = "MO6"
```

```text
/recalbox/share/thomson/TO7/.core.cfg
theodore_rom = "TO7"
```

```text
/recalbox/share/thomson/TO8,TO8D,TO9,TO9+.core.cfg
theodore_rom = "TO9+"
```

Para a última série, a máquina mais poderosa foi selecionada: o TO9+


>Acabou! Agora você tem 4 subsistemas Thomson. O emulador não está mais no modo automático e o risco de escolher o sistema errado ou o sistema padrão desaparece.
>
>Claro, o núcleo do Theodore pode às vezes "detectar automaticamente" a máquina, mas este não é o caso com outros núcleos que precisam ter o subsistema correto na inicialização.
{.is-success}

## Sobrecarregar a aparência das pastas <a id="sobrecarregar-a-aparencia-das-pastas"></a>

Para aperfeiçoar as possibilidades oferecidas pela definição de subsistemas, seja sobrecarregando a configuração do Recalbox para **MAME**, por exemplo, ou sobrecarregando o núcleo **Theodore** para aproveitar ao máximo as máquinas TO e MO da época, adicionamos a possibilidade para sobrecarregar a imagem e a descrição de uma pasta.

Isso permite, por exemplo, ter em uma pasta, a foto e a descrição da máquina cujas roms estão nesse diretório.

Tudo que você precisa fazer é adicionar pelo menos um arquivo de imagem no formato **PNG**, e nomeado `.pasta.imagem.png` na pasta onde você deseja sobrecarregar a imagem em EmulationStation.  
A resolução não importa, mas lembre-se de que uma resolução idêntica ou semelhante às suas imagens de _scrappe_ ainda é recomendada.

Opcionalmente, você pode adicionar uma descrição de texto, que deslizará sob a imagem, exatamente como nos jogos com _scrappe_.  
O arquivo deve ser um arquivo de texto simples, denominado`.pasta.descrição.txt`


>**Lembrete:**  
>Sobrecarga de diretório:**`/caminho/para/suas/roms/.retroarch.cfg`**  
>Sobrecarga de Rom:**`/caminho/para/suas/roms/arquivo.zip.retroarch.cfg`**
{.is-warning}

​

### Exemplo 1: do MO5 ao TO9 <a id="exemplo-1-do-mo-5-ao-to9"></a>

Vamos pegar a pasta **thomson** usado acima, que dividimos em 4 subsistemas como o **TOSEC** fez.

`/recalbox/share/roms/thomson/  
 ├── .núcleo.cfg  
 ├── gamelist.xml  
 ├── media  
 │ ├── box3d  
 │ ├── images  
 │ └── videos  
 ├── MO5  
 │ ├── .núcleo.cfg  
 │ ├── .pasta.descrição.txt  
 │ ├── .pasta.imagem.png  
 │ ├── [FD]  
 │ ├── [K7]  
 │ ├── [M5]  
 │ ├── [QD]  
 │ ├── [SAP]  
 │ └── [WAV]  
 ├── MO6  
 │ ├── .núcleo.cfg  
 │ ├── .pasta.descrição.txt  
 │ ├── .pasta.imagem.png  
 │ └── [K7]  
 ├── TO7  
 │ ├── .núcleo.cfg  
 │ ├── .pasta.descrição.txt  
 │ ├── .pasta.imagem.png  
 │ ├── [K7]  
 │ └── [M7]  
 └── TO8, TO8D, TO9, TO9+  
   ├── .núcleo.cfg  
   ├── .pasta.imagem.png  
   ├── .pasta.descrição.txt  
   ├── [FD]  
   ├── [K7]  
   ├── [QD]  
   └── [SAP]`

​

O arquivo `.pasta.imagem.png` na pasta /recalbox/share/roms/thomson contém uma imagem da máquina:

![Foto do MO5](https://gblobscdn.gitbook.com/assets%2F-LdKWTKrrUvJVmGP83hw%2F-Lo9zc7UGOw_EPL05mCC%2F-LoA3eJn4UNDXo7oJhJe%2F.folder.picture.png?alt=media&token=2366e182-a0a8-4cf1-a7f0-b1076bfdb8d1)



​

E o arquivo `.pasta.descrição.txt` contém:

```text
/recalbox/share/roms/thomson/MO5/.pasta.descrição.txt
Brand:    - Thomson (France)
CPU:    - Motorola 6809E running at 1 MHz
RAM:    - 48Kb (extensible)
ROM:    - 16Kb
Graphics:
    - Text mode : 40 columns x 25 lines
    - Graphic mode: 320 x 200, 16 colors (proximity constraint)
Sound:
    - 1bit generator (6bit DAC module extention possible)
Input devices:
    - 57 keys integrated keyboard
    - Optical pen
    - Joysticks
Interfaces:
    - External power supply
    - DIN Connector (optical pen)
    - DIN Connector (tape drive)
    - Peritel (RGB)
    - Extension port
Software:
    - BASIC 1.0 Integrated
Standard devices:
    - Cartridge port (Mémo5)
    - External tape drive (MO5 specific model)
    - External disk drive
Dimensions:
    - 51 x 291 x 190 mm
Weight:
   - 1.1 kg
Released:
   - 1984
```

​

E aqui está o resultado no EmulationStation:

![EmulationStation](https://gblobscdn.gitbook.com/assets%2F-LdKWTKrrUvJVmGP83hw%2F-Lo9zc7UGOw_EPL05mCC%2F-LoA8iKMCZj3QWLA2UNk%2FCapture%20du%202019-09-07%2011-52-59.png?alt=media&token=bcc9014a-8699-4fa2-9aa0-0f46aaa4bc6b)



### Exemplo 2: MAME <a id="exemplo-2-mame"></a>

Da mesma forma, no primeiro exemplo que mostra como ter várias versões do **MAME** na pasta MAME, poderíamos imaginar ter um belo logotipo MAME 2003 Plus e MAME 2010, seguido de um pequeno texto que informa o número de jogos, e a versão do romset MAME correspondente.

​

Um pequeno logotipo:

![](https://gblobscdn.gitbook.com/assets%2F-LdKWTKrrUvJVmGP83hw%2F-LoA8tUjoraIL5G-TUFl%2F-LoABzgL-dUQHM3ibkku%2F.folder.picture.png?alt=media&token=9627787d-fc60-4418-a61b-57c4a20fb7f7)

/recalbox/share/roms/mame/MAME2003Plus/.pasta.descrição.txt

​

Um pequeno texto:

```text
/recalbox/share/roms/mame/MAME2003Plus/.pasta.descrição.txt
MAME 2003 Plus est une version améliorée de MAME2003, avec énormement de correction de bug et des centaines de nouveaux jeux.​

RomSet Special basé sur le romset MAME 0.78​

4859 jeux au total!
```

​

E aqui está o resultado:

![](https://gblobscdn.gitbook.com/assets%2F-LdKWTKrrUvJVmGP83hw%2F-LoA8tUjoraIL5G-TUFl%2F-LoAECkWbLykI_YkSAYZ%2FSans%20titre.png?alt=media&token=6f61b085-6921-465e-801e-04913b229a86)

## Emuladores "Autônomos" \("_Standalone_"\) <a id="emuladores-autonomos-standalone"></a>

Atualmente, não podemos substituir a configuração de emuladores autônomos, exceto parcialmente aqueles do **Amiberry**, o emulador Amiga para ARM.

Não há planos para adicionar essas sobrecargas, pois elas exigem códigos e testes especiais. Também não é necessariamente viável para todos os emuladores, mas em todos os casos, exigirá mais ou menos tempo.

No entanto, dependendo das solicitações e de sua relevância, possivelmente podemos ver caso a caso.

