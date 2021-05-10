---
title: Montar automaticamente um armazenamento USB ao invés da partição SHARE
---

# Montar automaticamente um armazenamento USB ao invés da partição SHARE

É possível **usar uma unidade externa** como **partição SHARE**.


>Isso permite que você armazene todas suas ROMs, mídia e arquivos pessoais em uma mídia maior, como um Pen Drive ou um HD externo.
{.is-info}

* Você **vai precisar** de [acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal), bem como de **um dispositivo formatado em FAT32**. 
* Use **o comando** `mount` para **ver os volumes montados**:

  ```text
  rootfs on / type rootfs (rw)
  /dev/root on / type ext4 (rw,relatime,data=ordered)
  devtmpfs on /dev type devtmpfs (rw,relatime,size=242096k,nr_inodes=60524,mode=75 5)
  proc on /proc type proc (rw,relatime)
  devpts on /dev/pts type devpts (rw,relatime,gid=5,mode=620,ptmxmode=000)
  tmpfs on /dev/shm type tmpfs (rw,relatime,mode=777)
  tmpfs on /tmp type tmpfs (rw,relatime)
  sysfs on /sys type sysfs (rw,relatime)
  /dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
  /dev/mmcblk0p5 on /boot type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
  /dev/sda1 on /media/usb0 type vfat rw,sync,nodev,noexec,noatime,nodiratime,fmas=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro _
  ```

* **Localize a linha** que descreve a montagem do **seu dispositivo externo.** Deve ser **algo parecido** com isso:

`/dev/sda1 on /media/usb0 type vfat` **&lt;-----**

* **Copie** todos os dados **da partição SHARE** para **seu dispositivo**:

`cp -rv /recalbox/share/* /media/usb0/`


>Isso pode levar algum tempo, dependendo do tamanho da coleção de ROMs.
{.is-info}

* Agora, **edite o ponto de montagem** no arquivo **/etc/fstab :**

`vi /etc/fstab`

* **Pressione** "**i**" para **editar** 
* **Adicione** um "**\#**" para **comentar a seguinte linha**:

```text
/dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
```

Ficará **assim**:

```text
#/dev/mmcblk0p7 on /recalbox/share type vfat (rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,errors=remount-ro)
```

* E **adicione a nova linha** que seu dispositivo irá montar em **/recalbox/share** :

`/dev/sda1 /recalbox/share vfat defaults,rw 0 0` 

* Agora, **pressione "Esc", ":", "wq"** e finalmente "**Enter**" para salvar as **alterações e sair**.
* Agora você pode **reiniciar**.


>**Desde o Recalbox 4.0.0**, o sistema de armazenamento em mídia removível **é gerenciado diretamente no Emulationstation.**
>
>  
>Consulte o **tutorial** : [https://recalbox.gitbook.io/tutorials/v/portugues/sistema/instalacao/use-um-dispositivo-de-armazenamento-usb-no-recalbox](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/instalacao/use-um-dispositivo-de-armazenamento-usb-no-recalbox)
{.is-info}

