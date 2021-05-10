---
title: Notice Netplay Libretro
---

# Notice Netplay Libretro

## Le lobby Netplay <a id="le-lobby-netplay"></a>

Vous n'avez pas besoin de configurer quoi que ce soit pour vous connecter au lobby netplay. Accédez au menu Netplay, sélectionnez Lobby Netplay, puis sélectionnez le serveur auquel vous souhaitez vous connecter.

Pour y accéder, appuyer sur X \(suivant la configuration d’une manette Snes\) puis Lobby Netplay

Pour chaque jeu, vous aurez des informations :

* **Nom:** Nom de joueur de l'hôte \(l'icône confirme qu’il est bien sous recalbox\)
* **Pays:** Pays du serveur de votre hôte
* **Hash de la rom:** Correspondance de la Signature de la rom
* **Fichier rom:** Correspondance de la rom
* **Core:** Emulateur utilisé
* **Ver. du Core:** Version de l’Emulateur
* **Latence:** Ping
* **Ver. de RA:** Version de Retroarch
* **Arch. de l'hôte:** Architecture de l'hôte

**Vous verrez le résultat dans le bas de la fenêtre \(et devant chaque item de la liste\) vous indiquant les chances de succès de connexion :**

**Vert :** Vous avez la bonne rom avec le bon hash, le bon core. Toutes les chances sont de votre côté pour que ca marche !

**Bleu :** Pas de correspondance du hash \(certaines roms n’ont pas de hash, comme les systèmes arcade\), mais le bon fichier a été trouvé. Ça devrait marcher !

**Rouge :** Fichier non trouvé, système interdit, pas le bon core. Aucune chance que le jeu en ligne marche ! \(rien ne sera lancé\)

## **Hôte ou Client ?** <a id="hote-ou-client"></a>

**Hôte :** "Démarrer l'hébergement" en sélectionnant le jeu auquel vous voulez jouer en réseau avec la **touche Netplay et attendez les joueurs.**

**Client :** Rejoignez le lobby avec la **touche Netplay** depuis le menu système, puis sélectionnez l’hôte auquel vous souhaitez vous connecter.

## **Tuto vidéo Recalbox Netplay:** <a id="tuto-video-recalbox-netplay"></a>

​[https://www.youtube.com/watch?v=cC8\_64SiE\_0&index=20&list=PL2oNQ0AT7fx2ExiSNrfHUzga5GnogI4sh](https://www.youtube.com/watch?v=cC8_64SiE_0&index=20&list=PL2oNQ0AT7fx2ExiSNrfHUzga5GnogI4sh)​

## Roms <a id="roms"></a>

**Les ROM utilisées pour le Netplay sont les No-Intro.**

Nous les utilisons car les No-Intro ne prennent que :

* les meilleures Roms sans erreur, ni aucun changement.
* les plus proches possible des jeux originaux.
* ont une meilleure compatibilité

### Arcade <a id="arcade"></a>

**Pour les roms Arcade télécharger :**

* **Fba Libretro** Fullset version \(0.2.97.44\)
* **Neo-Geo** Fullset version \(0.2.97.44\)
* **Mame**
  * Mame 2003 Romset mame \(0.78\) \[Default Core\]
  * Mame 2010 Romset mame \(0.139\)
  * imame4all Romset mame \(0.37b5\)

### Consoles <a id="consoles"></a>

**Pour les roms Consoles télécharger un 'Set No-Intro''**

* 32X
* Master-System
* Megadrive
* Nes
* PC- Engine
* SG1000
* Supergrafx
* Super Nintendo

**Remarque :** Pour la **Dreamcast** télécharger un **''Set redump''** . Une configuration supplémentaire est nécessaire pour cette console.

## **FAQ** <a id="v-faq"></a>

#### **1- Pourquoi je ne peux pas héberger ?** <a id="1-pourquoi-je-ne-peux-pas-heberger"></a>

Il y a 2 possibilités :

* Connexion internet insuffisante

  **Essayez en étant client.**

* Votre port ne s'ouvre pas automatiquement

  **Essayez en utilisant la fonction NETPLAY MITM**

  ou

  **Ouvrez votre port manuellement \(Recommander\)**

Vérifiez que vos cores soient en adéquation avec votre machine \(pc, raspberry pi ou autre\). De plus, certaines machines ne supportent que la fonction client.

#### **3- Est-ce que le Netplay requiert l’ouverture de port pour fonctionner?** <a id="3-est-ce-que-le-netplay-requiert-louverture-de-port-pour-fonctionner"></a>

Oui, l'hôte et le client doivent ouvrir les ports correctement.

Il existe une option de secours qui peut être utilisée par ceux qui ne peuvent pas ouvrir leurs ports \(Fonction NETPLAY MITM\).

#### **4- De quoi avez-vous besoin pour que le netplay fonctionne correctement?** <a id="4-de-quoi-avez-vous-besoin-pour-que-le-netplay-fonctionne-correctement"></a>

* Même version de Recalbox
* Même core pour l’émulateur
* Même rom \(signature de rom identique, nommée à la lettre et à la ponctuation prés \)
* Être connecté en RJ45

#### **5- Le netplay PSX / N64 / Dreamcast / GameCube / Wii / DS fonctionne-t-il?** <a id="5-le-netplay-psx-n64-dreamcast-gamecube-wii-ds-fonctionne-t-il"></a>

Non, les exigences de performances de ces consoles rendent difficile le netplay.

#### **6- Puis-je jouer à des jeux GB / GBC / GBA / PSP / DS avec plusieurs personnes via Netplay?** <a id="6-puis-je-jouer-a-des-jeux-gb-gbc-gba-psp-ds-avec-plusieurs-personnes-via-netplay"></a>

Non, le netplay de RetroArch n’est pas une émulation de câble de liaison. Les GB, GBC, GBA et PSP ne sont actuellement pas possibles avec notre implémentation. Les échanges de Pokémons et autres sont donc impossibles. Mais, une exception notable est le même jeu GB / GBC \(Netplay via les cores TGB-Dual et Sameboy\).

#### **7- Quels sont les cores Libretro compatibles Netplay ?** <a id="7-quels-sont-les-cores-compatibles-netplay"></a>

**A. Arcades :**

* Fba\_libretro \(core fba\_libretro Romset 0.2.97.44\)
* mame 2003 \(core mame\_078\)
* neogeo \(core fba\_libretro Romset 0.2.97.44\)

**B. Consoles :**

* Master-System \(picodrive\)
* Megadrive \(picodrive\)
* Nes
* Pcengine
* Sega32x
* Sg1000
* Supergrafx
* Snes \(snes9x - enable multitap\)

