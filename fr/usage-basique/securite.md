---
title: Sécurité
description: Les options et configurations de sécurité de Recalbox
---

# Sécurité

La Recalbox **n'est pas sécurisée** par **défaut**.

De manière générale:

* Ne pas connecter sa Recalbox directement à Internet. 
* Ne pas stocker d'informations sensibles/privées sur sa Recalbox. 
* Faire des sauvegardes régulièrement. 
* Éteindre sa Recalbox entre deux sessions de jeu.

## Mot de passe Root

La Recalbox vient avec un mot de passe root \(super-utilisateur\) par défaut.  
  
On peut changer ce dernier via le menu **PARAMÈTRES AVANCES** puis **SÉCURITÉ**_._


>**Remarque :**  
>Il faudra refaire cette opération après chaque mise à jour, car les mises à jour de la Recalbox écrasent les fichiers existants et remettent donc le mot de passe à sa valeur initiale.
{.is-warning}

## Services réseau <a id="services-reseau"></a>

La Recalbox active plusieurs services réseau par défaut.  
  
Bien que très pratiques, ces services sont également des points d'entrée faciles pour des personnes mal intentionnées.

Il est de bonne pratique que de **désactiver les services** que vous n'utilisez pas **en éditant** la section **'Network'** du fichier **recalbox.conf**

Pour éditer ce fichier, deux solutions:

* Ouvre une invite de commande, et une fois connecté, tape:`nano recalbox.conf` 
* Ou bien sur ton ordinateur, ouvre une fenêtre web à l'adresse:`http://192.168.X.XX` pour ouvrir le Recalbox-manager, et édites la configuration depuis la page correspondante 

### Wifi

Si tu n'as pas besoin d'une connexion ou si tu utilises une connexion filaire, désactive le wifi :

```text
wifi.enabled=0
```



### Samba <a id="samba"></a>

Samba est un service très pratique pour transférer des fichiers depuis un ordinateur.

Si tu ne l'utilises pas, désactive-le en configurant :

```text
system.samba.enabled=0
```


>**Information :**  
>Les versions 6.1 supporte les partages Samba protégés par un mot de passe.
{.is-info}



### Manettes virtuelles <a id="manettes-virtuelles"></a>

Ce service te permets d'utiliser ton smartphone ou ta tablette en tant que manette.

Si tu n'utilises pas de telles manettes, désactive le service en configurant :

```text
system.virtual-gamepads.enabled=0
```

## Recalbox Manager

La Recalbox est fournie avec son propre serveur web, écoutant sur le port 80.  
  
Ce serveur permets de charger des roms en faisant du drag-and-drop et aussi de modifier la configuration.


>**Attention :**  
>Cependant, c'est un point d'accès en or pour une personne cherchant à prendre le contrôle de ton Raspberry.
{.is-danger}

Donc, si tu n'utilises pas le Recalbox manager \(par exemple, parce que tu as déjà toutes les roms de tes rêves sur ton Raspberry, ou bien si tu préfères transférer tes roms via le service Samba\), tu peux le désactiver en configurant:

```text
system.manager.enabled=0
```

Ces étapes devrait rendre ta box \(et par conséquence tous les appareils connectés à ton réseau\) un peu plus sécurisée...

