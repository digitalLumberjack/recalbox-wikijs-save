---
title: Configuração para GameHat
---

# Configuração para GameHat

Para quem deseja usar o Recalbox 6.0 com o GameHat, veja como:

1. Grave a imagem do Recalbox 6.0 em seu cartão SD.
2. Usando um PC/Mac, onecte o cartão SD e adicione esses parâmetros ao arquivo "_config.txt_" na raiz do cartão: **hdmi\_force\_hotplug=1 avoid\_warnings=1 max\_usb\_current=1 hdmi\_group=2 hdmi\_mode=1 hdmi\_mode=87 hdmi\_cvt 640 480 60 6 0 0 0 hdmi\_drive=2 display\_rotate=0**
3. Conecte um controle \(com fio\) e insira as configurações de wi-fi.
4. Quando você estiver conectado à sua rede, através da interface web \(ou SSH\), edite o arquivo [`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) assim:  
   Altere o comando  
   **controllers.gpio.enabled=0** para: **controllers.gpio.enabled=1** Altere o comando 

   **controllers.gpio.args=map=1,2** para: **controllers.gpio.args=map=5 gpio=5,6,13,19,21,4,26,12,23,20,16,18,-1**

5. Desconecte o controle e reinicie o Recalbox.
6. Após reiniciar, aperte um botão e configure!

Link para a Wiki do GameHat: [https://www.waveshare.com/wiki/Game\_HAT](https://www.waveshare.com/wiki/Game_HAT) \(em inglês\)


>**Nota:**
>
>O guia de instalação oficial do GameHat para Recalbox é apenas para versões do Recalbox anteriores a 6.x. Este manual reflete as instruções atualizadas para a versão 6.0 do Recalbox!
{.is-info}

