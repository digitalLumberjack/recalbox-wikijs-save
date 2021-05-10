---
title: Gestionnaire de mise à jour
---

# Gestionnaire de mise à jour

![](https://gblobscdn.gitbook.com/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8f1Xj72mnetMU5ge3p%2F-M8f5iNaSCD4S6XSmk5x%2Fimage.png?alt=media&token=67c61297-5a41-45d1-9074-c0e963b0d141)

## Une nouvelle façon de faire les mises à jour! <a id="une-nouvelle-facon-de-faire-les-mises-a-jour"></a>

Alors là, j'ai une bonne et une mauvaise nouvelle.

## La mauvaise <a id="la-mauvaise"></a>

* Vous allez encore devoir faire une **installation fraîche, vous ne pourrez mettre à jour les versions 6.1.1 et inférieures**.

## Les bonnes nouvelles en revanche <a id="les-bonnes-nouvelles-en-revanche"></a>

* **C'est probablement la dernière fois que vous aurez à le faire.**
* Le nouveau système de MAJ est bien plus rapide :
  * _**5mn maximum pour une MAJ**_ \(hors temps de téléchargement bien sur\).
* Le nouveau système de MAJ est bien plus robuste :
  * Terminé les MAJ qui crashent et qui vous obligent à tout recommencer \(même si ça restait rare, heureusement!\)
* Les nouvelles MAJ online seront gérées par EmulationStation: Affichage de la progression, gestion des erreurs, etc.
* Il vous sera possible de faire des MAJ offline de façon extrêmement simple: en copiant l'image de la nouvelle version dans un répertoire de la carte SD accessible à partir de tous les OS: Windows, linux et MacOS! Un petit reboot, le système détecte l'image, opère la MAJ et hop, terminé! Je vois déjà un large sourire illuminer le visage de tous ceux qui ont un GPI case 😀
* Il vous sera possible désormais de placer vos propres vidéos de boot, dans un répertoire facilement accessible sur le réseau \(dans `\\share`\) et de choisir si le Player doit jouer des vidéos seulement parmi celles de Recalbox, seulement parmi les vôtres, ou parmi tout ce qu'il a à disposition.
  * Qu'est-ce que ça vient faire dans les mises à jour vous demandez-vous? Rien, c'est juste que cette nouvelle possibilité est liée à la nouvelle structure de Recalbox pour faciliter les MAJ!
* Pour ceux qui souhaitent bidouiller le système et qui cassent tout, il vous sera très facile de faire un "reset" de votre recalbox, pour revenir sur un système comme s'il venait d'être installé, tout en ne touchant pas aux roms.
* N'en déplaise \(et c'est volontaire 👿\) à ceux qui escroquent et volent Recalbox autant que leurs clients.
  * Les _**Mises à jour ne sont plus désactivables**_ dans EmulationStation. Seule la notification par popup intrusif est désactivable. Mais vous verrez toujours un popup non intrusif vous signaler qu'une MAJ est disponible.

## Fonctionnement <a id="fonctionnement"></a>

* Il vous faut un minimum d'espace libre de 2Go dans `share` et 1Go dans `/boot` .
* Déposer l'image compressée dans `/boot/update` .

## Depannage <a id="depannage"></a>

* Si ça plante/bloque c'est sûrement due à un problème à la décompression ou à la copie, mais pas de risque de planter la recal.
  * Que faire ?

