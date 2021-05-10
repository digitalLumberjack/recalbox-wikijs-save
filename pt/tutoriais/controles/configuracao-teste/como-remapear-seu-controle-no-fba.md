---
title: Como remapear seu controle no FBA
---

# Como remapear seu controle no FBA


>Nota:
>
>**Somente** para **3.2.11** e a **revisão anterior.**
{.is-warning}

## 4 botões em X Y B e A <a id="4-botoes-em-x-y-b-e-a"></a>

Se você deseja **alterar o mapeamento** de botões **para o FBA.**

* Você precisa **editar este arquivo**:`recalbox/scripts/generateEmuConfigs/createFBAConfig.sh`
* **Edite** esta parte:

```text
    fbabtn['a']='Y'

    fbabtn['b']='X'

    fbabtn['x']='B'

    fbabtn['y']='A'

    fbabtn['pageup']='L'

    fbabtn['pagedown']='R'
```

