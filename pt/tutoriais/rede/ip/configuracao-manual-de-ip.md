---
title: Configuração Manual de IP
---

# Configuração Manual de IP

## Recalbox 4.0​ <a id="recalbox-4-0"></a>

Para **selecionar um endereço IP fixo para o seu Recalbox**, você precisará modificar o arquivo `/etc/network/interfaces`.

* ​[Obtenha acesso root via Terminal](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) e edite o arquivo: com:`nano /etc/network/interfaces`


>**Informação:**
>
>Para uma **solução permanente,** você deve **modificar** o arquivo `interfaces.base`. E antes de alterá-lo, você precisa montar a leitura/gravação do sistema de arquivos. Use os comandos:  
> `mount -o remount,rw /`  
> `nano /etc/network/interfaces.base`
{.is-info}

​

* **Encontre a linha** que contém a **interface** que você deseja modificar \(ethX para ethernet, wlanX para wifi\):

```text
auto eth0
iface eth0 inet dhcp
```

### Vamos mudar o endereço IP eth0. <a id="vamos-mudar-o-endereco-ip-eth-0"></a>

* **Substitua** as configurações atuais pelas do **IP fixo**:

  ```text
  auto eth0
  iface eth0 inet static
  address 192.168.1.10
  network 192.168.1.0
  netmask 255.255.255.0
  broadcast 192.168.1.255
  gateway 192.168.1.254
  ```

* Neste exemplo, sua: **A rede local** tem como endereço do modem 192.168.1.x. **O endereço da sua placa** é 192.168.1.254. **Sua máscara de rede** é, portanto, 255.255.255.0. E você deseja que **seu endereço** seja **192.168.1.10**

Ao Mudar para um endereço IP estático, você perderá a configuração do\(s\) servidor\(es\) DNS no processo. Para que a resolução de nomes funcione, você precisará criar um arquivo chamado`/etc/resolv.conf`. Por padrão, esse arquivo aponta para um arquivo gerado automaticamente localizado em`/tmp/resolv.conf`, para fazer isso de uma vez por todas, execute os seguintes comandos:

```text
rm /etc/resolv.conf
nano /etc/resolv.conf
```

Digite as seguintes linhas, que correspondem aos servidores DNS do projeto OpenDNS:

```text
nameserver 208.67.222.222
nameserver 208.67.220.220
```

Salve o arquivo.

Agora atualize as configurações com: `ifdown eth0 && ifup eth0`


>Essas alterações serão **reescritas a cada nova atualização!**  
>Você precisará repetir essas tarefas após cada atualização.
{.is-warning}

## A partir do Recalbox 4.1​ <a id="a-partir-do-recalbox-4-1"></a>

* ​[Obtenha acesso root via Terminal](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) 

Digite `connmanctl services` e observe o que é retornado, por exemplo:

`*AO Wired ethernet_b827eb6462be_cable`

* Então digite: `cd`

`nano custom.sh`

```text
#!/bin/bash
/usr/bin/connmanctl config ethernet_b827eb6462be_cable --ipv4 manual 192.168.1.181 255.255.255.0 192.168.1.1
mount -o remount,rw /
echo "nameserver 208.67.222.222" >> /etc/resolv.conf
echo "nameserver 208.67.220.220" >> /etc/resolv.conf
```

Substitua **ethernet** pelo **valor obtido anteriormente** e o **endereço IP** pelo que você deseja fornecer. Você pode substituir os endereços IP dos servidores DNS no projeto OpenDNS pelos servidores DNS \(se houver\) fornecidos pelo seu próprio ISP.

Saia do editor de texto nano com `Ctrl X`, responda à pergunta de economia digitando `Y` e, finalmente, pressione `Enter`.

Após sair do nano e voltar ao shell do terminal, digite o comando`chmod +x custom.sh`, tornando-o executável, e `reboot`para reiniciar o Recalbox.

## A partir do Recalbox 6.1 <a id="a-partir-do-recalbox-6-1"></a>

Desde a versão 6.1, é possível editar o IP manualmente no arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf):

```text
## Wifi - static IP
## if you want a static IP address, you must set all 3 values (ip, gateway, and netmask)
## if any value is missing or all lines are commented out, it will fall back to the
## default of DHCP
;wifi.ip=manual ip address
;wifi.gateway=new gateway
;wifi.netmask=new netmask
```

Você precisa remover o **`;`** da frente das últimas três linhas, ou a configuração não irá funcionar, e preenche-las com as informações que você deseja, por exemplo:

```text
wifi.ip=192.168.1.10
wifi.gateway=192.168.1.254
wifi.netmask=255.255.255.0
```

