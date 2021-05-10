---
title: Usando armazenamento externo
---

# Usando armazenamento externo


>**Informação:**  
>Você pode usar facilmente um **dispositivo de armazenamento USB** \(Pendrive, disco rígido externo com alimentação própria, etc.\) para armazenar suas roms, arquivos pessoais, etc...
>
>**Com este método**, o **sistema** \(no cartão SD\) e a **partição SHARE** \(no dispositivo\) **são separados**.
>
>Portanto, se você fosse **reinstalar seu sistema**, **manteria todos os seus dados de usuário**.  
>Você só terá que **reconectar seu dispositivo** ao Recalbox, **selecioná-lo no sistema e jogar**.
{.is-info}

## I - O formato da sua mídia <a id="i-o-formato-da-sua-midia"></a>

Primeiro, você deve usar **um dispositivo que use o seguinte sistema de arquivos**: **FAT32, EXFAT, EXT4 ou NTFS.**


>**Atenção:**
>
>As taxas de transferência podem **ser lentas** no caso de **NTFS**.  
>Certifique-se também de que o **sistema de arquivos** escolhido **é compatível com o sistema operacional do seu PC**.
{.is-danger}

\*\*\*\*

<table>
  <thead>
    <tr>
      <th style="text-align:center">Format<b>o</b>s</th>
      <th style="text-align:center">Tamanho m&#xE1;ximo do volume</th>
      <th style="text-align:center">Tamanho m&#xE1;ximo do arquivo</th>
      <th style="text-align:center">N&#xFA;mero m&#xE1;ximo de arquivos</th>
      <th style="text-align:center">Modo Leitura/Grava&#xE7;&#xE3;o</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">FAT</td>
      <td style="text-align:center">
        <p><b>2 TB</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
      </td>
      <td style="text-align:center">
        <p><b>4 GB</b>
        </p>
        <p><b>4</b>,2949<b> Go</b>
        </p>
      </td>
      <td style="text-align:center">Mais de <b>250 milh&#xF5;es</b>
      </td>
      <td style="text-align:center">
        <ul>
          <li>Windows : &#x2705;
            <br />
          </li>
          <li>Linux : &#x2705;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:center">NTFS</td>
      <td style="text-align:center"><b>256 TB</b>
      </td>
      <td style="text-align:center"><b>16 TB</b>
      </td>
      <td style="text-align:center"><b>4.294.967.295</b>
      </td>
      <td style="text-align:center">
        <p></p>
        <ul>
          <li>
            <p>Windows : &#x2705;</p>
            <p></p>
          </li>
          <li>Linux : &#x2705;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:center">Exfat</td>
      <td style="text-align:center"><b>128 PB</b>
      </td>
      <td style="text-align:center"><b>128 PB</b>
      </td>
      <td style="text-align:center"><b>2.796.202</b> por pasta</td>
      <td style="text-align:center">
        <p></p>
        <ul>
          <li>Windows : &#x2705;
            <br />
          </li>
          <li>Linux : &#x2705;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:center">ext4</td>
      <td style="text-align:center">
        <p><b>1 EB</b>
        </p>
        <p><b> </b>(limitado a 16 Tb pelo e2fsprogs)</p>
      </td>
      <td style="text-align:center"><b>16 TB</b>
      </td>
      <td style="text-align:center"> <b>4 bilh&#xF5;es</b>
      </td>
      <td style="text-align:center">
        <ul>
          <li>Windows : &#x274C;Leitura/Grava&#xE7;&#xE3;o via ext2fsd
            <br />
          </li>
          <li>Linux : &#x2705;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>


>**Atenção:**
>
>O RecalboxOS **não formatará** seu dispositivo, apenas **criará novos arquivos nele**.
{.is-danger}

## II - Opcional: sincronize seu dispositivo de armazenamento USB com o cartão SD <a id="ii-opcional-sincronize-seu-dispositivo-de-armazenamento-usb-com-o-cartao-sd"></a>


>**Informação:**  
>O Recalbox pode **sincronizar manualmente o seu dispositivo USB com o cartão SD.**  
>Esta etapa é **opcional**, mas deve ser executada **antes de alterar as configurações de armazenamento USB**.
{.is-info}

**Aqui estão as etapas:**

* **Inicie** o seu Recalbox.
* **Conecte seu dispositivo USB** quando você quiser
* \*\*\*\*[**Conecte-se em** SSH em seu pi.](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)
* **Digite** `cd /recalbox/scripts`
*  **O comando** `./recalbox-sync.sh list` fornece **a lista de dispositivos disponíveis.**

**​Por exemplo :**

```text
# ./recalbox-sync.sh list
INTERNALDEV
A80A-27A5 NO_NAME
```

Portanto, **o nome do meu dispositivo USB** é **NO\_NAME**, **o** **número do dispositivo** é **A80A-27A5**.  
Posso **sincronizar com:**

```text
./recalbox-sync.sh sync A80A-27A5
sending incremental file list
./
.keep
bios/
bios/lisez-moi.txt
bios/readme.txt
```

```text
sent 111,817,693 bytes received 8,256 bytes 9,723,995.57 bytes/sec total size is 111,758,686
speedup is 1.00 rsync error: some files/attrs were not transferred (see previous errors) (code 23)
 at main.c(1178) [sender=3.1.2]
```


>Notas:
>
>Aí está você! Não se preocupe com erros!  
>****Agora o **seu dispositivo USB** contém **a cópia dos dados do seu cartão SD.**  
>Você pode continuar com a próxima etapa.
{.is-warning}

## III - Configuração <a id="iii-configuracao"></a>

### Configurar o Recalbox <a id="configurar-o-recalbox"></a>

Para configurar o Recalbox para **usar um dispositivo de armazenamento USB.**

* **Conecte seu dispositivo** ao seu Recalbox, e **ligue-o.**
* Uma vez **na interface do Recalbox, pressione o botão START** em seu controle, vá para as **Configurações do sistema** e para **Armazenamento**.
* Agora **selecione seu dispositivo na lista**, **confirme** e **espere o sistema reiniciar.**


>**Informação:**
>
>**Durante esta fase de reinicialização**, o recalboxOS **criará na raiz** do seu dispositivo, uma nova pasta chamada **`recalbox`** que conterá toda a estrutura em árvore de sua **partição`/share`**.
{.is-info}

​

### Adicione seus arquivos <a id="adicione-seus-arquivos"></a>

Para **adicionar seus arquivos** \(ROMs, saves, BIOS, dados de scrappe, etc...\) ao seu **dispositivo de armazenamento**, você deve:

* **Desligar seu recalbox.**
* Em seguida, **conecte seu dispositivo ao PC.**
* Tudo o que você precisa fazer é copiar **seus arquivos** do PC **para o dispositivo**, **sem usar a rede local**.
* Assim que a **transferência for concluída**, tudo o que você precisa fazer é **reconectar o dispositivo** **ao seu Recalbox, ligá-lo e jogar.**

**​**

### Disco rígido invisível <a id="disco-rigido-invisivel"></a>

O que fazer se **após reiniciar o Recalbox ainda não conseguir v**er o disco rígido?


>**Informações:**
>
>**Às vezes**, depois de **selecionar o dispositivo no EmulationStation** e **reiniciar**, o Recalbox **falha ao criar o sistema de arquivos** nele.  
>Em seguida, ele **continua a usar os arquivos do cartão SD**.  
>Isso acontece especialmente com **alguns discos rígidos que demoram para inicializar**.
{.is-info}

O que você **pode fazer:**

* \*\*\*\*[**Faça login usando ssh.**](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)\*\*\*\*
* **Digite estes comandos:**`mount -o remount, rw /boot cd / boot nano recalbox-boot.conf`
* **Adicione** esta linha: `sharewait=30`
* **Salve** com **`Ctrl` + `X`**,**`Y`**,**`Enter`**
* **Digite** `reboot` e **confirme**, Recalbox **reiniciará.**

