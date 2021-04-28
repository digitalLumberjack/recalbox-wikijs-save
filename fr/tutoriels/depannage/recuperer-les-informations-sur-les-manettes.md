---
title: Récupérer les informations sur les manettes
---

# Récupérer les informations sur les manettes

Il existe quelques commandes utiles pour obtenir des informations sur les appareils pouvant être utilisés pour aider à résoudre les problèmes :

*  `cat /proc/bus/input/devices` pour afficher une liste des appareils disponibles
*  `lsusb -v` pour obtenir des informations sur les périphériques USB
*  `for i in /dev/input/event*; do echo $i;udevadm info -q all -n $i;done` pour obtenir des informations de l'_udev_ sur les appareils qui ont été mappés lors d'un événement
*  `for i in /dev/input/event*; do echo $i;(evtest $i) & ( evtestpid=$! && sleep 0.1 && kill -15 $evtestpid );done`

   dressera la liste de tous les boutons/axes/touches trouvés \(même s'il s'agit d'un clavier\)

Chaque fois que vous exécuterez une de ces commandes, il est préférable de ne pas coller la totalité de la sortie sur le forum ou le chat IRC. Utilisez plutôt quelque chose comme [http://pastebin.com/](http://pastebin.com/), collez votre sortie puis donnez le lien aux personnes avec qui vous communiquez.

