# How to remap your control in FBA


>Note:
>
>**Only** for **3.2.11** and **previous revision**.
{.is-warning}

## 4 buttons in X Y B and A

If you want to **change the button mapping for the FBA**.

* You need to **edit this file:**`recalbox/scripts/generateEmuConfigs/createFBAConfig.sh`
* **Edit** this part:

  ```text
      fbabtn['a']='Y'

      fbabtn['b']='X'

      fbabtn['x']='B'

      fbabtn['y']='A'

      fbabtn['pageup']='L'

      fbabtn['pagedown']='R'
  ```

