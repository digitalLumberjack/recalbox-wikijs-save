---
title: Analog audio output on Pi Zero
---

# Analog audio output on Pi Zero

## No audio output on Pi zero? No audio output on Pi zero?

It's true : to keep the Pi Zero small and inexpensive, the headphone audio filter is not included ... No jack plug to get music from your Recalbox ... You can still get audio digitally via HDMI, so if you connect your Pi to a monitor with speakers, it will work fine.

It doesn't matter if you've connected your Recalbox to your TV in your living room, but in an arcade terminal with a standard PC screen, or a TV, you can't get the sound from HDMI.

Well, that's not really true. If you chose to use a HDMI-VGA converter, you might be lucky enough to get one that has an audio jack output like this: [https://www.amazon.com/MOKiN-Adapter-Converter-Powered-Laptop/dp/B01F1T9IS4/ref=pd\_lpo\_147\_tr\_t\_3/153-2977990-6201028?ie=UTF8&psc=1&refRID=GV8D910Z9HMW8BW4FR0P](https://www.amazon.com/MOKiN-Adapter-Converter-Powered-Laptop/dp/B01F1T9IS4/ref=pd_lpo_147_tr_t_3/153-2977990-6201028?ie=UTF8&psc=1&refRID=GV8D910Z9HMW8BW4FR0P)

But if you use a Pi zero, you certainly want to integrate it in a small device, with a small TFT display on the SPI/I2C/DPI bus, then you won't have room for this converter.

## How audio is streamed on Raspberry Pi

As described in [https://learn.adafruit.com/introducing-the-raspberry-pi-zero/audio-outputs](https://learn.adafruit.com/introducing-the-raspberry-pi-zero/audio-outputs), other Raspberry Pi's use 2 PWM outputs with a filter circuit to create the sound output. On this page, you will find the real electronic device built into the Raspberry Pi to create the sound.

But, if you read carefully, it uses PWM on the GPIO 40 and 45 which are not highlighted on the Pi Zero.

The solution is to use PWM0 on GPIO 18 \(ALT5\) and PWM1 on GPIO 13 \(ALT0\) or GPIO 19 \(ALT5\) and create your own filter circuit.

The handling is detailed on the page [https://learn.adafruit.com/adding-basic-audio-ouput-to-raspberry-pi-zero/pi-zero-pwm-audio](https://learn.adafruit.com/adding-basic-audio-ouput-to-raspberry-pi-zero/pi-zero-pwm-audio).

With Recalbox, the easiest way is to add this line in the config.txt file :

```text
dtoverlay=pwm-2chan,pin=18,func=2,pin2=13,func2=4
```

It will reconfigure the pins at startup without any external software or services. The PWMO will be on the GPIO 18 \(pin 12 on the connector\), and the PWM1 on the GPIO 13 \(pin 33 on the connector\).

As described on [https://hackaday.io/project/9467-piboy-zero/log/35090-pi-zero-pwm-audio-device-tree-overlay](https://hackaday.io/project/9467-piboy-zero/log/35090-pi-zero-pwm-audio-device-tree-overlay), you can make your own overlay with the following source code:

```text
/dts-v1/;/plugin/;​/ {  compatible = "brcm,bcm2708";​  fragment@0 {    target = <&gpio>;    __overlay__ {      pinctrl-names = "default";      pinctrl-0 = <&pwm_audio_pins>;​    pwm_audio_pins: pwm_audio_pins {	brcm,pins = <13 18>;   /* gpio no ('BCM' number) */	brcm,function = <4 2>; /* 0:in, 1:out, 2: alt5, 3: alt4, 4: alt0, 5: alt1, 6: alt2, 7: alt3 */	brcm,pull = <0 0>;     /* 2:up 1:down 0:none */      };    };  }; };
```

If you have configured buildroot and have already mounted Recalbox, you can compile the dts with :

```text
output/build/linux-FIRMWARE/scripts/dtc/dtc -@ -I dts -O dtb -o pwm-audio-pi-zero-overlay.dtbo pwm-audio-pi-zero-overlay.dts
```

and you copy the `pwm-audio-pi-zero-overlay.dtbo` file into /boot/overlays of your Recalbox. The configuration is now simpler :

```text
dtoverlay=pwm-audio-pi-zero
```

### ​

### Quick sound output test

You can test if this works without creating the filter circuit. You can connect your headphones directly between the PWM pin and a ground as shown in the following figure.

It should work, but the sound may be faulty.

​

### Improving the sound quality

To create your filter, you will need certain electronic components:

* 2 resistors of 270 Ohms
* 2 x 150 Ohms resistors
* 2 capacitors of 10µF
* 2 capacitors of 33nF \(can be replaced with 22nF or 10nF capacitors\)

Here are the schematics:

![](https://camo.githubusercontent.com/a8cdcb22c9c1ea3d74b9a19cebd2221f62505d78/687474703a2f2f696d616765732e6d6f726572652e65752f617564696f46696c7465725f62622e706e67)

and the real filter :

![](https://camo.githubusercontent.com/4340ee9cb7edbed9f0cf0086c3ac8d470ecaadd6/687474703a2f2f696d616765732e6d6f726572652e65752f50695a65726f417564696f46696c7465722e6a7067)

You will have to amplify the output because the signals are filtered and have very low levels.

##  Amplification and volume control <a id="amplification-et-controle-du-volume"></a>

You can use a small 5V 2x3W amplifier. You can also add a stereo audio potentiometer to adjust the volume.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lzcoc4J5dudNcYgeHNG%2F-Lzcu6Q_D1r4PxVuKGSG%2F687474703a2f2f696d616765732e6d6f726572652e65752f617564696f416d706c692e6a7067.jpg?alt=media&token=b6215b91-a7af-4439-9816-ac0c0b8242fa)

