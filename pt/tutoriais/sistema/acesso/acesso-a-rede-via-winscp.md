---
title: Acesso à rede via WinSCP
---

# Acesso à rede via WinSCP

## Pré-requisitos​ <a id="pre-requisitos"></a>

* Verifique se o seu recalbox é iniciado e conectado à rede via cabo Ethernet ou um dongle wifi.

> Você tem alguma dúvida e sua rede possui acesso à Internet? Nada poderia ser mais simples, vá para o menu recalbox e depois em 'OPÇÕES DE REDE'. Você terá acesso ao seu IP e status da rede.

* Baixe e instale o software WinSCP
  * Para [Windows](https://winscp.net/eng/index.php)
  * Para o Mac Osx, não há versão do WinSCP, no entanto, você pode usar o Cyberduck no SFTP \(SSH\). Confira [este link](acesso-sftp-ssh-via-cyberduck-osx-win.md).
* Opcional: Descubra o endereço IP do seu Recalbox. Siga as instruções [deste tutorial](https://recalbox.gitbook.io/tutorials/v/portugues/rede/ip/descubra-o-seu-ip-na-rede), caso você não saiba como.

## Configuração​ <a id="configuracao"></a>

* Inicie o `WinSCP`
* Clique em `Novo site`
* Preencha as informações da seguinte maneira:
  * Protocolo de arquivo `SCP`
  * Host`recalbox` ou o IP que você identificou anteriormente \(_a configuração precisará ser modificada cada vez que você reiniciar o recalbox se tiver inserido o IP_\)
  * Porta `22`
  * Usuário `root`
  * Senha `recalboxroot`
  * Salve as alterações
  * Preencha as informações da seguinte maneira:
  * Salve a sessão como: `Recalbox`, por exemplo
  * Marque a caixa "Salvar senha \(não recomendado\)" e depois clique em`OK`
* Seu software está agora configurado
* Nos seus favoritos \(coluna da esquerda\), clique duas vezes em Recalbox
* Um pop-up será aberto informando sobre a conexão atual
* Outro pop-in pode abrir, solicitando:`Continue connecting to an unknown server and add its host key to a cache?` Clique em `yes`
* Você está conectado

## Mostrar arquivos ocultos <a id="mostrar-arquivos-ocultos"></a>


>Isso será útil para você **acessar** a pasta **.emulationstation** para **modificar o tema**, por exemplo.
{.is-info}

* Vamos para `Preferências` \(CTRL+ALT+P\)
* Então `Painéis`
* E marque a caixa `Mostrar arquivos ocultos`.

## Utilização <a id="utilisation"></a>

O uso é bastante intuitivo. Por padrão, você encontrará à esquerda seu computador e à direita a estrutura em árvore do seu recalbox.

**Algumas dicas:**

* Para voltar para a pasta superior ou para a raiz do recalbox, basta clicar na primeira pasta com uma seta indicando retorno, onde, ao invés de um nome de pasta, aparece apenas"`...`".
* Você pode depositar pastas com um simples arrastar e soltar na coluna da direita ou da coluna da direita.
* Você pode alterar as permissões em um arquivo clicando nele com o botão direito do mouse em `Propriedades`.
* Encontre o caminho para os arquivos e pastas úteis em \[[FAQ](https://github.com/recalbox/recalbox-os/wiki/FAQ)\] _**\(link a ser modificado!\)**_

## Colocar o Winscp em Português​ \(caso não esteja\) <a id="colocar-o-winscp-em-portugues-caso-nao-esteja"></a>


>Depois que o winscp estiver instalado, baixe o arquivo de idioma **português** nesta página:[ http://winscp.net/eng/translations.php](http://winscp.net/eng/translations.php)
{.is-info}

* Descompacte-o e coloque o arquivo `C:\Program Files(x86)\winscp\`
* Em seguida, execute winscp,

Se a interface ainda estiver em inglês, mudaremos o idioma para português:

* Clique no botão de ferramentas no canto inferior esquerdo, escolha `preferences`.
* No canto superior esquerdo, environnements &gt; languages &gt; portuguese - português deve aparecer; selecione-o e clique em ok.

## Adicionar Putty:​ <a id="adicionar-putty"></a>

* Basta inserir o executável do putty na pasta `%programfiles%\WinSCP\Putty`
* Em seguida, configure-o em winscp&gt; ferramentas&gt; Preferências&gt; Integração&gt;Formulários [Baixe aqui](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)​

Uma dica é também marcar a caixa: lembrar da senha da sessão e passe-a para Putty \(SSH\)​

## Adicionar Notepad++​ <a id="adicionar-notepad"></a>

* * Basta adicioná-lo ao winscp adicionando-o como um editor externo: Ferramentas&gt; Preferências&gt; Editores&gt; Adicionar Indique o caminho para o aplicativo notepad ++
* Marque as caixas conforme mostrado na captura de tela e clique no botão para cima para que fique no topo da lista de opções.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDH_QfkCLuZMg0ZPVok%2F-MDHi1znAnfNjQMhihYX%2Fw8cwp3b0.bmp?alt=media&token=19f2be1c-1e79-41b9-9417-8fb291ec5e1d)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDH_QfkCLuZMg0ZPVok%2F-MDHi4B91cuSpvJ6qqf2%2Fk2hy2lkl.bmp?alt=media&token=32c3cc2d-86fb-45ca-81d8-014f4305a208)

