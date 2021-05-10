---
title: Depurador Wi-Fi
---

# Depurador Wi-Fi

## Pré-requisitos​ <a id="pre-requisitos"></a>

* **Verifique** se o seu **dongle Wi-Fi** faz parte da [lista de compatibilidade](/compatibility/compatible-devices/dongle), OU, que **você tem uma placa com Wi-Fi**.
* Verifique se sua Wi-Fi está em WPA2, e que a senha não contém caracteres especiais, do contrário veja abaixo.
* Verifique se o seu wi-fi está no modo de descoberta.
* Se o seu **ponto de acesso usa o canal 12 ou 13**, ~~mude para um canal inferior ou~~ [~~atualize o firmware~~](https://raspberrypi.stackexchange.com/questions/43474/how-to-enable-wi-fi-channel-12-on-raspberry-pi-3/43616#43616) ==&gt; Consulte [Código Wi-Fi por país](codigo-wi-fi-por-pais.md).
* ​[Desative a Wi-Fi integrada do RPI 3](desativar-a-wi-fi-integrada-do-rpi-3.md) se desejar usar um dongle Wi-Fi USB.

## Configuração via Emulationstation​ <a id="configuracao-via-emulationstation"></a>

* **Conecte um teclado**
* **Vá** para o menu **do Emulationstation** \(Start\)&gt; Opções de rede&gt; Wifi, mude para **Ligado**
* **Insira SSID da rede, e a senha**
* Em seguida, **reinicie** o Recalbox.

## Configuração via recalbox.conf <a id="configuration-via-recalbox-conf-or-recalbox-conf-fr"></a>

* **Conecte** o Recalbox **por meio do cabo de rede no rj45**.
* **Edite** o arquivo [**recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) via [winscp](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp) e notepad ++ ou [putty](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) usando o **comando nano** para edição.
* **Ative a** Wi-Fi.
* **Remova os pontos-e-vírgulas** na frente de **ambas as linhas**.
* **Salve, faça logoff e reinicie** o Recalbox.

  ```text
  ## Activate wifi (0,1)   
  wifi.enabled=1   
  ## Wifi SSID (string)  
  wifi.ssid=new ssid   
  ## Wifi KEY (string)   
  wifi.key=new key
  ```

* Se **houver caracteres especiais** na **senha da Wi-Fi**: **Exemplo: 1a4a & 9f5g8! 41d** Você deve adicionar **barras invertidas** antes **desses caracteres** no arquivo **recalbox.conf**:

  ```text
  ## Wifi KEY (string)   
  wifi.key=1a4a\&9f5g8\!41d​
  ```

#### Diretamente no **Recalbox**: <a id="dans-recalbox-directement"></a>

Se você **não tem a possibilidade** de conectar um **cabo de rede**.

* **Conecte** um teclado.
* Você deve **sair do Emulationstation** com as seguintes teclas**:**

  **`F4`** seguido por **`Alt+F2`**

```text
user : root      
mdp : recalboxroot
```

* Em seguida, **edite** o arquivo [**recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) com **o comando nano:**

```text
nano /recalbox/share/system/recalbox.conf
```

* **Salve** as alterações `cltr+x` e `Y` e **reinicie** com \(`reboot` \)

## Solução de problemas​ <a id="solucao-de-problemas"></a>

### Caso n ° 1: falha sistemática <a id="caso-n-1-falha-sistematica"></a>

Se o Recalbox **não se conectar** ao roteador wi-fi, aqui estão **os pontos importantes a verificar**:

* **Verifique** se nenhum **cabo Ethernet está conectado** ao Recalbox. Na verdade, isso **desativa automaticamente** a Wi-Fi.
* **Verifique** se o **canal Wi-Fi do roteador** está **bem abaixo de 12**, porque nosso sistema atualmente usa um protocolo americano que não gerencia os canais 12 e 13.
* **Verifique** se **o protocolo Wi-Fi** está **em WPA** e não em WEP.

### Caso n ° 2: falha aleatória ou após \(re\) início <a id="caso-n-2-falha-aleatoria-ou-apos-re-inicio"></a>


>**Observações:**
>
>Se o seu Recalbox conseguir **se conectar ao Wi-Fi após configurá-lo**, mas você está tendo dificuldade **ao desligá-lo e ligá-lo novamente**, principalmente **desde a atualização de 09/02/2018**.
>
>Observe que é necessário **desligar o Recalbox corretamente.**  
>Isso significa que **você deve acessar o menu do Emulationstation** para **desligar o sistema antes de desligar a energia**.
{.is-warning}

**Como um lembrete**, como acontece com **qualquer computador**, **cortar a energia sem desligar corretamente** o Recalbox pode **corromper os dados**.

Em relação **ao Wi-Fi**, fizemos **uma atualização** permitindo **a edição de rede via Wi-Fi**, e o Recalbox **agora precisa salvar as informações do Wi-Fi ao desligar.** Por isso, **é fundamental desligá-lo corretamente**.

### Caso 3: nenhuma de suas dicas funciona <a id="caso-3-nenhuma-de-suas-dicas-funciona"></a>

 Se **nenhuma das dicas funcionar** ou se seu **dongle Wi-Fi** não **estiver na lista de compatibilidade**.

**Por favor, poste** um [dmesg completo](https://recalbox.gitbook.io/tutorials/v/portugues/resolucao-de-problemas/dmesg) **no fórum**, com **informações sobre o modelo do seu dongle**.

