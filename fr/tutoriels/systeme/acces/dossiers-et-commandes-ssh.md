---
title: Dossiers et commandes SSH
---

# Dossiers et commandes SSH

## Commandes SSH <a id="ssh-commands"></a>

**Accès au Root**

```text
ssh root@[IP address of Recalbox]
```

\*\*\*\*

**Monter le Recalbox en mode lecture/écriture**

```text
mount -o remount,rw / 
```

\*\*\*\*

**Arrêter EmulationStation**

```text
es stop
```

\*\*\*\*

**Démarrer Emulationstation**

```text
es start
```

\*\*\*\*

**Redémarrer Emulationstation**

```text
es restart
```

\*\*\*\*

**Changer le mot de passe root**

```text
passwd
```

\*\*\*\*

**Redémarrer Recalbox**

```text
reboot
```

\*\*\*\*

**Éteindre Recalbox**

```text
poweroff
```

\*\*\*\*

**Faites une capture d'écran**

```text
raspi2png
```

Il prendra une capture d'écran et créera un fichier sous `/recalbox/share/system/` sous le nom **snapshot.png**

Vous pouvez également modifier en un nom personnalisé votre capture avec `-p filename.png`

\*\*\*\*

**Informations sur le réseau**

```text
ifconfig
```

\*\*\*\*

**Vérifiez la température du CPU**

```text
cat /sys/class/thermal/thermal_zone0/temp  
```

Ensuite, divisez le résultat par 1000 pour obtenir la température en Celsius.

## Fichiers <a id="files"></a>

Configuration spécifique au Raspberry Pi, comme les paramètres d'overscan, l'overclocking, le mode vidéo par défaut, etc...

```text
nano /boot/config.txt  
```

\*\*\*\*

**Fichier de configuration Recalbox**

```text
nano /recalbox/share/system/recalbox.conf
```

