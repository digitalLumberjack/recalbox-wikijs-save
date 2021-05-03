---
title: Kodi Media Center
---

# Kodi Media Center

![](./kodi-media-center/image%20%2852%29.png)

Kodi est un espace multimédia intégré dans Recalbox.

Vous pouvez vous connecter à une grande variété de flux grâce à une connexion Ethernet pour profiter de films, de musique, et plus encore.

Les médias en direct et enregistrés sont accessibles avec une installation KODI correctement configurée. De même, vous pouvez simplement vous connecter à vos propres médias locaux via un port USB ou le réseau.


>**Information :**  
>Les contrôleurs sont désormais pris en charge dans kodi, mais si vous préférez, vous pouvez utiliser HDMI CEC ou une application distante pour smartphone. 
{.is-info}

## Base :

### Démarrage et extinction

Vous pouvez lancer **Kodi Media Center** soit en pressant le bouton **X** \(dans ES\), en appuyant sur **START** + en sélectionnant la première entrée du menu \(KODI\).

Pour quitter KODI, naviguez jusqu'à l'icône d'alimentation en bas à gauche du menu principal KODI et sélectionnez soit :

* "Power Off System"  ou
* "Reboot". Les deux éléments vous ramèneront au menu principal EmulationStation ; suivez les commandes normales de EmulationStation si vous souhaitez éteindre.

Dans la configuration par défaut \(3.3.0b17\), la fonction "Exit" peut verrouiller le système.  
De plus, vous ne pouvez pas mettre hors tension directement depuis KODI, vous devez retourner à EmulationStation si vous souhaitez effectivement mettre hors tension.



### **Nouveaux utilisateurs de KODI** :

Au premier lancement, KODI n'a que quelques options. Vous avez besoin d'une connexion Ethernet, sauf si vous utilisez uniquement des supports locaux ou connectés par USB.

Le [Wiki KODI](http://kodi.wiki/view/Main_Page) contient plus d'informations sur les spécificités de la mise en place et de l'utilisation de KODI. KODI est assez intuitif.  
Il trouve généralement les médias USB automatiquement lorsque vous entrez dans les options Vidéo ou Musique ; vous devriez voir votre média connecté par USB ou un chemin d'accès à celui-ci.

En outre, les onglets Vidéo, Musique et autres ont des "Addons" \(similaires à une application\).  
Il y a plusieurs "Addons" que vous pouvez télécharger directement à partir du registre principal au sein même de KODI, et plusieurs autres registres \(collection d'addons\) que les utilisateurs ont créés, vous devrez peut-être creuser un peu plus pour ajouter du contenu impressionnant.

* Pour obtenir des "Addons" de musique ou de vidéo, naviguez vers les onglets "Addons" sous l'onglet "Musique" ou "Vidéo" et cliquez dessus. ou
* Sélectionnez l'onglet principal en cliquant dessus et vous verrez tous les médias ou appareils connectés localement, "Addons" étant déjà installés. Cliquez sur "Addons" et trouvez le bouton qui dit "Get More". Cela vous mènera à une liste de "Addons" approuvés par KODI. Il suffit de sélectionner celui qui vous intéresse et de cliquer sur "Installer".

Cela se fera en arrière-plan et si vous disposez d'une connexion Ethernet décente, le téléchargement et l'installation prendront généralement moins d'une minute.

Si vous disposez d'un support réseau, vous devez configurer ces chemins dans les paramètres du système de fichiers.  
Là encore, tous ces éléments sont bien documentés sur leur propre [Wiki](http://kodi.wiki/view/Main_Page) et de nombreuses vidéos sont disponibles sur la configuration de KODI.

Remarques :

* Il y a quelques options dans la [configuration](/fr/usage-basique/premieres-notions/le-fichier-recalbox.conf) si vous souhaitez démarrer directement sur KODI à chaque fois plutôt que sur EmulationStation \(par défaut\).
* Pour votre installation initiale de KODI, vous aurez besoin d'un clavier, bien que ce ne soit pas obligatoire. Cela facilitera une partie de la configuration initiale. De plus, la plupart des applications Smartphone/Tablette \(si elles sont configurées dans KODI\) offrent un clavier comme indiqué lorsque vous entrez dans une boîte de dialogue qui en requiert un, ou cliquez simplement dans la boîte de dialogue ouverte pour faire apparaître un clavier à l'écran que vous pouvez utiliser avec votre contrôleur.
* Certaines personnes vendent des dongles ou des instructions pour obtenir du contenu sur votre KODI, mais il ne s'agit que de collections ou de répertoires pré-assemblés qui sont gratuits si vous les trouvez par vous-même.
* Certains "Addons" peuvent nécessiter un abonnement, comme Netflix ou Amazon Video, d'autres peuvent simplement vous demander de créer un compte comme Pandora.
* Si vos contrôleurs deviennent fous lorsque vous entrez dans KODI, c'est qu'ils ne sont pas correctement configurés. Revoyez la configuration des contrôleurs ; section des [contrôleurs de la Recalbox](/fr/usage-basique/premiere-utilisation-et-configuration#ii-configuration-dun-controleur)
* La version Raspberry Pi de KODI ne dispose pas de toutes les fonctionnalités et Add-Ons, mais la plupart sont présents.
* La première fois et à chaque fois que vous démarrez KODI, il effectue des mises à jour ou des vérifications de fond. Cela peut entraîner une utilisation irrégulière ou retardée de certaines fonctionnalités. En général, il suffit d'attendre un moment pour les éclaircir. Plus vous avez d'addons, plus cela peut prendre du temps et certains peuvent être réglés pour ne pas être automatisés.
* La version actuelle de Recalbox de KODI est "Helix".
* Cliquez ici pour le support SMB v2+ : [SMB v2 sur KODI](https://discourse.osmc.tv/t/kodi-and-smbv1/37441/5)

## OPTIONS :

[Recalbox.conf](/fr/usage-basique/premieres-notions/le-fichier-recalbox.conf) contient quelques options Kodi. Vous pouvez activer ou désactiver Kodi, activer le raccourci du bouton X ou démarrer automatiquement Kodi au démarrage.


>**Information :**  
>Les contrôleurs sont supportés dans Kodi.  
>Vous pouvez utiliser la fonction **HDMI CEC** de votre téléviseur, pour contrôler Kodi depuis votre télécommande ou **Yatse** une télécommande Kodi pour smartphone.
{.is-info}

## Divers :

### Gestion de l'alimentation avec HDMI CEC

Si vous essayez de quitter ou d'arrêter Kodi, votre Raspberry enverra toujours un ordre d'arrêt HDMI à votre amplificateur A/V + télévision. En conséquence, tous vos "périphériques" seront éteints.

Pour éviter ce comportement, vous devez désactiver le paramètre "Arrêt du périphérique en quittant" en allant dans :

> Système -&gt; Paramètres -&gt; Système -&gt; Dispositifs d'entrée -&gt; Périphériques -&gt; Adaptateur CEC

L'adaptateur CEC, permettra dans certains cas de contrôler votre KODI via votre télécommande de télévision habituelle si elles supportent toutes la CEC. CEC envoie les commandes à distance par câble VIA HDMI à votre IP. [Wiki Kodi CEC](http://kodi.wiki/view/CEC)

### 

### Configuration de Yatse :

Yatse et quelques autres applications sont des télécommandes pour KODI. Ces applications offrent souvent plus de contrôle et un contrôle plus intuitif de KODI. Ce n'est pas obligatoire mais si vous appréciez KODI, vous apprécierez probablement davantage l'expérience avec la télécommande de l'application.

**Vous devez d'abord lancer KODI sur votre Recalbox.**

Après l'installation de l'application Yatse, Yatse recherchera sur votre réseau les KODI's disponibles.

![](https://github.com/digitalLumberjack/recalbox-os/raw/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_1-300px.png)

Vous pouvez sauter cette étape et passer à la configuration manuelle.  
Il suffit de régler l'IP de la Recalbox sur votre réseau  
\(affiché dans le menu _Network Option_ de la Recalbox\) et le port sur **8081**

![](https://github.com/digitalLumberjack/recalbox-os/raw/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_2-300px.png)

Votre contrôleur Yatse est maintenant connecté :

![](https://github.com/digitalLumberjack/recalbox-os/raw/master/wiki/images/yatse/configure_yatse_for_kodi_recalbox_3-300px.png)

Si vous aimez Yatse, achetez l'**Unlocker** pour bénéficier de nouvelles fonctionnalités.

### 

### Configuration du joystick :

La configuration entre le joystick et l'action réalisée dans KODI peut être modifiée dans le fichier /recalbox/configs/kodi/input.xml en utilisant les actions et fonctions listées ici : [http://kodi.wiki/view/Keymap\#Commands](http://kodi.wiki/view/Keymap#Commands)

The current default mapping is :

* a: Select
* b: Retour
* x: Stop
* y: Menu
* start: Pause
* select: Menu contextuel
* pageup: \(_rien_\)
* pagedown: \(_rien_\)
* l2: \(_rien_\)
* r2: \(_rien_\)
* up: Haut
* down: Bas
* right: Droite
* left: Gauche
* joystick1up: Augmenter le volume
* joystick1down: Réduire le volume
* joystick1left: Réduire le volume
* joystick1right: Augmenter le volume
* joystick2up: Haut
* joystick2down: Bas
* joystick2left: Gauche
* joystick2right: Droite
* hotkey: \(_rien_\)

### 

### Aucun son sur la sortie Jack :

Si vous avez configuré Kodi pour utiliser la sortie audio Jack mais que vous n'obtenez aucun son, essayez de mettre ces variables de configuration dans le fichier `/boot/config.txt` :

```text
hdmi_ignore_edid_audio=1
hdmi_force_edid_audio=0
```

Il forcera l'audio à passer par la sortie Jack.

