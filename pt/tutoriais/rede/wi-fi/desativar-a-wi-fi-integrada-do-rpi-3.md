---
title: Desativar a Wi-Fi integrada do RPI 3
---

# Desativar a Wi-Fi integrada do RPI 3

Se você está decepcionado\(a\) com a velocidade do Wi-Fi integrado do raspberry pi 3 e quer desativá-lo, veja como fazer:

* **Conecte-se** ao [ssh via putty](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) ou [WinSCP](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp)​
* **Monte** a partição em modo gravação: `mount -o remount,rw /`
* **Edite** o seguinte arquivo: `nano /etc/modprobe.d/blacklist.conf`
* **Adicione** esta linha: `blacklist brcmfmac`
* **Salve** com `ctrl+x` + **`Y`** e **depois** `reboot`
* **Conecte** seu dongle Wi-Fi e **teste**.

