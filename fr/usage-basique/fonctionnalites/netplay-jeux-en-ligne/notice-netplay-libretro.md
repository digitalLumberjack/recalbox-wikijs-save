---
title: Notice Netplay Libretro
---

# Notice Netplay Libretro

## Le lobby Netplay

### **Hôte :**

* Depuis la liste des jeux **"**Démarrer l'hébergement" sur le jeu auquel vous voulez jouer en réseau avec la **touche Netplay.**


>Appuyer sur X \(suivant la configuration d’une manette Snes\) depuis le jeu voulant être lancer en Netplay.
{.is-info}

* Le menu des mots de passe apparaît **\(Nouveauté 7.0\)** :

![](/migration-images/usage-basique/fonctionnalites/netplay-jeux-en-ligne/image%20%2811%29.png)

* **Mot de passe Joueur requis** ON/OFF :

  Sélectionner ON, si vous voulez mettre un mot de passe joueur sur votre partie.

  * Les personnes voulant rejoindre en tant que **Joueur** devront avoir le même **"Mot de passe Joueur"** que l'hote.

* **Mot de passe Spectateur requis** ON/OFF : Sélectionner ON, si vous voulez mettre un **"Mot de passe Spectateur"** sur votre partie.
  * Les personnes voulant rejoindre en tant que **Spectateur** devront avoir le même **"Mot de passe Spectateur"** que l'hote.
* **Mot de passe Joueur** : Une sélection de mot de passe prédéfinis.
  * Bien sûre, vous pouvez personnaliser les mot de passe de cette liste
* **Mot de passe Spectateur** :

  Une sélection de mot de passe prédéfinis.

  * Bien sûre, vous pouvez personnaliser les mot de passe de cette liste

* Une fois que vous avez fait votre choix
  * Sélectionner Démarrer pour lancer la partie.
* **Attendez les joueurs** :
  * Une **pop-up** apparaît à **l'écran des utilisateurs de Recalbox qui sont connecter** pour les avertir qu'une session Netplay est disponible.

![](/migration-images/usage-basique/fonctionnalites/netplay-jeux-en-ligne/image%20%2887%29.png)

### **Client :**

* Rejoignez le lobby avec la **touche Netplay** depuis le menu système


>Pour y accéder, appuyer sur X \(suivant la configuration d’une manette Snes\) puis Lobby Netplay.
{.is-info}

![](/migration-images/usage-basique/fonctionnalites/netplay-jeux-en-ligne/image%20%28110%29.png)

* Sélectionnez l’hôte auquel vous souhaitez vous connecter.

## Informations dans le lobby

Pour chaque jeu, vous aurez des informations :

### Sur la gauche

* **Un signe :** ✅\(valider\) ou ❎ \(non valider\) Devant le logo de Realbox ou le nom de la rom.
* **Le logo Recalbox :** si la personne est sous Recalbox. Entre le signe et le nom de la rom
* **Le nom de la rom :** le nom exacte du fichier rom héberger. Après le signe et le logo Recalbox.

### Sur la droite

#### Résultat de base

* **Nom :** Nom de joueur de l'hôte \(l'icône confirme qu’il est bien sous Recalbox\)
* **Pays :** Pays du serveur de votre hôte
* **Hash de la rom :** Correspondance de la Signature de la rom
* **Fichier rom :** Correspondance de la rom
* **Core :** Emulateur utilisé
* **Ver. du Core :** Version de l’Emulateur
* **Latence :** Ping
* **Ver. de RA :** Version de Retroarch
* **Arch. de l'hôte :** Architecture de l'hôte

Vous verrez le résultat devant chaque item de la liste, ✅ \(valider\) ou ​❎ \(non valider\).



#### Résultat global

**Vous verrez le résultat globale dans le bas de la fenêtre à droite, vous indiquant les chances de succès de connexion :**

* **Vert :** Vous avez la bonne rom avec le bon hash, le bon core. Toutes les chances sont de votre côté pour que ça marche !

![](/migration-images/usage-basique/fonctionnalites/netplay-jeux-en-ligne/netplay-lobby-ok.png)

* **Bleu :** Pas de correspondance du hash \(certaines roms n’ont pas de hash, comme les systèmes arcade\), mais le bon fichier a été trouvé. Ça devrait marcher !

![](/migration-images/usage-basique/fonctionnalites/netplay-jeux-en-ligne/netplay-ok-nok.png)

* **Rouge :** Fichier non trouvé, système interdit, pas le bon core. Aucune chance que le jeu en ligne marche ! \(rien ne sera lancé\)

![](/migration-images/usage-basique/fonctionnalites/netplay-jeux-en-ligne/netplay-nok.png)

