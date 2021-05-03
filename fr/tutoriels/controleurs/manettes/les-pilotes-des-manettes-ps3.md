---
title: Les pilotes des manettes PS3
---

# Les pilotes des manettes PS3


>**Information :**
>
>Il existe différentes versions de manettes PS3 _sixaxis_ et _dualshock3_ sur le marché.
{.is-info}

**Recalbox** supporte **par défaut** les manettes **officielles.**  
Mais si vous possédez **un clone GASIA ou Shanwan,** vous devez **modifier le pilote** dans [recalbox.conf](/fr/usage-basique/premieres-notions/le-fichier-recalbox.conf) en **modifiant la ligne :**

`controllers.ps3.driver=official`

| Modèle | Pilote |
| :--- | :--- |
| Sixaxis | `official` |
| Dualshock3 | `official` |
| US Sixaxis | `shanwan` ?? |
| Shanwan | `shanwan` |
| Gasia | `gasia` |

 Pour déterminer quel type de clone vous possédez \(GASIA ou SHANWAN\), vous pouvez :

* **Brancher en USB** votre manette
* Puis **utiliser la** [commande dmesg](/fr/tutoriels/depannage/dmesg) 

Vous devriez alors voir **le type de manette** que vous possédez.

