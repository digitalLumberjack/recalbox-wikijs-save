---
title: Utilisation d'un stockage externe
---

# Utilisation d'un stockage externe

## Introduction

Vous pouvez très facilement **utiliser un périphérique USB de stockage** \(clé USB, disque dur externe auto alimenté etc.\) pour stocker vos roms, fichiers perso etc...

Premièrement, vous devez utiliser **un périphérique utilisant un système de fichiers** suivant : **FAT32, EXT4 ou NTFS** \(les taux de transferts peuvent être lents dans le cas du NTFS, attention donc\).


>**Information :**
>
>**Depuis la version 4.1**, vous pouvez également utiliser **le système de fichiers EXTFAT.**
{.is-info}

Soyez également certain que **le système de fichier** que vous choisirez **soit bien compatible avec le système d'exploitation de votre PC.**

RecalboxOS **ne formatera pas** votre périphérique, il ne **créera que de nouveaux fichiers dessus.**

## Optionnel : Synchroniser votre clé ou disque USB avec votre carte SD

Recalbox peut **synchroniser manuellement** **votre périphérique USB avec votre carte SD.**   
Cette étape est **optionnelle** mais doit être réalisée **avant de modifier vos paramètres de stockage USB.** 

**Voici les étapes:**

* **Démarrez** votre Recalbox. 
* **Branchez votre périphérique USB** quand vous voulez 
* [Connectez-vous en SSH](https://github.com/recalbox/recalbox-os/wiki/accès-root-sur-Terminal--%28FR%29) sur votre pi. 
* **Tapez** `cd /recalbox/scripts`  ****
*  **La command**e `./recalbox-sync.sh list` vous donne l**a liste des périphériques disponibles.** 

**Par exemple :**

```text
# ./recalbox-sync.sh list
INTERNAL
DEV A80A-27A5 NO_NAME
```

Donc le **nom de ma clé USB** est **NO\_NAME**, sa **référence de périphérique** est **A80A-27A5.**  
Je peux **la synchroniser avec.**

```text
./recalbox-sync.sh sync A80A-27A5
sending incremental file list
./
.keep
bios/
bios/lisez-moi.txt
bios/readme.txt
```

```text
sent 111,817,693 bytes received 8,256 bytes 9,723,995.57 bytes/sec total size is 111,758,686
speedup is 1.00 rsync error: some files/attrs were not transferred (see previous errors) (code 23)
 at main.c(1178) [sender=3.1.2]
```

## Configuration

## 

Vous y êtes! Ne vous inquiétez pas pour les erreurs!   
Maintenant **votre périphérique USB** contient la **copie des données de votre carte SD.**  
Vous pouvez continuer avec la prochaine étape.

### Configurer Recalbox

Configurer Recalbox pour **utiliser un périphérique de stockage USB.**

* **Branchez votre périphérique** à votre recalbox, puis **allumez la.** 
* Une fois **sous l'interface de recalbox**, **pressez le bouton start** de votre manette, **allez dans les options système** et **dans média de stockage.** 
* Maintenant, **sélectionnez votre périphérique** dans la liste, puis **validez** et **attendez que le système ait redémarré.**


>**Information :**
>
>**Durant cette phase de redémarrage**, recalboxOS va **créer à la racine de votre périphérique**, **un nouveau répertoire** nommé **\`recalbox\`** qui contiendra toute **l'arborescence de votre partition \`/share\`.**
{.is-info}



### Ajouter vos fichiers

Pour **ajouter vos fichiers** \(roms, sauvegardes de jeux, bios, données de scrape etc...\) sur votre **périphérique de stockage**, vous devez :

* **Eteindre votre recalbox.** 
* Puis **branchez votre périphérique à votre PC.** 
* Il ne vous reste plus qu'à **copier vos fichiers perso sur votre périphérique** depuis votre PC, **sans utiliser votre réseau local.** 
* Une fois **le transfert terminé**, il ne vous reste plus qu'à **rebrancher votre périphérique à votre recalbox, l'allumer et jouer.**


>**Informations :**
>
>**Avec cette méthode**, le **système** \(sur la carte sd\) et la **partition share** \(sur le périphérique\) **sont séparés.**  
>Donc ****si vous deviez **réinstaller votre système**, vous **conserveriez toutes vos données utilisateur.**   
>Vous n'aurez alors qu'à **rebrancher votre périphérique** à votre recalbox, puis **le sélectionner dans le système, et jouer.**
{.is-info}



### Disque dur invisible

Que faire si après **le redémarrage Recalbox ne voit toujours pas** le disque dur ?


>**Parfois**, après avoir sélectionné **le périphérique dans EmulationStation,** puis **redémarré**, Recalbox **ne parvient pas à créer le système de fichiers** sur celui-ci.  
>Il continue alors d'**utiliser les fichiers de la carte SD.**  
>Cela se produit notamment avec **certains disques durs assez lents à s'initialiser.**
{.is-info}

Ce que vous **pouvez faire**:

* **Connectez-vous en ssh** \(https://github.com/recalbox/recalbox-os/wiki/acc%C3%A8s-root-sur-Terminal--%28FR%29\) 
* **Tapez ces commandes:**  `mount -o remount, rw /boot cd / boot nano recalbox-boot.conf`  ****
* **Rajoutez** cette ligne : **sharewait=30** 
* **Sauvegardez** par **Ctrl X**`,`**Y**`,`**Entrée** 
* **Tapez** **reboot\`** et **validez**, Recalbox **redémarre.**


>**Remarque :**
{.is-warning}





