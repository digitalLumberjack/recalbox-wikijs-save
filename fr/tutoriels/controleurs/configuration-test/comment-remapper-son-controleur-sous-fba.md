---
title: Comment remapper son contrôleur sous FBA
---

# Comment remapper son contrôleur sous FBA


>_**Remarque :**_
>
>**Seulement** pour **3.2.11** et **la révision précédente.**
{.is-warning}

## 4 boutons on X Y B et A

Si vous souhaitez **changer le mapping** des boutons **pour FBA.**

*  Il faut **éditer ce fichier :** `recalbox/scripts/generateEmuConfigs/createFBAConfig.sh`  
* **Modifier** cette partie :

```text
    fbabtn['a']='Y'

    fbabtn['b']='X'

    fbabtn['x']='B'

    fbabtn['y']='A'

    fbabtn['pageup']='L'

    fbabtn['pagedown']='R'
```

