---
title: Ajouter votre propre script au demarrage
---

# Ajouter votre propre script au demarrage

Suivez ces instructions si vous souhaitez créer votre propre script de démarrage qui sera exécuté automatiquement lors du démarrage de **Recalbox**.

Tous les scripts de démarrage se trouvent dans `/etc/init.d`. Ils sont exécutés l'un après l'autre. Cela signifie que le script `S31emulationstation` sera traité avant `S99MyScript`. En fonction des noms de fichiers, vous pouvez déterminer l'ordre d'exécution.

La procédure de démarrage d'un script sera exécutée au démarrage et la procédure d'arrêt à l'arrêt de la Recalbox.

## Étapes pour créer votre propre script de démarrage :

* Connectez-vous avec un [accès root ](/fr/tutoriels/systeme/acces/acces-root-via-terminal)sur votre **Recalbox**.
* Le système est en lecture seule par défaut. Vous devez obtenir un accès en écriture avec la commande suivante : `mount -o remount rw, /`
* Changez le répertoire en `/etc/init.d` avec la commande suivante : `cd /etc/init.d`
* Tapez `ls` pour voir tous les scripts disponibles dans `init.d`.
* Créez un nouveau script avec `nano S99MyScript.py` \(vous pouvez bien sûr utiliser n'importe quel numéro, nom ou type de script \(.py, .sh, etc.\)\) et modifiez-le selon vos besoins. Pour cela, vous pouvez utiliser la structure de script suivante qui contient déjà les méthodes de démarrage, d'arrêt et de redémarrage / rechargement.

`#!/bin/bash`

```text
case "$1" in 
   start)  
         Add your startup code here!
         ;;  
   stop)  
         Add your shutdown code here!
         ;;  
   restart|reload)  
         Add your restart / reload code here!
         ;;  
   *)  
esac  

exit $?  
```

* Une fois que votre script est prêt, enregistrez-le et fermez-le avec `STRG + X`.
* Rendez-le exécutable avec la commande `chmod +x S99MyScript.py` \(ou quel que soit le nom de votre script\).
* Vous pouvez maintenant redémarrer la **Recalbox** ou lancer le script par vous-même avec `/etc/init.d/S99MyScript start`
* Vous êtes prêt !

