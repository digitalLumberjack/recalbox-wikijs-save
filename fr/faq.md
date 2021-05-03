---
title: 💡 FAQ
---

# 💡 FAQ

## Général

* **Sur quoi puis-je installer Recalbox OS ?**

> - Raspberry Pi Zero  
> - Raspberry Pi 1 \(B/B+\)  
> - Raspberry Pi 2  
> - Raspberry Pi 3 \(B/B+\)  
> - Raspberry Pi 4  
> - Raspberry Pi 400  
> - Odroid XU4  
> - Odroid Go Advance 2  
> - PC x86 \(32bits\)  
> - PC x86\_64 \(64bits\)

* **Comment puis-je participer ?**

> - Vous pouvez faire un don direct sur notre paypal    
> - Vous pouvez commandez votre matériels sur Kubii via ce lien \(une partie nous reviendra\)  
>  - Vous pouvez remonter des bugs ou des idées d'amélioration sur notre [Gitlab](https://gitlab.com/recalbox/recalbox/issues).  
>  - Vous pouvez participer sur les [forums Recalbox.com](http://blog.recalbox.com/forums)

* **Où puis-je voir l'avancée du développement de la Recalbox?**

> Sur le [gitlab de Recalbox-os](https://gitlab.com/recalbox).  
> Vous pouvez accéder :  
> - aux '[issues](https://gitlab.com/recalbox/recalbox/issues)' qui sont les tâches en cours.  
> - aux 'milestones' vous pourrez voir les tâches qui sont encore à développer, et celles qui sont terminées \(**Changer le lien**\).

* **La Recalbox contient combien de jeux ?**

> Nous essayons d'ajouter un maximum de jeux libres dans la distribution, pour que vous puissiez profiter de l'expérience Recalbox dès le premier lancement !  
> Rendez-vous sur [https://forum.recalbox.com/topic/52/homebrews-sur-la-recalbox](https://forum.recalbox.com/topic/52/homebrews-sur-la-recalbox) pour proposer vos homebrews !

* **Puis-je utiliser Recalbox dans une borne / bartop ?**

> Oui.  
> Le système Recalbox OS a été aussi pensé pour l'intégration dans les bornes et bartops.  
> - Vous pouvez brancher les boutons et joysticks directement sur les GPIO du Raspberry.  
> - Vous pouvez désactiver les menus pour éviter toute mauvaise manipulation.  
> - Il est aussi possible d'utiliser les sorties HDMI / DVI /VGA \(avec adaptateur\) ou RCA.  
> Plus d'infos sur [la page dédiée](/fr/tutoriels/systeme/installation/configuration-recalbox-pour-bartop-borne-arcade).

* **La Recalbox supporte une trentaine de consoles mais je n'en vois que quelques unes dans l'interface, que faire?**

> Seuls les systèmes ayant des jeux disponibles s'affichent.  
> Essayez d'ajouter vos roms \(voir la [Notice](https://github.com/recalbox/recalbox-os/wiki/Notice-%28FR%29)\) via le réseau et redémarrez la Recalbox pour voir apparaître les nouveaux systèmes.  
> De plus certains matériels ne supportent pas toutes les consoles.  
> Plus d'infos sur ~~**mettre le lien**~~

* **Dois-je overclocker mon Raspberry Pi?**

> Sur Raspberry Pi 1 \(y compris zero\), il est vivement conseillé d'overclocker le Raspberry en mode EXTREM. Vous perdez la garantie mais le gain de performance est phénoménal\).

## Emulationstation

* **Comment changer l'apparence du thème d'EmulationStation ?**

> Touche Entrée sur le clavier ou Start sur la manette → Paramètres interface → Thème \(tout en bas\)

* **Comment couper la musique de fond ?**

> Touche Entrée sur le clavier ou Start sur la manette → Paramètre du son → Mettre sur Off

* **Où se situent les fichiers de configuration d'EmulationStation dans le système de fichiers ?**

> /root/.emulationstation

* **Où sont situés les thèmes d'EmulationStation ?**

> /root/.emulationstation/themes

## Emulation

* **Pourquoi y a-t-il plusieurs émulateurs pour chaque système ?**

> L'émulation n'est pas une opération sans faille, il y a un équilibre entre performances, fonctionnalités et fidélité.  
> Étant donné que l'émulation n'est pas parfaite, il est préférable d'avoir plusieurs options pour la gérer, parfois un émulateur plus rapide sera meilleur mais peut avoir des problèmes inattendus, tandis qu'un plus lent peut avoir une précision plus élevée mais ne prend pas en charge certaines fonctionnalités spécifiques.

* **Comment changer l'émulateur par défaut pour un système donné ?**

> En appuyant sur Démarrer sur la manette de jeu, puis en accédant aux paramètres avancés, puis à la configuration avancée des émulateurs.  
> Vous pouvez sélectionner le système souhaité, enfin, vous pouvez changer les paramètres de l'émulateur et du noyau \(notez que le paramètre de base ne changera pas si le paramètre de l'émulateur indique Défaut\)

## Système

* **La recalbox supporte une 30ene de consoles mais je n'en vois que quelques unes, que ce soit dans l'interface EmulationStation ou dans le dossier share ?**

> Selon la Carte que vous utiliser vous aurais les émulateurs compatible avec celle-ci.  
> Veuillez regarder la liste des compatibilités selon les cartes :

* **Pourquoi sur certains systèmes comme la GBA, mes jeux affichent un écran noir puis un retour sous ES ?**

> Certains systèmes nécessitent des bios pour fonctionner.  
> Plus d'infos sur [la page dédiée du wiki.](https://github.com/recalbox/recalbox-os/wiki/Ajoutez-des-bios-%28FR%29)

## Dépannage général

* **Ma Recalbox vient de planter, dois-je la débrancher et la rebrancher?**

> Non, dans la plupart des cas, le système n'a pas complètement planté, seule EmulationStation l'a fait.  
>   
> Il existe plusieurs façons de gérer cette situation, la plus simple étant l'utilisation des fonctionnalités de débogage du webmanager pour redémarrer ES ou pour arrêter correctement Recalbox.   
>   
> Ne pas le faire peut corrompre vos données, surtout si vous utilisez un Raspberry Pi avec une carte SD.

## Dépannage Connectivité

### Windows 10 - impossible d'accéder à Recalbox depuis le partage réseau

* **Cas n°1: Aucun ordinateur, incluant Recalbox, n'est visible depuis Windows**

Si vous ne voyez aucun ordinateur depuis le réseau de Windows 10, c'est parce que la découverte du réseau est désactivée par défaut et que la configuration du réseau est positionnée sur "publique" ou que "rendre ce PC détectable" est sur "désactivé".

Vous devez aller dans les paramètres réseau et mettre votre réseau en mode "privé", ou mettre "rendre ce PC détectable" sur activé".

* **Cas n°2: Recalbox n'est plus accessible depuis la mise à jour n°1709 de Windows 10**

Depuis cette mise à jour, vous voyez Recalbox dans votre réseau, mais vous ne pouvez plus y accéder.

Explication officielle \(en anglais\): [https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/](https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/) ou [https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016](https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016)

Réparation rapide : Téléchargez et appliquez [ce patch](https://mega.nz/#!rUA3xDgI!a14w9TqQWinLriLANpk7BF_WkoNg8mw6fHloyPEZMPg)

Ce patch va désactiver la sécurité sur les accès réseaux anonymes dans Windows pour rétablir l'accès à Recalbox.

* **Cas n° 3 \(cas le plus courant\)**

Aller dans tous les paramètres / applications / programmes et fonctionnalités / activer ou désactiver des fonctionnalités windows et cocher : support de partage de fichiers SMB 1.0/CIFS / client SMB1.0/CIFS... puis redémarrer Windows.

