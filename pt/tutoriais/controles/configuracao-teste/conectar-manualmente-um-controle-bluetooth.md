---
title: Conectar manualmente um controle bluetooth
---

# Conectar manualmente um controle bluetooth

Você pode conectar seu joystick bluetooth manualmente.

Você precisará de [acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) para isso.

​

## Se a versão do Recalbox for menor ou igual a 4.0​ <a id="se-a-versao-do-recalbox-for-menor-ou-igual-a-4-0"></a>

Coloque o seu joystick bluetooth no modo de associação e digite : `hcitool scan`

Isso obterá o endereço mac do controle: `aa:bb:cc:dd:ee:ff Name:Bluetooth HID`

Em seguida, crie a conexão com o controle: `hidd --connect aa:bb:cc:dd:ee:ff`

E reinicie o Emulationstation : `/etc/init.d/S31emulationstation start`

## Se a versão do Recalbox for maior ou igual a 4.1 <a id="se-a-versao-do-recalbox-for-maior-ou-igual-a-4-1"></a>

Você tem duas opções. Uma pode não funcionar, se isso acontecer, tente a próxima. Inicie seu controlador no modo de emparelhamento, verifique se você o redefiniu anteriormente e se removeu quaisquer associações existentes. Atenção: por enquanto, você deve iniciar seu controle Bluetooth **depois** que o EmulationStation for iniciado.

​

### Usando o comando simple-agent <a id="usando-o-comando-simple-agent"></a>

Encontre o endereço mac do seu controle \(em formato maiúsculo\) usando : `/recalbox/scripts/bluetooth/test-device list`

Tente várias vezes se o seu controle não aparecer na lista. Se, após algumas tentativas, seu controle ainda não estiver listado, vá para o método B.

Se o seu controlador estiver listado, digite:`/recalbox/scripts/bluetooth/simple-agent hci0 "AA:BB:CC:DD:EE:FF"`

Onde **AA: BB: CC: DD: EE: FF é o endereço mac do seu dispositivo em maiúsculas**. Pode ser solicitado um código PIN, consulte a documentação do seu joystick. Se você ainda não conseguir emparelhar, tente o próximo método.

### ​Usando o comando bluetoothctl <a id="usando-o-comando-bluetoothctl"></a>

Inicie o `bluetoothctl` e digite os seguintes comandos:

```text
agent on
default-agent
power on
scan on
```

Aguarde até `bluetoothctl` listar seu dispositivo e:

```text
pair AA:BB:CC:DD:EE:FF
connect AA:BB:CC:DD:EE:FF
trust AA:BB:CC:DD:EE:FF
```

