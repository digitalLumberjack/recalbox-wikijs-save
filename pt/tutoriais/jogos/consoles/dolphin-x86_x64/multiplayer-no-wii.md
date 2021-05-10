---
title: Multiplayer no Wii
---

# Multiplayer no Wii


>Atenção:
>
>Válido para **todos os controles**, exceto **Wiimotes que funcionam diretamente**.
{.is-danger}


>Nota:
>
>Você deve primeiro seguir [este tutorial ](https://recalbox.gitbook.io/tutorials/v/portugues/jogos/consoles/dolphin-x86_x64/use-um-controle-que-nao-seja-wiimote)antes de continuar.
{.is-warning}

* **Vá para** o arquivo [**recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) na **pasta**`recalbox/share/system` e localize essa parte:

  ```text
  ## Wiimotes
  ## Real wiimotes must not be paired with recalbox system so that they can work with the wii emulator
  ## set emulatedwiimotes to 1 to emulate wiimotes with standard pads
  wii.emulatedwiimotes=0
  ```

* **Adicione** a seguinte linha após a configuração acima:

`wii.configfile=dummy`

Agora você pode **jogar multiplayer** no **Wii** com **seus controles**.

