---
title: Acesse uma partição em modo gravação
---

# Acesse uma partição em modo gravação


>**Informação:**
>
>Desde a versão 4.0.0, o sistema de partições foi alterado para limitar a corrupção do seu microsd.
{.is-info}

Portanto, as seguintes partições são acessíveis apenas como leitura:

* Partição do boot `/boot`
* Partição do sistema `/`

​**Dependendo das alterações** que você deseja fazer:

* `mount -o remount,rw /boot` **ou**
* `mount -o remount,rw /`

Depois que as alterações forem feitas, **a partição** voltará a ser **somente leitura** na próxima vez que o **sistema for reiniciado**.

## Winscp usando console​ <a id="winscp-en-utilisant-la-console"></a>

**Clique** no **ícone do console** e **digite** o comando **para deixar a partição em modo gravação**.

![](https://github.com/lackyluuk/recalbox-os/raw/master/wiki/images/WinSCP.PNG)

