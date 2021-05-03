---
title: Paramètres IP Manuel
---

# Paramètres IP Manuel

## Recalbox 4.0 <a id="recalbox-4-0"></a>

Afin de **sélectionner une adresse IP fixe pour votre Recalbox**, vous devrez **modifier le fichier** `/etc/network/interfaces`.

* [Obtenez un accès root via Terminal](/fr/tutoriels/systeme/acces/acces-root-via-terminal) et **éditez le fichier** avec : `nano /etc/network/interfaces`


>**Information :** 
>
>Pour une **solution permanente,** vous devez **modifier** le fichier **interfaces.base** .  
>Et avant de le modifier, vous devez **monter le système de fichiers en lecture écriture.** 
>
>**Essayez les commandes** : mount -o remount,rw / nano /etc/network/interfaces.base
{.is-info}

* [​Partition en écriture pour Recalbox 4.0.0](/fr/tutoriels/systeme/acces/acceder-a-une-partition-en-ecriture)

  

* **Recherchez la ligne** contenant **l'interface** que vous souhaitez modifier \(ethX pour l'ethernet, wlanX pour le wifi\) :

```text
auto eth0
iface eth0 inet dhcp
```

**Modifions l'adresse IP de eth0.**

* **Remplacez** les paramètres actuels par ceux de **l'IP fixe** :

```text
auto eth0
iface eth0 inet static
address 192.168.1.10
network 192.168.1.0
netmask 255.255.255.0
broadcast 192.168.1.255
gateway 192.168.1.254
```

* **Dans cet exemple votre :  Réseau local** derrière votre box est **192.168.1.x .** **L’adresse de votre box** est **192.168.1.254.**  **Le masque de votre réseau** est donc **255.255.255.0.**  Et vous souhaitez que **votre adresse** soit **192.168.1.10** 

En passant sur une adresse IP statique, vous perdrez la configuration de votre \(vos\) serveur\(s\) DNS au cours du processus. Pour que la résolution de noms fonctionne, vous devrez créer un fichier de noms `/etc/resolv.conf`. Par défaut, ce fichier pointe vers un fichier généré automatiquement situé dans `/tmp/resolv.conf`, donc pour le faire une fois pour toutes, exécutez les commandes suivantes :

```text
rm /etc/resolv.conf
nano /etc/resolv.conf
```

Saisissez les lignes suivantes, qui correspondent aux serveurs DNS du projet OpenDNS :

```text
nameserver 208.67.222.222
nameserver 208.67.220.220
```

Enregistrez le fichier.

Actualisez maintenant les paramètres avec : `ifdown eth0 && ifup eth0`


>Ces modifications seront **réécrites à chaque nouvelle mise à jour** !  
>Vous devrez répéter ces tâches après chacune d'entre elles.
{.is-warning}

## A partir de Recalbox 4.1 <a id="a-partir-de-recalbox-4-1"></a>

* [Obtenez un accès root via Terminal](/fr/tutoriels/systeme/acces/acces-root-via-terminal)

Tapez `connmanctl services` et notez ce qui est renvoyé, par exemple :

`*AO Wired ethernet_b827eb6462be_cable`

* Tapez ensuite : `cd`

`nano custom.sh`

```text
#!/bin/bash
/usr/bin/connmanctl config ethernet_b827eb6462be_cable --ipv4 manual 192.168.1.181 255.255.255.0 192.168.1.1
mount -o remount,rw /
echo "nameserver 208.67.222.222" >> /etc/resolv.conf
echo "nameserver 208.67.220.220" >> /etc/resolv.conf
```

Remplacez **ethernet** par la **valeur obtenue précédemment** et l'**adresse IP** par celle que **vous voulez donner.** Vous pouvez remplacer les adresses IP des serveurs DNS du projet OpenDNS par les serveurs DNS \(le cas échéant\) fournis par votre propre FAI.  


Puis quittez l'éditeur de texte nano par `Ctrl X`, répondez à la question de sauvegarde en tapant `Y` et enfin `Entrée`.

Après avoir quitté nano et être revenu au terminal shell, tapez la commande `chmod +x custom.sh`, ce qui la rend exécutable, puis `reboot` pour redémarrez votre Recalbox.

## À partir de Recalbox 6.1

Depuis la version 6.1, il est possible d'éditer l'IP manuellement dans le fichier recalbox.conf:

```text
## Wifi - static IP
## if you want a static IP address, you must set all 3 values (ip, gateway, and netmask)
## if any value is missing or all lines are commented out, it will fall back to the
## default of DHCP
;wifi.ip=manual ip address
;wifi.gateway=new gateway
;wifi.netmask=new netmask
```

Vous devez supprimer le**`;`** devant les trois dernières lignes, ou la configuration ne fonctionnera pas, et remplissez-les avec les informations souhaitées, par exemple:

```text
wifi.ip=192.168.1.10
wifi.gateway=192.168.1.254
wifi.netmask=255.255.255.0
```

