---
title: Accéder à une partition en écriture
---

# Accéder à une partition en écriture


>_**Information :**_ 
>
>Depuis la version 4.0.0, le système de partition a été modifié pour limiter la corruption de votre microsd. 
{.is-info}

De ce fait, les partitions suivantes sont accessible uniquement en lecture :

Vous pouvez être amené à **modifier** des fichiers dans **2 partitions de recalboxOS** \(via SSH\)**.** 

* Partition de boot  `/boot`  
* Partition du système  `/`



**Suivant les modifications** que vous souhaitez apporter faites :

* `mount -o remount,rw /boot`   **ou**
* `mount -o remount,rw /` 

Une fois les modifications réalisées, **la partition** sera **remise en lecture** au prochain **redémarrage du système.**

## Winscp en utilisant la console <a id="winscp-en-utilisant-la-console"></a>

**Cliquer** sur **l’icône Console** puis **saisir** la commande **pour mettre la partition en écriture.**

![winscp\_60p](https://github.com/lackyluuk/recalbox-os/raw/master/wiki/images/WinSCP.PNG)

