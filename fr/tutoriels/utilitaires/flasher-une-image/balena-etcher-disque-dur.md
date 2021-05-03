---
title: Balena Etcher \(Disque dur\)
---

# Balena Etcher \(Disque dur\)

[BalenaEtcher](https://www.balena.io/etcher/) \(ce programme est très simple d'utilisation\), vous pouvez flasher le fichier image sur le support désiré \(par exemple, une carte microSD pour un Raspberry Pi\). L'opération de flash d'une image ne prend que quelques secondes de manipulation.

* **Choisir l’image ISO à flasher :**

  * Cliquer sur “Select Image” et chercher le fichier à flasher. Le nom de l’image apparaît alors sous la première icône et un petit changement permet de modifier ce choix. 

* **Connecter un média de stockage :**

  La seconde icône en forme de stockage externe s’illumine.

  * Sélectionner un média de stockage.

Etcher valide automatiquement ce qu’il détecte comme un périphérique USB.  
II est possible de changer de destination en appuyant sur le petit “change”.   
Le programme indique la capacité du dispositif et signale si celui-ci est trop petit pour accepter l’image.


>**Remarque :**
>
>Pour l'**installation sur** **Disque Dur** **:**
>
>* Aller dans **Paramètres** \(Roue crantée en haut à droite\).
>* Désactiver **la fonction "unsafe mode"**.
>* Revenez au **Menu d'accueil.**
>* Sélectionner un **Disque Dur.**
{.is-warning}

![Etcher](https://farm3.staticflickr.com/2825/33298930764_c297e9dbf8_z.jpg)

* Appuyer sur le bouton **“Start ou Flash”** pour lancer la procédure. Etcher se charge de tout, formatage, préparation des partitions, copie des fichiers, etc…

![](/migration-images/tutoriels/utilitaires/flasher-une-image/image%20%28259%29.png)

* Le programme indique le travail en cours, il précise également le temps nécessaire au déroulement de l’opération et la vitesse de transfert des données.

![](/migration-images/tutoriels/utilitaires/flasher-une-image/image%20%28116%29.png)

* Il valide ensuite l’image.

![](/migration-images/tutoriels/utilitaires/flasher-une-image/image%20%28238%29.png)

* Et enfin signale le bon – ou le mauvais – déroulement de l’opération. Vous donne une clé pour vérifier l’intégrité de l’archive et vous propose de recommencer l’opération soit avec la même image en un clic, soit avec une image ISO différente.

![](/migration-images/tutoriels/utilitaires/flasher-une-image/image%20%28285%29.png)

* Vous pouvez éjecter le support de stockage.

Il existe une tonne d’alternatives à **Etcher,** en particulier [UNetbootin](https://unetbootin.github.io/) et [Rufus](https://rufus.akeo.ie/) qui fonctionnent admirablement bien.

