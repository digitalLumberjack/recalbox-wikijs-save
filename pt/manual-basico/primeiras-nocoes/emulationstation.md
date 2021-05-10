---
title: EmulationStation
description: Frontend do Recalbox
---

# EmulationStation

## Apresentação


>Ao **ligar o Recalbox**, você entra na interface **EmulationStation \(ES\)**.
>
>Ele permite que você **inicie seus jogos**, **ajuste certas opções** ou **atualize o Recalbox**. 
{.is-info}

Esta é a **primeira tela** dos **Sistemas**:

![](/migration-images/manual-basico/primeiras-nocoes/01.png)

Ele lista os **consoles** e **sistemas disponíveis**.

## Opções do EmulationStation

Ao pressionar **START**, você poderá alterar **algumas configurações do Recalbox**.

![](/migration-images/manual-basico/primeiras-nocoes/menu.png)

### Kodi Media Center

Permite iniciar o **Kodi Media Center** \(também conhecido como XBMC\).


>Você pode iniciar o Kodi a partir da tela inicial pressionando o botão **X** em seu controle.
{.is-info}

Para sair do Kodi, selecione "QUIT" no programa e você estará de volta ao EmulationStation.

Os controles são suportados no Kodi. Mas se preferir, você também pode usar HDMI-CEC \(permite usar o controle remoto da TV para navegar no Kodi\) ou um aplicativo de controle remoto para smartphone.


>**Para obter mais informações** sobre o **Kodi:**
>
>[Kodi no Recalbox](/v/portugues/manual-basico/funcionalidades/kodi-media-center)  
>[Use um controle remoto infravermelho](/v/portugues/manual-basico/funcionalidades/kodi-media-center/use-um-controle-remoto-infravermelho)
{.is-warning}

### Configurações de sistema

Você acessará as informações do sistema:

A versão do Recalbox atualmente instalada, o espaço de armazenamento usado / disponível, a escolha da mídia de armazenamento \(interna no cartão SD, chave USB, disco rígido externo, etc.\), a seleção do idioma do menu e o tipo de teclado.

### Atualizações

Este menu se propõe a ativar ou não as atualizações e escolher se deseja instalar apenas uma versão estável ou também as versões beta do Recalbox.

### Configurações dos jogos

Este menu oferece como configurações:

* **Formato do jogo:** Auto; Configuração do Retroarch; Fornecido pelo núcleo; Pixel; Específico do Retroarch; 1/1; 16/10; 16/15; 16/9; 19/12; 19/14; 2/1; 21/9; 3/2; 3/4; 30/17; 32/9; 4/1; 4/3; 5/4; 6/5; 7/9; 8/3; 8/7; 16/09
* **Suavização de Imagem**: Permite dar um pequeno efeito de desfoque aos pixels para que fiquem mais bonitos em nossas TVs modernas.
* **Retroceder/Rebobinar**: permite que você volte no tempo durante o jogo.


>Isso pode tornar alguns emuladores mais lentos \(PS1, Dreamcast, ...\) se você ativá-lo por padrão nesses emuladores. Você pode habilitá-lo apenas para alguns emuladores por meio do menu [Configurações avançadas](/v/portugues/manual-basico/primeiras-nocoes/emulationstation#configuracoes-avancadas). 
{.is-danger}

* **Salvar/Carregar automaticamente**: Permite que você retome um jogo de onde estava quando o deixou anteriormente.
* **Pressione duas vezes para sair do jogo**: Confirma que você deseja sair do jogo em andamento.
* **Configurando** **Shaders** : Você pode configurar facilmente os shaders para diferentes sistemas.

  * **Scanline:** ativam scanlines em todos os sistemas para obter uma renderização próxima a uma tela CRT.
  * **Retro:** são um pacote de shaders, correspondendo ao melhor shader para aplicar a cada sistema. Os shaders que compõem este pacote, são escolhidos pela comunidade e trarão a você a experiência de jogo mais próxima da experiência original para cada sistema!

Para obter mais informações, consulte [Configuração dos Shaders](https://recalbox.gitbook.io/tutorials/v/portugues/jogos/diversos/configuracao-dos-shaders-sombreamento).


>**Informação:**  
>Você também pode alterar o _shader_ enquanto joga, usando seu controle.  
>Use os [Comandos especiais](/v/portugues/manual-basico/primeiras-nocoes/durante-o-jogo#comandos-especiais) **Hotkey + R2** ou **Hotkey + L2** para ver o próximo shader ou o anterior.
{.is-info}

* **Escala Integrada \(Pixel Perfect\):** Exibe os jogos em sua resolução original.
* **Opções de Retroachievements:** permite que você configure Retroachievements \(equivalente a conquistas/troféus, mas para consoles mais antigos\).
* **Opções de NetPlay:** Permite configurar o NetPlay \(jogo online/em rede\).

### Configurações dos Controles

É aqui que você pode configurar seus controladores.

### Configurações da I**nterface**

Este menu oferece acesso às configurações da interface.

* **Protetor de tela:** Configure o protetor de tela com diferentes opções.
* **Relógio no menu**
* **Exibir Ajuda**
* **Configurar pop-ups**
* **Seleção rápida do sistema:** Usado para alternar de um sistema para o próximo sistema usando as teclas direita ou esquerda.
* **Teclado virtual**
* **Tema:** Escolha de diferentes temas criados pela comunidade \(esses novos temas não estão disponíveis por padrão com Recalbox\)

### Configurações de Áudio

Este menu permite desativar ou ativar a **música de fundo** no EmulationStation, ajustar o **volume do sistema** e selecionar a **saída de áudio** \(_Auto, Jack ou HDMI_\).

Para forçar a saída analógica, selecione _Jack_.

### Configurações de Rede

Este menu permite ativar e configurar o **Wi-Fi**, o **nome da rede** e obter o **endereço IP** do seu Recalbox.

Digite o SSID e a senha da sua rede Wi-Fi com um teclado. Assim que as informações forem validadas, o Wi-Fi será ativado.


>**Problema conhecido:** alguns caracteres especiais necessários para as informações de rede não podem ser inseridos.  
>Se você encontrar este problema, configure seu acesso wi-fi diretamente no arquivo "`recalbox.conf`".  
>Mais informações em "[O arquivo recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)".
{.is-warning}

### Banco de Dados

Para cada jogo, você pode obter informações \(capa, resumo, etc.\) que serão exibidas no menu de seleção de jogos do EmulationStation.

Pressione **START** e vá para SCRAPPER. Então siga as instruções na tela. Mais informações em "[Scrapper Interno](/v/portugues/manual-basico/funcionalidades/scrapper-interno)".

### Configurações Avançadas

* **Overclock** : Configurações de overclock \(_NENHUM &lt; ALTO &lt; TURBO &lt; EXTREMO_\)


>As configurações Turbo e Extremo podem causar danos irreversíveis ao Raspberry se não forem feitas em boas condições \(dissipação de calor, ventilação, ...\). A garantia do seu equipamento pode ser anulada.
{.is-danger}


>A classificação das predefinições de overclock para o RPi1, em ordem crescente de velocidade, são: NENHUM &lt; ALTO &lt; TURBO &lt; EXTREMO
>
>A configuração Extremo pode anular sua garantia RPi, mas é a única que lhe dará um bom desempenho com todos os emuladores do RPi1
{.is-warning}


>Também é aconselhável fazer um overclock do RPi2 se você quiser emular o N64 e obter a melhor experiência de jogo.
{.is-warning}

* Parâmetros de inicialização: vários parâmetros de inicialização.
* Configuração avançada do emulador: Permite configurar as opções do emulador independentemente das outras.
* Opções do Kodi
* Segurança: Permite reforçar a segurança do Recalbox e modificar a senha de root.
* Overscan
* Mostrar frequência
* Recalbox Manager
* Recalbox API

### Sair

Menu que permite **desligar o Recalbox.**

## Controles

#### Os comandos na interface:

A → Selecionar  
B → Voltar  
Y → Favoritos  
X → Iniciar Kodi  
Start → Menu  
Select → Opções \(na tela do sistema, abre o menu de reinicialização\)  
R → Próxima página  
L → Página Anterior

Quando você seleciona um sistema com o botão A, a tela muda e você acessa sua lista de jogos disponíveis.

Depois de iniciar o jogo, consulte[ Durante o jogo](/v/portugues/manual-basico/primeiras-nocoes/durante-o-jogo) para ver as opções disponíveis.

## Favoritos

Você pode definir um jogo como favorito pressionando a tecla **Y.**  
O jogo será então colocado no início da lista com uma ☆ na frente de seu nome.


>**Atenção:**  
>O sistema **deve ser desligado de forma correta usando o menu EmulationStation** para que a **lista de jogos favoritos** seja salva e encontrada na **próxima inicialização**.
{.is-danger}

