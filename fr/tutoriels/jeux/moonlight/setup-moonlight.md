---
title: Setup Moonlight
---

# Setup Moonlight

## **1. Intro**


>**Moonlight** est une **version open-source** de la technologie **Gamestream de NVidia.**
{.is-info}

**Si votre PC** répond aux exigences, vous pouvez **diffuser la plupart de vos jeux en streaming** sur **votre Recalbox.**   
D'un autre côté, Recalbox lit la **configuration des pads depuis EmulationStation** et la **convertit vers Moonlight.**

\*\*\*\*

### Fonctionnalités de Moonlight sur Recalbox : <a id="fonctionnalites-de-moonlight-sur-recalbox"></a>

* **Diffusez des jeux en streaming** sur votre **réseau local** ou via **Internet**
* Jusqu'à **4 joueurs** supportés
* Jusqu'à **1080p/60fps**
* D**écodage H264 accéléré** par le matériel sur **n'importe quelle version du Raspberry Pi**
* Supporte le **clavier et la souris**
* Jusqu'à **GFE 3,12**

\*\*\*\*

### Pré-requis <a id="pre-requis"></a>

**Configuration requise** pour Recalbox et le PC pour profiter de Moonlight :

* Un **contrôleur configuré en ES**
* **Compte Steam** \(optionnel\) ou **jeux supportés de façon autonome** \(voir [https://shield.nvidia.com/game-stream](https://shield.nvidia.com/game-stream)\)
* Un **GPU compatible Nvidia** \(voir [http://www.geforce.com/geforce-experience/system-requirements](http://www.geforce.com/geforce-experience/system-requirements)\)
* Une **connexion Ethernet** est **fortement** **recommandée**, le **WiFi n'est pas assez fiable.**


>**Si vous mettez à jour** à partir **d'une version 3.3.0 vers la 4.0.0,** _veuillez lire attentivement_ !
{.is-danger}

## **2. Configuration de Moonlight**


>Veuillez d'abord **vérifier la version de votre Recalbox**
{.is-warning}

### Version &gt;= 18.03.16 <a id="version-greater-than-18-03-16"></a>

La **Recalbox v.18.03.16** offre un **scrap plus agréable**, la possibilité de **diffuser en continu à partir de plusieurs PC du réseau** et une petite **option pour trouver les hôtes GFE** disponibles.

Voici une démo pour trouver des **hôtes GFE**, les connecter et les lancer :

```text
# /recalbox/scripts/moonlight/Moonlight.sh find
Listing available GFE servers :
GFE Host WIN10(192.168.111.35) GeForce GTX 760 running GFE 3.12.0.84
You can now run /recalbox/scripts/moonlight/Moonlight.sh pair <host>
<host> can be empty (not recommended if you have several GFE hosts), an IP or a PC name
# /recalbox/scripts/moonlight/Moonlight.sh pair
() /recalbox/share/system/configs/moonlight/moonlight.conf | /recalbox/share/system/configs/moonlight/keydir
Searching for server...
Connect to 192.168.111.35...
Generating certificate...done
Please enter the following PIN on the target PC: 3843
Succesfully paired
YOLO MODE !!!
# /recalbox/scripts/moonlight/Moonlight.sh init
YOLO Mode
Adding and scraping Brutal Legend ...
Adding and scraping Sacred Citadel ...
Adding and scraping Just Cause 3 ...
Adding and scraping Street Fighter V ...
Adding and scraping Just Cause 2 Multiplayer ...
Adding and scraping Tales of Zestiria ...
Adding and scraping Grand Theft Auto V ...
Adding and scraping Hell Yeah! Wrath of the Dead Rabbit ...
Adding and scraping Ultra Street Fighter IV ...
Adding and scraping Diablo III ...
Adding and scraping Pro Evolution Soccer 2017 ...
Adding and scraping Bionic Commando Rearmed ...
Adding and scraping Just Cause 2 ...
Adding and scraping Pro Evolution Soccer 2016 ...
Adding and scraping Broforce ...
Adding and scraping DmC: Devil May Cry ...
Adding and scraping Naruto Shippuden: Ultimate Ninja Storm 4 ...
Adding and scraping Steam ...
```

###  <a id="a-version-greater-than-4-0-0-0-beta1"></a>

### a. Version &gt;= 4.0.0.0 beta1 <a id="a-version-greater-than-4-0-0-0-beta1"></a>

**Recalbox 4.0.0** introduit de **nouvelles fonctionnalités** pour Moonlight :

* **Configuration automatique** des gamepads pour Moonlight
* **Configuration facile :** vous n'aurez **peut-être pas besoin de spécifier** l'adresse IP d'ordinateur
* **Les paramètres** de Moonlight **peuvent être personnalisés** dans le fichier `/recalbox/share/sysem/sysem/configs/moonlight/moonlight.conf`. Ou **via le réseau** : \\Recalbox\User Data\configs\moonlight\moonlight\moonlight.conf


>**Veuillez noter que.. :**
>
>* Le support de Moonlight sur Recalbox 4.0.0.0-beta2 est vraiment bien meilleure par rapport à 4.0.0.0-beta1. Assurez-vous que vous l'avez mise à jour.
>* La configuration **"sans configuration"** ne fonctionne de **manière fiable** que **si** vous n'avez **qu'un seul PC compatible** avec gamestream. Sinon, vous devrez **spécifier l'adresse IP de votre hôte gamestream** dans le fichier de configuration.
>* Il peut arriver que **l'IPv6** soit **utilisé à la place de l'IPv4**. **Désactiver IPv6** sur Windows.
>* Utilisez **toujours la dernière version de Recalbox**. La version **4.0.0.0-beta4** a apporté le **support GFE 2.11**
>* Si vous êtes **bloqué sur l'appairage** :
>  * Supprimez /**recalbox/share/system/system/configs/moonlight/keydir**
>  * Déconnectez **tous les périphériques** dans **GFE**,
>  * Connectez-vous à votre compte NVidia.
>  * Et essayez à nouveau l'appairage.
{.is-info}

#### **Configuration du pad :** 

Si **votre pad ne répond pas comme prévu** dans **Moonlight,** veuillez le **remapper dans EmulationStation et réessayer.**

\*\*\*\*

#### **Configuration** de votre Recalbox :

Vous êtes maintenant **prêt à configurer** votre Recalbox pour la **diffusion de jeux** :

1. **Quitter EmulationStation** \(via SSH ou en appuyant sur F4\)
2. **Connectez-vous** en tant que **root**
3. **Taper** `cd /recalbox/scripts/moonlight`
4. **Assurez-vous** que **seul votre PC compatible** gamestream **est disponible sur le réseau.**
5. **Lancez** `./Moonlight.sh pair`, et **entrez le chiffre donné sur votre ordinateur**
6. Une fois appairé, **lancez** `./Moonlight.sh init` pour **créer des liens rom** pour **EmulationStation + données de scrap**
7. **Redémarrez EmulationStation** et profitez de **Moonlight** !

```text
Using username "root".
# /etc/init.d/S31emulationstation stop
# cd /recalbox/scripts/moonlight
# ./Moonlight.sh pair
Moonlight Embedded 2.2.0 (EMBEDDED;CEC;PI)
Too many options: No such file or directory
Moonlight Embedded 2.2.0 (EMBEDDED;CEC;PI)
Searching for server...
Connect to 192.168.0.28...
Generating certificate...done
NVIDIA GeForce GTX 960M, GFE 2.11.4.0 (protocol version 7)
Please enter the following PIN on the target PC: 3660
1017 / 1017
Succesfully paired
# ./Moonlight.sh init
Fetching games from  ...
Scraping games ...
# /etc/init.d/S31emulationstation start
```


>**Étape facultative** si vous avez **d'autres PC compatibles** avec **Moonlight :**
>
>* Editez `/recalbox/share/share/sysem/configs/moonlight/moonlight.conf`
>* Supprimer le \# devant `#adresse =`
>* Ajoutez votre adresse IP. Ex : `adresse = 192.168.0.0.12`
>* Sauvegardez votre fichier
{.is-warning}

**Pour l'instant**, Recalbox ne **peut gérer qu'un seul** PC gamestream. **La prise en charge** de **plusieurs PC hôtes** pourrait arriver dans une **version ultérieure.**

\*\*\*\*

### b. Version &gt;= 3.3.0 beta15 <a id="b-version-greater-than-3-3-0-beta15"></a>

1. **Quitter EmulationStation** \(via SSH ou en appuyant sur F4\) /etc/init.d/S31emulstation stop
2. **Connectez-vous** en tant que **root**
3. **Assurez-vous** que /recalbox/share/roms/moonlight **existe**. Sinon, `mkdir -p /recalbox/share/roms/moonlight`.
4. Taper ****`cd/recalbox/scripts/moonlight`
5. Éditez **Moonlight.sh** et réglez **"moonlight\_ip="** sur l'adresse IP à partir de laquelle **vous voulez diffuser.  
  
   Par exemple :**  
   si l'adresse IP de votre PC est "192.168.1.1", éditez comme "moonlight\_ip=192.168.1.1", sauvegardez et quittez votre éditeur de texte  
  
   **Ou** dans SSH, `nano /recalbox/scripts/moonlight/Moonlight.sh`**.**

6. **Lancez** `./Moonlight.sh pair`, et **entrez le chiffre donné sur votre ordinateur**
7. Une fois **appairé**, **lancer** `./Moonlight.sh init` pour **créer des liens rom** pour **EmulationStation + données de scrap.**
8. **Lancez** `./Moonlight.sh map` pour **configurer votre contrôleur** \(pad solo uniquement supporté pour le moment, clavier + souris fonctionnant parfaitement\)
9. **Redémarrez EmulationStation** `/etc/init.d/S31emulstation restart` et **profitez de Moonlight !**

\*\*\*\*

### c. 3.3.0 beta7 &lt;= Version &lt;= Version &lt; 3.3.0 beta15 <a id="c-3-3-0-beta7-less-than-version-less-than-version-less-than-3-3-0-beta15"></a>

* Allez dans **"//recalbox/roms/moonlight"** ou par **ssh** dans **"//recalbox/share/roms/moonlight po"**

#### Dans ce dossier, vous avez :

```text
Moonlight.sh.hide
Moonlight.conf
```

###  

### d. Version &lt; 3.3.0 beta7 :

_Obtenez le Moonlight.sh.hide ici :_

* Renommer **Moonlight.sh.hide** sur **Moonlight.sh,** ouvrir avec Notepad++ ou autre le Moonlight.sh et remplacer par ceci :[ Moonlight.sh.hide\_v2](https://github.com/steak3/recalbox-buildroot/blob/unified/board/recalbox/share/roms/moonlight/Moonlight.sh.hide_v2)​
* Remplacer à **moonlight\_ip=YOUR\_IP\_HERE** par **moonlight\_ip=192.168.x.x** &lt;=== c'est l'adresse IP de votre PC
* Sauvegarder et quitter

Supprimer les soucis possibles sur **Moonlight.conf** ici.



**Dans SSH** sur la commande **/recalbox/share/roms/moonlight** :

 ****`./Moonlight.sh paire` 

Si cette **commande réussi**t, vous avez **ce message** :

```text
Trop d'options : Aucun fichier ou répertoire de ce type
Impossible d'ouvrir le fichier de configuration : hosts/192.168.x.x.x.conf
Génération du certificat...fait
Veuillez saisir le code PIN suivant sur le PC cible : 9958
Appairage réussi
```

* Sur votre PC, vous avez un popup Nvidia pour entrer votre code PIN
* Maintenant, **dans "Configuration du contrôleur"**, lancez cette commande `./Moonligh.sh carte`et suivez les informations à l'écran.
* **Redémarrez** votre Recalbox et **jouez** avec **Moonlight !**

## **3. ANNEXE** <a id="3-annexe"></a>

### v4.0.0 spécifique


>**Utilisateurs avancés uniquement :**   
>Vous pouvez **diffuser en continu** à partir d'un **ordinateur distant sur Internet**. 
{.is-danger}

* Vous devrez éditer **"//recalbox/scripts/moonlight/Moonlight.sh" pour**
  * Spécifier **l'adresse IP de l'hôte distant.**
  * **Définir la même adresse IP** dans **moonlight.conf**
  * Et **configurer la redirection de port** selon :[ https://github.com/moonlight-stream/moonlight-android/wiki/Setup-Guide\#streaming-over-the-internet](https://github.com/moonlight-stream/moonlight-android/wiki/Setup-Guide#streaming-over-the-internet)



### v3.3.0 spécifique


>Vous pouvez modifier la **configuration de l'affichage** dans **Moonlight :**
>
>* **720p en 30 images/seconde - 1080p en 30 images/seconde** 
>* **720p en 60 images/seconde - 1080p en 60 images/seconde**
{.is-info}



Vous devez **changer la Ligne 23** dans **Moonlight.sh** :

cmd="moonlight stream -remote **-1080 -60fps** -keydir ${moonlight\_keydir} -mapping ${moonlight\_mapping} ${moonlight\_ip}"


>**Remplacer** les paramètres **Gras** en fonction de **vos besoins.**
{.is-warning}

