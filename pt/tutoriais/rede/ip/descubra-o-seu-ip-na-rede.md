---
title: Descubra o seu IP na rede
---

# Descubra o seu IP na rede

## Configurações de rede Recalbox​ <a id="configuracoes-de-rede-recalbox"></a>

**Desde a versão 3.3.0:**

Aperte _Start_ e vá para as Configurações de Rede. O IP atual será exibido aqui.​

## Pré-requisitos​ <a id="pre-requisitos"></a>

Verifique se o seu recalbox está funcionando e conectado à rede com cabo Ethernet ou wifi

> Você tem alguma dúvida e sua rede tem acesso à Internet? Basta ir ao menu do seu recalbox e depois em UPDATE SYSTEM. Se um menu pop-up exibir a mensagem de que uma atualização está disponível ou nenhuma atualização disponível, o Recalbox terá acesso à Internet e, assim, à rede. Se a mensagem Plugue um cabo de rede for exibida, você não tem acesso à Internet ou pode ter um problema nas configurações do roteador, um cabo com defeito ou um dongle wifi não funcionando.

Cuidado, o endereço IP não é fixo e pode mudar a cada inicialização. Você pode definir um por si mesmo através da [configuração manual de IP](configuracao-manual-de-ip.md).

## No Windows​ <a id="no-windows"></a>

* Rode o comando **`Executar`**

  Se você não sabe onde está o comando Excecutar [_O Google é seu amigo_](https://answers.microsoft.com/pt-br/windows/forum/all/140-comandos-pelo-executar-do-windows/7d5062d6-9b2d-4766-bd78-0e31460fc0a6)_​_

* **Digite** **`cmd`** e tecle **`Enter`**
* Então, uma vez **no prompt de comando**, digite `ping recalbox` **e tecle** `Entrer`
* Você deve ter a **seguinte mensagem** exibida:

> Enviando uma solicitação 'ping' em RECALBOX com 32 bytes de dados Resposta de 192.168.0.XX: bytes = 32 horas = 1 ms TTL = 128 Resposta de 192.168.0.XX: bytes = 32 horas = 1 ms TTL = 128 Resposta de 192.168.0.XX: bytes = 32 horas = 1 ms TTL = 128 Estatísticas de ping para \[...\]

* Você tem **o seu IP**.

## No OSX​ <a id="no-osx"></a>

* Inicie **`Terminal`**

  **Está localizado** na pasta **`Utilitários`** _da pasta_ **`Aplicações`**

* Digite `arp -a`
* A **lista de todos os dispositivos conectados à rede,** no formato de lista IP, é **exibida**
* **O IP do Raspberry** está no formato **`192.168.0.XX`.**
* Você tem **o seu IP**.

## Outras soluções​ <a id="outras-solucoes"></a>

* Os **aplicativos de smartphones** estão disponíveis para **escanear sua rede**. Vá até a **loja correspondente do seu dispositivo\(playstore ou applestore\)** para encontrar **o aplicativo de sua escolha**.
* Outra solução consiste em acessar as configurações do seu roteador. A lista de dispositivos conectados está disponível lá.

