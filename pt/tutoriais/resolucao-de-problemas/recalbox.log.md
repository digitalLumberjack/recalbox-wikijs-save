---
title: Recalbox.log
---

# Recalbox.log

* Primeiro, obtenha [acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)​
* Para obter as últimas 100 linhas do arquivo recalbox.log, execute `tail -100 /recalbox/share/system/logs/recalbox.log`

Aqui está um exemplo das **últimas 10 linhas** de um arquivo **recalbox.log**:

```text
 # tail -100 /root/recalbox.log
 ---- recalbox-config.sh ----
 wlan0 be used as wifi interface
 starting wifi
 udhcpc (v1.23.1) started
 Sending discover...
 Sending select for 192.168.12.182...
 Lease of 192.168.12.182 obtained, lease time 259200
 deleting routers
 adding dns 192.168.12.4
           inet addr:192.168.12.182  Bcast:192.168.12.255  Mask:255.255.255.0
```

