---
title: Setting up your small TFT screen on the DPI bus
---

# Setting up your small TFT screen on the DPI bus

## Configuring your small TFT screen on DPI

### DPI \(DISPLAY PARALLEL INTERFACE\)

Source : [https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md](https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md)

A parallel RGB interface up to 24 bits is available on all Raspberry Pi cards with the 40 channel header \(A+, B+, Pi2, Pi3, Zero\) and the calculation module. This interface allows parallel RGB displays to be connected to the Raspberry Pi GPIO in either RGB24 \(8 bits for red, green and blue\) or RGB666 \(6 bits per color\) or RGB565 \(5 bits red, 6 green and 5 blue\). 

This interface is controlled by the GPU firmware and can be programmed by a user via special config.txt parameters and by enabling the correct Linux device tree overlay. 

By sending data via this parallel interface, you have no problems with bus bandwidth and display speed \(FPS\). But it uses almost all GPIO pins. 

This mode is very useful, you can fine-tune your display parameters: timings, resolutions, etc. 

This mode comes with new overlays, which allow to produce an RGB signal thanks to the VGA666 \(Get the passive VGA 666 adapter for Raspberry-Pi B+: [https://github.com/fenlogic/vga666](https://github.com/fenlogic/vga666)\) \([http://www.banggood.com/VGA-666-Adapter-Board-For-Raspberry-Pi-3-Model-B-2B-B-A-p-1071309.html](http://www.banggood.com/VGA-666-Adapter-Board-For-Raspberry-Pi-3-Model-B-2B-B-A-p-1071309.html)\).

```text
dtoverlay=vga666
```

You will be able to use the 5" [http://www.adafruit.com/products/1596](http://www.adafruit.com/products/1596), 7" [http://www.adafruit.com/products/2354](http://www.adafruit.com/products/2354) TFT screen from Adafruit thanks to the Kippah DPI TFT panel from Adafruit for Raspberry Pi a touch support [https://www.adafruit.com/products/2453](https://www.adafruit.com/products/2453)

```text
dtoverlay=dpi24
```

Then connect to Recalbox via ssh  
And Remount the read-write partition

 `mount -o remount, rw /boot`


>**IMPORTANT :**
>
>If you are using version 4.0.x, the `dpi24.dtbo` file is present and can be found in the `/boot/overlays` directory. You must rename it `dpi24.dtb` for the screen to work. On Recalbox 4.1, nothing to do.
{.is-warning}

Go to the `/boot/overlays` directory and rename the dtbo file to Recalbox 4.0.x

```text
cd /boot/overlays
mv dpi24.dtbo dpi24.dtb
```

You can now use

```text
dtoverlay=dpi24
```

### 3.5" TFT Geekwrom HD 800x480 screen for the Raspberry Pi 3B 2B

This screen is small in size and offers a resolution of 800x480. Its specifications are quite good:

![hd-tftScreen.png](https://camo.githubusercontent.com/8680157a6e810c62eae94925088b302873fdaff7/687474703a2f2f696d616765732e6d6f726572652e65752f68642d74667453637265656e2e706e67)

I found this amazing screen on the Chinese site: [http://www.banggood.com/Geekwrom-HD-3\_5-Inch-TFT-Display-Shield-800x480-For-Raspberry-Pi-3B-2B-With-2-Keys-And-Remote-IR-p-1069730.html](http://www.banggood.com/Geekwrom-HD-3_5-Inch-TFT-Display-Shield-800x480-For-Raspberry-Pi-3B-2B-With-2-Keys-And-Remote-IR-p-1069730.html) for less than 40€.

It can be used as is, without the fbcp program. Fbcp is not necessary either because the DPI mode uses the GPU directly.

To get support for this display, just add the following lines to your /boot/config.txt.

You now need to use an SSH connection to your Raspebrry Pi to perform/check the following steps Switch the file system to Read-Write mode to be able to make changes :

```text
mount -o remount, rw /boot
mount -o remount, rw /
```

Edit the file /boot/config.txt with nano or vim and add :

```text
#3.5 HD tft screen 800x480
dtoverlay=dpi24
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0

​#Banggood
framebuffer_width=800
framebuffer_height=480
dtparam=spi=off
dtparam=i2c_arm=off

enable_dpi_lcd=1
display_default_lcd=1
dpi_output_format=0x6f015
dpi_group=2
dpi_mode=87
hdmi_timings=480 0 16 16 24 800 0 4 2 2 0 0 0 60 0 32000000 6
display_rotate=3
```

Save the file and restart Recalbox... that should be enough, you can now view the incredible images displayed on this screen...

![&#xC9;cran TFT Geekwrom HD 3,5 pouces 800x480](https://camo.githubusercontent.com/e139870fc5e1e6ae285d64e46e6a00f9823f4071/687474703a2f2f696d672e796f75747562652e636f6d2f76692f714b6449744e737059564d2f302e6a7067)

### 5" and 7" TFT screen from Adafruit

To use these screens \([https://www.adafruit.com/product/2353](https://www.adafruit.com/product/2353), [https://www.adafruit.com/products/1596](https://www.adafruit.com/products/1596)\), you will need Adafruit's Kippah DPI TFT panel for Raspberry Pi with touch support [https://www.adafruit.com/products/2453](https://www.adafruit.com/products/2453) to operate them.

They also use the DPI mode. The configuration of the config.txt file is as follows:

```text
#3.5 HD tft screen 800x480
dtoverlay=dpi24
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0

#Adafruit
framebuffer_width=800
framebuffer_height=480
dtparam=spi=off
dtparam=i2c_arm=off

enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
dpi_output_format=0x6f005
hdmi_timings=800 0 40 48 88 480 0 13 3 32 0 0 0 60 0 32000000 6
display_rotate=3
```

### 4.0" HyperPixel Screen

Thanks glook for this tutorial : [https://forum.recalbox.com/topic/17854/ecran-hyperpixel-4-pouces/4](https://forum.recalbox.com/topic/17854/ecran-hyperpixel-4-pouces/4)

This screen is available at this address: [https://shop.pimoroni.com/products/hyperpixel-4](https://shop.pimoroni.com/products/hyperpixel-4) with or without touch screen.

Start by reading the Github here: [https://github.com/pimoroni/hyperpixel4](https://github.com/pimoroni/hyperpixel4)

You'll need to :

* compile hyperpixel4.dts into hyperpixel4.dtbo or find it on the web : `dtc -@ -I dts -O dtb -o hyperpixel4.dtbo hyperpixel4.dts`
* copy `hyperpixel4.dtbo` to `/boot/overlays/`
* add the configuration to the config.txt file:

```text
# Paramètres de l'écran LCD HyperPixel
dtoverlay=hyperpixel4
overscan_left=0
overscan_right=0
overscan_top=0
overscan_bottom=0
framebuffer_width=800
framebuffer_height=480
enable_dpi_lcd=1
display_default_lcd=1
dpi_group=2
dpi_mode=87
dpi_output_format=0x7f216
display_rotate=3
hdmi_timings=480 0 10 16 59 800 0 15 113 15 0 0 0 60 0 32000000 6
```

make sure the i2c and spinnaker are turned off:

```text
dtparam=i2c_arm=off
dtparam=spi=off
```

* Mount the partition : `mount -o remount,rw /`
* copy hyperpixel4-init located in the `/dist` directory to `/usr/bin/` on Recalbox
* finally, be sure to run this program at startup in Recalbox, by adding `hyperpixel4-init` on the command line in one of the init scripts in `/etc/init.d`

