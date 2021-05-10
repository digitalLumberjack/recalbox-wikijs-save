---
title: Use Wiimotes como controles
---

# Use Wiimotes como controles


>**Nota:**
>
>**O Dolphin** pode conectar até **4 wiimotes simultaneamente.**
>
>Para permitir o suporte de Wiimotes no Dolphin, a **dolphin bar mayflash** \(acessório\) é necessária:
>
>* Mude para o modo 4
{.is-warning}

* **Vá** para o arquivo [**recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) na **pasta** `recalbox/share/system` **.**
* Em seguida, **encontre este local**:

```text
## Wiimotes
## Real wiimotes must not be paired with recalbox system so that they can work with the wii emulator
## set emulatedwiimotes to 1 to emulate wiimotes with standard pads
wii.emulatedwiimotes=0
```

* **Modifique** a linha:  `wii.emulatedwiimotes=0`
* **Alterando de 0 para 1,** deixando assim:

  `wii.emulatedwiimotes=1`

Agora você pode jogar com os **Wiimotes**.

