---
title: Lista negra de áudio dos controles PS4
---

# Lista negra de áudio dos controles PS4

## Recalbox 4.1​ou Superior <a id="recalbox-4-1-ou-superior"></a>

Os controles PS4 são nativamente compatíveis via Bluetooth e USB. Se você tiver problemas com o áudio ao conectar ao USB, siga o próximo capítulo.

## Recalbox 4.0.X​ <a id="recalbox-4-0-x"></a>


>Alguns **controles PS4** têm um **módulo de áudio integrado** que impede a **reprodução de som na tv** ou nos **alto-falantes**.  
>Você precisa colocar este módulo de áudio na **lista negra\(**_**blacklist**_**\)** para **ter som** no seu dispositivo.
{.is-info}

​

* **Conecte** ao ssh [via **Putty**](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)**​**
* Monte a partição [**como gravação**:](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesse-uma-particao-em-modo-gravacao)​

```text
mount -o remount,rw /
```

* **Edite** o arquivo:

```text
nano /etc/modprobe.d/blacklist.conf
```

* **Adicione** esta linha:

```text
blacklist snd-usb-audio
```

* **Salve** e **reinicie**

