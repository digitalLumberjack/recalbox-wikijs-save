---
title: Tutorial Clrmamepro - Como verificar as versões das roms
---

# Tutorial Clrmamepro - Como verificar as versões das roms

piFBA, libretro\_fba, mame 2003, mame 2003-plus, mame 2010 e iMame4all, todos aceitam versões diferentes de roms. Para descobrir se suas ROMs são compatíveis, você pode usar o clrmamepro.

Este software utilizará um arquivo .dat que contém as informações das ROMs para uma determinada versão e verificará se as suas ROMs correspondem a elas. Ele usa CRC em todos os arquivos nos arquivos .zip e informa quais arquivos estão ausentes ou não são correspondentes.

Primeiro, obtenha o arquivo .dat correspondente ao emulador que você deseja usar:

* piFBA: [https://raw.githubusercontent.com/digitalLumberjack/recalbox-os/master/wiki/dat/fba\_029671\_od\_release\_10\_working\_roms.dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-os/master/wiki/dat/fba_029671_od_release_10_working_roms.dat)
* iMame4All: [https://github.com/libretro/mame2000-libretro/blob/master/metadata/MAME 0.37b5 XML.dat](https://github.com/libretro/mame2000-libretro/blob/master/metadata/MAME%200.37b5%20XML.dat)
* Fba 0.2.97.44 : [https://github.com/libretro/fbalpha/blob/master/dats/FB Alpha \(ClrMame Pro XML%2C Arcade only\).dat](https://github.com/libretro/fbalpha/blob/master/dats/FB%20Alpha%20%28ClrMame%20Pro%20XML%2C%20Arcade%20only%29.dat)
* Mame 2003: [https://github.com/libretro/mame2003-libretro/blob/master/metadata/mame2003.xml](https://github.com/libretro/mame2003-libretro/blob/master/metadata/mame2003.xml) 
* Mame 2003-plus: [https://github.com/libretro/mame2003-plus-libretro/blob/master/metadata/mame2003-plus.xml](https://github.com/libretro/mame2003-plus-libretro/blob/master/metadata/mame2003-plus.xml)
* Mame 2010: [https://github.com/libretro/mame2010-libretro/blob/master/metadata/mame2010.xml](https://github.com/libretro/mame2010-libretro/blob/master/metadata/mame2010.xml)

Baixe o ClrmamePro :

* Usuários do Windows : [http://mamedev.emulab.it/clrmamepro/](http://mamedev.emulab.it/clrmamepro/) \(Funciona no wine para usuários linux\)
* Usuários do MacOS X: [http://www.emulab.it/](http://www.emulab.it/), uma versão beta está disponível.

Faça o upload do seu arquivo .dat na seção "**Profiler**".

Vá para Configurações\("**Settings"**\) e defina o "**rom path**" para o seu diretório que contém suas ROMs.

Por fim, use o **Scanner** para verificar seu diretório rom e **verifique os logs** para ver quais arquivos estão faltando.

