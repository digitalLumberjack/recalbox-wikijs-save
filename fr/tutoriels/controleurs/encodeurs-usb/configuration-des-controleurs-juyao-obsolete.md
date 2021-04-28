---
title: Configuration des contrôleurs Juyao \(obsolète ?!\)
---

# Configuration des contrôleurs Juyao \(obsolète ?!\)

## Pinout <a id="pinout"></a>

Cette carte est l'une de celle qui permet de raccorder **le plus de boutons** et gère **deux joueurs**. Vous devez suivre le câblage suivant : ​

![Juyao mapping keys](http://image.dhgate.com/0x0/f2/albu/g2/M00/F2/A5/rBVaGlZhCQWAUlMrAAD1xDQpwYk580.jpg)


>**Attention :  
>Sur certaines cartes,** J1 et J2 sont i**nversés**, nous vous conseillons de **tester** vos stick **avant de tout raccorder**. Le risque serait que votre J1 soit à droite, votre J2 à gauche.
{.is-danger}

## Paramétrage <a id="parametrage"></a>

**Les interfaces USB Juyao** nécessitent quelques **paramétrages avant d'être reconnues** par Recalbox.

_**À partir de la version 4.1**,_ les configurations suivantes **seront obsolètes.**

* Commencez par vous ****[**connecter en SSH**](/v/francais/tutoriels/systeme/acces/acces-reseau-via-winscp) avec WINSCP et PuTTY.
* Passez votre partition [**en écriture**](/v/francais/tutoriels/systeme/acces/acceder-a-une-partition-en-ecriture) avec la commande`mount -o remount,rw /boot`  
* **Modifiez** ensuite le fichier situé dans `/boot/cmdline.txt` avec **Notepad++** \(sous windows\) ou en **SSH** `nano /boot/cmdline.txt`

1 . **Ajoutez** en fin de ligne avec un espace après les derniers mots

`usbhid.quirks=0x314:0x328:0x040`

2 . **Enregistrez** la modification \(Cltr+X sous nano puis Y pour sortir, ou simplement Ctrl+S puis Alt+F4\)

* **Redémarrez** le Raspberry Pi via **son interface** ou via **ssh** avec la commande `reboot`   
* **Rendez-vous** dans **l'interface de EmulationStation** puis **configurez uniquement le joueur 1** "options manettes" avec le schéma d'un pad Snes. 
* **Attribuez le J1** 
* **Lancez un jeu 2 joueurs** et **testez** vos joysticks et boutons. \(exemple : via Street Fighter\)


>**Attention :**  
>Nous insistons sur le fait qu'il suffit de faire _**seulement**_ la configuration du **joueur 1** directement **dans Emulationstation.**  
>La configuration du **joueur 2** devrait fonctionner si le **mappage est bien le même.** **N’essayez pas** configurer le joueur 2, cela **écraserait la configuration du joueur 1.**
{.is-danger}

