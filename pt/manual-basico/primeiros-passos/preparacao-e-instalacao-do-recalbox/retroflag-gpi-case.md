---
title: Carcaça RetroFlag GPi
---

# Carcaça RetroFlag GPi

## Preparação

### Elementos necessários

* 1 Carcaça RetroFlag GPi
* 1 Raspberry Pi Zero W
* 1 Cartão SD
* 1 Adaptador de cartão SD
* 1 Dissipador térmico \(para o seu RPI ZERO W\)
* 3 Pilhas



### As pilhas aconselhadas

* Baterias Duracell Recarregáveis ​​tipo AA 2500 mAh 5 ou 6 horas de autonomia [https://www.amazon.com.br/Duracell-Alcalina-AA-Recarreg%C3%A1vel-Unidades/dp/B07ZVWRJQN/ref=sr\_1\_1?dchild=1&qid=1599086890&refinements=p\_4%3ADuracell&s=electronics&sr=1-1](https://www.amazon.com.br/Duracell-Alcalina-AA-Recarreg%C3%A1vel-Unidades/dp/B07ZVWRJQN/ref=sr_1_1?dchild=1&qid=1599086890&refinements=p_4%3ADuracell&s=electronics&sr=1-1)  
* Panasonic BK-3HCDE/2BE eneloop pro 2500mAh Com 2 Pilhas Ni-MH AA/Mignon/LR6 [https://www.amazon.com.br/Recarreg%C3%A1vel-pequena-BK-3HCDE-2BB-unidades/dp/B075SNKSW6/ref=sr\_1\_fkmr0\_1?\_\_mk\_pt\_BR=%C3%85M%C3%85%C5%BD%C3%95%C3%91&dchild=1&keywords=Panasonic+BK-3HCDE%2F4BE+eneloop+pro+2500mAh+Lot+de+4+piles+Ni-MH+AA%2FMignon%2FLR6&qid=1599087009&sr=8-1-fkmr0](https://www.amazon.com.br/Recarreg%C3%A1vel-pequena-BK-3HCDE-2BB-unidades/dp/B075SNKSW6/ref=sr_1_fkmr0_1?__mk_pt_BR=%C3%85M%C3%85%C5%BD%C3%95%C3%91&dchild=1&keywords=Panasonic+BK-3HCDE%2F4BE+eneloop+pro+2500mAh+Lot+de+4+piles+Ni-MH+AA%2FMignon%2FLR6&qid=1599087009&sr=8-1-fkmr0)

Com uma bateria externa de 10.000mAH, fica perfeito.

## Apresentação da Carcaça Gpi

![](/migration-images/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/image%20%28167%29.png)

![](/migration-images/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/image%20%28315%29.png)

![](/migration-images/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/image-pt-br.png)



## Só gravar a imagem e começar a jogar!

![GPi Case](/migration-images/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/image%20%28202%29.png)

É simples assim! **O Recalbox detecta e instala automaticamente tudo o que é preciso** para fazer funcionar o seu GPi Case.

* Você só precisa gravar a imagem da última versão do Recalbox para Raspberry Pi1/Pi0 em seu cartão SD, inseri-lo no cartucho de seu GPI e ligá-lo!
* Aguarde alguns segundos, então você verá esta imagem na tela:

![Installation image](/migration-images/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/image%20%28197%29.png)

* Aguarde mais alguns segundos \(pode demorar mais com cartões SD de alta capacidade\) antes de o EmulationStation iniciar com sua tela normal:



![EmulationStation is starting...](/migration-images/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/image%20%28218%29.png)

* Quando terminar, aproveite um tema otimizado que torna sua experiência rica, suave e divertida!

## Qual é a diferença de um Recalbox normal?

Quando o Recalbox detecta e instala os itens específicos da carcaça GPI, ele também altera algumas configurações para você começar a trabalhar rapidamente.

Claro, todos os parâmetros estão disponíveis através do menu **START** e você pode ir e reconfigurar o que quiser depois.

**Aqui está a lista das configurações modificadas:**

* Todos os modos de vídeo estão definidos como `default` para evitar alterações desnecessária na resolução HDMI 
* O nome do host GPI está configurado para RECALBOXGPI
* Kodi e botão X estão desativados 
* O Gamepad virtual está desativado 
* As atualizações estão desativadas
* O Netplay está desativado 
* Bluetooth está desativado
* Os drivers XArcade e PS3 estão desabilitados
*  O pop-up de música está desativado 
* A configuração do XBOX360 é substituída pela do GPi \(Sim, o controlador GPi também é um XBOX360!\)
*  Nosso tema otimizado recalbox-gpicase já foi copiado para /recalbox/share/themes e ativado

**Aqui também está o que está instalado:**

* dpi-pizero-gpicase.dtbo: driver de tela da GPI 
* pwm-audio-pizero-gpicase.dtbo: driver de som do GPi 
* Script de desligamento especial do GPi, feito originalmente pela Retroflag e fortemente modificado para fazer o GPI desligar rapidamente.

**Configuração de conexão WIFI**

 Você ainda pode usar o menu START, acessar os submenus da rede e configurar o seu WIFI. 

No entanto, no GPi, você não tem escolha a não ser usar o controlador e o teclado virtual para inserir sua senha WIFI. Se sua senha for complexa, isso pode rapidamente se transformar em uma tarefa dolorosa.  
Aqui está uma solução rápida, passo a passo 

* Grave a imagem e inicialize seu GPi. Quando o EmulationStation iniciar, pressione **START**, entre no menu Rede, ative o WIFI e selecione seu SSID.
* Desligue seu GPi usando o menu **SELECT**/ opção Desligar e aguarde o _desligamento do Recalbox_!
* Remova o cartão SD e use um adaptador SD para acessar a partição **BOOT** em seu PC.
* Abra o arquivo recalbox-backup.conf, vá para a linha que começa com`;wifi.key=`
* Remova o caractere `;` e adicione sua senha WIFI após o `=`. 
* Salve tudo, insira o cartão SD no GPI e inicie-o.
* Assim que o EmlulationStation for iniciado, você deve estar conectado ao WIFI
* Abra \\recalboxgpi\share\system\recalbox.conf e altere novamente a linha `;wifi.key=`. Você também pode alterar esse arquivo usando o nano por meio de uma conexão SSH, se preferir.
* Salve. Isso é tudo, sua conexão está configurada.

## Instalar jogos



![](/migration-images/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/image%20%2844%29.png)

Agora que você está conectado à internet, você pode instalar seus jogos normalmente, usando o compartilhamento SAMBA \(\recalboxgpi\share em um explorador de arquivos\) ou através do WebManager \(http://recalboxgpi em um cliente web \).

Se o seu GPi Case não estiver conectado e você estiver executando o Windows no seu PC, você pode:

* Inicie a partir de um live-CD do Linux e acesse seus discos, bem como a partição SHARE no seu cartão SD, para que você possa copiar o que precisa no cartão SD. 
* Instalar o partitionguru 4
* Instalar o Paragon Software para acessar a partição linux EXT4 no seu cartão SD \([https://www.paragon-software.com/fr/home/linuxfs-windows/](https://www.paragon-software.com/fr/home/linuxfs-windows/)\)

Divirta-se com seus jogos favoritos!

## O que você deveria saber...

### Que tipo de jogos posso rodar no GPI??


>**Informação:  
>Você pode executar qualquer jogo, desde consoles e computadores de 8/16 bits até jogos Arcade.**  
>**Sim você pode! Sério :-\)**
{.is-info}

Para arcade, você possui o **PiFBA**, uma versão do **FBA** otimizada para **ARM** que requer um romset 0.2.96.37. O **FBNeo** \(antigo FBAlpha\), o **MAME2000** até o **MAME2003plus** também funcionam muito bem e muitos jogos podem ser reproduzidos lá.

Alguns jogos **GBA/SNES** , bem como alguns jogos Arcade, podem sofrer atrasos ou lentidão. Neste caso, você pode tentar desabilitar a opção "rebobinar" \(_Rewind_\) nas opções avançadas do emulador.  
No entanto, mesmo com opções otimizadas, alguns jogos não funcionarão em velocidade total.


>**Nota:**  
>Claro, não recomendamos instalar jogos de computador, pois eles geralmente precisam de um teclado e / ou mouse para inicializar.
{.is-warning}

### Posso fazer um overclock do Pi0?

Infelizmente, o Raspberry Pi0 não é facil de fazer o overclock. Além disso, o cartucho GPi não contém orifícios de ventilação para deixar o ar quente sair \(pelo menos a carcaça GPi v1 que estamos usando no momento desta escrita\).

_**Contudo, você pode fazer O/C por sua conta e risco!**_


>**Aviso:**  
>Se o seu GPI não estiver estável após selecionar uma opção de O/C a ponto de não poder mais alterar as opções, insira o cartão SD em seu PC e remova as linhas de O/C do arquivo`config.txt`
{.is-danger}

Você pode adicionar um pequeno dissipador de cobre, conforme mostrado na foto abaixo. Sua espessura não deve exceder 2 mm.

![](/migration-images/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/img_20190616_174526.jpg)



### Quanto tempo dura a bateria ?

Os primeiros testes mostram que você terá cerca de 2 horas de jogo com uma carga.

Lembre-se de que sua caixa GPI possui uma entrada USB. No carro ou em casa, use o cabo USB.


>I**nformação :**  
>Se a parte traseira do cartucho começar a ficar muito quente, recomendamos desligar o GPI e deixá-lo esfriar por um tempo.
{.is-info}



### Como posso fazer o scrape do meus jogos ?

Você sempre pode utilizar o scraper interno para alguns jogos. Mas, ele é configurado para fazer o scrape de grandes arquivos para um Recalbox normal. Usá-lo por Wi-Fi também pode ser lento e ineficiente.

_**Recomendamos fortemente que use um scraper externo**_.  
Ele será melhor e mais rápido.  
Você também pode configurar o tamanho máximo da imagem para 170x170 para economizar espaço e aumentar a velocidade do Emulation Station.

## Solução de problemas

* Se a tela ficar preta ou pular ao tocar no cartucho ou pousar o console:
  * Verifique todas as conexões.
  * Levante o Rpi no cartucho, para aproximá-lo do circuito impresso: Verifique os 4 pinos que sustentam o Pi 0, desparafusando-os levemente até que o Pi 0 fique perfeitamente paralelo ao cartucho. Dependendo do caso, desapertar os 2 pinos dourados superiores pode ser suficiente.


>**Nota:**  
>Este bug ocorre quando há um problema com a usinagem do cartucho e a conexão entre o Pi 0 e o cartucho não é feita corretamente.
{.is-warning}



* **Resolver problemas de estabilidade**

  * **1- O Micro-SD**

  Verifique seu microSD.  
  Alguns modelos têm problemas com o Pi, sem mencionar a baixa qualidade do microSd chinês.  
  Teste com outro SD, de preferência de outra marca.  


  * **2- As pilhas**

  _**Não instale o GPi com as pilhas!**_   
  Sempre use o cabo USB para instalação e teste inicial.  
  Se funcionar bem com o cabo e não com as baterias, ou elas estão esgotadas ou não estão fornecendo energia suficiente, apesar do regulador GPI.  
  A maioria das pilhas recarregáveis ​​são de 1,2 V, não 1,5 V.  


  * **3. O modelo de Pi0.**

  Parece que alguns modelos apresentam problemas de estabilidade, pelo menos com os clocks originais, configurados com o firmware do Pi \(é uma pena!\). Abra o arquivo _config.txt_ na partição FAT32 e adicione as seguintes linhas ao final do arquivo:

  ```text
  arm_freq=1000
  gpu_freq=500
  core_freq=500
  sdram_freq=500
  sdram_schmoo=0x02000020
  over_voltage=6
  sdram_over_voltage=2
  ```

  Isso forçará a configuração dos clocks com um leve overclock da GPU como um bônus.  


  * **4. Montagem**

  Embora montar o Pi seja relativamente fácil, pode ser que sua montagem resulte em contatos imperfeitos. Desmonte o cartucho, limpe os contatos do Pi e do GPI com uma solução de limpeza à base de álcool, remonte o Pi.  
  Limpe também os contatos do cartucho no GPI.  
  Verifique se o cartucho está encaixado corretamente. O botão de ligar não deve ser forçado, nem ao ligar ou desligar. Se estiver forçando, o cartucho está inserido incorretamente ou algo o está incomodando.  


  * **5. Finalmente...**

  Se, depois de tudo isso, não funcionar, ou ainda estiver instável, tente outro Pi para determinar se o Pi ou GPI estão com defeito. Pegue um emprestado ou, em últimos casos, pelo preço, compre outro. Se o GPI for o culpado, você pode tentar uma troca ou um reembolso. Se você tiver alguma dúvida com o vendedor, forneça a ele todos os procedimentos que você seguiu para provar sua boa fé em relação à incriminação do GPI.



* Se você estiver em alguma das seguintes situações:

  * Na primeira inicialização, não há nada na tela, mesmo depois de esperar um pouco.
  * Você não consegue configurar o Wi-Fi. Contacte-nos no servidor Discord ou no Fórum e forneça-nos os seguintes arquivos, disponíveis na partição BOOT do seu cartão SD:
    * `config.txt`
    * `recalbox-backup.conf`
    * `hardware.log`

  \*\*\*\*


>**Atenção :**  
>Para outros problemas, use os meios normais :  
>[Fórum](https://forum.recalbox.com/) ou [Gitlab issues](https://gitlab.com/recalbox/recalbox/issues)
{.is-danger}

