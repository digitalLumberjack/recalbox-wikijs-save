---
title: Sauvegardez vos données de scrape
---

# Sauvegardez vos données de scrape

### **Pour sauvegarder** votre scrape de jeux :

* **Avoir** un [accès root](/fr/tutoriels/systeme/acces/acces-root-via-terminal). 
* **Créer un dossier :**   `mkdir /recalbox/share/system/backup_scrape/`  ****
* **Utiliser cette commande** pour sauvegarder tes différents dossiers de scrape placés sur la partition partagée \(SHARE\). 

`cp -r /root/.emulationstation/downloaded_images /recalbox/share/system/backup_scrape/downloaded_images && cp -r /root/.emulationstation/gamelists /recalbox/share/system/backup_scrape/`




>En fonction de la quantité totale de scrapes que vous avez collectés, il peut arriver que l'affichage des sauvegardes soit retardée. Soyez patient !
{.is-info}

Allez ensuite dans le répertoire **backup\_scrape** du **système**, puis copiez le contenu du **backup\_scrape** sur votre PC ou sur votre stockage local.

\*\*\*\*

**Pour restaurer** cette sauvegarde sur le système de votre Recalbox, ajoutez votre sauvegarde dans le répertoire **backup\_scrape** dans le dossier système puis utilisez la commande suivante :

`cp -r /recalbox/share/system/backup_scrape/downloaded_images /root/.emulationstation/ && cp -r /recalbox/share/system/backup_scrape/gamelists /root/.emulationstation/`

Une fois la copie terminée, redémarrez votre Recalbox, et vos scrapes apparaîtront.

