---
title: Sicherheit
---

# Sicherheit

Die Recalbox ist **standardmäßig nicht gesichert**.



Im Allgemeinen :

* Verbinden Sie Ihre Recalbox nicht direkt mit dem Internet. 
* Speichern Sie keine sensiblen/privaten Informationen auf Ihrer Recalbox. 
* Erstellen Sie regelmäßig Backups. 
* Schalten Sie Ihre Recalbox zwischen zwei Spielsitzungen aus.



## Root-Passwort

## 

Die Recalbox enthält standardmäßig ein Root-\(Superuser-\)Passwort.

Letzteres kann über das Menü **ERWEITERTE EINSTELLUNGEN** und dann **SICHERHEIT** geändert werden.


>**Hinweis :**  
>Dieser Vorgang muss nach jedem Update wiederholt werden, da Updates der Recalbox bestehende Dateien überschreiben und somit das Passwort auf den ursprünglichen Wert zurücksetzen.
{.is-warning}



## Netzwerkdienste

## 

Die Recalbox aktiviert standardmäßig mehrere Netzwerkdienste.

Obwohl sehr bequem, sind diese Dienste auch einfache Einstiegspunkte für Menschen mit schlechten Absichten.

Es wird empfohlen, **die Dienste** die Sie nicht nutzen **zu deaktivieren**, indem Sie den Abschnitt "_**Network**_" in der Datei **recalbox.conf** bearbeiten.



Um diese Datei zu bearbeiten, gibt es zwei Lösungen :

* Öffnen Sie eine Eingabeaufforderung und geben Sie nach der Verbindung `nano recalbox.conf` ein 
* Oder öffnen Sie auf Ihrem Computer ein Webfenster unter : `http://192.168.X.XX`um den Recalbox-Manager zu öffnen und die Konfiguration auf der entsprechenden Seite zu bearbeiten. 

## 

### Wifi

Wenn Sie keine Verbindung benötigen oder wenn Sie eine kabelgebundene Verbindung verwenden, deaktivieren Sie wifi :

```text
wifi.enabled=0
```

## 

### Samba

Samba ist eine sehr praktische Software, um Dateien von einem Computer zu übertragen.

Wenn Sie es nicht verwenden, deaktivieren Sie es durch die Konfiguration :

```text
system.samba.enabled=0
```


>**Information :**  
>Die Version 6.1 unterstützt passwortgeschützte Samba-Freigaben.
{.is-info}



## 

### Virtuelle Controller

Mit diesem Service können Sie Ihr Smartphone oder Tablett als Controller verwenden.

Wenn Sie solche Controller nicht verwenden, deaktivieren Sie den Dienst durch Konfigurieren von :

```text
system.virtual-gamepads.enabled=0
```



## Recalbox Manager

## 

Die Recalbox verfügt über einen eigenen Webserver, der auf Port 80 lauscht.

Dieser Server ermöglicht das Laden von roms per ziehen und ablegen und auch das Ändern der Konfiguration.


>**Achtung :**  
>Es ist jedoch ein wichtiger Zugangspunkt für jemanden, der versucht, die Kontrolle über Ihre Raspberry zu übernehmen.
{.is-danger}

Wenn Sie also den Recalbox-Manager nicht verwenden \(z.B. weil Sie bereits alle Roms Ihrer Träume auf Ihrer Raspberry haben, oder wenn Sie Ihre Roms lieber über die Samba-Software übertragen möchten\), können Sie ihn deaktivieren, indem Sie :

```text
system.manager.enabled=0
```

Diese Schritte sollten Ihre Box \(und damit alle an Ihr Netzwerk angeschlossenen Geräte\) etwas sicherer machen...

