---
title: Connectez votre recalbox à un CRT avec composite
---

# Connectez votre recalbox à un CRT avec composite

Si vous souhaitez **connecter votre recalbox sur un CRT**, vous aurez besoin d'**un mini-jack vers RCA** comme celui-ci ​:

![RPi Audio/Video Socket](https://image.ibb.co/mQCKDJ/rpi_AV_socket.jpg)


>Attention, sur les **câbles de caméscopes,** la **sortie vidéo** pourrait être sur la **prise audio droite** \(rouge\).
>
>De plus, le **type de câble nécessaire** n'étant pas vraiment répandu.  
>Il est préférable de **tester au Multimètre** que le câble utilisé **correspond bien au schéma** proposé ci-dessus \(une inversion du Ground et de la vidéo sur le jack entraine une image noir & Blanc sautillante, signe d'un câble inadapté\).
{.is-danger}

* [Passez la partition boot en écriture](/v/francais/tutoriels/systeme/acces/acceder-a-une-partition-en-ecriture)
* [Modifiez le fichier /boot/config.txt](/v/francais/tutoriels/systeme/modification/editer-le-fichier-config.txt) en **commentant toutes les lignes commençant par** `hdmi_` **avec le symbole** `#`, et **ajoutant le sdtv\_mode supporté:**

```text
sdtv_mode=0    Normal NTSC   
sdtv_mode=1    Japanese version of NTSC – no pedestal  
sdtv_mode=2    Normal PAL   
sdtv_mode=3    Brazilian version of PAL – 525/60 rather than 625/50, different subcarrier
```

* Pour avoir un **meilleur son par la sortie composite**, activez le **driver audio expérimental** pour le Raspberry pi

```text
audio_pwm_mode=2
```


>**Attention**, ce mode peut créer un **ralentissement global de Recalbox**.
{.is-danger}

* **Si** c'est le cas, **passer la ligne en commentaire** et **forcer la sortie audio sur le jack**

```text
#audio_pwm_mode=2
hdmi_drive=1
```

* Finalement, **ajoutez** `hdmi_ignore_hotplug=1` pour **forcer le composite**.

Le système de fichiers est en lecture seule. Vous devrez utiliser Noobs pour modifier le fichier de configuration. Branchez un clavier USB et appuyez sur la touche Maj au démarrage pour accéder au menu de récupération. Ensuite, appuyez sur "e" pour obtenir le menu d'édition, et faites vos modifications ici. Vous pouvez changer la langue et la configuration du clavier en appuyant sur "l" et "k". 

Votre **config.txt** devrait ressembler à ça :

```text
sdtv_mode=2
hdmi_ignore_hotplug=1
audio_pwm_mode=2
```

* Ensuite **modifiez** [recalbox.conf](/v/francais/usage-basique/premieres-notions/le-fichier-recalbox.conf) et **réglez** `global.videomode` à `default`:

```text
global.videomode=default
```

* **Si** vous utilisez **l'émulateur n64** pensez aussi à **commenter cette ligne** :

```text
n64.videomode=DMT 9 HDMI
```

* et **décommentez** celle-ci :

```text
n64.videomode=default
```

* Pour finir, **désactivez le lissage des jeux** et **tous les shaders** dans le menu EmulationStation \(START -&gt; OPTIONS DES JEUX\) ce qui vous permettra **d'avoir le rendu original** sur tous les systèmes !

## Tout est lent avec le mode composite

`audio_pwm_mode=2` améliore le son mais peut ralentir le système en mode composite, en particulier sur Pi zéro. Dans ce cas, utilisez le mode suivant :

```text
audio_pwm_mode=0
```

