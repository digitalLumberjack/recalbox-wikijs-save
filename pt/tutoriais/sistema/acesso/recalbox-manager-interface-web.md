---
title: Recalbox Manager - Interface Web
---

# Recalbox Manager - Interface Web


>**Informação:**
>
>Recalbox Manager é uma interface web para acessar seu Recalbox através de um smartphone, tablet ou PC.
{.is-info}

## **Para se conectar** <a id="para-se-conectar"></a>

Basta digitar em seu navegador o nome:

* No windows \(IE, CHROME, FIREFOX\) :

  *  [http://recalbox/](http://recalbox/)​

  ​

* No Mac e Linux, ou usuário safari no Windows:

  * ​[http://recalbox.local/](http://recalbox.local/)​

  ​

* Se isso não funcionar, você pode usar o endereço IP do seu Recalbox:
  * **192.168.1.x**


>**Informação:**
>
>A maioria **dos roteadores** é configurada de forma que você **encontre seu recalbox** entre **192.168.1.2** e **192.168.1.254**.
>
>Para descobrir o seu endereço IP:  
>Menu do Emulationstation\(botão Start\)&gt; Opções de Rede&gt; Endereço IP
{.is-info}

\*\*\*\*

## **Interface** <a id="interface"></a>

Quando você está na página principal, pode navegar entre os seguintes menus:

* Editar o arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf).
* Adicionar/Remover BIOS.
* Adicionar/Remover ROMs.
* Consultar o log.​

### Ele permite: <a id="ele-permite"></a>

* Monitorar seu rpi.
* Editar o arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf).
* Iniciar o gamepad virtual \(útil para configurar seu recalbox em 5 minutos para o primeiro uso\) via smartphone ou tablet somente.
* Consultar os logs do Recalbox.​

### Ele permite que você arraste e solte: <a id="ele-permite-que-voce-arraste-e-solte"></a>

* Faça upload do BIOS verificando se o Checksum está correto
* Faça upload das roms em formato`.zip` ou extensão compatível com emuladores

​**Por padrão**, o gerenciador é **iniciado automaticamente**. Se você quiser, pode **desabilitá-lo** em [**recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)**​**

```text
## Recalbox Manager (gerenciador http)
system.manager.enabled = 1
```

## **Gamepad Virtual** <a id="gamepad-virtual"></a>

Para acessá-lo diretamente, basta inserir o IP do seu recalbox com a porta 8080 `http://192.168.0.X:8080 ou http://recalbox:8080`

Consulte o manual do usuário do [Gamepad Virtual aqui](https://recalbox.gitbook.io/tutorials/v/portugues/controles/controles/jogue-com-seu-smartphone-usando-o-gamepad-virtual)_**.**_

O github para feedback: [https://github.com/recalbox/recalbox-manager](https://github.com/recalbox/recalbox-manager)

