---
title: Monte a pasta SHARE do Recalbox remotamente em seu Linux
---

# Monte a pasta SHARE do Recalbox remotamente em seu Linux

Se você deseja montar a pasta SHARE de seu Recalbox em um computador rodando Linux, aqui está o procedimento:

* em `/etc/nsswitch.conf` : adicione wins no final da linha "hosts:"
* em `/etc/fstab`, adicione a linha:

  ```text
  //RECALBOX/share /mnt/recalbox cifs _netdev,noauto,user,username=root 0 0
  ```

* crie a pasta /mnt/recalbox :

  ```text
  mkdir /mnt/recalbox
  ```

* Agora você pode montar a partição SHARE como um usuário:

  ```text
  mount /mnt/recalbox
  ```

