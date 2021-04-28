---
title: Recalbox Manager - Interface web
---

# Recalbox Manager - Interface web


>_**Information :**_
>
>Recalbox Manager est une interface web pour accéder à votre Recalbox via un smartphone , une tablette ou votre PC.
{.is-info}

## **Pour vous connecter**

Il suffit de saisir dans votre navigateur web simplement son nom :

* Sous windows \(IE, CHROME, FIREFOX\) :

  *  [http://recalbox/](http://recalbox/)

* Sous Mac et linux, ou utilisateur de safari sous windows :

  * [http://recalbox.local/](http://recalbox.local/)

* Si cela ne fonctionne pas, vous pouvez utiliser l'adresse IP de votre Recalbox :
  * **192.168.1.x**


>**Informations :**
>
>La plus part **des routeurs** sont configurés de tel que vous devriez **trouver votre recalbox** entre  **192.168.1.2** et **192.168.1.254** .
>
>Pour connaitre son adresse IP :  
>Menu Emulationstation \(bouton start\) **&gt;** Option réseau **&gt;** Adresse IP
{.is-info}

## **Interface**

Lorsque vous êtes sur **la page principale**, vous pouvez **naviguer entre les menus** suivants :

* Éditer le fichier recalbox.conf. 
* Ajouter/Supprimer des bios. 
* Ajouter/Supprimer des roms. 
* Consulter les log.



**Il permet de :**

* Monitorez votre rpi.
* Modifier recalbox.conf.
* Lancer le gamepad virtuel \(pratique pour configurer en 5min sa recalbox pour la 1ère utilisation\) via smartphone ou tablette uniquement.
* Consulter les logs de Recalbox.



**Il permet de par glisser déposer :**

* Uploader les bios en vérifiant que le Checksum est correcte
* Uploader les roms au format `.zip` ou extension pris en charge par les émulateurs



**Par défaut**, le gestionnaire **démarre automatiquement.**  
Si vous voulez, vous pouvez **le désactiver** dans **recalbox.conf**

```text
## Recalbox Manager (gestionnaire de http)
system.manager.enabled = 1
```

## **Gamepad Virtuel**

Pour y accéder directement, il suffit de saisir l'ip de votre recalbox avec le port 8080 `http://192.168.0.X:8080 ou http://recalbox:8080`

Consulter le manuel d'utilisation **du Gamepad Virtuel** [ici](/v/francais/usage-basique/premiere-utilisation-et-configuration#ii-configuration-dun-controleur)_**.**_

Le github pour les retours : [https://github.com/recalbox/recalbox-manager](https://github.com/recalbox/recalbox-manager)

