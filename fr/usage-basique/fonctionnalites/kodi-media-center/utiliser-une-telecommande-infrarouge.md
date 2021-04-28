---
title: Utiliser une télécommande infrarouge
---

# Utiliser une télécommande infrarouge

La Recalbox peut être controlée via n'importe quelle télécommande Infrarouge. ****Cette fonctionnalité est pour Kodi..

Cela vous coutera environ 2€ et est très simple à mettre en place.


>**ATTENTION**:  
>Nécessite la version 6.1.1 de Recalbox ou plus
{.is-danger}

## I - Prérequis <a id="i-prerequis"></a>

### A - Un récepteur Infrarouge <a id="a-un-recepteur-infrarouge"></a>

**Pour fonctionner**, vous allez avoir besoin d'un **récepteur IR** : comme un module 38KHz TSOP4838 ; noter que cela peut aussi fonctionner avec certains autres composants. Vous pouvez en acheter sur internet pour **environ 1€** chez n'importe quel revendeur d'électronique ou en ligne.

![R&#xE9;cepteur IR](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/tsop.jpg)

### B - Des câbles dupont femelle/femelle. <a id="b-des-cables-dupont-femelle-femelle"></a>

Afin de **raccorder facilement votre récepteur sans soudure**, vous aurez besoin de **3 câbles dupont F/F.** Vous pouvez vous en procurer chez les mêmes revendeurs que votre récepteur pour quelques centimes.

![C&#xE2;bles dupont F/F](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/jumpers.jpg)

### C - Schéma <a id="c-schema"></a>

Pour **connecter le récepteur et les câbles**, suivez le schéma suivant :

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/schema.png)

​

**Exemple de montage :**

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/montage.jpg)

​

### D - Télécommande <a id="d-telecommande"></a>

**Quasiment toutes** les télécommandes sont supportés, **à condition qu'elles utilisent des standards.**

Toutes ces télécommandes, ont été **testé avec succès** :

* Une télécommande **Philips hifi.**
* Une télécommande **Samsung d'un enregistreur vidéo.**
* Une télécommande **Universelle.**
* Une télécommande **d'un Ordinateur MAC.**

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/remotes.jpg)

## II - Configuration <a id="ii-configuration"></a>

### A - config.txt <a id="a-config-txt"></a>

* Ouvrez le fichier[ config.txt](/v/francais/tutoriels/systeme/modification/editer-le-fichier-config.txt) situé dans **/boot/config.txt** via SSh.
* Pensez à **activer le mode lecture-écriture** sur la partition via la commande **''' Mount -o remount, rw /boot '''**
* **Décommenter** la ligne suivante en **retirant le \#**

```text
 #dtoverlay=lirc-rpi​
```

devient

```text
dtoverlay=lirc-rpi
```

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/config.png)

* **Redémarrer** votre Recalbox.

​

### B - Configuration télécommande <a id="b-configuration-telecommande"></a>

#### 1. Vérification des évènements IR <a id="1-verification-des-evenements-ir"></a>

Vérification que le matériel fonctionne.

* **Connectez vous à la Recalbox** via **ssh** ou directement sur **le terminal** \(voir [accès root sur Terminal](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal)\)
* **Lancez la commande** suivante : `lsmod`

Vous devez **voir s'afficher une ligne** commençant par **lirc\_rpi**.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/lsmod.png)

* Ensuite **lancer la commande** suivante : `mode2 -d /dev/lirc0`
* **A chaque pression** d'une touche de votre télécommande **en face de votre récepteur**, vous devriez **voir apparaître des chiffres sur le terminal**. La télécommande et le récepteur **fonctionne donc correctement**.
* **Appuyez** sur **Ctrl+C** pour **quitter.**

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/mode2.png)

#### ​ <a id="2-enregistrer-votre-telecommande"></a>

#### 2. Enregistrer votre télécommande <a id="2-enregistrer-votre-telecommande-1"></a>

* **Lancez** la commande : `irrecord -H /recalbox/share/custom.conf`
* **Appuyez** sur **entrée** pour **continuer**.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord1.png)

* **Appuyez** sur **entrée** pour **continuer.**

Entrez `customremote` comme nom de télécommande.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord1_2.png)

Appuyez sur entrée pour continuer.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord2.png)

Commencez maintenant à appuyer sur les touches de votre télécommande pendant environ une seconde.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord3.png)

Entrez le nom d'un bouton parmi les noms suivants et appuyez sur la touche de votre télécommande :

* **Entrez le nom de votre touche** parmi les noms ci-dessous et **appuyez** sur la touche de la **télécommande** :
  * KEY\_LEFT \(Gauche\)
  * KEY\_RIGHT \(Droite\)
  * KEY\_UP \(Haut\)
  * KEY\_DOWN \(Bas\)
  * KEY\_OK \(Ok\)
  * KEY\_EXIT \(Retour/Quitter\)
  * KEY\_PLAY \(Lecture et Pause\)
  * KEY\_STOP \(Stop\)
  * KEY\_VOLUMEUP \(Volume +\)
  * KEY\_VOLUMEDOWN \(Volume -\)
  * KEY\_INFO \(Affichage des infos à propos du média en cours de lecture\)
  * KEY\_MUTE \(Sourdine\)
  * KEY\_POWER \(Quitter\)
  * KEY\_MENU \(Menu\)

​

* **Et éventuellement** :
  * KEY\_ENTER
  * KEY\_DELETE
  * KEY\_MEDIA
  * KEY\_RECORD
  * KEY\_PAUSE
  * KEY\_FASTFORWARD
  * KEY\_REWIND
  * KEY\_CHANNELUP
  * KEY\_CHANNELDOWN
  * KEY\_NEXT
  * KEY\_PREVIOUS
  * KEY\_EPG
  * KEY\_SUBTITLE
  * KEY\_LANGUAGE
  * KEY\_ZOOM
  * KEY\_VIDEO
  * KEY\_AUDIO
  * KEY\_NUMERIC\_1
  * KEY\_NUMERIC\_2
  * KEY\_NUMERIC\_3
  * KEY\_NUMERIC\_4
  * KEY\_NUMERIC\_5
  * KEY\_NUMERIC\_6
  * KEY\_NUMERIC\_7
  * KEY\_NUMERIC\_8
  * KEY\_NUMERIC\_9
  * KEY\_NUMERIC\_0
  * KEY\_RED
  * KEY\_GREEN
  * KEY\_YELLOW
  * KEY\_BLUE
  * KEY\_PVR
  * KEY\_RADIO

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord4.png)

* **Répétez** l'opération pour **l'ensemble** ou un **maximum de boutons** sur votre télécommande.

Pour **paramétrer à nouveau une touche**, **retaper** son nom et **recommencer**.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord5.png)

* Lorsque vous avez **enregistré l’ensemble des touches** voulues, **appuyez sur entrée** pour **continuer.**
* Puis appuyez sur **une des touches très rapidement sans la** **maintenir** et **sans changer de touches**.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irrecord6.png)

* A la fin, le programme est **automatiquement fermé**.
* Si vous voulez **recommencer**, **effacer le fichier de configuration** via la commande : `rm /tmp/custom.conf` et redémarrer irrecord.

​

#### 3. Fichier de configuration <a id="3-fichier-de-configuration"></a>

* **Déplacer ensuite le fichier** vers via `mv /recalbox/share/custom.conf /recalbox/share/system/.config/lirc/lircd.conf` afin de **remplacer** le fichier **lircd.conf** par **votre fichier**.
* **Redémarrer votre Recalbox** ou **relancer le service lircd** via la **commande** : `/etc/init.d/S25lircd restart`

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/keeprestart.png)

​

#### 4. Vérifier que le paramétrage fonctionne <a id="4-verifier-que-le-parametrage-fonctionne"></a>

* **Taper** la **commande** `irw`
* **A chaque fois** que vous **appuyez sur une touche**, vous devriez voir une ligne apparaître avec le nom de la touche.
* **Appuyez** sur **Ctrl + C** pour **quitter**.

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/ir/irw.png)

* **Lancer Kodi** et **vérifiez** le fonctionnement.

## III - Configuration avancée <a id="iii-configuration-avancee"></a>

### A - Lircmap.xml <a id="a-lircmap-xml"></a>

* Vous pouvez **personnaliser** le paramétrage **des touches** des télécommandes **en éditant** le fichier **Lircmap.xml** dans :**`/recalbox/share/system/.kodi/userdata/Lircmap.xml`**


>**ATTENTION :**
>
>Si vous **avez effacer manuellement** le dossier **`~/.kodi`** et **relancer kodi sans avoir** au préalable **redémarrer votre Recalbox**, vous ne **verrez pas les customisations** de **Kodi** ou du fichier **Lircmap.xml**.
{.is-danger}

* Considérez la copie de **`/recalbox/share_init/system/.kodi/userdata/Lircmap.xml`** vers **`/recalbox/share/system/.kodi/userdata/Lircmap.xml`**

**​**

### B - remote.xml <a id="b-remote-xml"></a>

Vous pouvez modifier la **définition des touches et des actions** dans le fichier **remote.xml** dans **`/recalbox/share/system/.kodi/userdata/keymaps/remote.xml`**

**​**

### C - QUITTER / STOP <a id="c-quitter-stop"></a>


>A propos du fait que **le bouton retour ne stoppe pas un film** dans **Kodi.** Si vous **n'aimez pas ce comportement** dans Kodi ou parce que vous **n'avez qu'un bouton unique Stop / Retour** sur votre télécommande.
{.is-warning}

Vous pouvez **modifier** dans le fichier r**emote.xml** la section **"", "Back"** par **"Stop"**

**​**

### D - VOLUME HAUT/BAS <a id="d-volume-haut-bas"></a>


>Ce point concerne les **télécommandes CEC.**
{.is-info}

Si votre télécommande CEC **ne transfère pas les ordres des volumes**, vous pouvez **utiliser d'autres touches** en remplaçant par exemple dans **remote.xml** dans la section globale :

```text
  <skipplus>SkipNext</skipplus>
  <skipminus>SkipPrevious</skipminus>
```

par

```text
  <skipplus>VolumeUp</skipplus>
  <skipminus>VolumeDown</skipminus>
```

###  <a id="e-pause-sur-ok"></a>

### E - PAUSE sur OK <a id="e-pause-sur-ok-1"></a>

Sur la **skin Refocus** pour rendre **la pause plus facile \(**principalement sur une **télécommande Apple\),** vous pouvez **modifier** le fichier **`~/.kodi/addons/skin.refocus/720p/VideoOSD.xml`**

**En remplaçant :**

```text
  <defaultcontrol always="true">700</defaultcontrol>
```

**par :**

```text
  <defaultcontrol always="true">705</defaultcontrol>
```

