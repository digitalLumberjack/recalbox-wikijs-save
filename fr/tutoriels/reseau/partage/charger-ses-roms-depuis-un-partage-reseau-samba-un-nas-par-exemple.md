---
title: Charger ses roms depuis un partage réseau Samba \(un NAS par exemple\)
---

# Charger ses roms depuis un partage réseau Samba \(un NAS par exemple\)


>**Information :**
>
>Pour pouvoir stocker ses Roms sur un NAS et donc pouvoir en stocker beaucoup plus que sur une carte SD.
{.is-info}


>**Attention :**
>
>Le NAS et la Pi doivent **obligatoirement** être connectés en ethernet !
{.is-danger}

## **Sur le NAS**

* T_esté sur un Synology, mais le fonctionnement est identique un peu partout_ :
  * Créez un répertoire partagé \(appelons le "/roms/"\).
  * Créez un utilisateur avec les droits d’écriture/lecture sur ce répertoire \(ou réutiliser un utilisateur avec ces droits\).
  * Recréez l'architecture du répertoire Roms de la recalbox \(via le partage réseau, via ftp, ou à la main si vous voulez. L'important est d'avoir la même architecture, c'est à dire un répertoire par machines émulées. 
* Il est tout à fait possible de faire la même chose depuis le disque dur de votre PC. Sous Windows :
  * Vous pouvez créer un répertoire partagé
  * Le monter de la même manière sur la Recalbox.


>Remarque :
>
>Le seul inconvénient c'est que le PC servant de partage doit être allumé pour accéder aux Roms depuis la Recalbox.
{.is-warning}

## Sur votre Recalbox <a id="recalbox-version-greater-than-4-1"></a>


>**Depuis la version 4.1** de Recalbox, le **chargement des Roms depuis un partage réseau** est grandement **simplifié**. 
>
>Il est maintenant possible d'**indiquer au système** que le contenu du dossier **/recalbox/share** doit être monté depuis un partage réseau, **sans qu'il soit nécessaire de modifier** des fichiers **système** ou des **scripts de démarrage.**
{.is-info}

Depuis un terminal ou depuis une connexion SSH \([Voir le Tuto pour se connecter en SSH](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal)\)

* Passez le système de fichiers en mode "lecture/écriture" \(il est en "lecture uniquement" par défaut\). Cette modification restera active jusqu'au prochain redémarrage de la Recalbox :

```text
mount -o remount,rw /boot
```

* Maintenant, éditez le fichier **/boot/recalbox-boot.conf** avec votre éditeur préféré \(**nano**, **vi**\)²
* **Remplacez la ligne :**

```text
sharedevice=INTERNAL
```

* **Par la ligne :**

```text
sharedevice=NETWORK
```

Afin d'indiquer à la Recalbox que le contenu du dossier **/recalbox/share** doit être monté depuis un partage réseau \(et non depuis la carte SD\)

* Il est maintenant nécessaire de spécifier, toujours dans le fichier `recalbox-boot.conf`, les informations de connexion au NAS. Pour cela, deux options possibles :
  * **Les commandes basiques :** `sharenetwork_<nfs|smb><[0-9]>=<SHARE|ROMS|SAVES|BIOS>@<NAS>:<répertoire partagé>:<options>`
  * **Les commandes avancées :**  `sharenetwork_cmd<[0-9]>=<commande à exécuter>`

#### **Exemple :**

```text
sharenetwork_smb1=ROMS@192.168.0.1:recalbox/roms:username=recalbox,password=recalbox,vers=2.0
sharenetwork_smb2=SAVES@192.168.0.1:recalbox/saves:username=recalbox,password=recalbox,vers=2.0
```

#### **Autre exemple, avec les commandes avancées :**

```text
sharenetwork_cmd1=mount -o port=2049,nolock,proto=tcp 192.168.0.1:/Documents/recalbox /recalbox/share
```

## SMB v2 ou supérieure <a id="smb-v2-or-higher-support"></a>

* Ajouter ",vers=2.0" / ",vers=2.1" etc, par exemple :

```text
sharenetwork_smb1=ROMS@192.168.0.1:recalbox/roms:username=recalbox,password=recalbox,vers=2.0
sharenetwork_smb2=SAVES@192.168.0.1:recalbox/saves:username=recalbox,password=recalbox,vers=2.0
```

* Support SMB sur Windows :
  * 1.0: Win 2k/XP/Server 2003/Server 2003 R2
  * 2.0: Vista SP1/Server 2008
  * 2.1: Win7/Server 2008 R2
  * 3.0: Win8/Server 2012
  * 3.02: Win8.1/Server 2012
  * _3.11: Win10/Server 2016 \(doesn't work as of RecalBox 4.1/Dec 2017\)_

## Exemples avec la version 7.0 \(testés sur Pi3, Pi4, XU4, PC X86-32 et 64 bits\)

Voici les montages CIFS / SMB Possibles: 

### La commande basique

```text
sharenetwork_<nfs|smb><[0-9]>=<SHARE|ROMS|SAVES|BIOS|MUSIC|OVERLAYS|SCREENSHOTS|SHADERS|SCRIPTS>@<NAS>:<répertoire partagé>:<options>
```

### Soit l'ensemble du dossier SHARE

```text
sharedevice=NETWORK
sharewait=30
#TOUT LE DOSSIER SHARE EN ENTIER
sharenetwork_smb1=SHARE@<IP_DU_NAS>:<CHEMIN_NAS/SHARE>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
```



### Soit certains dossier\(s\) uniquement\(s\)

Depuis la version v7.0 il est désormais possible de sélectionner uniquement le ou les dossier\(s\) ci-dessous:

* ROMS
* SAVES
* BIOS
* MUSIC
* OVERLAYS
* SCREENSHOTS
* SHADERS
* SCRIPTS

```text
sharedevice=NETWORK
sharewait=30
#UNIQUEMENT UNE SELECTION DES DOSSIER
sharenetwork_smb1=ROMS@<IP_DU_NAS>:<CHEMIN_NAS/ROMS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb2=SAVES@<IP_DU_NAS>:<CHEMIN_NAS/SAVES>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb3=BIOS@<IP_DU_NAS>:<CHEMIN_NAS/BIOS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb4=MUSIC@<IP_DU_NAS>:<CHEMIN_NAS/MUSIC>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb5=OVERLAYS@<IP_DU_NAS>:<CHEMIN_NAS/OVERLAYS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb6=SCREENSHOTS@<IP_DU_NAS>:<CHEMIN_NAS/SCREENSHOTS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb7=SHADERS@<IP_DU_NAS>:<CHEMIN_NAS/SHADERS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
sharenetwork_smb8=SCRIPTS@<IP_DU_NAS>:<CHEMIN_NAS/SCRIPTS>:username=<ICI_LOGIN>,password=<ICI_PASSWORD>,vers=3.0
```

Si besoin voici en exemple mon fichier personnel.   
Chaque montage CIFS peut pointer vers un NAS spécifique.

Pour les overlays, il faut choisir en fonction de la résolution de son écran

```text
sharedevice=NETWORK
sharewait=30

#FULL ROMS
sharenetwork_smb1=ROMS@192.168.1.112:C/RCB/romsfull:username=USER,password=PASS,vers=3.0
#ROMS SELECTION
#sharenetwork_smb1=ROMS@192.168.1.112:C/RCB/roms:username=USER,password=PASS,vers=3.0
#ROMS POUR TESTS
#sharenetwork_smb1=ROMS@192.168.1.110:TEST/roms:username=USER,password=PASS+,vers=3.0

sharenetwork_smb2=SAVES@192.168.1.112:C/RCB/saves:username=USER,password=PASS,vers=3.0
sharenetwork_smb3=BIOS@192.168.1.112:C/RCB/bios:username=USER,password=PASS,vers=3.0
sharenetwork_smb4=SCREENSHOTS@192.168.1.112:C/RCB/screenshots:username=USER,password=PASS,vers=3.0

#720p pour Pi0 Pi2 Pi3
#sharenetwork_smb5=OVERLAYS@192.168.1.112:C/RCB/overlays720:username=USER,password=PASS,vers=3.0
#1080p pour Pi4 XU4 et PC en 1080p
sharenetwork_smb5=OVERLAYS@192.168.1.112:C/RCB/overlays1080:username=USER,password=PASS,vers=3.0
```

## _Lien Externe :_

**Il est fortement recommandé de retirer le support SMB v1 de votre machine Windows :**

* ​[http://www.zdnet.com/article/windows-10-tip-stop-using-the-horribly-insecure-smbv1-protocol/](http://www.zdnet.com/article/windows-10-tip-stop-using-the-horribly-insecure-smbv1-protocol/)​
* ​[https://www.howtogeek.com/321072/how-to-disable-smbv1-and-protect-your-windows-pc-from-attack/](https://www.howtogeek.com/321072/how-to-disable-smbv1-and-protect-your-windows-pc-from-attack/)​
* [​https://www.spamtitan.com/blog/stop-smbv1-ransomware-attacks/](https://www.titanhq.fr/blog/comment-arreter-attaques-ransomware-smbv1/)​
* ​[https://www.bostonhelpdesk.com/disabling-smbv1-one-defense-against-wanna-cry-ransomware/](https://www.bostonhelpdesk.com/disabling-smbv1-one-defense-against-wanna-cry-ransomware/)

