---
title: Connaitre l'IP sur son réseau
---

# Connaitre l'IP sur son réseau

## Paramètres du réseau Recalbox

**Depuis la version 3.3.0 :**

Appuyez sur Démarrer et allez dans Paramètres réseau. L'adresse IP actuelle est affichée à cet endroit.

## Prérequis <a id="prerequis"></a>


>Assurez-vous que votre recalbox est bien lancée et connectée au réseau via un câble ethernet ou un dongle wifi.
{.is-info}

> Vous avez un doute et votre réseau à un accès Internet ?  
> Rien de plus simple, rendez-vous dans le menu de Recalbox puis sur `METTRE A JOUR LE SYSTEME`.  
> Si un pop-up s'affiche avec le message `Une mise à jour est disponible` ou `Aucune mise à jour de disponible`, alors votre Recalbox a bien un accès à Internet et donc, au réseau.  
> Si le message `Veuillez brancher un cable réseau` s'affiche, soit vous n'avez pas Internet sur le réseau ce qui n'est pas problématique, soit vous avez un soucis de configuration sur votre routeur, un cable défectueux ou un dongle wifi qui ne fonctionne pas.


>Attention l'IP n'est pas fixe et est suceptible de changer à chaque redemarrage.   
>Vous pouvez en définir une vous même via le mini How-to dédié:  [Paramètres IP Manuel](/fr/tutoriels/reseau/ip/parametres-ip-manuel)
{.is-danger}

## Sous Microsoft Windows <a id="sous-microsoft-windows"></a>

* Lancer la commande **`Executer`**

  _Vous ne savez pas ou se trouve la commande exécuter,_ [_Google est votre ami_](https://www.justgeek.fr/liste-commandes-executer-run-windows-10-53978/)​

* **Tapez `cmd`** et faire **`Entrer`**
* Puis une fois **dans le terminal**, **tapez** `ping recalbox` **puis faire** `Entrer`
* Vous devriez avoir **le message suivant qui s'affiche** :

> Envoi d'une requête 'ping' sur RECALBOX avec 32 octets de données :  
> Réponse de 192.168.0.XX : octets=32 temps=1 ms TTL=128  
> Réponse de 192.168.0.XX : octets=32 temps=1 ms TTL=128  
> Réponse de 192.168.0.XX : octets=32 temps=1 ms TTL=128  
> Statistiques Ping pour \[...\]

* Vous avez **votre IP.**

## Sous Apple OSX <a id="sous-apple-osx"></a>

* Lancer le **`Terminal`**

  _**Il se trouve** dans le dossier_ **`Utilitaires`** _du dossier_ **`Applications`**

* Tapez-y `arp -a`
* La **liste de tous les appareils connectés au réseau**, sous forme de liste d'IP, **s'affiche**.
* **L’ip du Raspberry** est souvent du type **`192.168.0.XX`.**
* Vous avez **votre IP.**

## Autres solutions <a id="autres-solutions"></a>

* Des **applications smartphones** sont disponibles pour **scanner votre réseau**. Rendez-vous sur le **store de votre appareil** pour trouver **l'application de votre choix.** 
* **Une autre solution** consiste à se rendre dans **les paramètres du routeur de votre box Internet.** La **liste des périphériques connectés** y est **répertoriée.**

