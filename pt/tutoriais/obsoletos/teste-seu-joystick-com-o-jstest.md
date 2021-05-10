---
title: Teste seu joystick com o jstest
---

# Teste seu joystick com o jstest

Para testar seus controles, você pode usar o comando `jstest`, que permite listar informações seus controles.

* Primeiro você deve ter um [acesso root via terminal](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) 
* Para descobrir se seus controles foram detectados pelo sistema, use o seguinte comando:

  ```text
  cat /proc/bus/input/devices
  ```

* Depois que seus controladores são detectados, um evento especial é criado para cada um deles em `/dev/input`, você pode vê-los listando-os com este comando:

  ```text
  ls /dev/input/js*
  ```

* Agora você pode iniciar um comando especial para testar os botões e eixos do seu controle. Por exemplo, para testar seu primeiro controle no sistema:

  ```text
  jstest /dev/input/js0
  ```

* Você deve obter a seguinte resposta:

  ```text
  Driver version is 2.1.0.
  Joystick (Logitech Logitech Cordless RumblePad 2)
  has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
  and 12 buttons (BtnX, BtnY, BtnZ, BtnTL, BtnTR, BtnTL2, BtnTR2, BtnSelect, BtnStart, BtnMode, BtnThumbL, BtnThumbR).
  Testing ... (interrupt to exit)
  Axes:  0:     0  1:     0  Buttons:  0:off  1:off  2:off  3:off  4:off  5:off  6:off  7:off  8:off  9:off 10:off 11:off
  ```

**Agora,** você pode assistir **a resposta de todos os botões e eixos de seus controles.**

