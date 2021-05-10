---
title: Acesso root via Terminal
---

# Acesso root via Terminal

Para obter um terminal com acesso root no Recalbox, você tem duas opções:

## **SSH** <a id="ssh"></a>

Conecte-se via ssh ao Recalbox, com as seguintes credenciais:

**nome do host**: `recalbox` ou o **endereço IP do seu Recalbox** `192.168.x.xx`   
**login :**`root`   
**senha:**`recalboxroot`

* **Em um Mac:** você pode usar o terminal interno

> No Mac, se você receber este erro:: `Error opening terminal: xterm-256color`, na guia "Perfis" das preferências do terminal, depois "Avançado", mude “x-term 256 colors” para “x-term”.
>
> Se esse erro ocorrer quando você desejar usar o _nano_ no prompt de comando do Recalbox, digite primeiro `TERM=xterm`

* **No Windows**: você pode usar o [PuTTy](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) \(terminal recomendado\) ou o [MobaXTerm](https://mobaxterm.mobatek.net/)​
* **No Linux:** Use o terminal interno \(shell\)
  * **Digite** : `ssh root@your_recalbox_ip`

## Acesso direto <a id="acesso-direto"></a>

Na **interface do Emulationstation**:

* **Pressione** **`F4`** para **sair**.
* **Pressione** **`Alt + F2`** para **ir ao terminal**.
* Em seguida, **use as mesmas credenciais citadas acima**.


>**Importante:** Se você usar o acesso direto, é necessário ter um teclado conectado
{.is-info}

