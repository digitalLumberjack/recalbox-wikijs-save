---
title: Créer un dualboot raspbian recalbox
---

# Créer un dualboot raspbian recalbox

Zhitom a partagé son expérience pour créer un dualboot avec raspbian et recalbox-OS à partir de Noobs

1. Télécharger **Noobs** « Offline and network install » \(contient la dernière version de **Raspbian**\) à l’adresse suivante : [https://www.raspberrypi.org/downloads/](https://www.raspberrypi.org/downloads/)
2. Décompresser l’archive zip et copier tous les fichiers à la racine de la carte SD préalablement formatée, sous Windows, avec le logiciel **SDFormatter** : [https://www.sdcard.org/downloads/formatter\_4/eula\_windows/SDFormatterv4.zip](https://www.sdcard.org/downloads/formatter_4/eula_windows/SDFormatterv4.zip) ou sous **Linux**, créer une partition \(avec fdisk par exemple\), puis la formatter: \`sudo mkfs.fat /dev/sdX\` où \`/dev/sdX\` correspond à la partition précedemment créée, puis monter la paritition: \`sudo mount /dev/sdX /mnt/yourmountpoint\`
3. Télécharger la dernière version de **Recalbox** à l’adresse suivante : [https://archive.recalbox.com/](https://archive.recalbox.com/)
4. Décompresser l’archive et copier le dossier « **recalboxOS-rpi2** » \(ou un autre « recalboxOS » en fonction de la version que vous avez, par exemple \`recalboxOS-rpi3\` pour un Raspberry Pi 3\) situé dans le dossier « os » pour le coller dans le dossier « os » à la racine de la carte SD. Sous Linux, une fois que ceci est terminé, ne pas oublier de “démonter” la carte SD avec \`sudo umount /mnt/yourmountpoint\`
5. La carte SD est prête, il n’y a plus qu’à l’insérer dans le Raspberry !
6. Au premier démarrage après le splashscreen, vous avez une fenêtre qui apparait avec le choix des OS à installer. Cocher Raspbian et Recalbox puis cliquer sur « Install » \(ou taper i\). Il n’y a plus qu’à attendre une dizaine de minutes que l’installation se termine.
7. Au redémarrage après le splashscreen, une nouvelle fenêtre apparait avec le choix de l’OS à démarrer. Choisir Raspbian ou Recalbox et le tour est joué !

Par défaut, le timing de la fenêtre pour la sélection de l’OS est de dix secondes et passé ce temps, le système lancera automatiquement le dernier os préalablement démarré.

Pour information :

Lors de l’installation d’un dual boot sur une carte µsd de 16Go, la répartition de l’espace libre par défaut est la suivante: 4,1Go pour raspbian et 3Go pour recalbox.

Lors de l’installation d’un dual boot sur une carte µsd de 32Go, la répartition de l’espace libre par défaut est la suivante: 1,5Go pour NOOBS \(images d’installation + recovery\), 16,1Go pour raspbian et 14,1Go pour recalbox.

