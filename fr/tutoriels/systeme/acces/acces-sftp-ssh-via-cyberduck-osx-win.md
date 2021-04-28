---
title: Accès SFTP/SSH via Cyberduck \(macOS / Windows\)
---

# Accès SFTP/SSH via Cyberduck \(macOS / Windows\)

## Connexion réseau SSH avec Cyberduck <a id="connexion-reseau-ssh-avec-cyberduck"></a>

Voici comment vous connecter sur macOS et Windows en réseau à Recalbox en SFTP avec le logiciel Cyberduck.

Vous pourrez ainsi avoir accès facilement aux différents fichiers de configuration comme par exemple `/boot/config.txt`.   
Si vous êtes un habitué **des outils du shell**, ce tutoriel n'est pas fait pour vous , il s'adresse **aux utilisateurs de MacOS** qui ont besoin **d'une interface graphique.**


>**Informations :**
>
>**Cyberduck** est un logiciel gratuit sur macOS et Windows de transfert de fichiers.  
>Il gère de nombreux protocoles : FTP, FTP-SSL, SFTP, WebDAV, Swift, S3, Google Cloud Storage, Windows Azure Storage, Dropbox, Google Drive, Backblaze B2 Cloud Storage, Backspace Cloud Files.
{.is-info}

* Pour commencer, **téléchargez Cyberduck** à l’adresse suivante : [https://cyberduck.io/](https://cyberduck.io/) ​
* Ensuite il faut que votre Raspberry soit **connecté à votre réseau local.** 
* Vous pouvez trouver **l’adresse ip de votre raspberry** via le menu **« options réseau »,** l'adresse ip est requise \(le nom de réseau ne suffit pas\).

![](http://i.imgur.com/j6JPi37.png.jpg)

* Ensuite **ouvrez Cyberduck** et **faîtes « ouvrir une connexion »**
  * **Comme protocole** au lieu de FTP, **mettez SFTP** et dans le champ « port » mettez « 22 »
  * Dans le champ **« serveur »** rentrez **l’adresse ip** de votre raspberry
  * n**om d’utilisateur** : root
  * **mot de passe :** recalboxroot 
* **Cliquez** ensuite sur le bouton **« connecter »** et autorisez les empreintes inconnues.

![](http://i.imgur.com/8u6bNOe.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzXFyiZ2GP7JC1_rgsx%2F-LzXHmn3EKfcpu_-dU5L%2F687474703a2f2f692e696d6775722e636f6d2f635364327648372e706e67.png?alt=media&token=50e4e5a1-6dc1-4dde-8d22-cc5afe7b71d8)

* Ensuite pour **sauver la configuration** dans un **signet :**

![](http://i.imgur.com/ePuP7Ez.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzXFyiZ2GP7JC1_rgsx%2F-LzXHqae72oZE0M4pM2e%2F687474703a2f2f692e696d6775722e636f6d2f727174764d39442e706e67.png?alt=media&token=6b9471da-7d3e-41aa-9ec4-bc930f5ffe59)

* Profitez-en pour **le renommer avant de fermer la fenêtre :**

![](http://i.imgur.com/WexZz6G.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzXFyiZ2GP7JC1_rgsx%2F-LzXHuLiVqnsX_uoUTvm%2F687474703a2f2f692e696d6775722e636f6d2f706e494258554c2e706e67.png?alt=media&token=20df1e9c-2630-4086-98a1-bd71049d01d6)

* **Voilà :** ​

![](http://i.imgur.com/kvgMoPt.png)

Voilà, votre signet est sauvegardé.

Le dossier **config.txt** se trouve **dans** `/boot/` .  
Le dossier **partagé** de recalbox **dans** `/recalbox/share/`

## **Mettre les droits en écriture sur la carte SD** <a id="mettre-les-droits-en-ecriture-sur-la-carte-sd"></a>

Pour les bidouilleurs avertis, vous devez passer **les droits de la SD en écriture**, pour **modifier** le fameux fichier `config.txt`. 

* **Dans le menu** de Cyberduck, **utilisez** l’option **"envoyer une commande"**

![](http://i.imgur.com/1KWkCrH.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzXFyiZ2GP7JC1_rgsx%2F-LzXHxZhq4JQ37QKAnX_%2F687474703a2f2f692e696d6775722e636f6d2f6e4e717a7268572e706e67.png?alt=media&token=97695d3f-a08c-4a42-a797-dbfcb3fc80c6)

* Et **entrer :**

`mount -o remount,rw /boot`   


* Voilà, vous pouvez **modifier** le fichier `config.txt`, je vous conseille de **faire une sauvegarde du fichier d’origine** sur votre ordinateur, puis je remplace celui de la carte sd par mon fichier modifié.


>**Information :**
>
>**Au** **prochain redémarrage** de la Recalbox, **les droits** repasseront en **lecture seule.**
{.is-info}

**Source :** [https://forum.recalbox.com/topic/7341/tutoriel-se-connecter-en-ssh-pour-les-nuls-avec-cyberduck-pour-config-txt-osx-et-win](https://forum.recalbox.com/topic/7341/tutoriel-se-connecter-en-ssh-pour-les-nuls-avec-cyberduck-pour-config-txt-osx-et-win)

## **Quelques modèles de config pour overclock :**


>**ATTENTION :**
>
>L'overclocking peut endommager votre Raspberry !
{.is-danger}

**Overclock à 1.4 ghz**

```text
# Overclock
 arm_freq=1400
over_voltage=6
sdram_freq=575
sdram_schmoo=0x02000020
over_voltage_sdram_p=6
over_voltage_sdram_i=4
over_voltage_sdram_c=4
core_freq=500
v3d_freq=500
h264_freq=333
gpu_mem=400
force_turbo=0
```

**Overclock à 1.35 ghz**

```text
# Overclock
arm_freq=1350
over_voltage=5
sdram_freq=500
sdram_schmoo=0x02000020
over_voltage_sdram_p=6
over_voltage_sdram_i=4
over_voltage_sdram_c=4
core_freq=500
v3d_freq=500
h264_freq=333
gpu_mem=400
force_turbo=0
```

**Overclock à 1.3ghz**

```text
# Overclock
arm_freq=1300
over_voltage=5
sdram_freq=500
sdram_schmoo=0x02000020 
over_voltage_sdram_p=6
over_voltage_sdram_i=4
over_voltage_sdram_c=4
core_freq=500
v3d_freq=500
h264_freq=333
gpu_mem=400
force_turbo=0
```

