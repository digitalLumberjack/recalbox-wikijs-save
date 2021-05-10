---
title: Neogeo Unibios \(Arcade\)
---

# Neogeo Unibios \(Arcade\)

## O que a Unibios permite: <a id="o-que-a-unibios-permite"></a>

* Alterar região \(Europa / EUA / Japão\) e modo \(AES / MVS\)
* Acessar o "soft dip" para modificar a dificuldade/vida/tempo, etc... do jogo
* Usar o banco de dados de código de trapaças \(_cheats\)_
* Acessar o jukebox ... e muito mais!

## Como instalar no PiFBA: <a id="como-instalar-no-pifba"></a>

1. Baixe aqui \(versão 4.0\): [http://unibios.free.fr/download.html](http://unibios.free.fr/download.html)  
2.  Extraia o arquivo baixado e renomeie o arquivo `uni-bios.rom` para `asia-s3.rom`
3. Abra seu próprio arquivo `neogeo.zip`, já deve haver um arquivo`asia-s3.rom` dentro ; faça um backup, se necessário.
4. Substitua o arquivo`asia-s3.rom` já presente no `neogeo.zip` pelo recém-renomeado.
5. Carregue o novo `neogeo.zip` na pasta compartilhada `/bios` e `/finalburnalpha` do Recalbox.

## Como instalar no Fba\_libretro: <a id="como-instalar-no-fba_libretro"></a>

Inicie um jogo e vá para o menu Retroarch \( **Hotkey + B** \)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUck9GGWWKOtN1H8A-%2Fscreenshot-2020-07-05T15-04-14-338Z.png?alt=media&token=ed2d90d3-2798-42d0-8a67-365852711411)

Entre em:

Menu Rápido &gt; "Opções"

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUczWu7rY7cUbRAwW7%2Fscreenshot-2020-07-05T15-04-24-712Z.png?alt=media&token=c1af0b4f-9110-4428-96a2-d33145b63378)

e mude o "Modo Neo-Geo"  
De:  
"Usar bios especificado na chave dips BIOS abaixo"

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUdWNCiW42gDnd9NBX%2Fscreenshot-2020-07-05T15-04-44-781Z.png?alt=media&token=49b940fe-5bc4-4f26-bd0d-21a4ed1d4727)

Para:  
"Usar bios UNIBIOS"

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUdjU-KKE-LxRtB4yM%2Fscreenshot-2020-07-05T15-16-30-049Z.png?alt=media&token=5c6ee3b0-17f9-43f9-aa21-d848d9169a4d)

Em seguida, vá para "BIOS" e mude de "MVS Asia 6.1" para "Universe BIOS 4.0" ou "Universe BIOS 3.3"

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUe6ypsXo-wpizDUjX%2Fscreenshot-2020-07-05T15-05-04-261Z.png?alt=media&token=e4397547-295b-4b11-852e-e03da3f098b8)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MBUbGu0KFraUCpPWqHY%2F-MBUeD77bd-uem-_3pHh%2Fscreenshot-2020-07-05T15-05-14-178Z.png?alt=media&token=88dbcd52-185a-4194-903a-2b53c4e7b080)

## Utilização: <a id="utilizacao"></a>

### Para o Pifba <a id="para-o-pifba"></a>

* Inicie qualquer jogo neogeo, então você verá a nova tela de boot do UNIVERSE BIOS v4.0.
* Durante esta "tela de inicialização, pressione e segure `BXY` para alterar a região/modo ou pressione e segure `ABX`para ativar o menu "dip switch"
* Para acessar o menu dentro do jogo, você deve pressionar e segurar `BXY+START`

### Para o fba\_libretro <a id="para-o-fba_libretro"></a>

* Inicie qualquer jogo neogeo, você verá a nova tela de inicialização do UNIVERSE BIOS
* Durante esta "tela de inicialização, pressione e segure `CBA (XBA)` para alterar a região / modo - Pressione `C` para sair
* Para acessar o menu dentro do jogo, você deve pressionar e segurar simultaneamente `CBA (XBA) + START`

Para acessar o menu« dip switch » do fba\_libretro ao iniciar a tela de inicialização UNIVERSE BIOS, segure `A+X+Y`

### ​Configurando o soft dip : <a id="configurando-o-soft-dip"></a>

Verifique este Tutorial: [Ativar "Modo de configuração: configuração de exibição"](ativar-modo-de-configuracao-configuracao-de-exibicao.md)​

## BIOS <a id="bios"></a>

O Neo Geo requer um arquivo BIOS chamado neogeo.zip. Precisa ser colocado juntos com suas ROMs de Neo geo, onde elas estiverem, que pode ser:

```text
/recalbox/share/roms/neogeo
ou
/recalbox/share/roms/fba_libreto
ou
/recalbox/share/roms/fba
```

Aqui está o conteúdo de um arquivo BIOS neogeo.zip comprovadamente funcional:

```text
000-lo.lo
asia-s3.rom
japan-j3.bin
neo-geo.rom
ng-lo.rom
ng-sfix.rom
ng-sm1.rom
sfix.sfix
sm1.sm1
sp-1v1_3db8c.bin
sp-45.sp1
sp-e.sp1
sp-j2.sp1
sp-s.sp1
sp-s2.sp1
sp-u2.sp1
sp1.jipan.1024
uni-bios_1_0.rom
uni-bios_1_1.rom
uni-bios_1_2.rom
uni-bios_1_2o.rom
uni-bios_1_3.rom
uni-bios_2_0.rom
uni-bios_2_1.rom
uni-bios_2_2.rom
uni-bios_2_3.rom
uni-bios_2_3o.rom
uni-bios_3_0.rom
uni-bios_3_1.rom
vs-bios.rom
```

