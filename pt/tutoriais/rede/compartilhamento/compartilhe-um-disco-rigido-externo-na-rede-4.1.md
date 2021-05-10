---
title: Compartilhe um disco rígido externo na rede \(4.1\)
---

# Compartilhe um disco rígido externo na rede \(4.1\)


>**Objetivo:**   
>_Fazer com que um **disco rígido adicional** apareça \(não usado para roms, além de SHARE usando, por exemplo, SD\) c**onectado a USB no recalbox na rede do Windows** \(SAMBA\) próximo a  **\SHARE** como um NAS faria._
{.is-info}


>No **Windows** pode-se usar o **Putty em linha de comando** ou [WinSCP](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp), muito mais prático, pois compila **console, gerenciador de arquivos e editor de texto**, três funções utilizadas nesta manipulação.
{.is-warning}

**​**

**A manipulação foi testada na versão 4.1**, as versões anteriores exigiam mais modificações, como a montagem do disco no FSTAB.

* Conecte-se normalmente ao Recalbox: url: **recalbox** login: **root** mdp: **recalboxroot**
* Execute o comando **`mount -o remount,rw /`** para **desbloquear a proteção contra gravação** dos arquivos do sistema \(a **barra** no final é importante, o desbloqueio durará até a reinicialização\).
* Modifique /**etc/samba/smb.cfg** e adicione no final:

```text
[usb]
comment = usb
path = /media/usb0
writeable = yes
guest ok = yes
create mask = 0644
directory mask = 0755
force user = root
```

* **Salve e reinicie o Recalbox**, a modificação será **válida até a próxima atualização**.

