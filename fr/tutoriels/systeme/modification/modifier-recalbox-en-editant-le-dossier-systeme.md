---
title: Modifier Recalbox en éditant le dossier système
---

# Modifier Recalbox en éditant le dossier système

Le fichier recalbox.conf vous permet de configurer et personnaliser votre recalbox, mais vous pouvez aller plus loin en éditant le **répertoire Système**.

Ce répertoire peut être interne \(sur la carte micro-SD\) dans `/recalbox/share/system` ou sur un périphérique externe \(clé usb\) dans le répertoire `/recalbox/system`.

Ce répertoire est disponible :

* Via Samba \(Windows share\) sur `smb://recalbox.local/system` \(`\\recalbox.local/system` dans Windows Explorer\)
* Via ssh \(`/recalbox/share`\) ou directement en branchant la carte micro-SD ou le périphérique externe sur un OS compatible ext4

## Structure du répertoire Système <a id="structure-of-the-system-directory"></a>

Tous ces répertoires et fichiers ne sont pas présents par défaut dans votre répertoire Système.  
  
Créez-les si vous voulez les personnaliser.

```text
bios
cheats
extractions
kodi 
roms
   /snes
   /...
saves
screenshots
shaders
system
   /bluetooth
   /configs
   /logs
   /recalbox.conf
   /upgrade
   /ssh
   /.config
   /.emulationstation
      /es_input.cfg
      /es_settings.cfg
      /es_systems.cfg
      /themes
   /.kodi
   /.ssh
```

## Utilisation <a id="usage"></a>

Les fichiers contenus dans le **répertoire Système** ont toujours la priorité sur le répertoire Recalbox par défaut. **Lorsqu'un fichier n'est pas trouvé** dans le répertoire Système, le répertoire par défaut Recalbox\* sera utilisé.

Le **répertoire par défaut de Recalbox** a la même structure que le **répertoire Système** vous permettant de l'utiliser facilement pour copier des fichiers si nécessaire.

Le **répertoire Recalbox par défaut** est disponible :

* Via ssh \(`/recalbox/share_init`\)

| Répertoire ou fichier | Utilisation | Initialisation sur le répertoire système |
| :--- | :--- | :--- |
| bios | _Répertoire des bios d'émulation_ | copié |
| cheats | _Répertoire des fichiers de triche_ | fusionné |
| extractions |  | copié |
| kodi | _Musiques et vidéos_ | copié |
| roms/snes\(1\) | _Roms des systèmes d'émulation_ | copié |
| saves | _Sauvegardes d'émulation_ | copié |
| screenshots | _Captures d'écran d'émulation_ | copié |
| shaders | _Shaders_ | système |
| system/bluetooth | _Périphériques Bluetooth associés_ | copié |
| system/configs | _Configurations automatiques d'émulation et de KODI_ | le meilleur pour Kodi, copié pour les autres |
| system/logs | _Recalbox identifiants_ | copié |
| system/recalbox.conf | _Fichier de configuration Recalbox_ | copié |
| system/upgrade | _Emplacement pour le démarrage et root.tar.xz pour la mise à niveau_ | créé au besoin |
| system/ssh | _Clé ssh Recalbox côté serveur_ | copié |
| system/.config | _Configurations d'applications \(lirc\)_ | copié |
| system/.emulationstation/es\_input.cfg | _Configurations du joystick_ | copié |
| system/.emulationstation/es\_settings.cfg | _Configuration d'EmulationStation_ | copié |
| system/.emulationstation/es\_systems.cfg | ? | le meilleur |
| system/.emulationstation/themes | _Thèmes d'EmulationStation_ | fusionné |
| system/.kodi | _Fichiers KODI_ | copié |
| system/.ssh | _Clé ssh côté client_ | copié |


>**Légende :**
>
>**\(1\)** : Lorsque de nouveaux systèmes sont disponibles, un nouveau répertoire est créé. Si vous voulez réinitialiser les roms d'un système, supprimez le répertoire et redémarrez.
>
>_**copié**_ : au démarrage, si le répertoire n'existe pas, il est créé à partir du **répertoire Recalbox par défaut**. Vous pouvez le supprimer pour le réinitialiser. Notez que presque tous les répertoires copiés sont vides ou contiennent simplement un fichier LisezMoi.
>
>_**fusionné**_ : les deux répertoires, le **répertoire Système** et le **répertoire Recalbox par défaut** sont visibles.
>
>_**par défaut**_ : la fonctionnalité n'est pas terminée. Par exemple, la personnalisation des shaders n'est pas toujours possible. Seul le **répertoire Système** est pris en compte.
>
>_**le meilleur**_ : utiliser le **répertoire Système** s'il existe ou revenir au **répertoire Recalbox par défaut**.
>
>"Fusionné" et "le meilleur" permet aux développeurs de Recalbox de mettre à jour les fichiers système. Cependant, ce n'est pas toujours voulu ou possible sans une grande quantité de travail.
{.is-success}

