---
title: Touches du clavier via GPIO
---

# Touches du clavier via GPIO

**Recalbox** comporte le **module retrogame** sous le nom de **recalbox-retrogame**. Ce module va **permettre d'utiliser les GPIO** afin de reproduire le comportement **d'un vrai clavier USB sous Recalbox.**


>**Attention :**  
>_**Ne fonctionne que si** on retrouve la ligne_ **`controllers.gpio.enabled=0`** _dans **recalbox.conf**_
{.is-danger}


>**Exemples :**
>
>* Si vous voulez **intégrer un Raspberry Pi dans une vieille console** et **réutiliser les boutons** de la façade \(ex: PAUSE/SELECT d'une Atari 7800\) :
>  * **Câbler** \(sur une borne d'arcade\) **un bouton** qui aurait **le même comportement** **que la touche Echap d'un clavier.**
>  * Ou tout simplement réussir à **se passer d'un clavier.**
{.is-success}

## Installation

### Câblage

Il faut utiliser des **boutons poussoir** \(qui remonte après un appui\) et relier **une borne à une masse** \(GROUND\) et **l'autre borne à un GPIO**.

### Script

Afin de **lancer automatiquement le module au démarrage de Recalbox,** il est important **d'ajouter un script.**

* **Créer** un ficher texte **"S99retrogame"** sans extension 
* **Ajouter les deux lignes de codes** suivantes : 

```text
/usr/bin/recalbox-retrogame
exit 0
```

* **Donner les droits** : `chmod 775 /etc/init.d/S99retrogame` 
* **Placez-le dans :** `/etc/init.d/`  
* **Rebooter et vérifier** en SSH \(via Putty par exemple\) si le module s'est bien lancé **grâce à la commande :** `ps aux|grep recalbox-retrogame`. Si la commande **retourne un identifiant,** c'est que vous avez **réussi !**

