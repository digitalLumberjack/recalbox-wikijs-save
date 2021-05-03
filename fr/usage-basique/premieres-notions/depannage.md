---
title: Dépannage
---

# Dépannage

## Contrôleurs

### **Ma manette fonctionne dans Emulationstation mais pas lorsque je lance les émulateurs pourquoi ?**

Nous ajoutons un maximum de configuration de manettes dans emulationstation, afin de vous permettre de naviguer dans Emulationstation, mais pour beaucoup d'entre elles, vous devez les reconfigurer pour qu'elle fonctionne dans les émulateurs.

* Menu Emulationstation \(bouton start\)
* Options Manettes  &gt;  Configurer ma manette.

### Le contrôleur PS3 clignote mais ne s'associe pas.

* Branchez un contrôleur sur la Recalbox et attendez 10 secondes.
* Vous pouvez maintenant débrancher le contrôleur et appuyer sur le bouton Home.

### Le contrôleur PS3 semble mort

* Vous devez réinitialiser le contrôleur par un petit bouton derrière le contrôleur dans un petit trou, avec un trombone.

## Affichage

### Autre Bordure noire, image trop grande

* Utilisez votre téléviseur pour trouver le menu d'image et réglez la taille de l'image sur 1: 1 pixel ou plein.

Si cela ne fonctionne pas, essayez d'activer le surbalayage dans la boîte de sélection des paramètres du système de menus. Vous trouverez plus d'informations [dans ce tutoriel](/fr/tutoriels/video/configuration-daffichage/reglage-de-la-taille-de-limage-en-utilisant-loverscan-sous-tft).

### Écran noir sur moniteur PC

Si vous avez un écran noir sur le moniteur PC \(hdmi ou dvi\) éditez le fichier config.txt \(mise à jour au démarrage\) et supprimez la ligne hdmi\_drive = 2. Vous trouverez plus d'informations [dans ce tutoriel](/fr/tutoriels/video/lcd/connectez-votre-recalbox-a-un-ecran-dvi).

## Système

### Réinitialisation matérielle

Si vous souhaitez réinitialiser le système.

* Branchez un clavier USB et appuyez sur la touche Maj au démarrage.
* Vous pouvez réinstaller recalboxOS à partir d'ici.

Toutes vos données seront effacées. 

### Accès root

Utilisez la racine du nom d'utilisateur et le mot de passe recalboxroot.

* Vous pouvez vous connecter via ssh à la recalbox. Vous pouvez accéder à un terminal en quittant les émulations avec F4, puis appuyez sur ALT + F2. Vous pouvez obtenir plus d'informations en consultant [ce tutoriel](/fr/tutoriels/systeme/acces/acces-root-via-terminal).

