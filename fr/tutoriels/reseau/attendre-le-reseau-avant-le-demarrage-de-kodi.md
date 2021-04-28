---
title: Attendre le réseau avant le démarrage de Kodi
---

# Attendre le réseau avant le démarrage de Kodi

## Le problème <a id="le-probleme"></a>

Lorsque Kodi est en **mode démarrage automatique sur recalbox**, il est possible sur certain système que **le service réseau ne soit pas encore démarré** lorsque celui-ci se lance.  
Cela cause **des problèmes pour les utilisateurs** qui possèdent **des partages réseaux** ou **utilise une base de données distante.**

## Solution de contournement pour les versions pré 4.X.X <a id="solution-de-contournement-pour-les-versions-pre-4-x-x"></a>

Si vous utilisez **une version inférieur au 4.X.X**, la solution la plus simple est **de quitter puis relancer kodi** depuis Emulationstation, **le réseau devrait** avoir eu le temps durant l'intervalle **de démarrer.**

## Sur Recalbox 4.x \(et version ultérieur\) <a id="sur-recalbox-4-x-et-version-ulterieur"></a>

* Dans le fichier **recalbox.conf**, chercher dans la **section A - System options :**

```text
;kodi.network.waitmode=required
;kodi.network.waittime=10
;kodi.network.waithost=192.168.0.50
```

* **Décommenter** les lignes et **modifier les valeurs** selon vos besoins **en supprimant le point virgule.**


>**Informations :** 
>
>* _**kodi.network.waitmode**_  
>
>
>  * **required** - Utiliser cette option afin de forcer kodi à ne pas pouvoir se lancer avant d'avoir pu joindre l'adresse ip indiquée. 
>  * **wish** - Utilise un compte à rebours plutot que l'option de devoir pinger une machine avant de démarrer 
>
>  _\*\*\*\*_
>
>* _**kodi.network.waittime**_
>
>Temps en seconde à attendre avant que le démarrage de kodi échoue \(lorsque "required" est renseigné\) ou continue son démarrage \(lorsque wish est renseigné\)  
>
>
>* _**kodi.network.waithost**_
>
>L'adresse Ip du système utilisée pour tester la connexion réseau \(exemple : l'adresse ip de votre box ou de votre partage réseau utilisé par kodi\)
{.is-info}

