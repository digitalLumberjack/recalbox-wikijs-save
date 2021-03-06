---
title: NetFlix sur Kodi
description: NetFlix et NFAuthenfication.key pour Kodi
---

# NetFlix sur Kodi

## Requis

* Un compte netflix.
* Télécharger NF authentification key
* Windows : [https://www.dropbox.com/sh/80zv4umiiyx8ok1/AAABi-vk9CKNNXvpmzkCRTiIa?dl=0](https://www.dropbox.com/sh/80zv4umiiyx8ok1/AAABi-vk9CKNNXvpmzkCRTiIa?dl=0)
* Linux : [https://www.dropbox.com/sh/ls3veptflvneub1/AABz9Tt3EqKUb90PQXNarNxga?dl=0](https://www.dropbox.com/sh/ls3veptflvneub1/AABz9Tt3EqKUb90PQXNarNxga?dl=0)
* Navigateur chrome \(il prend en charge la navigation privée\)
* Votre manette ou votre télécommande pour naviguer dans Kodi.

## Sommaire

* Créer le fichier NFauthentification.key pour activer le compte
* Activation Netflix dans Kodi
* Connexion à votre compte Netflix

## Créer le fichier NFauthentification.key pour activer le compte

### **Sous Windows**

* Télécharger l’archive.
* Décompresser l’archive.
* Exécuter le fichier
* Cliquer sur le bouton 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhFgV52DzeISDj12lW%2F001.png?alt=media&token=04d0fe0d-6e55-486d-93d6-e6a2ce5aaa9e)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhGBN9MdR7MEzM1kkS%2F002.png?alt=media&token=b58ab514-85d6-49e9-a7c8-82b5451100c2)

* Patientez, création du fichier en cours, votre **navigateur internet** va s’ouvrir. Il faudra vous **loguer sur votre compte Netflix.**

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhGJd5NJEoCG2flAza%2F003.png?alt=media&token=25a495e2-4941-48cc-9d9f-56697e6ca996)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhGbWd-wWa0UQyTZd5%2F004.png?alt=media&token=92aa4f93-36e0-4460-98fd-e1e0865f6cfe)

* Une fois fait, une fenêtre avec un **code pin** vous sera donnée. 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhGqbtt4xiuMH5n43D%2F005.png?alt=media&token=a6dfdda6-aa45-4262-91d0-a622be5e9efa)

* Le fichier **NFAuthentication.key** est sauvegardé dans le même dossier que le logiciel.
* Il vous faudra le **transférer sur votre recalbox**, afin de le charger pour l’étape suivante.
  * Placer le n’importe où dans le share, du moment que vous le retrouvez. C’est un fichier temporaire qui reste actif pendant 5 jours. Passez ce délai il faudra refaire la procédure. 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhK-dfvvs8wRxZXtVJ%2F006.png?alt=media&token=31d583c0-38b3-486d-8f03-de5960096941)



### **Sous linux**

* Installer les packages suivantes :
  * pip install pycryptodomex
  * pip install websocket-client
* Exécuter le script :
  * python NFAuthenticationKey.py ou
  * python3 NFAuthenticationKey.py 

## **Activation Netflix dans Kodi**

* Lancer Kodi via recalbox.
* Se rendre dans les options systèmes.
* Puis Add-Ons .

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhLOl-o91_uHxcZcVP%2F007.png?alt=media&token=bbe233ee-917e-428b-b5e7-5dc24f9cfa21)

* Sélectionner **My Add-ons.**

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhLoRuzdyDnmfiL7Qm%2F008.png?alt=media&token=157e0dc7-16c4-454d-b6e8-ca497c831889)

* Ensuite, **Video Add-On.**

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhMeMAay7UWYqWaxcZ%2F009.png?alt=media&token=b38a64b6-d5e2-4778-9582-2499d45938c1)

* Puis Cliquer sur NETFLIX .

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhMv7r3H0dq6jfv7cc%2F010.png?alt=media&token=a107a73b-7274-41ed-89a9-5804f2742f42)

* Cliquer sur le bouton **Enable** pour activer le plugin. 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhN7GOPHwuGN9LY9RQ%2F011.png?alt=media&token=947e8c2d-f4a8-4979-9178-75c74b2a7980)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhNHPedO0vMMdU4arF%2F012.png?alt=media&token=ede2d0cb-0b3e-4e16-94ff-817d1fd29a90)

* Cliquer sur le bouton **Open. Une fenêtre s’ouvre, cliquer sur YES.**

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhNb9Of40nsYdF3L2b%2F013.png?alt=media&token=72777adb-4d66-446b-9521-d1aa1544ec97)

## **Connexion à votre compte Netflix**

* Choisir **NFAuthentification.key**
  * Patientez ...

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhNvjlvm5RXiV1puag%2F014.png?alt=media&token=3731c83a-9cf6-4e92-84f8-9d3511eb04ce)

* Il vous sera demandé de charger le fichier **NFAuthenfication.key**

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhO6BBnaQOSKXxK2bG%2F015.png?alt=media&token=e3428147-73aa-4e0d-8c83-6db66919d368)

* Dans la fenêtre suivante, entrer le **code Pin** donné dans la fenêtre **Numeric Pad**, valider par **DONE**. 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhOHf9f5hDgBUu0Fj8%2F016.png?alt=media&token=b14b431b-6e97-470c-b18f-060c32955c1c)

* Saisir votre login/mot de passe .

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhOQDvb6CIXivCDkbb%2F017.png?alt=media&token=8f93656d-8a71-495b-a339-35fb5af1689b)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhOV3dAJNZkmTbZgrS%2F018.png?alt=media&token=df676d9b-aed6-4b25-ae62-66dd7b7a4c3d)

* Et voila, vous aurez accès à vos différents profils. 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJhEVVm54QtWEa8zGlf%2F-MJhOfefiweYRq1r3myf%2F019.png?alt=media&token=93bab260-dc56-4e40-9cd6-ec69ce0e303a)

Félicitation vous pouvez profitez de NetFlix.

**Source :** [https://github.com/CastagnaIT/plugin.video.netflix/wiki/Login-with-Authentication-key](https://github.com/CastagnaIT/plugin.video.netflix/wiki/Login-with-Authentication-key)

