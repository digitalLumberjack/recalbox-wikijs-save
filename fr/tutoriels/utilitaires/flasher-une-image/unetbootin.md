---
title: UNetbootin
---

# UNetbootin

## Fonctionnalités

[UNetbootin](https://unetbootin.github.io/) peut créer une clé [USB Live](https://fr.wikipedia.org/wiki/Live_USB) amorçable.

Il charge des distributions en téléchargeant pour vous des fichiers ISO \(image CD\), ou en [utilisant un fichier ISO déjà téléchargé par vos soins](https://unetbootin.github.io/#other).

![](https://unetbootin.github.io/screenshot1.jpg)

## Utiliser Unetbootin

Sélectionnez un fichier ISO ou une distribution à télécharger, choisissez un disque cible \(clé USB ou disque dur\), puis redémarrez une fois terminé. Si votre clé USB n'est pas reconnue, reformatez-la au format FAT32.

![](https://unetbootin.github.io/screenshot2.jpg)

![](https://unetbootin.github.io/screenshot3.jpg)

![](https://unetbootin.github.io/screenshot4.jpg)

Si vous utilisez le mode d'installation « Clé USB » : après le redémarrage, [démarrez à partir de la clé USB](http://pcsupport.about.com/od/tipstricks/ht/bootusbflash.htm).

Sur les PC, il suffit généralement d'appuyer sur la touche Echap ou F12 immédiatement après le redémarrage de l'ordinateur, alors que sur Mac, vous devez maintenir appuyé la touche Option avant le démarrage d'OSX.

Si vous utilisez le mode d'installation « Disque dur » : après le redémarrage, sélectionnez l'entrée UNetbootin à partir du menu de démarrage.

## **Instructions de suppression \(applicable uniquement pour les installations sur disque dur\)**

Si vous utilisez Windows, UNetbootin devrait vous proposer de le supprimer au prochain démarrage de Windows. Alternativement, vous pouvez le supprimer via Ajout/suppression de programmes dans le Panneau de configuration.

Si vous utilisez Linux, relancez l'exécutable d'UNetbootin \(avec les privilèges administrateur\) et appuyez sur OK lors de l'invitation à la désinstallation.

La suppression est requise uniquement si vous avez utilisé le mode d'installation « Disque dur » ; pour supprimer le chargeur de démarrage depuis une clé USB, sauvegardez son contenu puis reformatez-la.

La désinstallation d'UNetbootin supprime simplement l'entrée UNetbootin depuis votre menu de démarrage ; si vous avez installé un système d'exploitation sur une partition utilisant UNetbootin, la suppression d'UNetbootin ne supprimera pas l'OS.

Pour supprimer manuellement une installation Linux, vous devez restaurer le chargeur de démarrage Windows en utilisant « fixmbr » depuis un CD de récupération et utiliser Parted Magic pour effacer la partition Linux et redimensionner la partition Windows.

{% tabs %}
{% tab title="Licence" %}
UNetbootin a été créé et écrit par [Geza Kovacs](http://www.gkovacs.com/) \(Github : [gkovacs](http://github.com/gkovacs), Launchpad : [gezakovacs](https://launchpad.net/~gezakovacs), [infos de contact](http://wiki.ubuntu.com/GezaKovacs)\).

Les traducteurs sont référencés sur la [page des traductions](https://github.com/unetbootin/unetbootin/wiki/translations).

UNetbootin est distribué sous [licence publique générale GNU \(GPL\) version 2](http://www.gnu.org/licenses/old-licenses/gpl-2.0.html) ou [supérieure](http://www.gnu.org/copyleft/gpl.html). Le contenu du site \(documentation, captures d'écran et logos\) est distribué sous [licence Creative Commons - Partage dans les mêmes conditions 3.0](http://creativecommons.org/licenses/by-sa/3.0/).
{% endtab %}
{% endtabs %}



