---
title: Connecter une Manette IPEGA
---

# Connecter une Manette IPEGA

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Ll99c7r4LdpvjDZhjVL%2F-Ll99fj3K7qBiFjXbCZ5%2Fimage.png?alt=media&token=1b3dd4fb-8b27-4152-82b6-76ec0b8b6f27)

## Astuces pour les manettes IPEGA <a id="astuces-pour-les-manettes-ipega"></a>

**Connecter votre Recalbox** **au réseau** puis via **Putty.**

* **Trouver la référence** de votre manette via la commande :`evtest` 

_**Exemple :**_ `PG-9055` 

* **Adapter** `ATTRS{name}=="PG-9055"` en fonction de **la référence de votre manette** et **copier/coller** l'ensemble de **ces commandes** dans la fenêtre de **Putty, puis valider par la touche** `enter` .

```text
mount -o remount, rw /
echo 'SUBSYSTEM=="input", ATTRS{name}=="PG-9055", MODE="0666", ENV{ID_INPUT_JOYSTICK}="1"'>>/etc/udev/rules.d/99-joysticks-exotics.rules
reboot && logout
```

## Connexion en Bluetooth <a id="connexion-en-bluetooth"></a>

* **Faire un reset** de votre manette **IPEGA, si vous l'utilisez avec un autre périphérique.** 
* **Mettre** le mode **`Home+X`** 
* **Exécuter** la recherche de manette **bluetooth** dans le menu Emulationstation &gt; Options Manettes

Vous pouvez vérifier si votre IPEGA est déjà dans la liste de ce fichier : `/etc/udev/rules.d/99-joysticks-exotics.rules`


>_**Remarque :**_
>
>**Si ce n'est pas le cas**, merci d'[**ouvrir une issue**](https://gitlab.com/recalbox/recalbox/-/issues) pour qu'elle soit **ajouté à la prochaine mise à jour** de Recalbox.
{.is-warning}

