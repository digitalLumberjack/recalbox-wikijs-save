---
title: Audio mais pas de vidéo \(Old 3.2.11\)
---

# Audio mais pas de vidéo \(Old 3.2.11\)


>**Informations :**
>
>L'émulateur pour N64 est **en phase beta**. Certains jeux **s'exécutent** parfaitement ; d'autres non.  
>Il peut arriver que lorsque vous **lancez un jeu,** vous **ayez le son mais pas de vidéo.**
{.is-info}

**Voici une solution possible :**

* Premièrement, vous devez **avoir un** [**accès root via votre terminal** ](/fr/tutoriels/systeme/acces/acces-root-via-terminal) 
* **Entrez les commandes suivantes** : - `cd ../recalbox/scripts`   ****- `nano emulatorlauncher.sh` pour éditer le fichier 
* **Trouvez les lignes** suivantes et **y remplacer** le **"4"** **par** un **"2" :**

```text
if [[ "$emulator" == "n64" ]]; then
/recalbox/scripts/runcommand.sh 4 "SDL_VIDEO_GL_DRIVER=/usr/lib/libGLESv2.so mupen64plus –corel
```

* **Appuyez** sur **`CTRL+X`** pour **quitter l'éditeur ;** puis sur **`Y`** pour **sauvegarder les modifications.** 
* **Entrez :** `reboot` pour **redémarrer** le Raspberry pi.

