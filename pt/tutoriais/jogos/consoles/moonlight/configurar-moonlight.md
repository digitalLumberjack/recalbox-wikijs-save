---
title: Configurar Moonlight
---

# Configurar Moonlight

## **1. Intro**​ <a id="1-intro"></a>


>**Moonlight** é uma **versão de código aberto** da tecnologia **Gamestream da NVidia.**
{.is-info}

**Se o seu PC** atender aos requisitos, você pode **transmitir via streaming a maioria dos seus jogos** para o Recalbox. Por outro lado, o Recalbox lê a **configuração do controle do EmulationStation** e o **converte para Moonlight**.

**​**

## Recursos do Moonlight no Recalbox: <a id="recursos-do-moonlight-no-recalbox"></a>

* **Transmita via streaming jogos** pela sua **rede local** ou pela **Internet**
* Suporte para até **4 jogadores**
* Até **1080p/60fps**
* **Decodificação H264 acelerada** por hardware **em qualquer versão do Raspberry Pi**
* Suporte para **teclado e mouse**
* Até **GFE 3.12**

## Pré-requisitos <a id="pre-requisitos"></a>

Configuração requisitada pelo Recalbox e pelo PC para desfrutar do Moonlight:

* Um **controle configurado no ES**
* **Conta Steam** \(opcional\) ou **jogos com suporte independente** \(consulte [https://shield.nvidia.com/game-stream](https://shield.nvidia.com/game-stream)\)
* Uma **GPU compatível com Nvidia** \(consulte [http://www.geforce.com/geforce-experience/system-requirements](http://www.geforce.com/geforce-experience/system-requirements)\)
* Uma **conexão Ethernet** é **altamente recomendada**, o **WiFi não é confiável o suficiente**.


>**Se você estiver atualizando** da **versão 3.3.0 para 4.0.0**, _leia com atenção!_
{.is-danger}

## **2. Configuração do Moonlight**​ <a id="2-configuracao-do-moonlight"></a>


>Verifique primeiro **a versão do seu Recalbox**
{.is-warning}

### Versão &gt;= 18.03.16 <a id="versao-greater-than-18-03-16"></a>

O **Recalbox v.18.03.16** oferece um **scraping mais agradável**, a capacidade de **transmitir de vários PCs da rede** e uma pequena **opção para encontrar hosts GFE** disponíveis.

Aqui está uma demonstração para encontrar **hosts GFE**, conectá-los e iniciá-los:

```text
# /recalbox/scripts/moonlight/Moonlight.sh find
Listing available GFE servers :
GFE Host WIN10(192.168.111.35) GeForce GTX 760 running GFE 3.12.0.84
You can now run /recalbox/scripts/moonlight/Moonlight.sh pair <host>
<host> can be empty (not recommended if you have several GFE hosts), an IP or a PC name
# /recalbox/scripts/moonlight/Moonlight.sh pair
() /recalbox/share/system/configs/moonlight/moonlight.conf | /recalbox/share/system/configs/moonlight/keydir
Searching for server...
Connect to 192.168.111.35...
Generating certificate...done
Please enter the following PIN on the target PC: 3843
Succesfully paired
YOLO MODE !!!
# /recalbox/scripts/moonlight/Moonlight.sh init
YOLO Mode
Adding and scraping Brutal Legend ...
Adding and scraping Sacred Citadel ...
Adding and scraping Just Cause 3 ...
Adding and scraping Street Fighter V ...
Adding and scraping Just Cause 2 Multiplayer ...
Adding and scraping Tales of Zestiria ...
Adding and scraping Grand Theft Auto V ...
Adding and scraping Hell Yeah! Wrath of the Dead Rabbit ...
Adding and scraping Ultra Street Fighter IV ...
Adding and scraping Diablo III ...
Adding and scraping Pro Evolution Soccer 2017 ...
Adding and scraping Bionic Commando Rearmed ...
Adding and scraping Just Cause 2 ...
Adding and scraping Pro Evolution Soccer 2016 ...
Adding and scraping Broforce ...
Adding and scraping DmC: Devil May Cry ...
Adding and scraping Naruto Shippuden: Ultimate Ninja Storm 4 ...
Adding and scraping Steam ...
```

### ​a. Versão &gt;= 4.0.0.0 beta1 <a id="a-version-greater-than-4-0-0-0-beta1"></a>

**Recalbox 4.0.0** apresenta **novos recursos** para o Moonlight:

* **Configuração automática** de gamepads para Moonlight
* **Configuração fácil:** você **pode não precisar especificar** o endereço IP do computador
* **As configurações** do Moonlight **podem ser personalizadas** no arquivo:`/recalbox/share/sysem/sysem/configs/moonlight/moonlight.conf`. Ou **pela rede**: `\\Recalbox\User Data\configs\moonlight\moonlight\moonlight.conf`


>**Observe que ..:**
>
>* O suporte ao Moonlight no Recalbox 4.0.0.0-beta2 é muito melhor em comparação com o 4.0.0.0-beta1. Certifique-se de atualizá-lo.
>* A configuração **"nenhuma configuração"** só funciona de **forma confiável** se você tiver apenas um **PC compatível** com o gamestream. Caso contrário, você precisará **especificar o endereço IP do host do gamestream** no arquivo de configuração.
>* Pode haver momentos em que **IPv6** é **usado em vez de IPv4. Desative o IPv6** no Windows.
>* Sempre use a **versão mais recente do Recalbox**. A versão 4.0.0.0-beta4 trouxe suporte GFE 2.11
>* Se você estiver travado no emparelhamento:
>  * Exclua**`/recalbox/share/system/system/configs/moonlight/keydir`**
>  * Desconecte **todos os periféricos no GFE,**
>  * Faça login em sua conta NVidia.
>  * E tente emparelhar novamente.
{.is-info}

#### Configuração do controle: <a id="configuracao-do-controle"></a>

Se o **seu controle não responder como esperado** no **Moonlight**, **remapeie-o no EmulationStation e tente novamente**.

**​**

#### Configuração do seu Recalbox: <a id="configuracao-do-seu-recalbox"></a>

Agora você está pronto **para configurar** seu Recalbox para **streaming de jogos:**

1. **Saia do EmulationStation** \(via SSH ou pressionando F4\)
2. **Faça login** como **root**
3. **Digite** `cd /recalbox/scripts/moonlight`
4. **Certifique-se** de que **apenas o seu PC compatível** com o gamestream **esteja disponível na rede.**
5. **Execute** `./Moonlight.sh pair`, e **insira o número fornecido no seu computador**
6. Uma vez emparelhado, **execute** `./Moonlight.sh init` para **criar links de rom** para o **Emulationstation + dados de scrap**
7. **Reinicie o EmulationStation** e aproveite o **Moonlight!**

   ```text
   Using username "root".
   # /etc/init.d/S31emulationstation stop
   # cd /recalbox/scripts/moonlight
   # ./Moonlight.sh pair
   Moonlight Embedded 2.2.0 (EMBEDDED;CEC;PI)
   Too many options: No such file or directory
   Moonlight Embedded 2.2.0 (EMBEDDED;CEC;PI)
   Searching for server...
   Connect to 192.168.0.28...
   Generating certificate...done
   NVIDIA GeForce GTX 960M, GFE 2.11.4.0 (protocol version 7)
   Please enter the following PIN on the target PC: 3660
   1017 / 1017
   Succesfully paired
   # ./Moonlight.sh init
   Fetching games from  ...
   Scraping games ...
   # /etc/init.d/S31emulationstation start
   ```


>**Etapa opcional** se você tiver **outros PCs compatíveis** com **Moonlight:**
>
>* Edite `/recalbox/share/share/sysem/configs/moonlight/moonlight.conf`
>* Exclua o **\#** antes de`#adresse =`
>* Adicione seu endereço IP. Ex: `adresse = 192.168.0.0.12`
>* Salve seu arquivo
{.is-warning}

**Por enquanto**, o Recalbox pode **gerenciar apenas um** PC gamestream. **O suporte** para **vários PCs host** pode chegar em uma **versão futura.**

**​**

### b. Versão &gt;= 3.3.0 beta15 <a id="b-version-greater-than-3-3-0-beta15"></a>

1. **Saia do EmulationStation** \(via SSH ou pressionando F4\) /etc/init.d/S31emulstation stop
2. **Faça login** como **root**
3. **Certifique-se** de que /recalbox/share/roms/moonlight **existe**. Caso contrário,`mkdir -p /recalbox/share/roms/moonlight`.
4. Digite `cd/recalbox/scripts/moonlight`
5. Edite **Moonlight.sh** e defina **"moonlight\_ip="** o endereço IP de onde **você deseja fazer o stream**.  **Por exemplo:** se o endereço IP do seu PC for "192.168.1.1", edite como "moonlight\_ip=192.168.1.1", salve e saia do editor de texto **Ou** em SSH,`nano /recalbox/scripts/moonlight/Moonlight.sh`**.** ​ 
6. **Execute**`./Moonlight.sh pair`, e **insira o número fornecido no seu computador**
7. Uma vez **emparelhado, execute** `./Moonlight.sh init` para **criar links de rom no EmulationStation + dados de scrap.**
8. **Execute** `./Moonlight.sh map` para c**onfigurar seu controle** \(controle único somente suportado no momento, teclado + mouse funcionam perfeitamente\)
9. **Reinicie o EmulationStation** `/etc/init.d/S31emulstation restart`e **aproveite o Moonlight!**

**​**

### c. 3.3.0 beta7 &lt;= Versão &lt;= Versão &lt; 3.3.0 beta15 <a id="c-3-3-0-beta7-less-than-version-less-than-version-less-than-3-3-0-beta15"></a>

* Vamos para **"//recalbox/roms/moonlight"** ou por **ssh** em**"//recalbox/share/roms/moonlight po"**

**Nesta pasta você tem:**

```text
Moonlight.sh.hide
Moonlight.conf
```

### d. Versão &lt; 3.3.0 beta7 : <a id="d-version-less-than-3-3-0-beta7"></a>

_Obtenha o Moonlight.sh.hide aqui:_

* Renomeie **Moonlight.sh.hide** para **Moonlight.sh**, abra com Notepad ++ ou outro o Moonlight.sh e substitua por este: [Moonlight.sh.hide\_v2](https://github.com/steak3/recalbox-buildroot/blob/unified/board/recalbox/share/roms/moonlight/Moonlight.sh.hide_v2)​
* Substitua em **moonlight\_ip=YOUR\_IP\_HERE** par **moonlight\_ip=192.168.x.x** &lt;=== este é o endereço IP do seu PC
* Salvar e sair

Remova possíveis preocupações em **Moonlight.conf** aqui.

​

**Em SSH** sob comando **/recalbox/share/roms/moonlight** :

 `./Moonlight.sh paire`

Se este **comando for bem-sucedido,** você receberá **esta mensagem**:

```text
Too many options: No such file or directory
Cannot open config file: hosts / 192.168.x.x.x.conf
Certificate generation ... done
Please enter the following PIN code on the target PC: 9958
Pairing successful
```

* No seu PC, você tem um pop-up da Nvidia para inserir o seu código PIN
* Agora, em "**Configuração do controle**", execute este comando `./Moonligh.sh carte`e siga as informações na tela.
* **Reinicie** o Recalbox e **aproveite o Moonlight!**

.

## **3. ANEXO**​ <a id="3-anexo"></a>

### v4.0.0 específica <a id="v-4-0-0-specifique"></a>


>**Somente usuários avançados:**  
>você pode **transmitir de um computador remoto pela Internet.**
{.is-danger}

* Você precisará editar **"//recalbox/scripts/moonlight/Moonlight.sh"**para
  * Especifique **o endereço IP do host remoto**.
  * **Defina o mesmo endereço IP** em **moonlight.conf**
  * E **configure o encaminhamento de porta** de acordo com:[ https://github.com/moonlight-stream/moonlight-android/wiki/Setup-Guide\#streaming-over-the-internet](https://github.com/moonlight-stream/moonlight-android/wiki/Setup-Guide#streaming-over-the-internet)

​

### v3.3.0 específica <a id="v-3-3-0-specifique"></a>


>Você pode alterar **a configuração de exibição** no **Moonlight :**
>
>* **720p em 30 quadros/segundo - 1080p em 30 quadros/segundo**
>* **720p em 60 quadros/segundo - 1080p em 60 quadros/segundo**
{.is-info}

​Você deve alterar a linha 23 em **Moonlight.sh** :

cmd="moonlight stream -remote **-1080 -60fps** -keydir ${moonlight\_keydir} -mapping ${moonlight\_mapping} ${moonlight\_ip}"


>**Substitua** as configurações de **negrito** de acordo com **suas necessidades.**
{.is-warning}

