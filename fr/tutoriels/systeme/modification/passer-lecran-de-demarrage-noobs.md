---
title: Passer l'écran de démarrage noobs
---

# Passer l'écran de démarrage noobs


>Vous pouvez **gagner quelques secondes au démarrage** en forçant **NOOBS** pour **démarrer directement** sur la partition**`boot`**.
{.is-info}

* **Mettez votre carte SD** dans votre **ordinateur** personnel.
* **Ouvrez la partition** `RECOVERY` et **créer un fichier nommé** `autoboot.txt`
* **Éditez** le fichier et **ajoutez la ligne** suivante :
  * Avec une Recalbox en **version 3.3.0**

    ```
    boot_partition=5
    ```

  * Avec une Recalbox en **version 4.0.0**

    ```text
    boot_partition=6
    ```



**Cela évitera** l'écran de démarrage NOOBS et vous **booterez directement** sur recalboxOS.  
  
Si vous voulez **réactiver l'écran de NOOBS**, il suffit de **supprimer le fichier** `autoboot.txt`

