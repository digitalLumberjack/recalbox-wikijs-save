---
title: Arcade Simples no Recalbox
---

# Arcade Simples no Recalbox

## Introdução \(6.0-DragonBlaze\) <a id="introducao-6-0-dragonblaze"></a>

​O Arcade sempre foi a emulação mais complicada por causa de sua natureza: as máquinas Arcade nem todas usam o mesmo hardware e, portanto, devem ser emuladas independentemente. Imagine que você queira jogar 5 jogos de arcade diferentes, talvez precise usar cinco emuladores diferentes. Já se você quiser jogar cinco jogos SNES, poderá usar um só, o mesmo emulador SNES para todos os 5 jogos.

E é para isso que o MAME foi inventado: Mame pode ser comparado a um meta-emulador, reunindo os diferentes emuladores de cada máquina de arcade em um único sistema, que permite ao usuário jogar facilmente jogos de arcade sem nenhum conhecimento do hardware da máquina de arcade que os executa.

Isso não é pouca coisa, e é por isso que o MAME é tão complicado de usar.

​

## Princípios gerais de emulação MAME​ <a id="principios-gerais-de-emulacao-mame"></a>

Existem apenas dois princípios gerais a serem entendidos para usar facilmente o MAME em seu Recalbox: romsets e arquivos de BIOS/driver

​

### Os romsets <a id="os-romsets"></a>

Um romset é o conjunto de diferentes roms de jogo emulados por uma determinada versão do MAME. Um romset contém roms pai que são roms contendo a versão 'principal' de um jogo e roms clone que são versões 'alternativas' das roms pai. Como você pode imaginar, na maioria dos casos, você pode se livrar das roms clones e usar apenas os roms principais \(chamados de 'pais' nos arcade\).

A maior parte do código usado para executar essas ROMs de jogos está incluída no executável MAME. Infelizmente, isso significa que existe uma relação forte e interdependente entre uma versão do MAME e as versões das ROMs do jogo: quando uma nova versão do MAME é lançada, às vezes é necessário que os desenvolvedores atualizem as ROMs do jogos para que funcionem perfeitamente com a nova versão do emulador.

Para simplificar: se você estiver usando uma versão específica do emulador MAME, por exemplo a versão 0.78, você deve pegar e usar a versão 0.78 do romset. Alguns jogos de outro romset podem funcionar com a sua versão 0.78 do MAME, **mas a única maneira de ter certeza absoluta de que a grande maioria dos jogos funcionará, é sempre usar uma versão do MAME com o romset da mesma versão**.

Para versões recentes do MAME \(como a usada por fba\_libretro\) existem cada vez menos roms de jogo atualizadas e às vezes é possível usar um romset mais antigo e ainda ter a maioria dos jogos jogável.

​

## ​BIOS / Drivers <a id="bios-drivers"></a>

Algumas ROMs de jogos em um romset podem exigir arquivos BIOS, sendo o caso mais popular dos jogos neogeo.

Vamos usá-los como exemplo: Se você quiser usar jogos neogeo, terá que copiar o arquivo BIOS/driver \(neste caso neogeo.zip\) na mesma pasta da ROM do jogo. Isso é tudo!

Claro, se você usar subpastas para seus jogos \(para separar por gênero ou hardware, por exemplo\), você terá que copiar os arquivos BIOS para cada pasta contendo jogos que os requeiram. **Como esses arquivos BIOS são bastante pequenos em tamanho, é mais fácil copiá-los todos para cada uma das suas subpastas.**

Onde encontrar esses arquivos BIOS, você me diz? Bem, é muito simples: em seu romset!

Se um jogo não iniciar e retornar diretamente para a tela da Emulationstation, tente encontrar o BIOS correspondente e copie-o para a pasta da ROM do jogo.

​

## A Emulação Arcade no Recalbox​ <a id="a-emulacao-arcade-no-recalbox"></a>

Como a página [Arcade Avançado no Recalbox](arcade-avancado-no-recalbox.md) explica, existem vários emuladores de arcade incluídos no Recalbox.

Precisamos apenas de dois deles para executar a maioria dos jogos de arcade em seu Raspberry Pi.

Esses dois sistemas são:

* Mame
  * _mame/romset versão :_ 0.78
  * _pasta das roms :_ mame
* FBA\_libretro
  * FBA é uma versão alternativa do MAME \(emulando menos máquinas de arcade\), mas funciona de acordo com os mesmos princípios que acabei de explicar.
  * _mame/fba romset versão :_ 0.189 corresponde ao romset FBA 0.2.97.44
  * _pasta das roms:_ fba\_libretro

Alguns jogos funcionam apenas no Recalbox com Mame e outros com FBA\_libretro._**​**_

## Vamos configurar seu Recalbox! <a id="vamos-configurar-seu-recalbox"></a>

Em primeiro lugar, baixe os romsets completos para os dois emuladores:

* romset 0,78 para mame
* romset 0.189 \(ou romset FBA 0.2.97.44\) para fba\_libretro. Se você não conseguir encontrar o romset na versão certa, uma versão superior pode ser baixada, mas será necessário torná-la compatível seguindo as etapas [deste tutorial.](https://recalbox.gitbook.io/tutorials/v/portugues/utilitarios/gerenciamento-de-rom/tutorial-clrmamepro-como-verificar-as-versoes-das-roms)​

Você pode preferir fazer o download de cada jogo um de cada vez, pois os romsets completos são muito grandes, mas raramente é fácil encontrar roms individuais e ter certeza de que estão na versão correta. Romsets completos são a única maneira segura de evitar dores de cabeça!

Você está a poucos minutos de jogar excelentes jogos de arcade em seu Recalbox.

​

### Cópia de BIOS/drivers <a id="copia-de-bios-drivers"></a>

Em primeiro lugar, vamos copiar os arquivos BIOS/drivers de nossos romsets, ao contrário das BIOS de outros consoles, elas não são copiadas para o pasta BIOS, mas para a pasta das roms:

* Consiga os seguintes arquivos do romset 0.78 do MAME e copie-os para a pasta das roms de mame, a lista completa dos arquivos é: _acpsx.zip, cpzn1.zip, cpzn2.zip, cvs.zip, decocass.zip, konamigx.zip, megaplay.zip, megatech.zip, neogeo.zip, nss.zip, pgm.zip, playch10.zip, skns.zip, stvbios.zip, taitofx1.zip, tps.zip_
* Consiga os seguintes arquivos do romset 0.189 \(FBA 0.2.97.44\) do fba\_libretro e copie-os para a pasta das roms de fba\_libretro, apenas dois deles são necessários: _neogeo.zip_ e _pgm.zip_

## _​_Copiando jogos <a id="copiando-jogos"></a>

* Mame Copie a ROM do jogo \(arquivo zip não descompactado\) de seu romset 0.78 para a pasta de roms: mame
* fba\_libretro Copie a rom do jogo \(arquivo zip não descompactado\) de seu romset 0.189 \(FBA 0.2.97.44\) para a pasta de roms: fba\_libretro
* JOGUE! \(ou não\)​

## Dicas adicionais <a id="dicas-adicionais"></a>

* Se você deseja ocultar seus arquivos BIOS no EmulationStation, oculte-os usando o menu select
* Lembre-se, se você quiser usar subpastas dentro da pasta de roms, faça uma cópia dos arquivos BIOS/drivers em cada uma das subpastas e mova seus jogos para essas subpastas.
* Leia [Arcade Avançado no Recalbox](https://recalbox.gitbook.io/tutorials/v/portugues/jogos/arcade/arcade-avancado-no-recalbox)

