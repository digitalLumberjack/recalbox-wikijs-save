---
title: Recalbox.log
---

# Recalbox.log

* Premièrement obtenez [un accès root](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal)
* Pour obtenir les 100 dernières lignes du fichier recalbox.log exécutez `tail -100 /recalbox/share/system/logs/recalbox.log`

Voici un exemple des **10 dernières ligne** d'un fichier **recalbox.log** :

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

