---
title: Scripts em eventos do EmulationStation
---

# Scripts em eventos do EmulationStation


>**Recalbox 7.0 e superior!**
{.is-warning}

## Qual é o ponto?

O principal interesse é poder executar ações externas com base nas ações do usuário no EmulationStation.

Claro, é principalmente no Raspberry Pi e outras placas que permitem uma fácil pilotagem por hardware, que este recurso revelará todo o seu potencial.

Em um determinado número de eventos do EmulationStation, seremos capazes de lançar um script \(ou um executável\) ou enviar uma mensagem MQTT que os scripts irão esperar e processar.

A cada evento, um arquivo é preenchido com um monte de informações que os scripts podem ou não usar.

## Funcionamento <a id="funcionamento"></a>

### Os eventos <a id="os-eventos"></a>

Começamos com a lista exaustiva de eventos, quando são acionados e se expõem informações adicionais que serão passadas como parâmetros aos scripts.

| Evento | Quando? | Configurações |
| :--- | :--- | :--- |
| Start | Iniciando ou reiniciando o EmulationStation | Número de partidas |
| Stop | Parando EmulationStation | Número de partidas |
| Shutdown | Desligamento completo do sistema |  |
| Reboot | Reinicio do sistema |  |
| Quit | Parando o EmulationStation seguindo uma solicitação externa \(parando no case GPI pelo botão liga/desliga, por exemplo\) |  |
| Relaunch | Reiniciando o EmulationStation \(gamelist.xml modificado externamente, por exemplo, ou atualizando listas de jogos\) |  |
| SystemBrowsing | O usuário está na lista de sistemas e um novo sistema acaba de ser selecionado. | Nome abreviado do sistema |
| GamelistBrowsing | O usuário está em uma lista de jogos e um novo jogo \(ou pasta\) acaba de ser selecionado. | Caminho do arquivo ROM |
| RunGame | Um jogo será liniciado | Caminho do arquivo ROM |
| RunDemo | Um jogo será lançado em modo de demonstração | Caminho do arquivo ROM |
| EndGame | Um jogo acabou | Caminho do arquivo ROM |
| EndDemo | A demonstração de um jogo acabou | Caminho do arquivo ROM |
| Sleep | Iniciando o protetor de tela |  |
| WakeUp | Saindo do protetor de tela |  |
| ScrapStart | Uma sessão de scrappe de vários jogos foi iniciada |  |
| ScrapStop | Uma sessão de scrappe de vários jogos terminou | Número de jogos feitos scrappe |
| ScrapGame | Acabou de ser feito scrappe em um jogo | Caminho do arquivo ROM |
| ConfigurationChanged | Algo mudou na configuração |  |

​

### Os scripts <a id="os-scripts"></a>

Os scripts devem ser colocados em **`/recalbox/share/userscripts`** ou **`\\recalbox\share\userscripts`** ou em subpastas se você quiser organizá-los.

O próprio EmulationStation escolhe o melhor inicializador, se necessário, dependendo da extensão dos scripts:

* .sh: Iniciado por **sh**
* .ash: Iniciado por **ash** \(um shell otimizado fornecido por busybox\)
* .py: Iniciado por **python** \( = python2.7 no Recalbox \)
* .py2: iniciado explicitamente por **python2.7**
* .py3: iniciado explicitamente por **python3.7**

Todas as outras extensões são consideradas executáveis ​​e os arquivos são iniciados diretamente.


>No momento em que este livro foi escrito, Python3 ainda não estava disponível no Recalbox!
{.is-danger}

#### Parâmetros de inicialização <a id="parametres-de-lancements"></a>

Cada script / executável é iniciado com os seguintes argumentos:

**script** -action _**action**_ -statefile _**statefile**_ \[-param _**parametre**_\]

* _**action**_ é o evento que iniciou o script, tudo em minúsculas.
* _**statefile**_ é o arquivo que contém as informações adicionais. Veja [o parágrafo neste artigo](scripts-em-eventos-do-emulationstation.md#le-fichier-de-status-complet-demulationstation).
* _**parametre**_ é o parâmetro opcional do evento. Se o evento não tiver parâmetros, -param não estará presente.

#### Filtrando <a id="filtrage"></a>

Por padrão, os scripts são iniciados para cada evento.

Para filtrar e apenas iniciar o script para determinados eventos direcionados, tudo que você precisa fazer é indicá-los entre colchetes e separados por vírgulas. A quebra não é importante.

Por exemple: **`/recalbox/share/userscripts/marquee[start,stop].sh`** só será iniciado quando o EmulationStation iniciar ou parar.  
Ou ainda:**`/recalbox/share/userscripts/gamesinfo[browsinggamelist,rungame,rundemo,scrapgame].sh`** só será iniciado para eventos que dizem respeito diretamente aos jogos, para exibir informações do jogo em uma tela secundária, por exemplo.

#### Síncrono / Assíncrono <a id="synchrone-asynchrone"></a>

Todos os scripts são iniciados de forma assíncrona. Ou seja, o EmulationStation continua sua execução enquanto o script é executado em paralelo.

Na maioria dos casos, isso não importa, mas há momentos em que queremos bloquear o EmulationStation até que nosso script seja concluído. Um caso de uso típico é um script que seria executado em eventos de reinicialização ou desligamento do sistema.  
Nesse caso, precisamos nos certificar de que nosso script seja executado corretamente antes que o sistema inicie seu procedimento de desligamento, caso contrário, podemos perder informações ou pior.

Para que um script seja executado de forma síncrona, basta colocar um**`(sync)`** no nome do arquivo.

Por exemple: **`/recalbox/share/userscripts/backup[reboot,shutdown](sync).sh`** será executado quando o sistema for desligado ou reinicializado. O EmulationStation será bloqueado até o final de sua execução e o desligamento do sistema começará somente depois.

#### Scripts permanentes <a id="scripts-permanents"></a>

Alguns scripts podem precisar ser executados continuamente. Principalmente se forem usados ​​para interceptar mensagens [MQTT que veremos logo abaixo](scripts-em-eventos-do-emulationstation.md#mqtt).

Basta colocar **`(permanent)`** no nome do arquivo de um script para que seja iniciado pelo EmulationStation na inicialização.


>Se o EmulationStation for reiniciado, os scripts persistentes continuarão a ser executados e não serão reiniciados.
{.is-info}

### MQTT <a id="mqtt"></a>

Recalbox inclui um mini servidor **MQTT** \(Mosquitto\) que permite "_publicar/assinar_".

Sempre que o EmulationStation irá executar scripts em um evento, ele também publicará o evento \(em letras minúsculas\) no tópico**`/Recalbox/EmulationStation/Event`**.

Um programa que lê esse tópico pode, portanto, interceptar todos os eventos a um custo de uso do processador quase zero. Mosquitto fornece 2 pequenos executáveis **`mosquitto_pub`** e **`mosquitto_sub`** que respectivamente permitem que você publique uma mensagem em um tópico ou espere por uma mensagem de um tópico.

Portanto, você pode usar **`mosquitto_sub`** em um script para lêr e aguardar eventos do EmulationStation, como segue:**`event = $(mosquitto_sub -h 127.0.0.1 -p 1883 -q 0 -t /Recalbox/EmulationStation/Event -C 1)`** Este comando bloqueia a execução do script até que um evento seja postado. O script então recupera o tipo de evento da variável **`event`**.


>Compreendemos rapidamente o valor dos scripts permanentes: em vez de lançar um script a cada vez, para cada evento, podemos lançar um script permanente e fazer com que ele intercepte todos os eventos em um loop.  
>É uma solução muito menos onerosa para o sistema.
{.is-info}


>O Mosquitto é iniciado explicitamente no loop local IP 127.0.0.1, o que impede seu acesso e uso fora do Recalbox, por razões de segurança óbvias.  
>Se você quiser mudar sua configuração, é aqui que acontece: [https://mosquitto.org/man/mosquitto-conf-5.html](https://mosquitto.org/man/mosquitto-conf-5.html)​
{.is-danger}

### O arquivo de status completo do EmulationStation <a id="o-arquivo-de-status-completo-do-emulationstation"></a>

Em cada evento, o EmulationStation grava um pequeno arquivo no disco ram: **`/tmp/es_state.inf`**

Este arquivo é um arquivo simples do tipo ini, contendo associações **chave=valor**.

Este arquivo já está na versão 2.0. Até o Recalbox 6.1.1, este arquivo continha um número de chaves fixas, com valores vazios dependendo do contexto. A versão 2.0 mantém a compatibilidade com 1.0, mas adiciona chaves fixas e opcionais, dependendo do contexto.

Aqui está a lista de chaves / valores disponíveis desde a versão 1.0:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Chave</th>
      <th style="text-align:left">Valor</th>
      <th style="text-align:left">Pode estar vazio?</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">System</td>
      <td style="text-align:left">Nome completo do sistema afetado pelo evento. Pode estar vazio.</td>
      <td
      style="text-align:left">Sim</td>
    </tr>
    <tr>
      <td style="text-align:left">SystemId</td>
      <td style="text-align:left">Nome abreviado do sistema relacionado ao evento. Pode estar vazio</td>
      <td
      style="text-align:left">Sim</td>
    </tr>
    <tr>
      <td style="text-align:left">Game</td>
      <td style="text-align:left">Nome completo do jogo afetado pelo evento. Pode estar vazio</td>
      <td style="text-align:left">Sim</td>
    </tr>
    <tr>
      <td style="text-align:left">GamePath</td>
      <td style="text-align:left">Caminho completo da rom envolvida pelo evento. Pode estar vazio</td>
      <td
      style="text-align:left">Sim</td>
    </tr>
    <tr>
      <td style="text-align:left">ImagePath</td>
      <td style="text-align:left">Caminho completo da imagem do jogo afetada pelo evento. Pode estar vazio</td>
      <td
      style="text-align:left">Sim</td>
    </tr>
    <tr>
      <td style="text-align:left">State</td>
      <td style="text-align:left">
        <p>Cont&#xE9;m um dos seguintes valores:</p>
        <ul>
          <li>playing : um jogo est&#xE1; em andamento</li>
          <li>demo : um jogo est&#xE1; em modo Demo</li>
          <li>selected : todos os outros casos.</li>
        </ul>
      </td>
      <td style="text-align:left">N&#xE3;o</td>
    </tr>
  </tbody>
</table>

E a lista do que está disponível além disso, desde 2.0:

| Chave | Valor | Eventos |
| :--- | :--- | :--- |
| Action | O nome do evento que gerou a gravação do arquivo de estado. | Todos |
| ActionData | Parâmetros do evento, possivelmente vazios | Todos |
| Emulator | Emulador padrão para o sistema afetado. | BrowsingSystem |
| Core | Núcleo usado por padrão para o sistema afetado. Pode ter o mesmo valor que o emulador para emuladores sem plug-ins como o Amiberry. | BrowsingSystem |
| Emulator | Emulador usado para iniciar este jogo. | Jogos \(\*\) |
| Core | Núcleo usado para iniciar este jogo. A mesma observação que para o núcleo do sistema. | Jogos \(\*\) |
| IsFolder | É igual a 1 se uma pasta for selecionada na lista de jogos e 0 se for um jogo. | Jogos \(\*\) |
| ThumbnailPath | Caminho completo para a miniatura correspondente ao jogo. \(\*\*\) | Jogos \(\*\) |
| VideoPath | Caminho completo para o vídeo do jogo. \(\*\*\) | Jogos \(\*\) |
| Developer | Nome do desenvolvedor ou estúdio de desenvolvimento. \(\*\*\) | Jogos \(\*\) |
| Publisher | Nome do editor. \(\*\*\) | Jogos \(\*\) |
| Players | Número de jogadores. \(\*\*\) | Jogos \(\*\) |
| Region | Região do jogo \(\*\*\) | Jogos \(\*\) |
| Genre | Gênero do jogo \(\*\*\) | Jogos \(\*\) |
| GenreId | Identificador numérico do gênero do jogo. \(\*\*\) | Jogos \(\*\) |
| Favorite | É igual a 1 se o jogo estiver nos favoritos, caso contrário, 0. \(\*\*\) | Jogos \(\*\) |
| Hidden | Vale 1 se o jogo estiver oculto, caso contrário, 0. \(\*\*\) | Jogos \(\*\) |
| Adult | Vale 1 se o jogo for classificado como adulto, caso contrário, 0. \(\*\*\) | Jogos \(\*\) |


>\(\*\) Significa em detalhes: GameBrowsing, RunGame, RunDemo, EndGame, EndDemo e GameScrap.
>
>\(\*\*\) Cada uma dessas informações provém dos metadados associados ao jogo em questão. Portanto, podem estar vazios se o jogo não tiver sido feito scrappe.
{.is-info}


>_**Este arquivo é gravado antes da execução dos scripts de envio da mensagem MQTT**_. Portanto, é válido quando os scripts são executados. **Porém...**  
>Alguns eventos estando extremamente próximos, é possível que este arquivo já tenha sido alterado por um segundo evento quando você for lê-lo após um primeiro evento. Portanto, é aconselhável:
>
>* Verifique o valor da chave **`action`** para ter certeza de que corresponde ao evento desejado.
>* Não presuma que uma chave opcional estará necessariamente presente ou que uma chave fixa terá necessariamente um valor.
{.is-warning}

## ​As Boas práticas

Aqui está uma série de dicas para escrever seus scripts. Você é livre para ignorar isso, mas esteja ciente de que a execução de scripts em cada evento do EmulationStation pode ter um impacto no sistema:

* Desaceleração do sistema
* Atrasos nos jogos, atrasos no som...
* Lentidão ao iniciar os jogos
* etc.

Tanto quanto possível, mantenha seus scripts no mínimo.

Evite scripts que não filtram eventos. Se o Recalbox adicionar eventos em versões futuras, seus scripts serão ainda mais solicitados.

Evite scripts síncronos se não for estritamente necessário \(durante a fase de desligamento\).

Aproveite ao máximo o shell **`ASH`** em vez do **`SH`**, é muito mais rápido e melhor. Por outro lado, tem algumas pequenas diferenças com **`SH`**. [https://fr.wikipedia.org/wiki/Almquist\_shell](https://fr.wikipedia.org/wiki/Almquist_shell)​

Se você precisar processar muitos eventos, use um único script permanente junto com **`mosquitto_sub`**, você economizará muitos recursos do sistema.

