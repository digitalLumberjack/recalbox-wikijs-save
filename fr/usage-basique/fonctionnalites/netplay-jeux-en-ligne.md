---
title: Netplay \(Jeux en Ligne\)
---

# Netplay \(Jeux en Ligne\)

![](./netplay-jeux-en-ligne/logo-recalbox_netplay.png)

## **Introduction** <a id="i-introduction"></a>

Le Netplay est une fonctionnalité permettant le mode multijoueur en réseau avec certains émulateurs via la mise en réseau peer-to-peer \(P2P\) pour réduire la latence du réseau, afin de garantir la meilleure expérience possible en synchronisant en continu plusieurs instances exécutant le même noyau d'émulation et le même contenu.  
Vous avez également la possibilité d’avoir aussi des personnes pouvant rejoindre en mode spectateur \(latence supplémentaire\).  
Du jeu en ligne sur nos vieilles consoles qui ne connaissait même pas encore cette faculté !

## **Recommandations:**

### Connexion :

* Connectez votre machine en Câble Ethernet RJ45 \(une connexion wifi étant bien moins stable\).
* Avoir une box qui gère l'UPNP ou Ouvrir son port manuellement.
* Si la Recalbox est derrière le routeur, tout est OK \(simple NAT\).
* Si la Recalbox est derriere 2 routeurs alors le Netplay ne passe pas \(Double NAT\).

### Roms :

* **Pour les Consoles Cartouches :**
  * Utilisez des roms issues de romsets **No-Intro** \(dumps plus proche des jeux originaux\)
* **Pour les Consoles CD :**
  * Utilisez des roms issues de romsets **Redump** \(dumps plus proche des jeux originaux\)

### Système :

* Si vous utilisez un Raspberry Pi0, Pi1, Pi2 , Pi3-b et Pi3-b+ un **overclock** \(À 1300 MHZ\) est **conseillé voir obligatoire**.
* Pour les versions Pc x86-64 \(64bit\), x86 \(32bit\) et l’Odroid l’overclock n’est pas nécessaire.

## Message d'erreur Netplay

#### En tant que client: "Failed to Initialize Netplay" ==&gt; «Échec de l'initialisation de Netplay»[¶](https://j7mtvrpe2jptssgylib6apqjre--docs-libretro-com.translate.goog/guides/netplay-faq/#as-client-failed-to-initialize-netplay) <a id="as-client-failed-to-initialize-netplay"></a>

«Échec de l'initialisation de Netplay» signifie souvent que vous n'avez pas pu vous connecter à l'hôte.  
Confirmez que vous disposez de l'adresse IP correcte pour l'hôte et que l'hôte a commencé à héberger une session NetPlay. Dites à l'hôte de vérifier si son pare-feu basé sur l'hôte autorise RetroArch à accepter les connexions et confirmez que la redirection de port fonctionne.

#### En tant qu'hôte: "Port Mapping Failed" ==&gt; «Échec du mappage de port»[¶](https://j7mtvrpe2jptssgylib6apqjre--docs-libretro-com.translate.goog/guides/netplay-faq/#as-host-port-mapping-failed) <a id="as-host-port-mapping-failed"></a>

«Échec du mappage de port» indique probablement un problème de transfert de port UPnP.  
Si vous pouvez configurer manuellement votre passerelle réseau pour transférer le port TCP 55435 à l'adresse IP du réseau local de votre appareil RetroArch, vous pouvez le faire. Vous pouvez également activer l'utilisation d'un serveur relais \(rajoute une latence\).

#### "Content not found, try loading content manually" ==&gt; "Contenu non trouvé, essayez de charger le contenu manuellement" <a id="retroarch-says-content-not-found-try-loading-content-manually"></a>

* Chargez le contenu manuellement, placez le contenu dans votre liste d'historique récent ou scannez votre contenu vers une liste de lecture.

## **FAQ** <a id="v-faq"></a>

#### **1- Pourquoi je ne peux pas héberger ?** <a id="1-pourquoi-je-ne-peux-pas-heberger"></a>

Il y a 2 possibilités :

* Connexion internet insuffisante

  **Essayez en étant client.**

* Votre port ne s'ouvre pas automatiquement

  * **Activez l'option UPNP de votre box internet**

  ou

  * **Ouvrez votre port manuellement \(Recommander\)**

  ou en dernier recours

  * **Essayez en utilisant la fonction NETPLAY MITM** 

#### **2- Si je lance l'hébergement, le jeu se coupe et revient sur le menu recalbox.** <a id="2-si-je-lance-lhebergement-le-jeu-se-coupe-et-revient-sur-le-menu-recalbox"></a>

Vérifiez que vos cores soient en adéquation avec votre machine \(pc, raspberry pi ou autre\). De plus, certaines machines ne supportent que la fonction client.  


#### **3- Est-ce que le Netplay requiert l’ouverture de port pour fonctionner?** <a id="3-est-ce-que-le-netplay-requiert-louverture-de-port-pour-fonctionner"></a>

Oui, l'hôte et le client doivent ouvrir les ports correctement.

Il existe une option de secours qui peut être utilisée par ceux qui ne veulent pas ouvrir leurs ports \(Fonction NETPLAY MITM\).  


#### **4- De quoi avez-vous besoin pour que le netplay fonctionne correctement?** <a id="4-de-quoi-avez-vous-besoin-pour-que-le-netplay-fonctionne-correctement"></a>

* Même version de Recalbox.
* Même version de Retroarch ou Dolphin.
* Même core pour l’émulateur.
* Même rom \(nommée à la lettre et à la ponctuation prés et signature de rom identique\).
* Être connecté en RJ45 \(recommandé\). 

#### **5- Le netplay PSX / N64 / Playstation / PSP / Dreamcast / DS fonctionne-t-il?** <a id="5-le-netplay-psx-n64-dreamcast-gamecube-wii-ds-fonctionne-t-il"></a>

Non, les exigences de performances de ces consoles rendent difficile le netplay.  


#### **6- Puis-je jouer à des jeux GB / GBC / GBA / PSP / DS avec plusieurs personnes via Netplay?** <a id="6-puis-je-jouer-a-des-jeux-gb-gbc-gba-psp-ds-avec-plusieurs-personnes-via-netplay"></a>

Non, le netplay de RetroArch n’est pas une émulation de câble de liaison.  
Les GB, GBC, GBA et PSP ne sont actuellement pas possibles avec notre implémentation.  
Mais, une exception notable est le même jeu GB / GBC \(Netplay via les cores TGB-Dual et Sameboy\).  
Les échanges de Pokémons et autres sont donc impossibles.   


#### 7- RetroArch prend-il en charge le netplay multiplateforme?[¶](https://j7mtvrpe2jptssgylib6apqjre--docs-libretro-com.translate.goog/guides/netplay-faq/#does-retroarch-support-cross-platform-netplay) <a id="does-retroarch-support-cross-platform-netplay"></a>

Oui, mais votre kilométrage peut varier, en particulier lorsque l'endianité diffère.  


