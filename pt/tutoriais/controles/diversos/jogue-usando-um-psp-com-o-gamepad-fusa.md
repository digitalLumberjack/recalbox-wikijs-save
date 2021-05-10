---
title: Jogue usando um PSP com o Gamepad FuSa
---

# Jogue usando um PSP com o Gamepad FuSa

​

Com firmware customizado como o **pro CFW** e o **ME CFW**, mas também graças à flexibilidade natural do PSP e do hardware semi-aberto, com a ajuda do controle FuSa \(um aplicativo caseiro para PSP\), você consegue um dos melhores controles SNES para o seu Raspberry Pi.

## O que nós precisamos?​ <a id="o-que-nos-precisamos"></a>

* Um PSP modelo 1xxx 2xxx ou 3xxx \(modelos 2xxx e 3xxx de preferência\)
* Um cartão de memória Pro Duo de 1 GB ou superior
* Um cabo mini USB para USB A
* Um Firmware personalizado \(Pro ou ME / LME\)
* Um PC ou seu Pi para transferir os arquivos via SAMBA
* O aplicativo do [controle FuSa](https://foosa.do.am/load/fusa_gamepad_version_03/3-1-0-33)​

## Para começar: <a id="para-comecar"></a>

Baixe o zip do gamepad FuSa, depois ligue seu PSP com seu cartão de memória em seu console, e, se for um modelo 3000 ou superior, execute seu CFW \(modelos antigos não precisam iniciá-lo porque esses modelos começam já com o CFW carregado\), conecte o cabo USB ao PSP e ao PC, descompacte o zip em`/PSP/GAMES/` e desconecte-o do PC de forma segura.

Agora inicie o aplicativo e conecte-o ao seu Pi, a tela do PSP deve estar desligada, mas o LED de energia normalmente deve permanecer ligado.

## Disposição recomendada dos botões:​ <a id="disposicao-recomendada-dos-botoes"></a>

Para uma experiência perfeita, dentro e fora do Emulationstation, incluindo Kodi e todos os núcleos RetroArch e, porque todos os gamepads Playstation no Japão usam o mesmo layout de um controle SNES, mas, com diferentes símbolos, sugiro usar esta configuração de botão, além de minha pequena sugestão para botões de volume e botão home no Kodi.

![Disposi&#xE7;&#xE3;o dos Bot&#xF5;es no PSP](https://cloud.githubusercontent.com/assets/10035308/16599632/7f34c9ec-42c0-11e6-8988-0b2d6e795d10.png)

## Leve em consideração:​ <a id="leve-em-consideracao"></a>

* PSP Street não é compatível.
* Se seu PSP estiver em boas condições, é muito melhor do que um controle genérico ou um joystick 360. Os botões são muito responsivos e o D-Pad é ótimo para jogos retro.
* O Pi NÃO é capaz de carregar totalmente um PSP.
* Os botões de volume não funcionam no Emulationstation ou RetroArch
* Você pode acessar uma configuração mais detalhada nos arquivos .ini do FuSa.

