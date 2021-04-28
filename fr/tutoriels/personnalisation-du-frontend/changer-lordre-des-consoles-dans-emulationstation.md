---
title: Changer l'ordre des consoles dans EmulationStation
---

# Changer l'ordre des consoles dans EmulationStation

## Étapes <a id="etapes"></a>

* **Se connecter en SSH** à votre Recalbox. 
* **Se rendre** dans le dossier **d'EmulationStation** dans le répertoire **share\_init** .`cd /recalbox/share_init/system/.emulationstation`
*   **Stopper EmulationStation** &gt; `/etc/init.d/S31emulationstation stop`   
* **Editer** le fichier `es_system.cfg` &gt; `nano es_system.cfg`   Dans ce fichier, vous trouverez **toutes les entrées des consoles** que Recalbox supporte. **Changer juste l'ordre des entrées** telles que vous souhaitez les voir **apparaître** dans **EmulationStation.** 
* **Sauvegardez** vos modifications. 
* **Démarrer EmulationStation** &gt; `/etc/init.d/S31emulationstation start` 

## Remarques <a id="remarques"></a>

Malheureusement, ce n'est **pas possible** à l'heure actuelle de rendre l'entrée **"Favorites"** en **première position.**

