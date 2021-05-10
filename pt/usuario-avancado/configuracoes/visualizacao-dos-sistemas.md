---
title: Visualização dos Sistemas
description: >-
  Funcionamento e modificação de exibição dos sistemas. (Recalbox v6.1 e
  superior)
---

# Visualização dos Sistemas

## Funcionamento da exibição <a id="funcionamento-da-exibicao"></a>

A exibição dos sistemas no menu Recalbox é gerenciada pelo arquivo "es\_systems.cfg". Este arquivo está localizado na pasta:

./recalbox/**share\_init**/system/.emulationstation/es\_systems.cfg

Ele contém os nomes dos diferentes sistemas que são suportados pela sua versão do Recalbox. É construído da seguinte forma:

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Panasonic 3DO</fullname>
    <name>3do</name>
    <path>/recalbox/share/roms/3do</path>
    <extension>.iso .ISO .cue .CUE .chd .CHD</extension>
    <command>python /usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc %CONTROLLERSCONFIG% -system %SYSTEM% -rom %ROM% -emulator %EMULATOR% -core %CORE% -ratio %RATIO% %NETPLAY%</command>
    <platform>3do</platform>
    <theme>3do</theme>
    <emulators>
      <emulator name="libretro">
        <cores>
          <core>4do</core>
        </cores>
      </emulator>
    </emulators>
  </system>
  <system>
      [. . .]
  </system>
  [. . .]
</systemList>
```

Os sistemas são exibidos na ordem em que estão listados neste arquivo. Ele também contém a configuração desses sistemas.

## Alterar a ordem de exibição <a id="alterar-a-ordem-de-exibicao"></a>


>**IMPORTANTE:** NÃO SE DEVE MODIFICAR o arquivo "es\_systems.cfg" original \(que está no diretório "share\_init"\). No caso de um problema com as modificações feitas posteriormente, continua sendo a única fonte para fazer o Recalbox funcionar corretamente.
{.is-danger}

A alteração da ordem de exibição deve ser feita apenas a partir do arquivo "es\_systems.cfg" na pasta:


>./recalbox/**share**/system/.emulationstation/es\_systems.cfg
{.is-info}

**Originalmente, este arquivo não existe**. Copie o arquivo original ou crie um novo arquivo. Uma vez criado o novo arquivo, é possível colocar os sistemas na ordem que você deseja. A configuração do sistema ainda será obtida do "es\_systems.cfg" original, mas a ordem do sistema será conforme definido no novo arquivo.

Se um sistema estiver faltando, ou for inserido incorretamente no novo arquivo, a prioridade será dada ao arquivo original. Para o novo arquivo, existem apenas 2 chaves de entrada obrigatórias: "**fullname**" e "**platform**", todas as outras são opcionais. O arquivo deve ser construído, no mínimo, da seguinte forma:

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Nintendo Entertainment System</fullname>
    <platform>nes</platform>
  </system>
  <system>
    <fullname>Family Computer Disk System</fullname>
    <platform>fds</platform>
  </system>
  <system>
    <fullname>Super Nintendo Entertainment System</fullname>
    <platform>snes</platform>
  </system>
  <system>
    <fullname>Satellaview</fullname>
    <platform>satellaview</platform>
  </system> 
    [. . .]
  </system>
  [. . .]
</systemList>
```

## Adicione um sistema "Personalizado" <a id="adicione-um-sistema-personalizado"></a>


>**IMPORTANTE:** NÃO SE DEVE **MODIFICAR** o arquivo "es\_systems.cfg" original \(que está no diretório "share\_init"\). No caso de um problema com as modificações feitas posteriormente, continua sendo a única fonte para fazer o Recalbox funcionar corretamente.
>
>Esta manipulação não permite adicionar um novo emulador ao Recalbox, permite apenas adicionar uma nova entrada do sistema no menu de seleção.
>
>É possível combinar a modificação da ordem dos sistemas e a adição de um ou mais sistemas personalizados.
{.is-danger}

Quanto à modificação da ordem dos sistemas, a adição de um sistema “customizado” deve ser feita apenas a partir do arquivo “es\_systems.cfg” presente no seguinte diretório:


>./recalbox/**share**/system/.emulationstation/es\_systems.cfg
{.is-info}

**Originalmente, este arquivo não existe**. Copie o arquivo original ou crie um novo arquivo. Uma vez que o novo arquivo foi criado, agora é possível adicionar um novo sistema a ele.

Se um sistema for inserido incorretamente no novo arquivo, a prioridade será retornada ao arquivo original. Para o novo arquivo, todas as chaves de entrada são necessárias. Portanto, para criar um novo sistema, a maneira mais fácil é começar a partir de um sistema existente \(e correspondente às ROM que queremos incluir\) e modificar apenas o que for estritamente necessário:  
- _**« fullname »**_ : Usado para fornecer o nome do novo sistema.  
_-_ _**« path »**_ : Usado para indicar a pasta que contém as roms do novo sistema.  
_-_ _**« theme »**_ : Usado para indicar qual tema usar. Você deve primeiro criar este novo tema \(logotipo, plano de fundo, ...\)  
**Todas as outras entradas não devem ser alteradas.**

Aqui está um exemplo de adição de um sistema baseado em SNES para incluir apenas roms traduzidas:

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Super Nintendo Fan Trad</fullname>
    <name>snes</name>
    <path>/recalbox/share/roms/snestrad</path>
    <extension>.smc .sfc .SMC .SFC .mgd .MGD .zip .ZIP .7z .7Z</extension>
    <command>python /usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc %CONTROLLERSCONFIG% -system %SYSTEM% -rom %ROM% -emulator %EMULATOR% -core %CORE% -ratio %RATIO% %NETPLAY%</command>
    <platform>snes</platform>
    <theme>snestrad</theme>
    <emulators>
      <emulator name="libretro">
        <cores>
          <core>snes9x2005</core>
          <core>snes9x2010</core>
          <core>snes9x2002</core>
        </cores>
      </emulator>
    </emulators>
  </system>
</systemList>
```

