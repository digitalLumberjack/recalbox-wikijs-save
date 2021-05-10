---
title: Conectar Nintendo Joycon
---

# Conectar Nintendo Joycon


>**Aviso:**
>
>**Esta técnica** suporta **cada Joycon** como **dois controles independentes**, sem possibilidade de **combinar os Joycons em um único controle**.
{.is-danger}

![](https://images-na.ssl-images-amazon.com/images/I/81HcDCFUQFL._SL1500_.jpg)

* **Retire os Joycons** do Nintendo Switch e **pressione o pequeno botão preto** localizado entre **os botões L e R.**


>**Nota:**
>
>Esta operação **deverá ser repetid**a quando o **controle for desligado**.
{.is-warning}

* **Encontre o endereço Mac** do seu controle:

**Via Putty** na linha de comando, **insira** este comando abaixo, validando com `enter`:

`bluetoothctl`

* Seu controle é reconhecido como: `-[NEW] Device AA:88:EB:D2:59:34 Joy-Con (R)`

**Observe o endereço MAC** do seu controle! !

* Em seguida, **digite os seguintes comandos, um após o outro**:

  ```text
  agent on
  default-agent
  power on
  scan on
  ```

* **Aguarde** até que `bluetoothctl` **exiba seu dispositivo**, e **digite estes comandos**:

  ```text
  pair AA:88:EB:D2:59:34
  connect AA:88:EB:D2:59:34
  trust AA:88:EB:D2:59:34
  ```

* **Se esses comandos** retornarem `successfull`, então **seu Joycon está conectado** ao seu Recalbox.
* Vá para **as Opções de Controles** para **configurar as teclas** no **menu Emulationstation**.

