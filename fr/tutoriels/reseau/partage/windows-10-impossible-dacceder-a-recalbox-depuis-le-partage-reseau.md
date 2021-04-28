---
title: Windows 10 - Impossible d'accéder à Recalbox depuis le partage réseau
---

# Windows 10 - Impossible d'accéder à Recalbox depuis le partage réseau

## Cas n°1: Aucun ordinateur, incluant Recalbox, n'est visible depuis Windows <a id="cas-n-1-aucun-ordinateur-incluant-recalbox-nest-visible-depuis-windows"></a>

Si vous **ne voyez aucun ordinateur** depuis le réseau de **Windows 10**, c'est soit :

* **La découverte du réseau est désactivée** par défaut et que **la configuration du réseau est positionnée sur "publique"**  ou 
* Que **"rendre ce PC détectable" est sur "désactivé".**

Vous devez **aller dans les paramètres réseau** et **mettre votre réseau** en mode **"privé"**, ou **mettre "rendre ce PC détectable" sur activé".**

​[Un petit tutoriel en images ici.](https://forum.recalbox.com/topic/10621/mini-tuto-windows-10-que-faire-si-recalbox-n-est-pas-accessible-en-réseau)  
_**\(récupérer ce mini-tuto pour en faire un nouvel onglet !\)​**_

## Cas n°2: Recalbox n'est plus accessible depuis la mise à jour n°1709 de Windows 10 <a id="cas-n-2-recalbox-nest-plus-accessible-depuis-la-mise-a-jour-n-1709-de-windows-10"></a>


>_**Remarque :**_
>
>**Depuis** cette mise à jour, **vous voyez Recalbox** dans votre réseau, mais vous **ne pouvez plus y accéder.**
{.is-warning}

* **Explication officielle** \(en anglais\) [https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/](https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/)  ou [ ](https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016)[https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016](https://support.microsoft.com/fr-fr/help/4046019/guest-access-in-smb2-disabled-by-default-in-windows-10-and-windows-ser) 
* **Réparation rapide:**  Téléchargez et appliquez [ce patch](https://mega.nz/#!rUA3xDgI!a14w9TqQWinLriLANpk7BF_WkoNg8mw6fHloyPEZMPg)​


>_**Information :**_
>
>Ce patch **va désactiver la sécurité sur les accès réseaux anonymes** dans Windows, **pour rétablir l'accès à Recalbox.**
{.is-info}

## Cas n° 3 <a id="cas-n-3"></a>

* **Aller** dans : `Paramètres / Applications / Programmes et fonctionnalités / Activer ou désactiver des fonctionnalités windows`  
* Activer en **cochant :** `support de partage de fichiers SMB 1.0/CIFS / client SMB1.0/CIFS...`  
* Puis **redémarrer Windows.**

