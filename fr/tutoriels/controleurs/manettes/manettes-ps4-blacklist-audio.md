---
title: Manettes PS4 blacklist audio
---

# Manettes PS4 blacklist audio

## Recalbox 4.1

Les manettes PS4 sont supportés en Bluetooth et USB. Si vous avez des problèmes avec l'audio lorsque vous êtes branché sur USB, suivez le chapitre suivant.

## Recalbox 4.0.X


>Certains **contrôleurs PS4** ont un **module audio intégré** qui empêche la **diffusion du son sur votre tv** ou **haut-parleur.**  
>Vous devez **blacklister** ce module audio pour **récupérer le son** sur votre périphérique.
{.is-info}

* **Connectez-vous** en ssh via putty 
* Montez la partition **en écriture :**

```text
mount -o remount,rw /
```

* **Éditez** le fichier :

```text
nano /etc/modprobe.d/blacklist.conf
```

* **Ajoutez** cette ligne :

```text
blacklist snd-usb-audio
```

* **Sauvegardez** et **redémarrez**

