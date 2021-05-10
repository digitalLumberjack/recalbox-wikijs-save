---
title: Préparation
---

# Préparation

## **I- Préparation des roms :** <a id="ii-preparation-des-roms"></a>

Vous devez respecter 5 étapes pour que vos roms soient préparées pour jouer en Netplay.

### **A - Les romsets Compatibles Netplay Libretro:** <a id="a-les-fullsets-compatibles-netplay"></a>

#### **1. Arcades :** <a id="1-arcades"></a>

* **Fba\_libretro** &gt; Romset fba\_libretro 0.2.97.44\)
* **Mame** Selon \(Choisir le romset selon le core voulant être jouer\)
  * Mame 2003 &gt; Romset mame \(0.78\) \[Default Core\]
  * Mame 2010 &gt; Romset mame \(0.139\)
  * imame4all &gt; Romset mame \(0.37b5\)
  * Neo-geo &gt; core fba libretro 0.2.97.44\)

#### 2. Consoles : <a id="2-consoles"></a>

* Dreamcast \(Libretro Flycast\)
* Master-System \(picodrive\)
* Megadrive \(picodrive\)
* Nes
* Snes \(snes9x - enable multitap\)
* Pc-Engine
* Sega 32x
* Sg-1000
* Supergrafx

### **B - Les romsets Compatibles Netplay Standalone:** <a id="a-les-fullsets-compatibles-netplay-1"></a>

#### Consoles : <a id="consoles"></a>

* GameCube
* Wii

### **C - Trier vos romsets** <a id="b-trier-vos-romsets"></a>

Les différentes préférences de tris.

#### **1 - National ou international ?** <a id="1-national-ou-international"></a>

* **National :** Si vous voulez jouer uniquement avec les personnes du même pays que vous : gardez uniquement les roms de votre pays **puis privilégiez les roms USA et Japon pour les manquants.**
* **International :** Si vous voulez jouer avec des personnes des autres pays : gardez une rom de chaque pays.

Mettre un exemple

​

#### **2 - Les Retroachievements :** <a id="2-les-retroachievements"></a>

Certains trophées Retroachievement, ont besoin de la rom USA pour valider les retroachievements et certains jeux n'existent que en version JAP.

​[https://recalbox.gitbook.io/tutorials/fr/generalite/retroachievements](https://recalbox.gitbook.io/tutorials/fr/generalite/retroachievements)

#### **3 - Trier avec un logiciel** <a id="3-trier-avec-un-logiciel"></a>

Pour savoir déterminer à quoi correspondent [les codes et tags dans les roms](https://recalbox.gitbook.io/tutorials/fr/generalite/tags-utilises-dans-le-nom-des-roms).

**Plusieurs logiciels existent :**

* Universal Rom Cleaner

​[https://github.com/Universal-Rom-Tools/Universal-ROM-Cleaner/releases](https://github.com/Universal-Rom-Tools/Universal-ROM-Cleaner/releases)​

* Clrmamepro \( à l'aide d'un fichier dat\)

​[https://mamedev.emulab.it/clrmamepro/](https://mamedev.emulab.it/clrmamepro/)​

* Romulus \( à l'aide d'un fichier dat\)

​[http://romulus.net63.net/\#downloads](https://romulus.cc/#downloads)​

* RomCenter \( à l'aide d'un fichier dat\)

​[http://www.romcenter.com/](http://www.romcenter.com/)​

​

#### **4 - Trier à la main** <a id="4-trier-a-la-main"></a>

Travail fastidieux qui vous demandera une énorme patience et beaucoup de temps.

​

### **D - Obtention d'un fichier dat pour les logiciels de tri** <a id="c-obtention-dun-fichier-dat-pour-les-logiciels-de-tri"></a>

Téléchargez les fichiers dat de vos consoles à trier.

​[http://datomatic.no-intro.org/](http://datomatic.no-intro.org/)​

​[http://redump.org/downloads/](http://redump.org/downloads/)​

​

### **E - Scraper vos romsets** <a id="d-scraper-vos-romsets"></a>

Plusieurs façons existent pour scraper vos roms:

#### **1. Scraper avec l'outil intégré de Recalbox** <a id="1-scraper-avec-loutil-integre-de-recalbox"></a>

* Menu EmulationStation \(Start\)
* Scraper

#### **​** <a id="2-scraper-vos-roms-avec-des-logiciels-dedies-pour-conserver-plus-dinformation-dans-le-titre-de-vos-jeux-metadata-exemple-hack-region-traduction"></a>

#### **2. Scraper vos roms avec des logiciels dédiés pour conserver plus d'information dans le titre de vos jeux \(Metadata exemple : Hack Region traduction\)** <a id="2-scraper-vos-roms-avec-des-logiciels-dedies-pour-conserver-plus-dinformation-dans-le-titre-de-vos-jeux-metadata-exemple-hack-region-traduction-1"></a>

* **Skraper**

​[https://www.skraper.net/](https://www.skraper.net/) \(compatible windows/Linux et bientôt Mac\).

* **Universal XML Scraper**

​[https://github.com/Universal-Rom-Tools/Universal-XML-Scraper](https://github.com/Universal-Rom-Tools/Universal-XML-Scraper) \(compatible windows\)

**Tuto video de Skraper et Universal XML Scraper:**

​[https://www.youtube.com/watch?v=vV8DxtdOCaU&index=15&list=PL2oNQ0AT7fx2ExiSNrfHUzga5GnogI4sh](https://www.youtube.com/watch?v=vV8DxtdOCaU&index=15&list=PL2oNQ0AT7fx2ExiSNrfHUzga5GnogI4sh)​

​

### **F - Hasher vos roms** <a id="e-hasher-vos-roms"></a>

Le **HASH** est une empreinte numérique unique pour une **meilleure reconnaissance** lors du choix d’une partie \(il s'agit d'un checksum CRC32 de la rom\).

* Pour vérifier le hash d'une ou plusieurs roms manuellement depuis votre ordinateur :

Télécharger ce logiciel [md5sum](http://esrg.sourceforge.net/utils_win_up/md5sum/).​

* Depuis un `terminal` `crc32 /path/to/file` .
* Remplacer /path/to/file par le chemin de votre fichier.
* Ouvrir votre `terminal` .
* Saisir `crc32 /path/to/file` .
* Remplacer `/path/to/file` par le chemin de votre fichier.
  * `Clic droit` sur votre fichier, choisir `copier`.
  * Puis `coller` \(cmd+v\) dans la fenêtre du `terminal`.
* **Le Hash est donc obligatoire pour le bon fonctionnement du Netplay.**
* Menu Emulationstation
* Options des jeux
* Options Netplay
* HASH

Cependant des roms ne possèderont pas de Hash, c’est le cas des systèmes d’Arcade:

* Fba Libretro
* Mame
* Neo-Geo

**Information :** Certains programmes peuvent hasher et scrapper en même temps par exemple Skrapper !!.

## **II- Paramétrage du système Netplay** <a id="iii-parametrage-du-systeme-netplay"></a>

### **A - Configurer votre port** <a id="b-configurer-votre-port"></a>

**Information :** Certains modems possèdent l'UPnP qui permet l'ouverture/fermeture automatiques des ports.

#### **1. Vérifiez que votre port gère l’UPnP :** <a id="1-verifiez-que-votre-port-gere-lupnp"></a>

* Commencez à héberger un jeu !!!.
* * Renseignez le port 55435 puis appuyez s ur Check.

#### 2. La réponse est “positif” : <a id="2-la-reponse-est-positif"></a>

Vous n'avez pas besoin d'ouvrir le port, passer à l'étape C

#### 3. La réponse est “négatif” : <a id="3-la-reponse-est-negatif"></a>

Ouvrez **un port manuellement** \(recommandé\) ou utilisez **Netplay MITM**.

* **Connexion directe \(relay server sur off\)** Il est nécessaire d’ouvrir le port 55435 de votre modem internet. **Ouvrir votre port manuellement:** Selon votre FAI l’opération à faire est différente. Renseignez-vous sur le site de votre opérateur ou sur des forums.
* **L'option Netplay MITM** Relay Server \(**Le Server relais\)** permet d’outrepasser l’ouverture des ports de votre modem. Cela permet d'acheminer les deux côtés de la connexion via un serveur d'intermédiaire.

  Cependant cela aura un impact sur la vitesse à laquelle les données se synchronisent et donc sur la réactivité du jeu

#### **Dans qu'elle cas l'utiliser?** <a id="dans-quelle-cas-lutiliser"></a>

* Votre routeur ne prend pas en charge le protocole UPnP \(ouverture et fermeture automatique des ports\)
* Vous ne pouvez pas ouvrir vos ports
* Vous avez un doute : **Activez l'option Utiliser l’option Netplay MITM.**

**Attention :**

Il est recommandé d'ouvrir son port manuellement ou d'avoir une box qui gère l'UPnP, car le serveur relais va ajouter une latence supplémentaire.

RetroArch ne vérifie pas si vos ports sont ouverts, pas plus que le serveur de lobby libretro. Assurez-vous donc d'ouvrir votre port correctement ou activez le serveur relais, sinon les utilisateurs ne pourront pas se connecter à votre session.

​

### **B - Configuration de votre surnom** <a id="c-configuration-de-votre-surnom"></a>

Nous vous conseillons de mettre le même pseudo que sur Discord afin de se repérer plus facilement.

* Menu EmulationStation
* Options des jeux
* Options netplay
* Surnom
* **Renseignez votre pseudo**

