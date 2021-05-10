---
title: Encontre as informações sobre os controles
---

# Encontre as informações sobre os controles

Existem alguns comandos úteis para obter informações sobre dispositivos que podem ser usados ​​para ajudar a solucionar problemas:

*  `cat /proc/bus/input/devices` para exibir uma lista de dispositivos disponíveis
*  `lsusb -v` para obter informações sobre dispositivos USB
*  `for i in /dev/input/event*; do echo $i;udevadm info -q all -n $i;done` para obter informações do _udev_ sobre os dispositivos que foram mapeados durante um evento
* `for i in /dev/input/event*; do echo $i;(evtest $i) & ( evtestpid=$! && sleep 0.1 && kill -15 $evtestpid );done`
*  irá listar todos os botões / eixos / chaves encontrados \(mesmo se for um teclado\)

Sempre que você executar um desses comandos, é melhor não colar toda a saída no fórum ou bate-papo IRC. Em vez disso, use algo como [http://pastebin.com/](http://pastebin.com/), cole sua saída e forneça o link para as pessoas com quem você entrar em contato.

