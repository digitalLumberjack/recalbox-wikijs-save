---
title: FBCP - Utilisation de FBCP pour les petits écrans TFT
---

# FBCP - Utilisation de FBCP pour les petits écrans TFT

Cette page est encore en construction. N'hésitez pas à la corriger et à ajouter des informations ;\)

## Qu'est-ce que le FBCP ? <a id="what-is-fbcp"></a>

​[https://github.com/tasanakorn/rpi-fbcp](https://github.com/tasanakorn/rpi-fbcp)​

Ce programme est utilisé pour copier le framebuffer primaire vers le framebuffer secondaire \(par exemple, FBTFT\). Il nécessite le dernier firmware Raspberry Pi \(à partir du 11 juillet 2013\) pour fonctionner correctement.

FBCP prend un instantané de `/dev/fb0`, le copie dans `/dev/fb1` et attend 25ms avant de se répéter. L'instantané prend environ 10ms et avec un délai de 25ms, il donne environ 1000/\(10+25\) = 28fps ; utilisation CPU : environ 2%.


>**Note :**
>
>L'instantané et le rafraîchissement du pilote `/dev/fb1` ne sont pas synchronisés.
{.is-info}

## Pourquoi avez-vous besoin de FBCP ? <a id="why-do-we-need-fbcp"></a>

Comme Recalbox n'utilise pas Xorg ou un autre serveur graphique, tous les affichages sont effectués sur le premier framebuffer \(`/dev/fb0`\) \(sortie HDMI ou composite\) qui utilise la puissance du GPU et l'accélération matérielle.

Dans le cas de l'utilisation de Xorg, nous pouvons facilement rediriger l'affichage sur le /dev/fb1. Ce n'est pas aussi simple avec le mode framebuffer de Recalbox. Même si cela est possible avec certains programmes, grâce à la variable d'environnement dans certains cas [https://github.com/notro/fbtft/wiki/Framebuffer-use](https://github.com/notro/fbtft/wiki/Framebuffer-use).

Dans le cas d'une utilisation ou d'un écran TFT SPI/I2C, ce nouvel écran reçoit le second framebuffer \(`/dev/fb1`\) et ne tire pas profit du GPU.

Et dans le cas de la Recalbox, tous les programmes envoient leur affichage sur `/dev/fb0`. Ainsi, si vous essayez de l'utiliser avec un petit écran I2C/TFT, vous n'obtiendrez aucun affichage même si votre écran est bien configuré et activé.

Ainsi FBCP vous permet d'afficher le contenu de `/dev/fb0` grâce à la prise de vue instantanée.

Cette méthode n'est pas nécessaire dans le cas des écrans qui utilisent le mode d'affichage DPI \(voir [ici](https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md)\).

## Version modifiée du programme FBCP Recalbox <a id="modified-version-of-the-recalbox-fbcp-program"></a>

​[https://github.com/ian57/rpi-fbcp](https://github.com/ian57/rpi-fbcp)

En fait, FBCP n'est pas encore inclus dans Recalbox, mais il devrait être disponible dans la version 4.1. Le programme original a été modifié pour essayer d'obtenir plus de 28 FPS, avec une réduction du temps d'attente :

```text
//usleep(25 * 1000);
usleep(5 * 1000); //only 5 ms to try to get 60fps
```

Si vous voulez l'essayer, vous pouvez le compiler ou obtenir le bon fichier binaire [ici](https://github.com/ian57/rpi-fbcp) en fonction de votre version de Pi.

Pour le compiler, vous pouvez obtenir la branche rb-4.1.X-fbcp ou simplement ajouter le répertoire `rpi-fbcp` dans le [répertoire du paquet](https://github.com/ian57/recalbox-buildroot/tree/rb-4.1.X-fbcpV2/package/rpi-fbcp/) avec ses 2 makefiles pour faire un essai.

Ce programme ne nécessite pas beaucoup de dépendance et devrait se compiler sur les versions 4.0 et 4.1. Pour créer et installer le programme dans l'arbre buildroot Recalbox, il suffit d'exécuter `make rpi-fbcp` dans le répertoire racine de votre arbre buildroot Recalbox. Vous obtiendrez le programme `fbcp` dans le répertoire de sortie /target/usr/bin lorsque la compilation sera terminée.

Ensuite, il suffit d'exécuter la commande `make` générale pour créer le fichier img de Recalbox avec le programme FBCP, ou simplement de le copier dans le répertoire /usr/bin de la partition Recalbox de votre carte SD.

Après cela, lisez [cette page](/fr/tutoriels/video/tft/configurez-votre-petit-ecran-tft-sur-le-bus-spi) pour configurer votre écran et le lancer au démarrage.

