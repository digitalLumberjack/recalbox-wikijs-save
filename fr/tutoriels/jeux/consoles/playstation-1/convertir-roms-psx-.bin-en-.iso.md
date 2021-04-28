---
title: Convertir les fichiers ISOs PSX .BIN en .ISO
---

# Convertir les fichiers ISOs PSX .BIN en .ISO

## Introduction

Nous allons développer ici une solution pour obtenir un seul fichier au format .ISO par jeu.  
Tous les jeux fonctionnent sur ce modèle à condition que les fichiers .BIN téléchargés fonctionnent également.


>Un problème récurrent avec les roms pour la PSX est que les fichiers sont plus souvent aux formats .BIN et .CUE qu'en .ISO, et parfois encore des roms au format .BIN.ECM
>
>L'un des inconvénients de ces fichiers, c'est qu'ils sont souvent plusieurs, 2 ou 3 fichiers voire parfois des dizaines. Cela peut fausser la qualité de la présentation dans l'interface d'EmulationStation \(on peut se retrouver avec plusieurs fichiers par jeu, et du coup le nombre total de jeux pour ce système est aussi faussé\).  
>  
>****Ce problème d'affichage sous EmulationStation survient soit :
>
>* Si vous ne scrapper pas vos roms.
>* Si vous avez mal configuré votre logiciel de scrap.
>
>Toutefois, les roms au formats .BIN et .CUE sont fonctionnel aussi.
{.is-info}

Tout d'abord le ****fichier ISO est une image de disque en binaire, c'est le format qui nous intéresse car l'intégralité du jeu tient en un seul fichier.

### Le fichier BIN

Le fichier .BIN est également une image de disque, c'est un format très proche de l'ISO. L'inconvénient est que les fichiers BIN peuvent être plusieurs, voire parfois très nombreux, et sont généralement accompagnés d'un autre fichier au format CUE.

### Le fichier CUE

Le fichier .CUE est un petit fichier texte qui accompagne les .BIN. Il peut être ouvert avec n'importe quel éditeur de texte, son seul but est d'aider à l'indexation des fichiers BIN qu'il accompagne. Pour indiquer à l'émulateur qui va le lire, où sont les fichiers BIN, quels sont leur noms, leur ordre, et parfois les différentes pistes audio contenues.

### Le fichier .BIN.ECM

Le fichier .BIN.ECM est plus rare, c'est le résultat d'un fichier BIN compressé.   
Nous allons voir dans la dernière partie comment le décompresser.

La première remarque c'est que souvent, un jeu est composé d'un fichier BIN accompagné d'un fichier CUE. Dans ce cas, le fichier CUE \(texte\), qui a pour rôle d'indexer les différents fichiers BIN qui l'accompagnent ne sert plus à rien. Les utilisateurs l'ont bien compris, en effet, dans ce cas de figure, il suffit de supprimer le fichier CUE, et alors le fichier BIN est autonome \(comme un ISO\), vous pouvez le laisser tel quel, ça fonctionne.


>**Attention :**
>
>Cela n'est pas toujours si simple : voyez à l'exemple 4b de ce tuto, il y a des fichiers CUE qui ne servent à rien, d'autres sont plus complets et donc importants.
{.is-danger}

Vous pouvez apprendre à faire la différence en les consultant systématiquement, vous avez aussi la possibilité de convertir toutes vos roms pour n'avoir aucun problème\).

La seconde remarque est de ne jamais renommer les fichiers BIN que nous venons de voir.  
En effet, si vous ouvrez un fichier CUE avec un éditeur de texte, vous allez voir qu'il liste tous les fichiers.BIN qu'il accompagne. Si vous renommez les fichiers BIN, alors ça ne correspond plus.  
  
Vous pouvez dans ce cas renommer tous les BIN dans le fichier CUE, mais c'est une étape qu'il est plus simple d'éviter en ne renommant pas les fichiers. Lorsque vous aurez obtenu un fichier ISO vous aurez la liberté de le renommer comme vous le souhaitez.

## Convertir un fichier BIN en ISO

Nous allons maintenant aborder la conversion des fichiers BIN en ISO. Pour cela, utilisé le logiciel [**IsoBuster**](http://www.isobuster.com/fr/) \(pour Windows, compatible Windows 10\), gratuit en version de démonstration.

* Ouvrez [**IsoBuster**](https://www.isobuster.com/fr/)
* Allez dans le menu `Fichier` et cliquez sur `Ouvrir un fichier image` 
* Allez chercher où se trouve le jeu à convertir au format BIN/CUE.
* Comme on ne peut pas sélectionner plusieurs fichiers BIN à incorporer dans **IsoBuster**, l'astuce est de se servir du fichier CUE, qui lui indexe tous les fichiers BIN qui forment le jeu. Cet exemple n'est pas intéressant parce qu'il n'y a qu'un fichier BIN, mais le principe serait le même avec 3 ou 30 fichiers BIN : on se sert du fichier .CUE.

Si votre rom est en 1 fichier BIN et que vous avez supprimé le fichier .CUE, pas de soucis à se faire, ça fonctionne en sélectionnant directement le fichier .BIN​.


>**Remarque :**
>
>Sauf que je viens d'avoir un autre cas avec Rayman, composé de _Rayman.bin_ et _Rayman.cue_   
>Comme vous pouvez le voir dans la capture ci-dessous, le fichier .CUE est beaucoup plus complet et indexe en plus les pistes audio du jeu. Les fichiers .CUE ne sont pas tous aussi complets, mais c'est une bonne habitude de toujours travailler avec le fichier .CUE.
{.is-warning}


>Voici [une archive](https://www.google.fr/search?q=cue_and_sbis) contenant les fichiers CUE pour toutes les roms PSX.​
{.is-info}

* Dans la colonne de gauche, clic droit sur la racine \[CD\], puis, dans les menus, cliquez sur **Extraire CD** et cliquez sur **Données brutes \(.BIN, .ISO\)**.
* Vous pouvez donner un nom à votre fichier d'exportation, le nom du jeu désiré.  Habituellement, à cette étape dans les programmes, si vous ne mettez pas d'extension de fichier \(.ISO\) mais que vous vérifiez que c'est sélectionné .ISO en dessous, votre fichier arrive bien en .iso Avec **IsoBuster** ce n'est pas le cas, votre fichier n'aura aucune extension de fichier si vous ne l'écrivez pas. Vous pourrez l'ajouter plus tard mais vous pourriez aussi vous y perdre, il est plus simple de bien mettre l'extension .iso dans le nom du fichier. 
* La conversion prend quelques secondes. 
* Si vous avez sélectionné un .CUE, Cliquez sur `Non`. De toute façon, étant utilisé dans le logiciel, il ne peut pas être écrasé. ​

Vous avez obtenu votre jeu au format ISO, qui aura été extrait à côté des fichiers BIN et CUE originaux.

## BIN compressé \(**BIN.ECM\)**

Et nous allons finir avec le cas plus rare le BIN compressé, au format .BIN.ECM  
Supprimer l'extension .ECM pour obtenir un .BIN ne fonctionne pas, il faut passer par un programme de décompression.

Il y a plusieurs méthodes, vous pouvez essayer :

{% tabs %}
{% tab title="Windows" %}
* En passant par le navigateur Chrome sur ce site \(bouton Add\). 
* Téléchargez le programme **Un-ECM.exe** \(24Ko\) [sur cette page](https://archive.org/details/ECMToolsV1.0).
* Faites une extraction du logiciel **Un-ECM.exe** dans un répertoire du même nom parmi vos programmes, et retenez son chemin d'installation.
* Faites un clic droit sur votre fichier .BIN.ECM et faites `Ouvrir avec`.
* Dans la liste des programmes proposés, faites défiler vers le bas, et cliquer sur `Rechercher une autre application sur ce PC` et ouvrez-le avec le programme **Un-ECM.exe**.
* Vous pouvez cocher la case `Toujours ouvrir avec cette application`, ainsi, à l'avenir, un double-clic sur un fichier .BIN.ECM décompressera automatiquement le fichier BIN dans ce même répertoire.
{% endtab %}

{% tab title="macOS" %}
* En passant par le navigateur Chrome sur ce site \(bouton Add\). 
* Il y a des méthodes en ligne de commande, où la méthode est de glisser les fichiers dans le terminal. Vous trouverez des tutoriels appropriés en cherchant les termes "BIN.ECM" et "Un-ECM" + le nom de votre système d'exploitation.
{% endtab %}

{% tab title="Linux" %}
* En passant par le navigateur Chrome sur ce site \(bouton Add\). 
* Il y a des méthodes en ligne de commande, où la méthode est de glisser les fichiers dans le terminal. Vous trouverez des tutoriels appropriés en cherchant les termes "BIN.ECM" et "Un-ECM" + le nom de votre système d'exploitation.
{% endtab %}
{% endtabs %}

Le fichier BIN obtenu est donc utilisable en l'état ou vous pouvez aussi le convertir en ISO comme on l'a vu précédemment.

