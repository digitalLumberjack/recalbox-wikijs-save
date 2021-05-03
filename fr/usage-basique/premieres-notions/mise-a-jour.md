---
title: Mise à jour
---

# Mise à jour

## Processus de mise à jour


>**Information :**
>
>Voici les **possibilités de mises à jour** de Recalbox.  
>J'espère que ce résumé vous aidera et vous apportera les réponses que vous chercher.
{.is-info}

_Vérifier votre situation :_

### **Est il possible de faire la mise à jour de Recalbox x.x vers Recalbox 7.0 ?**

_**Non**, il n'est pas possible de faire la mise à jour vers la nouvelle version de Recalbox 7.0.  
 Une installation propre est requise. Voir plus bas pour instruction._



### **Est-il possible de faire un multiboot avec PINN ou NOOBS avec Recalbox 6 RCxxx ?**

**Non.** Il est pas possible de faire un multiboot avec les versions béta,ou RC \(release candidate\) de Recalbox avec Noobs.  
Lorsque que:

* Recalbox 6 sera en version stable.
* Que Noobs accepte de nous ajouter à sa liste.\*
* Semblerait que PINN suit notre développement. \(A tester\)



### **Que faire si j'utilise un thème custom**

* Assurez vous d'être à jour au niveau des systèmes, des fichiers de configuration de votre thème.
* Contacter l'auteur de votre thème ou le sujet de votre thème afin de vérifier si une nouvelle version à jour est disponible.
* Utiliser un thème personnalisé en 720p sur Raspberry, en 1080p votre rpi va souffrir.
* Nous **n'assurons pas le support** pour les thèmes personnalisés **non officiel de Recalbox.**
* Merci de mettre **le thème de recalbox par défaut** pour vérifier vos bugs avant de poster votre problème sur le forum.



### **Que faire si j'utilise des OVERLAYS ?**

* Si vous utilisez ceux de [screenscraper](https://www.screenscraper.fr/forum.php), aller vérifier si les packs ont été mis à jour pour recalbox 6.0
* Si vous avez créer vos overlays, retroarch a ajouté un nouveau aspect ratio qui décale certains overlays :

  * tester 22 ou 23 sur cette ligne : 

  `aspect_ratio_index = 21`



### **Les arcades**

Recalbox a mis à jour les cores des émulateurs arcade : mame & fba libretro et ajouter d'autres émulateurs.

Par ce fait, il faut adapter vos romsets :

* Les fichiers dat globaux se trouvent désormais dans /bios/mame2003 ou /fba ou /mame2010 ou /advmame
* Pour réaliser des dat parent-only, neogeo parent only etc... il vous suffira d'utiliser ce [tutoriel datutil.exe](https://forum.recalbox.com/topic/4571/tutorial-datutil) pour les créer.
* core libretro Fba libretro : romset 0.2.97.44
* core libretroMame 2003 : romset mame 0.78
* core libretroMame 2010 : romset mame 0.139
* émulateur standalone advanceMame : romset mame 0.106\(réservé aux utilisateurs expérimentés\).
* Mame 2003-plus : romset 0.78 et plus \([documentation](https://docs.libretro.com/library/mame2003_plus/#Building-romsets-for-MAME-2003-Plus)\) \([documentation pour créer votre romset](https://github.com/libretro/mame2003-plus-libretro/wiki)\).
* [Mame 2003-plus](https://github.com/libretro/mame2003-plus-libretro/blob/master/CHANGELOG.md) est une version évolué de mame 2003 proposant des options supplémentaires absentes de mame 2003 et des jeux supplémentaires.
* Consulter la documentation arcade.



### **Votre RPI dans un boitier**

* Assurez vous d'avoir une bonne ventilation.
* Un bon câble d'alimentation.
* Si vous avez des soucis , sortir votre RPI de votre boitier et tester Recalbox 7.0 à nu.



### **Nos conseils :**

* Avoir une sauvegarde de votre share sur votre PC ou disque dur externe.
* Utiliser un support amovible \(clé usb ou disque dur externe\) vous comprendrez rapidement qu'une réinstallation est plus rapide.
* Utiliser un scrapper externe
* Toujours avoir 2 microsd, 8Go suffit pour le système \(une pour la version stable, une autre pour vos tests, ou tests béta\) d'où l'intérêt d'avoir ses roms sur support amovible.
* Installer des dissipateurs thermiques ou ventilateur si nécessaire notamment si :
  * Si vous overlockez votre CM.
  * Si votre Recalbox est dans un boîtier.

## Lancer la mise à jour


>**Information :**
>
>La **mise à jour de Recalbox** est accessible via le menu "**Mise à Jour**" accessible en appuyant sur **START**.
{.is-info}

* **Configurez votre wifi** ou **branchez un câble réseau** sur votre Recalbox.
* Sélectionnez "**OPTIONS SYSTEME**".
* Puis “**Mettre à jour la Recalbox**”.
* Et  "**Démarrer la mise à jour**". 

Le système **redémarre automatiquement** après la mise à jour !


>**Attention :**
>
>Si vous utilisez une version de Recalbox **antérieure à la version 7.0**, il n'est **pas possible** d'effectuer une Mise à Jour de manière **automatique.**
>
>Il vous faudra effectuer une[ **réinstallation popre**](/fr/usage-basique/premieres-notions/reinstallation-propre) pour pourvoir bénéficier de [la dernière version disponible.](https://archive.recalbox.com/)  
>  
>Ainsi de procéder au processus de mise à jour pour **ne pas perdre** vos réglages, sauvegardes, roms et bios.
{.is-danger}

