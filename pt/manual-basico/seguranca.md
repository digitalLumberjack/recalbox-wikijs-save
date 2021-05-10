---
title: Segurança
description: Opções e configurações de segurança do Recalbox
---

# Segurança

O Recalbox **não é seguro por padrão**.

De maneira geral:

* Não conecte seu Recalbox diretamente à Internet.
* Não armazene informações confidenciais / privadas em seu Recalbox.
* Faça backups regularmente.
* Desligue seu Recalbox entre duas sessões de jogo.

## **Senha root**

O recalbox têm uma senha root \(super-usuário\) padrão.

Você pode alterar ela através do menu **CONFIGURAÇÕES AVANÇADAS** e **SEGURANÇA**.


>**Nota:**
>
>Esta operação deverá ser refeita após cada atualização, pois as atualizações do Recalbox sobrescrevem os arquivos existentes e, portanto, redefinem a senha para o seu valor inicial.
{.is-warning}

## **Serviços de Rede:**

O Recalbox ativa vários serviços de rede por padrão.

Embora muito práticos, esses serviços também são pontos de entrada fáceis para pessoas mal-intencionadas.

É uma boa prática **desabilitar os serviços** que você não está usando, **editando** a seção '**Network**' do arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)

Para editar este arquivo, duas soluções:

* Abra um prompt de comando e, uma vez conectado, digite: `nano recalbox.conf`
* Ou, no seu computador, abra uma janela da web no endereço: `http: //192.168.X.XX` para abrir o Recalbox Manager, e edite a configuração da página correspondente

**WiFi**

Se não precisar de uma conexão, ou se usa um cabo ethernet:

```text
wifi.enabled=0
```



**Samba**

Samba é um serviço muito útil para transferir arquivos de um computador.

Se você não o usar desative-o assim:

```text
system.samba.enabled=0
```


>**Informação :**  
>A versão 6.1 suporta compartilhamento Samba protegido por uma senha.
{.is-info}

**Controles virtuais:**

Este serviço permite que você use seu smartphone ou tablet como um controle.

Se você não usar esses controles; desative o serviço :

```text
system.virtual-gamepads.enabled=0
```

## Recalbox Manager <a id="recalbox-manager"></a>

O Recalbox vem com seu próprio servidor web, acessado pela porta 80.

Este servidor permite carregar ROMs usando arraste-e-solte, e também permite modificar a configuração.


>**Atenção :**  
>Contudo, é um ponto de acesso muito importante para quem quer assumir o controle do seu raspberry.
{.is-danger}

Então, se você não usa o Recalbox manager \(por exemplo se têm todas as ROMs no raspberry, ou se prefere transferi-las de outra maneira\), você pode desativá-lo :

```text
system.manager.enabled=0
```

Essas etapas devem tornar seu Recalbox \(e consequentemente todos os dispositivos conectados à sua rede\) um pouco mais seguros...

