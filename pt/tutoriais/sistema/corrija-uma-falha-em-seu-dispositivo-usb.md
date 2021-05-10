---
title: Corrija uma falha em seu dispositivo USB
---

# Corrija uma falha em seu dispositivo USB


>**Informação:**
>
>**Uma** **dica** que pode te ajudar, caso **sua mídia removível esteja corrompida**.
{.is-info}

* **O comando** `dmesg` no **SSH** deu a você uma boa **lista de mensagens de erro** na **mídia removível no fat32** após uma **desconexão forçada**.

`[ 270.403604] FAT-fs (sda5): error, fat_get_cluster: invalid cluster chain (i_pos 1592299)`

* Para **repará-lo** via Putty em ssh, **execute o seguinte comando**:

`fsck /dev/sda5`


>**Informação:**
>
>O **dispositivo USB** é visto em sda5.
{.is-info}

* **Escolha** **`1`** e **responda** à pergunta apertando **`Y`**.

  ```text
  fsck 1.42.13 (17-May-2015) 
  fsck.fat 3.0.28 (2015-05-16) 
  0x41: Dirty bit is set. Fs was not properly unmounted and some data may be corrupt. 
  1) Remove dirty bit 
  2) No action 
  ? 1 
    Contains a free cluster (2538261). Assuming EOF. 
    File size is 49861 bytes, cluster chain length is 0 bytes. 
    Truncating file to 0 bytes. 
  Reclaimed 4 unused clusters (65536 bytes). 
  Perform changes ? (y/n) y
  ```

* Em seguida, **reinicie** o seu raspberry.

