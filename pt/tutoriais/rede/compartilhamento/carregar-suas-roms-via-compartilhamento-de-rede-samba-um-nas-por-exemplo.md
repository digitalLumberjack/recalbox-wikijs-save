---
title: Carregar suas ROMs via compartilhamento de rede Samba \(um NAS, por exemplo\)
---

# Carregar suas ROMs via compartilhamento de rede Samba \(um NAS, por exemplo\)


>Ser capaz de armazenar seus Roms em um NAS e, portanto, ser capaz de armazenar muito mais do que em um cartão SD
{.is-info}


>**Obrigatoriamente** o NAS e o Pi devem ser conectados via Ethernet!
{.is-danger}

Em primeiro lugar, o **NAS** \(_testado em Synology, mas a operação é a mesma em quase todos os lugares_\):

* Crie uma pasta compartilhada \(vamos chamá-la de "/roms/"\)
* Crie um usuário com direitos de gravação/leitura para esta pasta. \(ou reutilize um usuário com esses direitos\)
* Recrie a arquitetura da pasta **Roms** do Recalbox \(via compartilhamento de rede, via ftp ou manualmente se quiser ;\) o importante é ter a mesma arquitetura, ou seja, uma pasta para cada máquina emulada.

**Opcional:**

_É perfeitamente possível fazer o mesmo a partir do disco rígido do seu PC. No Windows, você pode criar uma pasta compartilhada e montá-la da mesma forma no Recalbox. A única desvantagem: o PC deve estar ligado para acessar os ROMs no Recalbox._

#### **Agora no Recalbox** <a id="agora-no-recalbox"></a>

## Versão do Recalbox&gt; = 4.1 <a id="versao-do-recalbox-greater-than-4-1"></a>


>**Desde a versão 4.1** do Recalbox, o **carregamento de ROMs de um compartilhamento de rede** é muito **simples**.
>
>Agora é possível **indicar ao sistema** que o conteúdo da pasta **/recalbox/share** deve ser montado a partir de um compartilhamento de rede, **sem a necessidade de modificar** os arquivos do **sistema** ou **scripts de inicialização**.
{.is-info}

A partir de um terminal ou de uma conexão SSH \([veja o tutorial para conectar em SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)\)

* Coloque o sistema de arquivos no modo "leitura/gravação" \(é "somente leitura" por padrão\). Esta modificação permanecerá ativa até a próxima reinicialização do Recalbox:

```text
mount -o remount,rw /boot
```

* Agora edite o arquivo **/boot/recalbox-boot.conf** com seu editor favorito \(via nano, por exemplo\)

**Substitua a linha:**

```text
sharedevice=INTERNAL
```

**Pela linha:**

```text
sharedevice=NETWORK
```

Para indicar ao Recalbox que o conteúdo da pasta **/recalbox/share** deve ser montado a partir de um compartilhamento de rede \(e não do cartão SD\)

* Agora é necessário especificar, sempre no arquivo `recalbox-boot.conf`, as informações de conexão NAS. Existem duas opções possíveis para isso:
  * **Os comandos básicos:**

    `sharenetwork_<nfs|smb><[0-9]>=<SHARE|ROMS|SAVES|BIOS>@<NAS>:<répertoire partagé>:<options>`

  * **Os comandos avançados:** `sharenetwork_cmd<[0-9]>=<commande à exécuter>`

**Exemplo:**

```text
sharenetwork_smb1=ROMS@192.168.0.1:recalbox/roms:username=recalbox,password=recalbox,vers=2.0
sharenetwork_smb2=SAVES@192.168.0.1:recalbox/saves:username=recalbox,password=recalbox,vers=2.0
```

**Outro exemplo, com comandos avançados:**

```text
sharenetwork_cmd1=mount -o port=2049,nolock,proto=tcp 192.168.0.1:/Documents/recalbox /recalbox/share
```

## SMB v2 ou superior <a id="smb-v-2-ou-superior"></a>

* Adicione ", vers = 2.0" / ", vers = 2.1" etc., por exemplo:

```text
sharenetwork_smb1=ROMS@192.168.0.1:recalbox/roms:username=recalbox,password=recalbox,vers=2.0
sharenetwork_smb2=SAVES@192.168.0.1:recalbox/saves:username=recalbox,password=recalbox,vers=2.0
```

* Suporte SMB no Windows:
  * 1.0: Win 2k/XP/Server 2003/Server 2003 R2
  * 2.0: Vista SP1/Server 2008
  * 2.1: Win7/Server 2008 R2
  * 3.0: Win8/Server 2012
  * 3.02: Win8.1/Server 2012
  * _3.11: Win10/Server 2016 \(não funciona a partir do RecalBox 4.1/Dec 2017\)_

## Exemplos com a versão 7.0 \(testado em Pi3, Pi4, XU4, PC X86-32 e 64 bits\)

Aqui estão os possíveis conjuntos CIFS / SMB:

### O comando básico

```text
sharenetwork_<nfs|smb><[0-9]>=<SHARE|ROMS|SAVES|BIOS|MUSIC|OVERLAYS|SCREENSHOTS|SHADERS|SCRIPTS>@<NAS>:<répertoire partagé>:<options>
```

### Toda a pasta SHARE

```text
sharedevice=NETWORK
sharewait=30
#TOUT LE DOSSIER SHARE EN ENTIER
sharenetwork_smb1=SHARE@<IP_DU_NAS>:<CHEMIN_NAS/SHARE>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
```

### Ou determinado \(s\) arquivo \(s\) apenas

Desde a versão v7.0 agora é possível selecionar apenas uma das pastas abaixo:

ROMS  
SAVES  
BIOS  
MUSIC  
OVERLAYS  
SCREENSHOTS  
SHADERS  
SCRIPTS

```text
sharedevice=NETWORK
sharewait=30
#UNIQUEMENT UNE SELECTION DES DOSSIER
sharenetwork_smb1=ROMS@<IP_DU_NAS>:<CHEMIN_NAS/ROMS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb2=SAVES@<IP_DU_NAS>:<CHEMIN_NAS/SAVES>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb3=BIOS@<IP_DU_NAS>:<CHEMIN_NAS/BIOS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb4=MUSIC@<IP_DU_NAS>:<CHEMIN_NAS/MUSIC>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb5=OVERLAYS@<IP_DU_NAS>:<CHEMIN_NAS/OVERLAYS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb6=SCREENSHOTS@<IP_DU_NAS>:<CHEMIN_NAS/SCREENSHOTS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb7=SHADERS@<IP_DU_NAS>:<CHEMIN_NAS/SHADERS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb8=SCRIPTS@<IP_DU_NAS>:<CHEMIN_NAS/SCRIPTS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
```

Se necessário, aqui está um exemplo do meu arquivo pessoal.  
Cada montagem CIFS pode apontar para um NAS específico.

Para sobreposições/overlays, você deve escolher de acordo com a resolução da sua tela

```text
sharedevice=NETWORK
sharewait=30

#FULL ROMS
sharenetwork_smb1=ROMS@192.168.1.112:C/RCB/romsfull:username=USER,password=PASS,vers=3.0
#ROMS SELECTION
#sharenetwork_smb1=ROMS@192.168.1.112:C/RCB/roms:username=USER,password=PASS,vers=3.0
#ROMS POUR TESTS
#sharenetwork_smb1=ROMS@192.168.1.110:TEST/roms:username=USER,password=PASS+,vers=3.0

sharenetwork_smb2=SAVES@192.168.1.112:C/RCB/saves:username=USER,password=PASS,vers=3.0
sharenetwork_smb3=BIOS@192.168.1.112:C/RCB/bios:username=USER,password=PASS,vers=3.0
sharenetwork_smb4=SCREENSHOTS@192.168.1.112:C/RCB/screenshots:username=USER,password=PASS,vers=3.0

#720p pour Pi0 Pi2 Pi3
#sharenetwork_smb5=OVERLAYS@192.168.1.112:C/RCB/overlays720:username=USER,password=PASS,vers=3.0
#1080p pour Pi4 XU4 et PC en 1080p
sharenetwork_smb5=OVERLAYS@192.168.1.112:C/RCB/overlays1080:username=USER,password=PASS,vers=3.0
```



### _Link externo:_ <a id="link-externo"></a>

**É altamente recomendável remover o suporte SMB v1 de sua máquina Windows:**

* [http://www.zdnet.com/article/windows-10-tip-stop-using-the-horribly-insecure-smbv1-protocol/](http://www.zdnet.com/article/windows-10-tip-stop-using-the-horribly-insecure-smbv1-protocol/)​
* ​[https://www.howtogeek.com/321072/how-to-disable-smbv1-and-protect-your-windows-pc-from-attack/](https://www.howtogeek.com/321072/how-to-disable-smbv1-and-protect-your-windows-pc-from-attack/)​
* [​https://www.spamtitan.com/blog/stop-smbv1-ransomware-attacks/](https://www.titanhq.fr/blog/comment-arreter-attaques-ransomware-smbv1/)​
* ​[https://www.bostonhelpdesk.com/disabling-smbv1-one-defense-against-wanna-cry-ransomware/](https://www.bostonhelpdesk.com/disabling-smbv1-one-defense-against-wanna-cry-ransomware/)

