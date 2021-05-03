---
title: Sortie audio analogique sur Pi Zero
---

# Sortie audio analogique sur Pi Zero

## Pas de sortie audio sur le Pi zéro ? Vraiment ?

Oui ! Pour que le Pi Zero reste petit et peu coûteux, le filtre audio du casque n'est pas inclus. Pas de prise jack pour obtenir de la musique de votre Recalbox. Vous pouvez toujours obtenir de l'audio numériquement via HDMI, donc si vous branchez votre Pi sur un moniteur avec des haut-parleurs, cela fonctionnera très bien.

Ce n'est pas grave si vous avez branché votre Recalbox sur votre téléviseur dans votre salon, mais dans une borne d'arcade avec un écran de PC standard, ou un téléviseur... vous ne pouvez pas obtenir le son du HDMI.

Enfin, ce n'est pas vraiment vrai. Si vous utilisez un convertisseur HDMI-VGA, vous pourriez avoir la chance d'en avoir une qui a une sortie audio jack comme [celui-ci](https://www.amazon.fr/dp/B075L812M3/).

Mais si vous utilisez un Pi zéro, vous voulez certainement l'intégrer dans un petit appareil, avec un petit écran TFT sur le bus SPI/I2C/DPI, et vous n'aurez pas de place pour ce convertisseur.

## Comment l'audio est diffusé sur Raspberry Pi

Comme décrit sur [cette page](https://learn.adafruit.com/introducing-the-raspberry-pi-zero/audio-outputs), les autres Raspberry Pi utilisent 2 sorties PWM avec un circuit de filtrage pour créer la sortie sonore. Sur cette page, vous trouverez le véritable dispositif électronique intégré dans le Raspberry Pi pour créer le son.

Mais, si vous lisez attentivement, il utilise le PWM sur les GPIO 40 et 45 qui ne sont pas mis en évidence sur le Pi Zero.

La solution consiste à se positionner sur PWM0 sur GPIO 18 \(ALT5\) et PWM1 sur GPIO 13 \(ALT0\) ou GPIO 19 \(ALT5\) et à créer son propre circuit de filtrage.

La manipulation est décrite en détail sur [cette page](https://learn.adafruit.com/adding-basic-audio-ouput-to-raspberry-pi-zero/pi-zero-pwm-audio).

Avec Recalbox, le moyen le plus simple est d'ajouter cette ligne dans le fichier `config.txt`. Elle reconfigurera les broches au démarrage sans aucun logiciel ou service externe. Le PWMO sera sur la GPIO 18 \(broche 12 sur le connecteur\), et le PWM1 sur la GPIO 13 \(broche 33 sur le connecteur\).

```text
dtoverlay=pwm-2chan,pin=18,func=2,pin2=13,func2=4
```

Comme décrit dans [cette page](https://hackaday.io/project/9467-piboy-zero/log/35090-pi-zero-pwm-audio-device-tree-overlay), vous pouvez faire votre propre superposition avec le code source suivant :

```text
/dts-v1/;
/plugin/;

/ {
  compatible = "brcm,bcm2708";

  fragment@0 {
    target = <&gpio>;
    __overlay__ {
      pinctrl-names = "default";
      pinctrl-0 = <&pwm_audio_pins>;

    pwm_audio_pins: pwm_audio_pins {
	brcm,pins = <13 18>;   /* gpio no ('BCM' number) */
	brcm,function = <4 2>; /* 0:in, 1:out, 2: alt5, 3: alt4, 4: alt0, 5: alt1, 6: alt2, 7: alt3 */
	brcm,pull = <0 0>;     /* 2:up 1:down 0:none */
      };
    };
  };
 };
```

Si vous avez configuré buildroot et que vous avez déjà monté Recalbox, vous pouvez compiler les dts avec :

```text
output/build/linux-FIRMWARE/scripts/dtc/dtc -@ -I dts -O dtb -o pwm-audio-pi-zero-overlay.dtbo pwm-audio-pi-zero-overlay.dts
```

Et vous copiez le fichier `pwm-audio-pi-zero-overlay.dtbo` dans /boot/overlays de votre Recalbox. La configuration est maintenant plus simple :

```text
dtoverlay=pwm-audio-pi-zero
```

### Test rapide de la sortie sonore

Vous pouvez tester si cela fonctionne sans créer le circuit de filtrage. Vous pouvez connecter un haut-parleur de casque directement entre la broche PWM et une masse comme indiqué dans la figure suivante.

Il devrait fonctionner, mais le son peut avoir des défauts.

### Améliorer le rendu sonore

Pour créer votre filtre, vous aurez besoin de certains composants électroniques :

* _2 résistances de 270 Ohms_
* _2 résistances de 150 Ohms_
* _2 condensateurs de 10µF_
* _2 condensateurs de 33nF_ \(peuvent être remplacés par des condensateurs 22nF ou 10nF\)

Voici les schémas :

![audioFilter\_bb.png](https://camo.githubusercontent.com/a8cdcb22c9c1ea3d74b9a19cebd2221f62505d78/687474703a2f2f696d616765732e6d6f726572652e65752f617564696f46696c7465725f62622e706e67)

et le vrai filtre :

![PiZeroAudioFilter.jpg](https://camo.githubusercontent.com/4340ee9cb7edbed9f0cf0086c3ac8d470ecaadd6/687474703a2f2f696d616765732e6d6f726572652e65752f50695a65726f417564696f46696c7465722e6a7067)

Vous devrez amplifier la sortie car les signaux sont filtrés et ont des niveaux très bas.

##  Amplification et contrôle du volume

Vous pouvez utiliser un petit amplificateur 5V 2x3W.  
Vous pouvez également ajouter un potentiomètre audio stéréo pour pouvoir régler le volume.

![](/migration-images/tutoriels/audio/image%20%2862%29.png)

