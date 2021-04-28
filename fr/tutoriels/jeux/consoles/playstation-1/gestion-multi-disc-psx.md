---
title: Gestion multi-disques PSX
---

# Gestion multi-disques PSX


>**Informations :**
>
>Avoir un seul fichier pour vos jeux multi-disques est possible. Il suffit de créer un fichier eboot contenant vos images iso, bin, img via le logiciel gratuit **psx2psp**.
>
>On vous rappelle que vous devez disposez de vos propres images de disques PSX !
{.is-info}

## **Création du fichier eboot**

* Recherchez la version **psx2psp v1.42**, la télécharger et l’exécuter.
* Choisissez le mode classic puis sur la partie de gauche, charger un à un vos ISOs.
* Choisissez votre répertoire d'enregistrement.
* Cliquez sur le bouton `Convert`, puis patientez.

Placez votre dossier ou renommez le fichier eboot créé vers votre recalbox dans le dossier   
`/recalbox/share/roms/psx`.

## **Changement de CD**

Pour changer de CD en cours de jeu, il faut activer 2-3 options dans le menu RetroArch.

* Ouvrez le menu RetroArch pendant le jeu \(par défaut **Hotkey + B**\).
* Allez dans settings/general settings et passer l’option configuration save on exit sur on. 


>**Attention :**
>
>À partir de ce moment là, toutes les modifications que vous effectuerez dans les options seront sauvegardées quand vous quitterez le menu RetroArch.
{.is-danger}

* Allez dans settings/input settings et chercher les options portant le nom, disk eject toggle, disk next, disk previous. Il faut alors leur affecter des touches de votre manettes n’ayant pas encore de fonction spéciale attribuée.
* Quittez RetroArch et retournez en jeu.


>**Remarques :**
>
>​Quand vous serez à l’écran d’un jeu vous demandant de changer de CD, il vous suffira alors d’éjecter virtuellement le CD \(en faisant hotkey + le raccourci attribué à l’option disk eject toggle\), de changer de cd, et de refermer virtuellement le lecteur cd.  
>Votre jeu démarrera alors automatiquement sur le CD suivant.
>
>Vous pouvez [consulter cette discussion](https://forum.recalbox.com/topic/482/roms-playstation-et-nombre-de-jeux) sur le forum en cas de problème.
{.is-warning}

## **Pour changer de CD sur PCSX-reARMed \(r22\)**

Méthode pour des fichiers .bin

* Rentrez dans le menu RetroArch \(**Hotkey + B**\)
* Choisissez Quick menu, puis core disk option.
* Éjectez le cd virtuel en choisissant disk cycle tray status.
* Cherchez le répertoire où se trouve le cd que vous voulez charger \(logiquement dans `/recalbox/share/roms/psx`\) avec disk image append.

