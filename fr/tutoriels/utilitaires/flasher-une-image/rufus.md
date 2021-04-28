---
title: Rufus
---

# Rufus

Rufus est un utilitaire permettant de formater et de créer des média USB démarrables, tels que clés USB, mémoire flash, etc.

Il est particulièrement utile pour les cas où :

* vous voulez créer un média d’installation USB à partir d’une image ISO démarrable \(Windows, Linux, UEFI, etc.\)
* vous voulez travailler sur une machine qui n’a pas de système d’exploitation installé
* vous voulez programmer un BIOS ou un autre type de firmware depuis DOS
* vous voulez lancer un utilitaire de bas-niveau

En dépit de sa petite taille, Rufus fournit tout ce dont vous avez besoin !

Oh, et Rufus est **rapide**. Par exemple, il est environ deux fois plus rapide qu'[UNetbootin](http://unetbootin.sourceforge.net/), [Universal USB Installer](http://www.pendrivelinux.com/universal-usb-installer-easy-as-1-2-3) ou [l'utilitaire Windows 7 USB](https://www.microsoft.com/en-us/download/windows-usb-dvd-download-tool), pour la création d'un média d'installation USB à partir d'une image ISO Windows 7.  
Il est aussi marginalement plus rapide pour la création de média USB démarrables Linux.

* [**Téléchargez le fichier exécutable**](https://rufus.akeo.ie/)
* Lancez-le \(aucune installation n'est nécessaire\)

Le fichier exécutable est signé de manière digitale, et la signature doit indiquer :

* "Akeo Consulting" \(v1.3.0 ou supérieure\)
* "Pete Batard - Open Source Developer" \(v1.2.0 ou antérieure\)

## **Notes sur le support DOS :**

Si vous créez un disque démarrable USB avec un clavier non-US, Rufus essaie de sélectionner une disposition de clavier qui correspond à la langue de votre système.  
Dans ce cas, [FreeDOS](http://www.freedos.org), qui est la sélection par défaut, est recommandé vis-à-vis de MS-DOS, car il supporte plus de dispositions internationales de clavier.

## **Notes sur le support d'images ISO :**

Toutes les versions de Rufus, depuis la version 1.1.0, permettent la création d'un média USB démarrable à partir d'une [image ISO](http://en.wikipedia.org/wiki/ISO_image) \(.iso\).

Si vous n'avez pas de fichier ISO, la création d'une telle image, à partir d'un disque optique ou depuis un ensemble de fichier, est facile à effectuer.  
Vous pouvez juste utilisez l'une des nombreuses applications gratuites de gravure CD ou DVD, telles que [CDBurnerXP](http://cdburnerxp.se/) ou [ImgBurn](http://www.imgburn.com/).

{% tabs %}
{% tab title="Licence" %}
[GNU General Public License \(GPL\) version 3](http://www.gnu.org/licenses/gpl.html) ou ultérieure.  
Vous êtes libres de distribuer, modifier ou encore vendre ce logiciel, tant que vous respectez la licence GPLv3.

Rufus est produit de manière 100% transparente, depuis son [code source public](https://github.com/pbatard/rufus), en utilisant un environnement [MinGW32](http://www.mingw.org).
{% endtab %}
{% endtabs %}

