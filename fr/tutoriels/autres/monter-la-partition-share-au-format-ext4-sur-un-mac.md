---
title: Monter la partition share au format ext4 sur un Mac
---

# Monter la partition share au format ext4 sur un Mac


>**Information :**
>
>Ce tutoriel est destiné aux utilisateurs possédant une version antérieur à **Mac OS X 10.6.5**, étant donner que **macOS** à intégrée nativement l'exploitation d’exFAT depuis cette version.
{.is-info}

## Installation

* Installer le logiciel [Paragon ExtFS](https://www.paragon-software.com/fr/home/extfs-mac/#) disponible en test gratuitement pendant 10 jours.
* Redémarrer votre Mac.
* Ensuite à l'insertion de votre SD, tous les volumes Ext4 vont monter automatiquement sur le bureau y compris la partition share.

## Modification de la partition


>**Attention :**
>
>Si vous avez fait une installation basique, c'est à dire flasher une image de Recalbox sur carte microSD avec Etcher par exemple, vous ne pourrez pas modifier les partitions.
{.is-danger}

Si vous souhaitez modifier les partitions il faut faire une installation Recalbox multiboot avec PINN [https://sourceforge.net/projects/pinn/](https://sourceforge.net/projects/pinn/) qui est une alternative à NOOBS.

* Une fois Recalbox installé
* Vous éteignez votre machine
* Vous prenez la microSD
* Vous la mettez dans l'adaptateur fourni que vous connectez à votre Mac.
* Les partitions se montent et vous pouvez les modifier.

## Via le réseau

* Démarrez la Recalbox.
* Menu du finder `Aller` faire défiler jusqu'à `Se connecter au serveur` ou `cmd K`
* Entrer l'IP de la Recalbox
* Cliquez sur le bouton `se connecter comme` dans la fenêtre qui s'ouvre avec comme identifiants login: `root` mot de passe: `recalboxroot` 
* Choisissez de monter le volume share.


>**Remarque :**
>
>Notez que pour le transfert de nombreux fichiers via la méthode réseau \(par exemple des textures HD dans des dossiers cachés\), des erreurs peuvent se produire, signalées sur le finder.
{.is-warning}

