---
title: Os drivers dos controles PS3
---

# Os drivers dos controles PS3


>**Informação:**
>
>Existem diferentes versões de controles PS3 _sixaxis_ e _dualshock3_ no mercado.
{.is-info}

**Recalbox** suporta joysticks **oficiais nativamente**. Mas, se você tem **um clone GASIA ou Shanwan,** você precisa **modificar o driver** em [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) **modificando a linha**:

`controllers.ps3.driver=official]`

| Modelo | Driver |
| :--- | :--- |
| Sixaxis | `official` |
| Dualshock3 | `official` |
| US Sixaxis | `shanwan` ?? |
| Shanwan | `shanwan` |
| Gasia | `gasia` |

Para determinar que tipo de clone você possui \(GASIA ou SHANWAN\), você pode:

* **Conectar** seu controle **via USB**
* Então, usar o comando [dmesg](https://recalbox.gitbook.io/tutorials/v/portugues/resolucao-de-problemas/dmesg)​

Você conseguirá ver o **tipo de controle** que possui.

