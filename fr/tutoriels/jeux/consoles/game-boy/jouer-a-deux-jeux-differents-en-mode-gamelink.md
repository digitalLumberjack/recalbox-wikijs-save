---
title: Jouer à deux jeux différents en mode Gamelink
---

# Jouer à deux jeux différents en mode Gamelink

TGBDual permet de jouer à la GameBoy et la GameBoy Color en simulant un câble GameLink pour du multi-joueur. Cependant, pour utiliser deux jeux différents, la manipulation à faire est plus complexe.

Ce tutoriel va assumer que vous savez déjà lancer un jeu sur deux Game Boy avec TGBDual.


>Utiliser deux jeux différents permet d'utiliser la sauvegarde des jeux pour chaque GameBoy.
{.is-success}

## Deux jeux, un même système

La configuration la plus simple est de jouer à deux jeux différents d'un même système \(gb+gb ou gbc+gbc\), car cela ne demande aucune manipulation de sauvegarde.

Pour ce faire, la première chose à faire est de lancer un jeu du système souhaité \(gb ou gbc\) avec TGBDual.


>Le jeu lancé ici avec **TGBDual** n'a pas d'importance, tant qu'il se **lance correctement** et que il est **rangé dans le dossier du système voulu**.
{.is-warning}

Une fois le jeu lancé, il faut appuyer sur **Hotkey+B** pour accéder au menu RetroArch :

![Menu rapide de Ratroarch](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYAFNfcHufLOAweFEY%2Fimage.png?alt=media&token=4ad3d0ca-2df4-4012-a1f7-9d2d3c8f8e72)

Ensuite appuyer sur le bouton de retour \(**A** par défaut sur un Pi3B\) pour accéder au menu principal.

![Menu Principal de Retroarch](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYAgpTJbLxZ5ohGv5Y%2Fimage.png?alt=media&token=9575d729-7f69-454b-a210-b4203bc568d0)

Une fois dans ce menu, il faut se placer sur **Load 2 Player Game Boy Link** et valider ****avec **B**.


>En dessous de cette option, il est actuellement écrit "Current content: GameBoy \#1"
{.is-info}

Vous arrivez maintenant dans le dossier contenant le jeu que vous avez originellement lancé, il vous faut aller sur le jeu souhaité dans la première Game Boy à utiliser, et confirmer avec **B**.

![Menu permettant le choix du premier jeu](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYBL1TUqTYCn6W2KfW%2Fimage.png?alt=media&token=b632cbbb-02b4-4a61-8499-409d442178d0)


>Si le jeu est zippé, il vous faudra demander de parcourir l'archive, puis d'ouvrir la rom contenue à l'intérieur.
{.is-danger}

![Cas d&apos;un jeu zipp&#xE9;: Il faut parcourir l&apos;archive...](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYBiEvD5S6lzOtFYBf%2Fimage.png?alt=media&token=92b92aa6-10db-47e8-b532-0a01f2c9d311)

![...puis s&#xE9;lectionner la rom voulue.](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYBllRmAz8ypQU57k5%2Fimage.png?alt=media&token=b541a3bd-d9d4-48dc-a446-e00e78cbe1f2)

On se retrouve ensuite de nouveau dans le menu principal, et il faut sélectionner de nouveau **Load 2 Player Game Boy Link**.

![On s&#xE9;lectionne de nouveau l&apos;option.](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYCaAw4CvBnp5txCUv%2Fimage.png?alt=media&token=b05b52fb-46fb-4922-8098-5a45edb5e1a7)


>Cette fois, en dessous de l'option, il est écrit "Current content: GameBoy \#2", ce qui signifie que nous allons choisir le jeu de la seconde Game Boy.
{.is-info}

On se retrouve dans le même menu de selection du jeu, cette fois-ci, on va sélectionner le jeu de l'autre Game Boy.

![S&#xE9;lection du second jeu.](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYD9FoELV_qoHw55Qa%2Fimage.png?alt=media&token=edfafe57-d237-4fed-adaa-64a44329a356)


>Là encore, si le jeu est zippé, il faudra parcourir l'archive, puis ouvrir la rom contenue à l'intérieur.
{.is-danger}

Enfin, on se retrouve devant le menu principal de RetroArch, et Il faut cette fois-ci sélectionner l'option **Start 2 Player Game Boy Link**.

![Menu principal, On peut enfin choisir de lancer les deux jeux.](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYDnfJm2J-_Ary7TYx%2Fimage.png?alt=media&token=0dbf2a82-3c4a-4b91-bc1e-210e9c03e5f1)


>En dessous de l'option, un récapitulatif des jeux sélectionnés pour chaque GameBoy est donné.
{.is-info}

![R&#xE9;sultat final.](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYEBAjAgTFaE5tdtcc%2Fimage.png?alt=media&token=d5f41a42-e3ab-46a8-9fca-42f889eab1c0)



## Deux jeux, deux systèmes différents.

Dans le cas où l'on voudrait lancer deux jeux, mais l'un de game boy color, et l'autre de la game boy originale. Une étape supplémentaire se rajoute: Placer la sauvegarde des deux jeux dans le même dossier avant de démarrer.

Ainsi, si vous souhaitez lancer le système GBC depuis EmulationStation, vous devrez déplacer la sauvegarde du jeu GB concerné \(dans **share\saves\gb**\) dans le dossier **share\saves\gbc**.


>Ainsi, pour le jeu **Pokemon - Version Bleue \(France\) \(SGB Enhanced\)** dans le dossier gb, il faut déplacer les fichiers   
>**Pokemon - Version Bleue \(France\) \(SGB Enhanced\).rtc**   
>et   
>**Pokemon - Version Bleue \(France\) \(SGB Enhanced\).srm** dans le dossier **share\saves\gbc**. puis récupérer ces fichiers une fois la partie terminée et l'émulateur fermé pour les remettre à leur endroit d'origine.
{.is-info}

