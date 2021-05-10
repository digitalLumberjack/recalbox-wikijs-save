---
title: Conectar controles IPEGA
---

# Conectar controles IPEGA

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Ll99c7r4LdpvjDZhjVL%2F-Ll99fj3K7qBiFjXbCZ5%2Fimage.png?alt=media&token=1b3dd4fb-8b27-4152-82b6-76ec0b8b6f27)

## Dicas para controles IPEGA​ <a id="dicas-para-controles-ipega"></a>

**Conecte seu Recalbox à rede**, em seguida, via **Putty.**

* **Encontre a referência do seu controle** por meio do comando :`evtest`

_**Exemplo :**_ `PG-9055`

* **Adapte** `ATTRS{name}=="PG-9055"` de acordo com a referência de seu controlador e **copie / cole** todos **esses comandos** na janela do **Putty e valide com a tecla** `enter` .

  ```text
  mount -o remount, rw /
  echo 'SUBSYSTEM=="input", ATTRS{name}=="PG-9055", MODE="0666", ENV{ID_INPUT_JOYSTICK}="1"'>>/etc/udev/rules.d/99-joysticks-exotics.rules
  reboot && logout
  ```

## Conexão Bluetooth:​ <a id="conexao-bluetooth"></a>

* **Reinicie** seu controle **IPEGA**, **se estiver usando-o com outro dispositivo.**
* **Modo de configuração`Home+X`**
* **Procure por um controle bluetooth** no menu Emulationstation&gt; Opções de Controle

Você pode verificar se o seu ipega já está na lista neste arquivo:`/etc/udev/rules.d/99-joysticks-exotics.rules`


>**Nota:**
>
>**Se não estiver**, **abra um problema** para que seja **adicionado à próxima atualização** do Recalbox:  
>[https://gitlab.com/recalbox/recalbox/issues](https://gitlab.com/recalbox/recalbox/issues)
{.is-warning}

