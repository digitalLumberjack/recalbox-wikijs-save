---
title: Connecter manuellement le contrôleur Bluetooth
---

# Connecter manuellement le contrôleur Bluetooth

Vous pouvez connecter votre contrôleur Bluetooth manuellement. Pour cela, vous aurez besoin d'un [accès root](/v/francais/tutoriels/systeme/acces/acces-root-via-terminal).

## Si la version de Recalbox est inférieure ou égale à la 4.0

Mettez votre contrôleur bluetooth en mode association, et tapez :  
 `hcitool scan`

Cela permettra d'obtenir l'adresse mac du contrôleur :  
 `aa:bb:cc:dd:ee:ff Name:Bluetooth HID`

Ensuite, créez la connexion avec le contrôleur :  
 `hidd --connect aa:bb:cc:dd:ee:ff`

Et relancer Emulationstation :  
 `/etc/init.d/S31emulationstation start`

## Si la version de Recalbox est supérieure ou égale à la 4.1

Vous avez deux possibilités. L'une peut ne pas fonctionner, alors essayez l'autre ensuite. Démarrez votre contrôleur en mode appairage, assurez-vous que vous l'avez préalablement réinitialisé et que vous avez supprimé toute association existante.  
Attention : pour l'instant, vous devez démarrer votre contrôleur Bluetooth après qu'EmulationStation ait démarré.

### Utilisation de la commande simple-agent

Trouvez l'adresse mac de votre contrôleur \(en format majuscule\) en utilisant :  
 `/recalbox/scripts/bluetooth/test-device list`

Essayez plusieurs fois si votre contrôleur n'est pas dans la liste. Si après quelques essais, votre contrôleur n'est toujours pas répertorié, passez à la méthode B.

Si votre contrôleur figure dans la liste, tapez :  
 `/recalbox/scripts/bluetooth/simple-agent hci0 "AA:BB:CC:DD:EE:FF"`

AA:BB:CC:DD:EE:FF correspond à l'adresse mac de votre périphérique en majuscules. Un code PIN peut vous être demandé, veuillez vous référer à la documentation de votre pad. Si vous ne pouvez toujours pas faire l'appairage, essayez la méthode suivante.

### Utilisation de la commande bluetoothctl

Démarrez `bluetoothctl` puis tapez les commandes suivantes :

```text
agent on
default-agent
power on
scan on
```

Attendez que `bluetoothctl` répertorie votre appareil, puis tapez les commandes suivantes :

```text
pair AA:BB:CC:DD:EE:FF
connect AA:BB:CC:DD:EE:FF
trust AA:BB:CC:DD:EE:FF
```

