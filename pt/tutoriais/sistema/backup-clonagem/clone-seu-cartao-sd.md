---
title: Clone seu cartão SD
---

# Clone seu cartão SD


>Tenha cuidado se **quiser clonar para outro cartão SD!** Dois cartões SD **de fabricantes diferentes**, supostamente com a **mesma capacidade**, não terão exatamente o **mesmo tamanho**.  
>Portanto, você pode **não conseguir restaurar** o backup em um **cartão SD de outra marca**, a menos que seja maior do que o tamanho original.
{.is-danger}

* **Para clonar** seu cartão SD e ter um backup completo de seu recalbox, você pode usar estes softwares:

  * **Windows** : [Win32 Disk Imager](http://sourceforge.net/projects/win32diskimager/) com a função READ
  * **MacOS X** : ApplePi-Baker
  * **Linux** : use o comando DD em um terminal \(mais informações posteriormente\)

  ​

* Conecte seu cartão SD em seu PC usando o Linux. Determine qual dispositivo é o seu cartão SD

`sudo fdisk -l`

* Uma vez na pasta de backup, extraia e compacte o cartão SD com este comando:

`sudo dd if=/dev/sdX | gzip -9 > ./recalbox-20150411-sdb.img.gz` \(A letra X deve ser substituída pela letra determinada na etapa um.\)

* **Para restaurar** seu backup, conecte seu cartão SD formatado em FAT32 em seu PC e use este comando:

`gunzip ./recalbox-20150411-sdb.img.gz | sudo dd of=/dev/sdX` \(onde /dev/sdX é o seu cartão SD\). _Para monitorar o progresso do processo_`dd`_, abra um novo terminal e digite o seguinte comando_ `watch -n 5 sudo pkill -USR1 -n -x dd`

