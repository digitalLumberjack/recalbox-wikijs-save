---
title: Arcade Avançado no Recalbox
---

# Arcade Avançado no Recalbox

Esta página é uma continuação de [Arcade Simples no Recalbox](arcade-simples-no-recalbox.md)​

## ​Tipo de romset: non-merged, split e merged​ <a id="tipo-de-romset-non-merged-split-e-merged"></a>

Existem três tipos de romset:

* em **split \(dividido\)**, os arquivos compartilhados entre pais e clones são apenas no zip pai. para usar um clone, você deve, portanto, ter roms pai e clone
* em **non-merged \(não-mesclado\)**, todos os arquivos necessários para o clone estão no zip deste
* em **merged \(mesclado\)**, pai e clone são mesclados no mesmo zip

O mais interessante é, portanto, o RomSet **non-merged \(não-mesclado\)​**

## ClrMamePro <a id="clrmamepro"></a>

Para verificar a compatibilidade de seus jogos, você pode usar [clrmamepro e o tutorial correspondente.](https://recalbox.gitbook.io/tutorials/v/portugues/utilitarios/gerenciamento-de-rom/tutorial-clrmamepro)​

## Todos os emuladores de arcade no Recalbox <a id="todos-os-emuladores-de-arcade-no-recalbox"></a>

> Agora você pode usar até quatro emuladores de arcade diferentes na versão mais recente do Recalbox \(mame, imame4all, piFba, fbNeo\) e o emulador Neogeo "_fake_". Você pode escolher o núcleo que deseja usar em [**Recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)**​**

## **piFBA** <a id="pifba"></a>

_Recalbox todas as versões_

piFBA é o mais otimizado dos emuladores FBA no RecalBox, mas é compatível com muito menos jogos do que fba\_libretro. Use apenas se você tiver um pi0 / 1 ou se quiser melhorar o desempenho de um determinado jogo que apresente problemas de desempenho no fba\_libretro

* Baseado no RomSet MAME: **FBA 0.2.96.71** \(Abril de 2007\) 'com base no conjunto MAME 0,114'
* Peso: 3.62GB
* Romsets emulados: 684 \(nenhum clone neste conjunto\)
* Lista de compatibilidade: [/recalbox/share/roms/fba/clrmamepro/piFBA\_gamelist.txt](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba/clrmamepro/piFBA_gamelist.txt)
* Arquivo Dat : [/recalbox/share/roms/fba/clrmamepro/fba\_029671\_od\_release\_10\_working\_roms.dat](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba/clrmamepro/fba_029671_od_release_10_working_roms.dat)

## **Imame4all** <a id="imame-4-all"></a>

_Recalbox todas as versões_

Imame4allé recomendado para jogos antigos que não funcionam no piFBA

* Baseado no RomSet: MAME **0.37b5** \(Julho de 2000\)
* Peso : 1.86GB
* Romsets emulados: 2 270 \(inclui clones, etc...\)
* Conjuntos ativos: 2241/2241
* Pais: 560/560
* Clones: 990/990
* Outros: 690/690
* BIOS: 1/1
* Lista de compatibilidade: [/recalbox/board/recalbox/share/roms/mame/clrmamepro/imame4all\_gamelist.txt](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/imame4all/imame4all_gamelist.txt)
* Arquivo Dat : [/recalbox/share/roms/mame/clrmamepro/imame4all.dat](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/imame4all/imame4all.dat)


>_Se um jogo não funcionar no RomSet 0.37b5, você pode tentar o mesmo jogo do RomSet MAME 0.81_
{.is-warning}

## **Libretro-mame2003** <a id="libretro-mame2003"></a>

_Recalbox v3.3.0-beta-11_

libretro-mame2003 é um emulador mais recente do que imame4all. Muitos outros jogos são funcionais, mas este emulador está disponível apenas em RPI2 e RPI3.

* Baseado no RomSet: MAME 0.78 \(Dezembro de 2003\)
* Peso: 1.86GB
* Romsets emulados: 4 705 \(incluindo clones, etc...\)
* Conjuntos ativos: 4705/4705
* Pais: 1042/1042
* Clones: 2039/2039
* Outros: 1624/1624
* BIOS: 1/1
* Arquivo Dat:  [/recalbox/recalbox-os/master/wiki/dat/mame2003.dat](https://raw.githubusercontent.com/recalbox/recalbox-buildroot/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/mame2003/mame2003.dat)

## **Libretro-mame2003-plus** <a id="libretro-mame-2003-plus"></a>

_Recalbox_ _4.1_

MAME 2003-Plus \(também conhecido como MAME 2003+ ou mame2003-plus\) é um núcleo de emulador de sistema de arcade libretro que enfatiza o alto desempenho e ampla compatibilidade com dispositivos móveis, computadores de placa única, sistemas integrados e outras plataformas semelhantes.

Para tirar proveito do desempenho inferior e dos requisitos de hardware de uma arquitetura MAME anterior, o MAME 2003-Plus começou com o código base MAME 2003, derivado do mame 0.78. Com base nisso, os contribuintes do MAME 2003-Plus retro-portaram suporte para várias centenas de jogos adicionais, bem como outros recursos não presentes originalmente no MAME 0.78.

Versão MAME: 0.78-0.188 \(MAME 0.78 como linha de base com outras ROMs baseadas em conjuntos de ROMs MAME posteriores\)

* Conjuntos ativos: 4850
* BIOS: 15
* CHDs: 30
* Amostras: 66 + 6 "Amostras de Trilha Sonora" Opcionais
* Arquivo Dat: [MAME 2003-Plus XML DAT File](https://github.com/libretro/mame2003-plus-libretro/blob/master/metadata/mame2003-plus.xml)

## **Libretro-mame2010** <a id="libretro-mame2010"></a>

_Recalbox_ 2018.02.x

* Baseado no RomSet: MAME 0.139
* Conjuntos ativos: 8782
* BIOS: 67
* CHDs: 406
* Amostras: 70 \(4 amostras ausentes\)
* Arquivo Dat:

## Libretro-mame2015 <a id="libretro-mame2015"></a>

_Recalbox 6.0_

* Baseado no RomSet: MAME 0.160
* Conjuntos ativos:
* BIOS:
* CHDs:
* Amostras:
* Arquivo Dat:

## **AdvanceMame 3.x** <a id="advancemame-3-x"></a>

_Recalbox 4.1_

Emulador autônomo, inicialmente adicionado para configuração de telas CRT. É baseado no romset mame 0.106.

* Baseado no RomSet: MAME 0.106
* Conjuntos ativos: 6166
* BIOS: 26
* CHDs: 86
* Amostras: 64 \(3 amostras ausentes\)
* Arquivo Dat:

## **Libretro FBA** <a id="libretro-fba"></a>

_Recalbox 6.0_

Libretro FBA é um núcleo de libretro baseado em FBA, é o único a rodar alguns sistemas \(CPS3 por exemplo\), mas, é mais lento que o piFBA

* Baseado no RomSet FBA: RomSet FBA 0.2.97.44 que é baseado no conjunto MAME 0.189
* Arquivo Dat: [fba 0.2.97.44 dat](https://github.com/libretro/fbalpha/tree/master/dats)




>Você pode encontrar o _changelog_ \(registo de alterações\) FBA no seguinte local: [fbalpha changelog](https://www.fbalpha.com/view/240/)
{.is-info}

## **Libretro Flycast** <a id="libretro-flycast"></a>

Libretro Flycast é um núcleo libretro baseado no Sega Dreamcast disponível apenas na arquitetura x86\_64 e x86. Ele é capaz de executar os seguintes sistemas Sega Arcade:

* Naomi M1 _cartucho suportado_
* Naomi M2 _cartucho suportado_
* Naomi M4 _cartucho suportado_
* Naomi GD-ROMs
* Sammy Atomiswave.

_Recalbox \(6.1\)_

* Flycast suporta roms com formato `.bin + .lst`, mas também formato `.zip` \(para melhor compatibilidade, use o ROMSET MAME 0.135 mínimo ou o mais recente possível com esses arquivos CHD!\)
* O Flycast requer estas bios :

| **BIOS** | **MD5** |
| :---: | :---: |
| bios/dc/naomi.zip | eb4099aeb42ef089cfe94f8fe95e51f6 |
| bios/dc/awbios.zip | 0ec5ae5b5a5c4959fa8b43fcf8687f7c |
| **BIOS**   | **OPCIONAL** |
| bios/dc/f355dlx.zip | 5e83867c751f692a000afdf658dc181f |
| bios/dc/f355bios.zip | f126d318f135f38ee377fef2acf08d7e |
| bios/dc/airlbios.zip | 3f348c88af99a40fbd11fa435f28c69d |
| bios/dc/hod2bios.zip | 9c755171b222fb1f4e1439d5b709dbf1 |

* RomSet mínimo: MAME 0.135
* Conjuntos ativos:
* BIOS:
* CHDs:
* Arquivo Dat:

​

* Os jogos de **Naomi** _**cartucho suportado**_ _devem estar no formato_ `.zip` ou `.bin + .lst`
* ​Os jogos de **Naomi GD-ROMS** _devem estar no formato_ `.bin + .lst` ou no format `.zip + .chd` Exemple para o jogo **`cfield.zip`** : `/recalbox/share/roms/naomi/cfield/...`

  `/recalbox/share/roms/naomi/cfield/gdl-0025.chd`

  `/recalbox/share/roms/naomi/cfield/cfield.zip`

* Os jogos **Sammy Atomiswave** _devem estar no formato_ `.zip` _ou_ _`.bin + .lst`_


>Para uma melhor compatibilidade, o formato `.zip` de roms extraídas de um romset MAME é recomendado!
{.is-danger}

* Você pode encontrar o Github do Flycast no seguinte local: [Flycast Github](https://github.com/libretro/flycast)​
* Recalbox separa plataformas **Naomi** e **Sammy Atomiswave**

  Você encontrará o arquivo `.dat` em seu Recalbox neste local:`/share/bios/dc/` para verificar e classificar suas roms com clrmamepro

## **Neogeo \(**_**fake**_**\)** <a id="neogeo-fake"></a>

O sistema Neogeo não é um emulador em si. Ele permite que os jogos neogeo sejam isolados separadamente de outros jogos de arcade, eles então aparecerão como um sistema dedicado no EmulationStation. Por padrão, ele usa FBA libretro. Você pode usar o seguinte arquivo dat para criar e verificar seu romset: [FBA 0.2.97.44 Neogeo Somente](https://github.com/libretro/fbalpha/blob/master/dats/FB%20Alpha%20%28ClrMame%20Pro%20XML%2C%20Arcade%20only%29.dat)​

