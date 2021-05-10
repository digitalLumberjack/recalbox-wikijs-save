---
title: Ativação fácil do desligamento seguro com uma carcaça Retroflag
---

# Ativação fácil do desligamento seguro com uma carcaça Retroflag

## Pré-requisitos​ <a id="pre-requisitos"></a>

* Um **Recalbox atualizado**
* Uma **carcaça Retroflag** suportando **desligamento seguro.**


>**Informação:**
>
>As unidades Retroflag compatíveis são:
>
>* nespi case +
>* superpi case
>* megapi case
{.is-info}


>**Atenção:**
>
>O nespi case comum não suporta esta função, somente a versão _plus_ \(nespi case +\)
{.is-danger}

## Instalação​ <a id="instalacao"></a>

* **Instale** o Raspberry Pi **na sua carcaça** seguindo as informações do **manual que vem junto com a mesma**.
* **Defina** o interruptor de **desligamento seguro para ON**


>Informações:
>
>Recalbox **gerencia nativamente** o desligamento seguro, você só precisa **ativá-lo** no arquivo **recalbox.conf**.
>
>Se você **não conhece** o arquivo **recalbox.conf**, veja aqui: [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)​
{.is-info}

**No início** do arquivo [**recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), há uma seção dedicada a **gestão de alimentação** do seu Recalbox:

​

### **------------ A - System Options -----------** <a id="a-system-options"></a>

### **Uncomment the system.power.switch you use** <a id="uncomment-the-system-power-switch-you-use"></a>

;system.power.switch=ATX\_RASPI\_R2\_6 \# [http://lowpowerlab.com/atxraspi/\#installation](http://lowpowerlab.com/atxraspi/#installation)​

;system.power.switch=MAUSBERRY \# [http://mausberry-circuits.myshopify.com/pages/setup](http://mausberry-circuits.myshopify.com/pages/setup)​

;system.power.switch=REMOTEPIBOARD\_2003 \# [http://www.msldigital.com/pages/support-for-remotepi-board-2013](http://www.msldigital.com/pages/support-for-remotepi-board-2013)​

;system.power.switch=REMOTEPIBOARD\_2005 \# [http://www.msldigital.com/pages/support-for-remotepi-board-plus-2015](http://www.msldigital.com/pages/support-for-remotepi-board-plus-2015)​

;system.power.switch=WITTYPI \# [http://www.uugear.com/witty-pi-realtime-clock-power-management-for-raspberry-pi](http://www.uugear.com/witty-pi-realtime-clock-power-management-for-raspberry-pi)​

;system.power.switch=PIN56ONOFF \# [https://recalbox.gitbook.io/tutorials/fr/xii-autres/ajouter-un-bouton-on-off-a-votre-recalbox](https://recalbox.gitbook.io/tutorials/fr/xii-autres/ajouter-un-bouton-on-off-a-votre-recalbox)​

;system.power.switch=PIN56PUSH \# [https://recalbox.gitbook.io/tutorials/fr/xii-autres/ajouter-un-bouton-on-off-a-votre-recalbox](https://recalbox.gitbook.io/tutorials/fr/xii-autres/ajouter-un-bouton-on-off-a-votre-recalbox)​

;system.power.switch=PIN356ONOFFRESET \# [https://recalbox.gitbook.io/tutorials/fr/xii-autres/ajouter-un-bouton-on-off-a-votre-recalbox](https://recalbox.gitbook.io/tutorials/fr/xii-autres/ajouter-un-bouton-on-off-a-votre-recalbox)​

;system.power.switch=PIN356PUSHRESET \# [https://recalbox.gitbook.io/tutorials/fr/xii-autres/ajouter-un-bouton-on-off-a-votre-recalbox](https://recalbox.gitbook.io/tutorials/fr/xii-autres/ajouter-un-bouton-on-off-a-votre-recalbox)​

. . .


>**Nota:**
>
>A **linha** que nos interessa, que gerencia o interruptor \(On/Off e Reset\) é  
>:; system.power.switch = PIN356ONOFFRESET \#  
>[https://recalbox.gitbook.io/tutorials/v/portugues/adicione-um-botao-liga-desliga-ao-seu-recalbox](https://recalbox.gitbook.io/tutorials/v/portugues/adicione-um-botao-liga-desliga-ao-seu-recalbox)
{.is-warning}

* **Simplesmente** remova o **`;`** na frente **desta linha** e **salve** esta modificação.
* **Reinicie** seu Recalbox, **os botões** em sua carcaça agora estão funcionais.


>**Informação:**
>
>Veja como os **botões reagem:**
>
>* **ON/OFF**: **Liga** ou **desliga** o sistema.
>* **RESET**: \[pressionar rapidamente no jogo\] = **Reinicia o Jogo** \[pressionar demorado no jogo\] = **Retorna ao menu ES** \[pressionar no menu ES \(rápido ou demorado\)\] = **Reinicia o Sistema**
>* ASSISTINDO: \[flashes\] = **durante a inicialização do sistema** \[corrigido\] = **quando o sistema está funcionando**
{.is-info}

