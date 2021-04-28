---
title: Pas de son jack
---

# Pas de son jack

Si vous **utilisez la prise jack** de votre rpi **comme sortie son** et que le son n'est **pas disponible** avec l'émulateur **N64**, veuillez suivre ce qui suit.

* **Connectez-vous** en [accès root](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal) 
* **Modifiez** le fichier de configuration de **mupen64plus** avec la commande suivante :

`nano /recalbox/configs/mupen64/mupen64plus.cfg`

* Puis **modifiez la ligne :**

```text
# Audio output to go to (0) Analogue jack, (1) HDMI OUTPUT_PORT = 1
```

**En :**

```text
# Audio output to go to (0) Analogue jack, (1) HDMI OUTPUT_PORT = 0
```

* Vous n'avez alors plus qu'à **enregistrer le fichier** avec `ctrl+x` **puis** `y` , **suivi de** `entrée`, puis à rebooter votre rpi ****avec **la commande** `reboot`.

Le son devrait **être disponible**.


>Cette modification **peut également être faite** à partir de [WinSCP](/v/francais/tutoriels/systeme/acces/acces-reseau-via-winscp) si vous êtes allergique **au terminal.**
{.is-info}

