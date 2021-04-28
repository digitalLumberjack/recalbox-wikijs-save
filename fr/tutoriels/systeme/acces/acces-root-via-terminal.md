---
title: Accès root via Terminal
---

# Accès root via Terminal

Afin d'obtenir un terminal avec un accès root sur Recalbox, vous avez deux options :

## **SSH**

Se connecter via ssh à Recalbox, avec les informations d'identification suivantes :

* Adresse IP de votre Recalbox : `192.168.x.x`
* Identifiant : `root`
* Mot de passe : `recalboxroot`

{% tabs %}
{% tab title="Windows" %}
Vous pouvez utiliser ces logiciels :

* [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
* PowerShell
{% endtab %}

{% tab title="macOS" %}
Le Terminal est fourni d'origine dans le système. Ouvrez votre dossier `Applications` et allez dans le répertoire `Utilitaires` pour le trouver.

Ligne de commande à exécuter : `ssh root@ip-de-votre-Recalbox`
{% endtab %}

{% tab title="Linux" %}
Le Terminal est fourni d'origine dans le système. Son emplacement dépend de la distribution Linux que vous utilisez.

Ligne de commande à exécuter : `ssh root@ip-de-votre-Recalbox`
{% endtab %}
{% endtabs %}

## **Accès direct**

Dans l'interface EmulationStation :

* Appuyez sur **`F4`** pour quitter EmulationStation**.**
* Appuyez sur **`Alt + F2`** pour obtenir un terminal.
* Utilisez les mêmes identifiants que ci-dessus.

