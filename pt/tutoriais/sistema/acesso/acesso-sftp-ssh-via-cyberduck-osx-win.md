---
title: Acesso SFTP/SSH via Cyberduck \(OSX/WIN\)
---

# Acesso SFTP/SSH via Cyberduck \(OSX/WIN\)

Aqui está como conectar seu Mac Osx e Windows em rede com seu Recalbox via SFTP com o software Cyberduck.

Assim, você poderá ter **acesso fácil aos vários arquivos de configuração**, como `/boot/config.txt`, por exemplo. Se você está familiarizado com **as ferramentas de shell**, este tutorial não é para você, é para **usuários do MacOS** que precisam de uma **interface gráfica**.


>**Informações:**
>
>**Cyberduck** é um software **gratuito** de **transferência de arquivos** para **Mac** e **Windows**. Ele gerencia muitos **protocolos**: FTP, FTP-SSL, SFTP, WebDAV, Swift, S3, Google Cloud Storage, Windows Azure Storage, Dropbox, Google Drive, Backblaze B2 Cloud Storage, Backspace Cloud Files.
{.is-info}

* Para começar, **baixe o Cyberduck** no seguinte endereço: [https://cyberduck.io/](https://cyberduck.io/) ​
* Em seguida, seu Raspberry deve **estar conectado à sua rede local**.
* Você pode encontrar **o endereço IP do seu Raspberry** através do menu "opções de rede"; o endereço IP é necessário \(o nome da rede não é suficiente\).

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDHjBcXX5KuFzmw1iZX%2F-MDHlDF1-EDXSE7gytbd%2Fcwf0u56x.bmp?alt=media&token=ef3c615d-bb17-4a35-bf19-c774ed1fa0ec)

* Em seguida, abra o Cyberduck e clique em **«**Open Connection**»**
  * **Como protocolo** em vez de FTP, **coloque SFTP** e, no campo "port", coloque "22"
  * No campo "server", digite o endereço IP do seu raspberry
  * **Username**: root
  * **Password:** recalboxroot
* Em seguida, clique no botão **« connect »** e autorize as impressões digitais desconhecidas.

![](http://i.imgur.com/8u6bNOe.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzXFyiZ2GP7JC1_rgsx%2F-LzXHmn3EKfcpu_-dU5L%2F687474703a2f2f692e696d6775722e636f6d2f635364327648372e706e67.png?alt=media&token=50e4e5a1-6dc1-4dde-8d22-cc5afe7b71d8)

* Em seguida, para **salvar a configuraçã**o em um **favorito**:

![](http://i.imgur.com/ePuP7Ez.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzXFyiZ2GP7JC1_rgsx%2F-LzXHqae72oZE0M4pM2e%2F687474703a2f2f692e696d6775722e636f6d2f727174764d39442e706e67.png?alt=media&token=6b9471da-7d3e-41aa-9ec4-bc930f5ffe59)

* Aproveite a oportunidade **para renomear antes de fechar a janela**:

![](http://i.imgur.com/WexZz6G.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzXFyiZ2GP7JC1_rgsx%2F-LzXHuLiVqnsX_uoUTvm%2F687474703a2f2f692e696d6775722e636f6d2f706e494258554c2e706e67.png?alt=media&token=20df1e9c-2630-4086-98a1-bd71049d01d6)

* **Pronto:** ​

![](http://i.imgur.com/kvgMoPt.png)

Aqui está, seu favorito está salvo.

A pasta `config.txt` está localizada em `/boot/`.  
A pasta **compartilhada** recalbox **em** `/recalbox/share/`

## Coloque os direitos de gravação no cartão SD <a id="coloque-os-direitos-de-gravacao-no-cartao-sd"></a>

​

Para os hackers experientes, você deve **habilitar** **os direitos de gravação do SD**, para modificar o famoso arquivo`config.txt`.

* **No menu** do Cyberduck, use a opção **"send a command"**

![](http://i.imgur.com/1KWkCrH.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzXFyiZ2GP7JC1_rgsx%2F-LzXHxZhq4JQ37QKAnX_%2F687474703a2f2f692e696d6775722e636f6d2f6e4e717a7268572e706e67.png?alt=media&token=97695d3f-a08c-4a42-a797-dbfcb3fc80c6)

* E **digite :**

`mount -o remount,rw /boot`

* Aqui, você pode **modificar** o arquivo `config.txt`, aconselho a **fazer um backup do arquivo original** no seu computador e substituí-lo no cartão sd pelo meu arquivo modificado.


>**Informação:**  
>**Na próxima vez que você reiniciar** o Recalbox, **os direitos** voltarão para **somente leitura**.
{.is-info}

**Fonte:** [https://forum.recalbox.com/topic/7341/tutoriel-se-connecter-en-ssh-pour-les-nuls-avec-cyberduck-pour-config-txt-osx-et-win](https://forum.recalbox.com/topic/7341/tutoriel-se-connecter-en-ssh-pour-les-nuls-avec-cyberduck-pour-config-txt-osx-et-win)​

​

## Alguns modelos de configuração para overclock:​ <a id="alguns-modelos-de-configuracao-para-overclock"></a>


>**ATENÇÃO:**  
>  
>Overclock pode danificar seu Raspberry! Faça por sua conta e risco!
{.is-danger}

**Overclock para 1.4 ghz**

```text
# Overclock
 arm_freq=1400
over_voltage=6
sdram_freq=575
sdram_schmoo=0x02000020
over_voltage_sdram_p=6
over_voltage_sdram_i=4
over_voltage_sdram_c=4
core_freq=500
v3d_freq=500
h264_freq=333
gpu_mem=400
force_turbo=0
```

**Overclock para 1.35 ghz**

```text
# Overclock
arm_freq=1350
over_voltage=5
sdram_freq=500
sdram_schmoo=0x02000020
over_voltage_sdram_p=6
over_voltage_sdram_i=4
over_voltage_sdram_c=4
core_freq=500
v3d_freq=500
h264_freq=333
gpu_mem=400
force_turbo=0
```

**Overclock para 1.3ghz**

```text
# Overclock
arm_freq=1300
over_voltage=5
sdram_freq=500
sdram_schmoo=0x02000020 
over_voltage_sdram_p=6
over_voltage_sdram_i=4
over_voltage_sdram_c=4
core_freq=500
v3d_freq=500
h264_freq=333
gpu_mem=400
force_turbo=0
```

