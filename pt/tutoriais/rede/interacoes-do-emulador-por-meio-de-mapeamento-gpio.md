---
title: Interações do emulador por meio de mapeamento GPIO
---

# Interações do emulador por meio de mapeamento GPIO

Os comandos de rede são usados ​​para controlar partes do RetroArch. Para fazer isso, os comandos são enviados para o RetroArch via UDP \(User Datagram Protocol\).

Normalmente no **Recalbox**, esses comandos são transmitidos pela função **Hotkey** do controle. Por exemplo, para reiniciar o jogo, pressione as teclas **Hotkey + A** ou para salvar o jogo, pressione as teclas **Hotkey + Y.**

Lembre-se de que isso só funciona com **o RetroArch** / os **emuladores que fazem parte do libretro**.

### Ativar <a id="ativar"></a>

Mas esses comandos também podem ser enviados para RetroArch por meio de uma linha de comando ou pinos GPIO. Para fazer isso, você deve ativar a opção de **comandos de rede** no menu RetroArch ou modificar a seguinte linha no `retroarch.cfg` :

* `network_cmd_enable = «true»`​

### Transmita um comando via GPIO <a id="transmita-um-comando-via-gpio"></a>

#### Exemplos de aplicação: <a id="exemplos-de-aplicacao"></a>

Você está usando uma carcaça de console de jogo retro existente \(NES, N64, etc.\) e deseja usar o botão de reset original para reiniciar o jogo que está jogando atualmente e não para reiniciar todo o hardware \(Raspberry Pi, etc.\).

O script a seguir mostra como enviar o comando de rede **RESET** ao RetroArch por meio dos pinos 5 e 6 do GPIO para reiniciar o jogo atual.

```text
import RPi.GPIO as GPIO  
import time  
import socket  
# addressing information of target  
IPADDR = "127.0.0.1"  
PORTNUM = 55355  
# enter the data content of the UDP packet  
COMMAND = "RESET"  
# initialize a socket, think of it as a cable  
# SOCK_DGRAM specifies that this is UDP  
try:  
    s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)  
except socket.error:  
    print 'Failed to create socket'  
    sys.exit()  
GPIO.setmode(GPIO.BCM)  
GPIO.setup(3, GPIO.IN, pull_up_down=GPIO.PUD_UP)  
def exitEmulator(channel):  
    s.sendto(COMMAND, (IPADDR, PORTNUM))  
GPIO.add_event_detect(3, GPIO.FALLING, callback=exitEmulator, bouncetime=500)  
while True:  
    time.sleep(10)  
```

Com este script, não só é possível fazer **RESET** nos emuladores, mas também pode usar o comando necessário a partir vários comandos. Você pode **SAIR** dos emuladores \(retornar ao EmulationStation\), **CARREGAR** ou **SALVAR** um estado do jogo, **PAUSAR** o jogo, etc. Para fazer isso, basta substituir o comando **RESET** do **COMMAND = RESET** por um comando de sua escolha.


>**ATENÇÃO:**
>
>Este script pode não funcionar com todos os comandos de rede do RetroArch. Para alguns funciona, mas para outros, requer mais trabalho para fazê-lo funcionar \(por exemplo, FASTFORWARD\_HOLD\).
{.is-danger}

Você também pode remapear os pinos do Raspberry Pi.

E **não se esqueça: o Recalbox** já tem opções integradas para reiniciar, ligar e desligar o hardware que você está usando por meio de botões e GPIO:

​[https://recalbox.gitbook.io/tutorials/v/portugues/adicione-um-botao-liga-desliga-ao-seu-recalbox](https://recalbox.gitbook.io/tutorials/v/portugues/adicione-um-botao-liga-desliga-ao-seu-recalbox)​

​

## Comandos <a id="comandos"></a>

Os seguintes comandos são suportados pelo RetroArch:

* FAST\_FORWARD
* FAST\_FORWARD\_HOLD
* LOAD\_STATE
* SAVE\_STATE
* FULLSCREEN\_TOGGLE
* QUIT
* STATE\_SLOT\_PLUS
* STATE\_SLOT\_MINUS
* REWIND
* MOVIE\_RECORD\_TOGGLE
* PAUSE\_TOGGLE
* FRAMEADVANCE
* RESET
* SHADER\_NEXT
* SHADER\_PREV
* CHEAT\_INDEX\_PLUS
* CHEAT\_INDEX\_MINUS
* CHEAT\_TOGGLE
* SCREENSHOT
* MUTE
* NETPLAY\_FLIP
* SLOWMOTION
* VOLUME\_UP
* VOLUME\_DOWN
* OVERLAY\_NEXT
* DISK\_EJECT\_TOGGLE
* DISK\_NEXT
* DISK\_PREV
* GRAB\_MOUSE\_TOGGLE
* MENU\_TOGGLE

## ​Envie um comando através da linha de comando <a id="envie-um-comando-atraves-da-linha-de-comando"></a>

Você também pode enviar comandos de rede por meio da linha de comando no Linux. Veja como fazer:

*  `echo -n "QUIT" | nc -u -w1 127.0.0.1 55355`

RetroArch está na **porta 55355** por padrão.

