---
title: Debugger le Wifi
description: Comment se connecter en wifi ?
---

# Debugger le Wifi

## Pré-requis <a id="pre-requis"></a>

* **Vérifier** que votre **dongle wifi** fait parti de la [liste de compatibilité](/hardware-compatibility/compatible-devices/dongle) ou que **vous possédez une board qui à la Wifi.** 
* **Vérifier** que votre **clé wifi** **soit en WPA2**, ne contienne **pas de caractères spéciaux** de préférence **sinon voir plus bas.** 
* **Vérifier** que votre **wifi** est en **mode découverte.** 
* Si votre **point d'accès utilise le cannal 12 ou 13**, ~~passer sur un canal inférieur ou~~ [~~mettre à jour le firmware~~](https://raspberrypi.stackexchange.com/a/43616) ==&gt; Voir [Indicatif Wifi d'un pays ](/fr/tutoriels/reseau/wifi/indicatif-wifi-dun-pays)
* [Blacklister le wifi intégré](/fr/tutoriels/reseau/wifi/blacklist-wifi-integre-du-rpi-3) si vous souhaitez **utiliser une clé wifi USB.**

## Configuration via emulationstation <a id="configuration-via-emulationstation"></a>

* **Brancher un clavier** 
* **Se rendre** dans le menu **d'Emulationstation** \(Start\) &gt; Options Réseau &gt; Wifi sur **On** 
* **Entrer les informations SSID, Clé**  
* Puis **redémarrer** Recalbox.

## Configuration via [recalbox.conf](/fr/usage-basique/premieres-notions/le-fichier-recalbox.conf)_\*\*\*\*_ <a id="configuration-via-recalbox-conf-or-recalbox-conf-fr"></a>

* **Connecter** Recalbox via **le câble réseau en rj45.** 
* **Modifier** le fichier **recalbox.conf** via winscp et notepad++ ou putty en utilisant la **commande nano** pour l'édition. 
* **Activer** le wifi. 
* **Supprimer** **les points virgules** devant **les deux lignes.** 
* **Enregistrer , fermer la session et redémarrer** Recalbox.

```text
## Activate wifi (0,1)   
wifi.enabled=1   
## Wifi SSID (string)  
wifi.ssid=new ssid   
## Wifi KEY (string)   
wifi.key=new key
```

* Si **caractères spéciaux** dans la **clé Wifi :** **Exemple :** **1a4a&9f5g8!41d** il faut ****rajouter **des anti-slash** devant **ces caractères** **dans** le fichier **recalbox.conf** :

```text
## Wifi KEY (string)   
wifi.key=1a4a\&9f5g8\!41d
```



#### **Dans Recalbox** directement :

Si vous n'avez **pas la possibilité** de connecter **un câble réseau.**

* **Brancher** un clavier. 
* Il faut **sortir d'Emulationstation** avec **les touches suivantes :**

  **`F4`** `suivi de` **`Alt+F2`**

```text
user : root      
mdp : recalboxroot
```

* Puis **éditer** le fichier **recalbox.conf** avec **la commande nano :**

```text
nano /recalbox/share/system/recalbox.conf
```

* **Enregistrer** les modifications `cltr+x` puis `Y` et **redémarrer** \(`reboot` \)

## Dépannage <a id="depannage"></a>

### Cas n°1 : panne systématique <a id="cas-n-1-panne-systematique"></a>

Si votre Recalbox **ne se connecte pas du tout** à votre routeur wifi ou votre box, voici **les points importants à contrôler:**

* **Vérifier** qu'aucun **câble ethernet n'est branché** sur Recalbox. En effet, cela **désactive automatiquement** le Wifi. 
* **Vérifier** que le **canal Wifi du routeur ou de la box** est bien **inférieur à 12**, car notre système utilise actuellement un protocole américain qui ne gère pas les canaux 12 et 13. 
* **Vérifier** que **le protocole Wifi** est bien sur **le WPA** et non le WEP.

### Cas n°2 : panne aléatoire ou après \(re\)démarrage <a id="cas-n-2-panne-aleatoire-ou-apres-re-demarrage"></a>


>**Remarques :**
>
>Si votre Recalbox parvient bien à **se connecter au wifi après paramétrage**, mais que vous rencontrez des difficultés lorsque **vous l'éteignez et la rallumez**, surtout depuis **la mise à jour du 09/02/2018.**
>
>Notez qu'il est **impératif** **d'éteindre correctement** votre **Recalbox.**  
>Cela signifie que vous devez **passer par le menu d'Emulationstation** pour **arrêter le système avant de couper l'alimentation.**
{.is-warning}

**Pour rappel**, comme pour **tout ordinateur**, le fait de **couper l'alimentation sans éteindre proprement** Recalbox risque de **corrompre les données.**

En ce qui concerne **la Wifi**, nous avons fait **une mise à jour** permettant le **montage réseau via Wifi**, et Recalbox a maintenant **besoin de sauvegarder les informations wifi à l'extinction.**  
C'est pourquoi **il est capital de l'éteindre correctement.**  


### Cas n°3 : Aucune de ses astuces ne fonctionnent

Si **aucune de ses astuces ne fonctionnent** ou que votre **dongle wifi** ne fait **pas partie de la liste de compatibilité.**

**Merci de poster** un [dmesg complet](/fr/tutoriels/depannage/dmesg) sur **le forum** en donnant **les informations sur le modèle de votre dongle.**

