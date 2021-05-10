---
title: Comandos de rede para RetroArch
---

# Comandos de rede para RetroArch


>Os comandos de rede são usados ​​para controlar partes do RetroArch. Para fazer isso, os comandos são enviados para RetroArch via UDP \(_User Datagram Protocol_\). Normalmente, esses comandos são enviados por meio da função **Hotkey** do controle. Por exemplo, para reiniciar o jogo você pressiona **Hotkey + A** ou para salvar o jogo você pressiona **Hotkey + Y**.
{.is-info}

## Ativar​ <a id="ativar"></a>

Mas esses comandos também podem ser enviados para o RetroArch por meio da linha de comando ou pinos GPIO. Para fazer isso, você deve ativar a opção de **comandos de rede** no menu RetroArch, ou, modificar a seguinte linha em`retroarch.cfg` :

* `network_cmd_enable = "true"`

​

## Enviar um comando através da linha de comando​ <a id="enviar-um-comando-atraves-da-linha-de-comando"></a>

Abaixo você vê como enviar um comando de rede por meio da linha de comando no Linux:

* `echo -n "QUIT" | nc -u -w1 127.0.0.1 55355`

RetroArch está na porta 55355 por padrão.

​

## Transmita um comando via GPIO​ <a id="transmita-um-comando-via-gpio"></a>

### Exemplo de aplicação: <a id="exemplo-de-aplicacao"></a>

Você está usando uma carcaça de console de jogo retro existente \(NES, N64, etc.\) e deseja usar o botão de reinicialização original para reiniciar o jogo que está jogando atualmente e não para reiniciar todo o hardware \(Raspberry Pi , etc.\).

O script a seguir mostra como enviar o comando de rede **RESET** ao RetroArch por meio dos pinos 5 e 6 do GPIO para reiniciar o jogo atual:

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

## ​Comandos​ <a id="comandos"></a>

Os seguintes comandos são suportados:

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

