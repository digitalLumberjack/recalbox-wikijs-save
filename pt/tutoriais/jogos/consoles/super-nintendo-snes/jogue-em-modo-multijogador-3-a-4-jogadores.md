---
title: Jogue em modo multijogador \(3 a 4 jogadores\)
---

# Jogue em modo multijogador \(3 a 4 jogadores\)

**Até 4 jogadores podem jogar** no emulador SNES no **Recalbox.**

Se você quiser **desfrutar do modo multijogador** no SNES, precisará de um controle por jogador, **devidamente configurado**.

* **Edite** o arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) para **substituir o emulador** SNES por `snes9x_next`

  ```text
  # ------------ I - EMULATORS CHOICES ----------- #
  ## You can override the global configuration here
  snes.core=snes9x_next
  ```

* **Salve** e **reinicie** o Recalbox corretamente.
* **Comece um jogo de SNES** \(como Micro Machines, por exemplo\).
* **Abra o menu Retroarch** pressionando **`Hotkey + B`**.
* **Altere as** seguintes **configurações**:

  ```text
  Setting / Configuration / Save Configuration On Exit : ON
  Setting / Input / User 2 Device Type / Multitap
  Quick menu / Restart Content
  ```

* Você pode **redefinir** `Salvar Configuração ao Sair` para`OFF` **após reiniciar** o jogo.

E está feito! O jogo está funcionando e você é o rei da noite!

