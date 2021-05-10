---
title: Editer le fichier config.txt
---

# Editer le fichier config.txt


>**ATTENTION !**
>
>À partir de Recalbox 7.2.0, les modifications suivantes se font dans le fichier `/boot/recalbox-user-config.txt` !
{.is-danger}


>Tout d'abord, passez ****[**la partition de boot en écriture**](/fr/tutoriels/systeme/acces/acceder-a-une-partition-en-ecriture)\*\*\*\*
{.is-warning}

Il est localiser dans le system at `/boot/config.txt`

**Il y a deux façons de modifier le fichier config.txt.**

## **SSH**

* [Se connecter avec ssh](/fr/tutoriels/systeme/acces/acces-root-via-terminal)
* Utiliser **nano** pour **éditer** le fichier **/boot/config.txt**

  `nano /boot/config.txt`

## **Noobs**

* **Branchez un clavier USB** et appuyez sur **Maj** durant le **boot de recalbox** pour accéder au _**menu de Recovery.**_
* **Appuyez sur** **"e"** pour obtenir le **menu édition**, et vous pourrez effectuer des modifications directement sur le fichier.  Vous pouvez **changer la langue** **du clavier** en a**ppuyant sur "l" et "k".**

