---
title: Clrmamepro
---

# Clrmamepro

Dans ce tutoriel, nous allons vous apprendre en quelques clics à vous servir de Clrmamepro pour extraire \(rebuilder\) ou pour scanner un romset arcade. 

## I - Avant de commencer

### 1 - Éléments nécessaires

Au préalable il vous faut :

* Le logiciel Clrmamepro [ici](https://mamedev.emulab.it/clrmamepro/).
* Un [romset MAME](/fr/usage-avance/l-arcade-dans-recalbox) qui correspond à votre émulateur.
* Les samples \(optionnel selon le romset\). 
* Les [CHDs](/fr/usage-avance/l-arcade-dans-recalbox) \(optionnel selon le romset\).
* Un fichiers .DAT ou .XML dans le dossier [share](/fr/usage-basique/gestion-des-fichiers)\bios de votre recalbox.

### 2- Définitions

* **Set :** Fichier compressé\(.zip/.7z/.rar\) de jeux, drivers et bios.
* **Rom :** Fichier contenu dans un set.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MLgDdUyTQV_o1ouBl2S%2F-MLgI45h-_oq2HWJ-mea%2Fzip%2Broms.PNG?alt=media&token=679415ee-7281-4a80-9f51-d725ce655d0b)

* **Qu'est ce qu'un fichier dat ?** Les fichiers dat sont des fichiers textes avec des informations sur les jeux émulés avec une version spécifique de l'émulateur MAME.  Dans ses fichiers dat, on trouve les informations pour des sets particuliers comme : nom de la rom \(name\), année \(year\), fabricant \(manufacturer\), information de fusion \(merge\), rom parent \(romof\) ou clone de \(cloneof\), taille de la rom \(size\), CRC pour chaque rom. CRC est un algorithme qui permet de vérifier l'intégrité d'un fichier, clrmamepro l'utilise pour vérifier vos rom-sets
* **ClrmamePro :** C'est un logiciel qui vous permet de vérifier et reconstruire vos romsets arcade en fonction d'un fichier d'information au format xml ou dat.

### **3 - Installation**

* Téléchargez ClrmamePro pour [Windows](http://mamedev.emulab.it/clrmamepro/#downloads) ou pour [macOS](http://www.emulab.it/) ; sous Linux, utilisez [Wine](https://doc.ubuntu-fr.org/wine).


>Information : le fichier zip est une version portable.
{.is-info}

* Installez le.
* Récupérez le fichier dat de l’émulateur arcade souhaité.
* Démarrer Clrmamepro :
  * Exécutez clrmamepro via un clic droit sur l’icône.
  * _Puis "Exécuter en tant qu'administrateur_".


>**Astuce sous Windows :**
>
>* Rendez vous sur l’exécutable cmpro64.exe ou cmpro32.exe
>* Puis clic droit
>* Choisir _Propriétés_
>* Aller dans l'onglet _Compatibilité_
>* Puis cocher la case "_Exécuter en tant qu'administrateur"_.
>* Valider par Ok.
>
>Le programme s’exécutera toujours en administrateur désormais.
{.is-success}

## II - Utilisation

### 1 - Descriptif des fonctions

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MMErFEHY8TsELozlqVl%2F-MMErRzCRIzDRLg2qg3A%2FMenu%20V2.PNG?alt=media&token=a85fbc37-c7a9-4e7a-8d91-f0f53270fc4b)

### 2 - Rebuilder \(reconstruire\)

* Démarrer clrmamepro.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MLiX8hY5WInyQdZCmAQ%2F-MLiXwQ-N9gNpJwzBaKn%2FDossier%20clrmamepro%20exe.png?alt=media&token=5bb8a953-abdb-44b7-a35c-db1d54d42c12)

* Pour sélectionner votre fichier .dat cliquez sur "Add DatFile".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKEuhcF-nfUGJjPVIF6%2FAdd%20DatFile.png?alt=media&token=69510622-93a3-439a-8591-26ae617b5815)

* Sélectionnez votre fichier puis "ouvrir".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKEv0dW7gi6nsc9Gy8j%2FScan%202.PNG?alt=media&token=55e0492d-95e7-4b99-880e-e6dbac8cbbd1)

* Une fois sélectionné, vous pouvez indiquer un dossier ou un sous dossier. En sélectionnant "ok" clrmamepro va créer un dossier "NEW DATFILES" automatiquement.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEOho4ehzBtMCxz1BQ%2F-MKEOwXY9ef5h9XTFlwo%2FOK%20PROFIL.png?alt=media&token=0eb76f20-90de-48c0-8d47-a5b3c48dda07)

* Sélectionnez votre fichier .dat puis "Load/Update" afin de le charger

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKEvFM1VMLuY7WbdfiP%2FLoadUpdats.png?alt=media&token=428598bc-4717-4e05-8712-d9e98fd33172)

* Clrmamepro vous propose de créer ou de mettre à jour la configuration. Nous vous conseillons de cliquer sur "Default".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEOho4ehzBtMCxz1BQ%2F-MKERegpPhTWTE7Uj7Bf%2FDAT%20par%20default.png?alt=media&token=30149fcb-139c-41c0-a1ba-8cb6bddfe5c9)

* Clrmamepro va lire et charger votre fichier et vous devriez arriver sur le menu général.
  * Pour extraire un romset cliquer sur "Rebuilder"

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKEvr6h905ehsyoc8mw%2FRebuild1.png?alt=media&token=ce29dabc-57e8-4c01-be83-c32bead25724)

* Dans la "source" vous devez indiquer le dossier de votre romset MAME.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKEwXPo75SbJ2sk9f3D%2Fselecte%20source.png?alt=media&token=b13f1330-1d26-420d-84b9-6fc064c05b47)

* Sélectionnez le dossier ou se trouve votre romset puis "OK".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKEw_kM02PaNi0r8_p_%2FSelection%20source%202.png?alt=media&token=617696f8-34fe-4709-8d3b-9aed2e845b43)

* Dans la "destination" vous devez indiquer un dossier pour récolter le romset de l'extraction.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKExSTgTzHaT2bCwYSO%2FSelection%20destination.PNG?alt=media&token=21342c66-a3e1-44ec-ba08-cd7da3f61a9d)

* Sélectionnez le dossier de destination puis "OK".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKExVTh9PZzyGbUKLv_%2FScan%209.PNG?alt=media&token=fd34a4c3-0005-4c11-907c-d889e5401f31)

* **Dans le menu Rebuilder, vous pouvez paramétrer :** _****_

  1 -  [**Le type de romset**](/fr/usage-avance/l-arcade-dans-recalbox) que vous voulez créer **\(Merge Options\) :**

  * Non-merged
  * Split
  * Merged

  **2 - Les Options :** \(Nous vous conseillons les paramètres par default\)

  * Option de compression\(.zip/.7z/.rar\).
  * Option de recompressions. Si vous souhaitez ou non recompresser les fichiers.
  * "Show Statistics" pour voir les résultats à la fin du Rebuild.
  * "Remove Matched Sourcefiles". Si cette option est activée, clrmamepro va extraire et supprimer les fichiers correspondant à votre fichier .DAT de votre Romset MAME.
  * "Systems" et" Advanced". Ne vous aventurez pas ici pour le moment. 

  Lancez enfin l'extraction en cliquant sur "Rebuild".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEty0zbPHIFL7T9Mdp%2F-MKExpu4QH94JekI5Yg1%2FRebuild.png?alt=media&token=e9f3741d-835b-4201-bc75-89fa54cda8dd)

* Laissez faire clrmamepro jusqu'à la fin.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKF1Bhs7lSEXdmp7fjD%2F-MKF1z0HsNOhxadPwj7J%2FRebuild%20en%20cours.PNG?alt=media&token=49ba0ea3-950f-4b21-ab19-524708cb4bbd)

* Et voila! Nous vous conseillons de faire un scanner du dossier de destination afin de vérifier qu'il est parfait🙂.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKF2dEVJywho3NzzvA2%2F-MKF3r6B_p0E7X1Eh9IG%2FDossier%20neogeo%20plein.PNG?alt=media&token=fecb950f-e5c9-4229-bd68-5d02681fd87f)

### 3 - Scanner \(Vérifier\)

* Démarrer clrmamepro.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MLiX8hY5WInyQdZCmAQ%2F-MLiXwQ-N9gNpJwzBaKn%2FDossier%20clrmamepro%20exe.png?alt=media&token=5bb8a953-abdb-44b7-a35c-db1d54d42c12)

* Pour sélectionner votre fichier .dat cliquez sur "Add DatFile".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEBoPvmyzR3vbZu0Al%2F-MKEOGLUudiTUB6QjZpG%2FAdd%20DatFile.png?alt=media&token=46208298-ed53-42a7-a95f-ae49b5c61246)

* Sélectionnez votre fichier puis "ouvrir". 

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEghsLReYgI2bT__0Y%2F-MKEngUxTiCoiZ8r36Zn%2FScan%202.PNG?alt=media&token=9935c072-cf79-4780-a5a8-efb1da3f9ee6)

* Une fois sélectionné, vous pouvez indiquer un dossier ou un sous dossier. En sélectionnant "ok" clrmamepro va créer un dossier "NEW DATFILES" automatiquement.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEOho4ehzBtMCxz1BQ%2F-MKEOwXY9ef5h9XTFlwo%2FOK%20PROFIL.png?alt=media&token=0eb76f20-90de-48c0-8d47-a5b3c48dda07)

* Sélectionnez votre fichier .dat puis "Load/Update" afin de le charger.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEOho4ehzBtMCxz1BQ%2F-MKEVO95DEFK3D00RQT7%2FLoadUpdats.png?alt=media&token=fa71fe57-8a73-440c-9d42-94460d788788)

* Clrmamepro vous propose de créer ou de mettre à jour la configuration. Nous vous conseillons de cliquer sur "Default".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEOho4ehzBtMCxz1BQ%2F-MKERegpPhTWTE7Uj7Bf%2FDAT%20par%20default.png?alt=media&token=30149fcb-139c-41c0-a1ba-8cb6bddfe5c9)

* Clrmamepro va lire et charger votre fichier et vous devriez arriver sur le menu général. Pour indiquer ou se trouve votre romset nous allons cliquer sur "Settings".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEOho4ehzBtMCxz1BQ%2F-MKEPGkDRT88M5F-ovB9%2FSettings.png?alt=media&token=32757b5c-b984-41bf-97b6-3e7af67e0907)

* Le chemin vers votre romset dans "ROM-Paths" en cliquant sur "Add".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEOho4ehzBtMCxz1BQ%2F-MKEQ0b7zDdu7Z2Rl2D5%2FAdd%20Rom%20path.png?alt=media&token=7929d5e5-6613-48cd-9611-63487c9e9be8)

* Sélectionnez le dossier ou se trouve votre romset que vous souhaitez scanner puis "OK". 

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKJN1YX-TQmnUVVDmkX%2F-MKJNimOxbuyGi9iD0sH%2FScan%208.PNG?alt=media&token=f3c54217-d32a-43f8-881f-1596ab96a2ca)

* Pour Mame, si le romset doit contenir des samples, vous devez donner le chemin des samples de la même manière avec "Sample-Paths".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKZcV6M7UtiVAmH6lLW%2F-MKZdbDQuN5VdWPSxnj2%2FCapture%20d%E2%80%99%C3%A9cran%20%2844%29.png?alt=media&token=abecda6d-ba22-4409-9123-eebb29787fa1)

* Sauvegardez les chemins en cliquant sur "Save As Def.". 

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEVTVKn0icdU-_KDeb%2F-MKEW3QHsdTu8_8MHhA9%2FSave%20As%20Default%20Rompath.png?alt=media&token=dff7115b-c7b2-4bec-b77f-58f9ca624032)

* Clrmamepro vous confirme que c'est pris en compte alors cliquez sur "OK".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKJOPRd5Tw0HF-ZmSg0%2F-MKJOeAtyzo0rB6eW4sB%2FCurrent%20setting%20ok.png?alt=media&token=b15a5f88-2b90-4de6-bc9f-bcbabce643c1)

* Vous pouvez fermer cette fenêtre.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEghsLReYgI2bT__0Y%2F-MKEo6GOdMkkFM-LG0ES%2FScan%209.PNG?alt=media&token=872037af-38d9-47b1-8b70-78b2c066056f)

* Une fois revenu sur le menu principal cliquez sur "Scanner".

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEghsLReYgI2bT__0Y%2F-MKEoErjBqZCTQ5p871m%2FScann.png?alt=media&token=a5a956d4-7294-4301-9601-2023d7c152e6)

* Dans le menu **Scanner** vous devez paramétrer : 

**Les éléments à scanner \(You want to scan\) :** 

* Sets \(bios/jeux/drivers\), 
* Roms \(puces qui composent chaque Sets\)
* samples \(Drivers complémentaires pour certains jeux Mame\)
* [CHDs ](/fr/usage-avance/l-arcade-dans-recalbox)\(Que vous avez ajouté à votre Romset\)

 [**Le type de romset**](/fr/usage-avance/l-arcade-dans-recalbox) **que vous avez \(You prefer\) :**

* Non-merged
* Split
* Merged

**Les messages pendant et après le scan \(Prompts\) :**

* Ask Before Fixing
* Add/Show Statistics

**Check/Fix :** Clrmamepro va vérifier ce qui est dans la colonne de gauche "check". Si vous souhaitez que clrmamepro fasse des corrections vous pouvez cocher les cases de la colonne de droite "Fix". Attention avec l'option "fix" clrmamepro va enlever les dossier et fichiers qui ne correspondent pas à votre DAT et les placer dans son "backup".

**Options :** Ne vous aventurez pas ici pour le moment 

Lancez enfin le scan en cliquant sur "New Scan"

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEghsLReYgI2bT__0Y%2F-MKEp2sGAXASmaiaIiG2%2FScan%2012a.PNG?alt=media&token=e17dcc19-06a9-499b-b9cc-a4733aa37641)

* Dans cette fenêtre vont s'afficher les différents problèmes de votre set. \(Exemple: missing rom\) Vous pouvez exporter une liste de ce qu'il vous manque dans l'onglet "Miss List" afin de compléter.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKEghsLReYgI2bT__0Y%2F-MKEpBTyfRWuT9zBDIrj%2FScan%2012b.PNG?alt=media&token=b255046b-a857-4efd-8b54-54764ab1461d)

* Enfin, vous aurez les résultats du scanner dans la fenêtre "statistics". Le plus important est la partie "Missing" ci-dessous il manque rien donc parfait.

![](https://gblobscdn.gitbook.com/assets%2F-LzWj9p28FD5y9arPHmj%2F-MKJ_g1tL10NE8R7Yivd%2F-MKJ_jT1X_BaBZaeebBp%2FScan%2013.PNG?alt=media&token=3ef17232-dcd4-4fe8-a391-5205107e18b2)

