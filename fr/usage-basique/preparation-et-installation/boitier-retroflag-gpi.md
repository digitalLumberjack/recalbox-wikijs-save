---
title: Boîtier RetroFlag GPi
---

# Boîtier RetroFlag GPi

## Préparation

### Éléments nécessaires

* 1 x Boîtier RetroFlag GPi
* 1 x Raspberry Pi Zéro W
* 1 x Carte SD
* 1 x Adaptateur de carte SD
* 1 x Dissipateur thermique \(pour votre carte RPI ZERO W\)
* 3 X Piles



### Les piles conseillées

* Duracell Recharge Ultra Piles Rechargeables type AA 2500 mAh 5 ou 6h autonomie [https://www.amazon.fr/dp/B00E3DVQFS?ref=ppx\_pop\_mob\_ap\_share](https://www.amazon.fr/dp/B00E3DVQFS?ref=ppx_pop_mob_ap_share) 
* Panasonic BK-3HCDE/4BE eneloop pro 2500mAh Lot de 4 piles Ni-MH AA/Mignon/LR6 [https://www.amazon.fr/gp/product/B00JWC40JY/ref=ppx\_yo\_dt\_b\_asin\_title\_o03\_s00?ie=UTF8&psc=1](https://www.amazon.fr/gp/product/B00JWC40JY/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1)

Avec une batterie externe de 10 000maH là c’est le festival !

## Présentation du Gpi Case

![](/migration-images/usage-basique/preparation-et-installation/image%20%28276%29.png)

![](/migration-images/usage-basique/preparation-et-installation/image%20%28248%29.png)

![](/migration-images/usage-basique/preparation-et-installation/image%20%2860%29.png)

## Flashez et démarrez !


>**Remarque :**  
>_**N'installez pas le GPI sur des piles !**_   
>Utilisez toujours le cordon USB pour l'installation et les premiers tests.
{.is-warning}

![GPi Case](/migration-images/usage-basique/preparation-et-installation/image%20%28202%29.png)



Flashez et démarrez, c'est aussi simple que ça ! _**Recalbox détecte et installe tout ce qui est nécessaire automatiquement.**_ 

Pour faire fonctionner votre boîtier GPI 

* Il vous suffit de flasher la dernière version de Recalbox pour Raspberry Pi1 / Pi0 sur votre carte SD, l'insérer dans la cartouche de votre GPI, et l'allumer ! 
* Attendez quelques secondes, puis vous devriez voir cette image sur votre écran :

![Image d&apos;installation](/migration-images/usage-basique/preparation-et-installation/image%20%28197%29.png)

* Attendez encore quelques secondes \(ça peut prendre plus longtemps avec des cartes SD haute capacité\) avant qu'EmulationStation ne démarre avec son écran habituel :

![EmulationStation d&#xE9;marre...](/migration-images/usage-basique/preparation-et-installation/image%20%28218%29.png)

* Une fois que c'est fait, appréciez un thème optimisé qui rend votre expérience riche, fluide et amusante !

## Qu'est-ce qui change par rapport à une Recalbox normal?

Quand Recalbox détecte et installe les éléments propres au boîtier GPI, il change aussi quelques paramètres pour vous permettre d'aller jouer rapidement.  
  
Bien sûr, tous les paramètres sont disponibles à travers le menu **START** et vous pourrez aller reconfigurer d'origine, tout ce que vous souhaitez ensuite.



### Voici une liste des paramètres modifiés par défaut :

* Tous les videomode sont mis à `default` pour éviter les changements de résolution HDMI inutiles 
* Le nom d'hôte du GPI est configuré à **RECALBOXGPI** 
* Kodi et le bouton X sont désactivés 
* La manette virtuelle est désactivée 
* Les mises à jour sont désactivées 
* Le Netplay est désactivé 
* Le bluetooth est désactivé 
* les pilotes XArcade & PS3 sont désactivés 
* Le popup musical est désactivé 
* La configuration XBOX360 a été remplacée par celle du GPI \(Oui, la manette du GPI est aussi une manette d'XBOX360 !\) 
* Notre thème optimisé recalbox-gpicase est déjà copié dans `/recalbox/share/themes` et activé



### Et sont aussi installés :

* dpi-pizero-gpicase.dtbo : Pilote de l'écran du GPI 
* pwm-audio-pizero-gpicase.dtbo : Pilote du son du GPI 
* Un script spécial d'arrêt pour le GPI, fait à la base par Retroflag et fortement modifié pour que le GPI s'éteigne rapidement.

## Configurer la connexion WIFI

Vous pouvez toujours utiliser le menu START, aller dans les sous-menus réseau et configurer le WIFI.

Cependant, sur le GPi, vous n'avez d'autre choix que d'utiliser la manette et le clavier virtuel pour entrer votre mot de passe. Si il est complexe, cela peut vite se transformer en une tâche fastidieuse.

  
Voilà une solution rapide, pas à pas

* Flashez et démarrez votre GPi. Quand EmulationStation a démarré, appuyez sur **START**, allez dans le menu réseau, activez le WIFI et sélectionnez votre SSID. 
* Eteignez votre GPi en utilisant le menu **SELECT** / option Arrêt, et _attendez que Recalbox s'éteigne !_ 
* Enlevez la carte SD et accédez à la partition **BOOT** sur votre PC. 
* Ouvrez le fichier recalbox-backup.conf, allez à ligne commençant par `;wifi.key=`  
* Enlevez le `;` et ajoutez votre mot de passe WIFI après le `=`. 
* Sauvegardez le tout, insérez la carte SD dans le GPI et démarrez-le. 
* Une fois EmlulationStation lancé, vous devriez être connecté en WIFI 
* Ouvrez \\recalboxgpi\share\system\recalbox.conf et changez encore la ligne `;wifi.key=`Vous pouvez aussi utiliser nano en ssh si vous le souhaitez. 
* Sauvegardez. C'est tout, vous êtes configuré !

## Installer des jeux

![](/migration-images/usage-basique/preparation-et-installation/image%20%2844%29.png)

Maintenant que vous êtes connecté à internet, vous pouvez installer vos jeux comme d'habitude, en utilisant le partage SAMBA \( `\\recalboxgpi\share` dans un explorateur de fichiers\) ou à travers le WebManager \( `http://recalboxgpi` dans un client web\)

Si votre GPI n'est pas connecté, et que vous faites tourner Windows sur votre PC, vous pouvez :

* Démarrer sur un live-CD linux , et avoir accès à vos disques ainsi qu'à la partition "share" de votre carte SD, de façon à ce que vous puissiez copier ce que vous voulez sur la carte SD. 
* Installer Partitionguru 4 
* Installer Paragon Software pour pouvoir accéder à la partition linux EXT4 de la carte SD \( [https://www.paragon-software.com/fr/home/linuxfs-windows/](https://www.paragon-software.com/fr/home/linuxfs-windows/#) \)

Amusez-vous avec vos jeux favoris !

## Ce que vous devriez savoir...

### Quel genre de jeux je peux faire tourner sur le GPI ?


>_**Information :  
>Vous pouvez lancer n'importe quel jeu des consoles et ordinateurs 8/16 bits jusqu'à l'arcade**_.  
>_**Oui, vraiment ! :-\)**_
{.is-info}

Pour l'arcade, vous avez **PiFBA**, une version de FBA optimisée pour ARM qui requiert un romset 0.2.96.37.  
**FBNeo** \(ancien FBAlpha\), **MAME2000** jusque **MAME2003plus** tournent aussi très bien et beaucoup de jeux y sont jouables.

Quelques jeux **GBA/SNES** ainsi que quelques jeux d'Arcade peuvent souffrir de lag ou ralentissements. Dans ce cas, vous pouvez essayer de désactiver l'option "rewind" dans les options avancées de l'émulateur.   
Cependant, même avec des options optimisées, certains jeux ne tourneront pas en full-speed.


>**Remarque :**  
>Il n'est pas recommandé d'installer des jeux pour ordinateur, ils ont souvent besoin d'un clavier et/ou d'une souris pour démarrer.
{.is-warning}



### Est-ce que je peux overclocker mon Pi0 ?

Malheureusement, le Raspberry Pi0 n'est pas facile à overclocker. De plus, la cartouche du GPi ne contient pas de trous de ventilation pour laisser l'air chaud sortir \(Du moins sur le boîtier GPi v1 utilisé au moment où cette page a été rédigée\).

_**Vous pouvez toujours jouer avec les options d'O/C, à vos risques et périls !**_


>**Attention :**  
>Si votre GPI n'est pas stable après avoir sélectionné une option d'O/C au point où il ne vous est plus possible de changer les options, insérez la carte SD dans votre PC et enlevez les lignes d'O/C depuis le fichier`config.txt`
{.is-danger}

Vous pouvez ajouter un petit radiateur en cuivre comme montré dans la photo ci-dessous. Son épaisseur ne doit pas dépasser 2mm.

![](/migration-images/usage-basique/preparation-et-installation/img_20190616_174526.jpg)



### Combien de temps dure la batterie ?

Les premiers tests montrent que vous aurez environ 2h de jeu sur une charge.

N'oubliez pas que votre boîtier GPI dispose d'une prise USB. Dans une voiture où à la maison, utilisez le câble USB.


>I**nformation :**  
>Si le dos de la cartouche commence à devenir très chaud, nous vous recommandons d'arrêter le GPI et de le laisser refroidir pendant un petit moment.
{.is-info}



### Comment je peux scraper mes jeux ?

* **Scrapeur interne :** Vous pouvez toujours utiliser le scraper interne, il est configuré pour scraper de gros fichiers dans le but de les afficher dans une RecalBox normale. L'utiliser sur WIFI est lent et inefficace. 
* **Scrapeur externe :** _****_**Nous recommandons vivement d'utiliser un scraper externe**. Il sera meilleur et plus rapide.


>**Remarque :**
>
>Vous pouvez aussi configurer la taille d'image max à 170x170 pour économiser de l'espace et accroître la vitesse d'EmulationStation avec le **Scrapeur externe.**
{.is-warning}

## Dépannage

* **Si l' affichage devient noir ou saute en effleurant la cartouche ou posant la console :**
  * Vérifier toutes les connexions.
  * Rehausser le rpi dans la cartouche, pour le rapprocher du circuit imprimé : Jouer avec les 4 plots qui supportent le Pi 0, en les dévissant légèrement jusqu'à ce que le Pi 0 soit parfaitement parallèle avec la cartouche. Selon les cas, dévisser les 2 plots dorés du haut peut suffire.


>**Remarque :**  
>Ce bug survient lors d'un problème d'usinage de la cartouche, la connexion entre le Pi 0 et la cartouche ne se fait pas correctement.
{.is-warning}

* **Résoudre les problèmes de stabilité :**

  * **1- La Micro-SD**

  Vérifiez votre microSD.  
  Certains modèles ont des soucis avec les Pi, sans compter les µSD chinoise de piètre qualité.  
  Testez avec une autre SD, de préférence d'une autre marque.  


  * **2- Les piles**

  _**N'installez pas le GPI sur des piles !**_   
  Utilisez toujours le cordon USB pour l'installation et les premiers tests.  
  Si ça fonctionne correctement avec le cordon et pas avec les piles, soit elles sont déchargées, soit elles ne fournissent pas assez de jus, malgré le régulateur du GPI.  
  La plupart des rechargeables sont des 1.2V, pas des 1.5V.  


  * **3. Le modèle de Pi0.**

  Il semblerait que certains modèles aient des problèmes de stabilité, du moins avec les clocks d'origines, configurées avec le Firmware du Pi \(c'est un comble !\).  
  Ouvrez le fichier `config.txt` dans la partition FAT32, et ajoutez les lignes suivantes à la fin du fichier :

  ```text
  arm_freq=1000
  gpu_freq=500
  core_freq=500
  sdram_freq=500
  sdram_schmoo=0x02000020
  over_voltage=6
  sdram_over_voltage=2
  ```

  Cela forcera la configuration des clocks avec un léger overclocking du GPU en prime.  


  * **4. Montage**

  Bien que le montage du Pi soit relativement facile, il se pourrait que votre montage induise des contacts imparfaits. Démontez la cartouche, nettoyez les contacts du Pi et du GPI avec une solution nettoyante à base d'alcool, remontez le Pi.  
  Nettoyez également les contacts de la cartouche dans le GPI.  
  Vérifiez que la cartouche soit bien enfichée. Le bouton d'allumage ne doit pas forcer, ni à l’allumage ni à l'extinction. S'il force, c'est que votre cartouche est mal insérée ou, que quelque-chose la gêne.  


  * **5. Pour finir...**

  Si malgré tout, votre Pi ne fonctionne pas, ou s'il reste instable, essayez avec un autre pour déterminer qui du  Pi ou du GPI est fautif. Faites-vous en prêter un, ou à la limite, vu le prix, rachetez-en.  
   Si le GPI est fautif, vous pourrez tenter un échange ou une reprise. En cas de soucis avec le vendeur, donnez lui toute la procédure que vous avez suivi afin de prouver votre bonne foi quant à l’incrimination du GPI.  

* Si vous êtes dans l'une des situations suivantes :
  * Au premier démarrage, il n'y a rien à l'écran même après avoir attendu un peu.
  * Vous ne pouvez pas configurer le WIFI. Contactez-nous sur le serveur Discord ou sur le Forum et donnez-nous les fichiers suivants, disponibles dans la partition BOOT de votre carte SD :
    * `config.txt`
    * `recalbox-backup.conf`
    * `hardware.log`


>**Attention :**  
>Pour les autres problèmes, écrivez-nous sur :   
>[Forum](https://forum.recalbox.com/) ou [Gitlab issues](https://gitlab.com/recalbox/recalbox/issues)
{.is-danger}

