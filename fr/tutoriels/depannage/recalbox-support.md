---
title: Recalbox support
---

# Recalbox support


>Dans la version 4.0.0 de recalboxOS, un script nommé recalbox-support.sh a été ajouté afin d'aider les développeurs sur les problèmes que vous pouvez rencontrer avec vos périphériques.
{.is-info}

recalbox-support.sh donne les informations suivantes sur :

* joytstick
* kodi
* lirc
* system \(lsmod, lsusb, tv service, es\_settings, recalbox.conf, recalbox.log,config, df, etc...\)



**Si** vous avez correctement [configurer winscp](/v/francais/tutoriels/systeme/acces/acces-reseau-via-winscp)

**Connectez-vous** en ssh via putty via winscp , **executer cette commande** :

`/recalbox/scripts/recalbox-support.sh`

le chemin d'accès de l'archive vous sera indiqué dans la fenêtre.


>Attention :
>
>Le mode console de winscp , donnera un message d'erreur sur lsmod, il faut impérativement utiliser putty.
{.is-danger}

**Récupérer l'archive** sur votre PC puis **l'uploader** vers un hébergeur de fichier ;  
par exemple :

* ​[dl.free.fr](http://dl.free.fr/)​
* ​[zippyshare](http://www.zippyshare.com/)

## Via recalbox-manager <a id="via-recalbox-manager"></a>

**Ouvrir** votre navigateur internet : 

* Sous Windows [http://recalbox/help](http://recalbox/help) ou [http://ip\_recalbox/help](http://ip_recalbox/help)
* Sous Mac / Linux [http://recalbox.local/help](http://recalbox.local/help).



**Un lien** sera automatiquement uploadé et un lien vous sera donner.

**Poste** le lien **dans votre sujet** en cours sur le **forum** ou **dans l'issue** que vous avez ouverte.

