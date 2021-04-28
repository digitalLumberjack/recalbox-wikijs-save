---
title: GPIO joystick driver for Raspberry Pi
---

# GPIO joystick driver for Raspberry Pi

mk\_arcade\_joystick\_rpi is fully integrated into the Recalbox distribution: see [http://www.recalbox.com​](https://www.recalbox.com/pt-br/)​

**The Hotkeybtn branch now supports an additional button per player, instead of MCP23017 support**

## Introduction

The Raspberry Pi is an amazing tool that I discovered a month ago. The RetroPie project made me want to build my own arcade machine with simple buttons and joysticks.

So I started connecting my joysticks and buttons to the Raspberry Pi and wrote the first half of that driver to connect my joysticks and buttons directly to his GPIO ports.

However, the Raspberry Pi B Rev 2 has a maximum of 21 usable GPIO ports, which is not enough to connect all 28 switches \(2 joysticks and 20 buttons\) required by a standard panel.

UPDATE 0.1.5: GPIO customization added

UPDATE 0.1.4: Compatibility with Raspberry Pi 2

UPDATE 0.1.3: Compatibility with 3.18.3:  
The driver installation now works with the 3.18.3 kernel, released with the latest firmware.

UPDATE 0.1.2: Downgraded to 3.12.28+:  
Since the module does not load a kernel and recent headers, we are adding the ability to downgrade your firmware to a compatible version, until we find a solution.

UPDATE 0.1.1: Raspberry Pi B + version:  
The new Raspberry Pi B + revision brought us 9 additional GPIO ports, so we can now connect 2 joysticks and 12 buttons directly to the GPIO ports. I updated the driver to support the 2 joysticks in the configuration of the GPIO ports.

#### ​ <a id="undefined"></a>

#### Even more joysticks

A small cheap chip called MCP23017 allows you to add 16 external GPIOs and accepts only two GPIO ports on the Raspberry Pi. The chip allows you to use GPIOs as input or output; the input is what we're looking for, if we want even more joysticks.

If you want to use more than one chip, the i2c protocol allows you to choose different addresses for the connected device, but they all use the same SDA and SCL GPIO.

In theory, you can connect up to 8 chips, so 8 joysticks.

## The software

The joystick driver is based on the gamecon\_gpio\_rpi driver from [marqs](https://github.com/marqs85).

It is written for 4 directional joysticks and 8 buttons per player. The use of an MCP23017 extends the input numbers to 16: 4 directions and 12 buttons.

It can recognize joysticks + buttons connected to the Raspberry Pi GPIO ports \(two joysticks in the RPi B + revision\) and up to 5 other joysticks + buttons from the MCP23017 chips. An MCP23017 is required for each joystick.

It uses Raspeberry Pi and MCP23017 internal pull-ups, so all switches must be connected directly to their corresponding GPIO and GROUND.

## Common cases: Joysticks connected to GPIO ports

#### ​Pinout <a id="pinout"></a>

Consider a 6-button control panel with this button order:

```text
 ↑   Ⓨ Ⓧ Ⓛ  
← →	 Ⓑ Ⓐ Ⓡ  
 ↓  
```

Where: R = TR and L = TL

Here is the summary of pinout for GPIO rev B ports:

![](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOs.png)

If you have a Raspberry Pi Rev B + 1 or 2:

![](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_GPIOsb+.png)

Obviously, the ground can be common to all switches.

## Installation

#### ​Installation script

Download the installation script:

```text
mkdir mkjoystick
cd mkjoystick
wget https://github.com/recalbox/mk_arcade_joystick_rpi/releases/download/v0.1.4/install.sh
```

Update your system:

```text
sudo sh ./install.sh updatesystem
sudo reboot
```

Remember to restart \(or the next part will not work\) and restart the script without arguments:

```text
sudo sh ./install.sh
```

Now go to ~~**Loading the driver**~~

### Manual installation

System update:

```text
sudo apt-get update
sudo apt-get upgrade
sudo rpi-update
```

1 - Install everything you need:

```text
sudo apt-get install -y --force-yes dkms cpp-4.7 gcc-4.7 git joystick
```

2 - Install the latest kernel headers:

```text
sudo apt-get install -y --force-yes raspberrypi-kernel-headers
```

3.a - Install the driver version \(preferably\):

```text
wget https://github.com/recalbox/mk_arcade_joystick_rpi/releases/download/v0.1.4/mk-arcade-joystick-rpi-0.1.4.deb
sudo dpkg -i mk-arcade-joystick-rpi-0.1.4.deb
```

3.b - Or compile and install with dkms:

3.b.1 - Download the files:

```text
git clone https://github.com/pinuct/mk_arcade_joystick_rpi/tree/customgpio
```

3.b.2 - Create a folder in "/usr/src/_module_-_module-version_/"

```text
mkdir /usr/src/mk_arcade_joystick_rpi-0.1.5/
```

3.b.3 - Copy the files to the folder:

```text
cd mk_arcade_joystick_rpi/
cp -a * /usr/src/mk_arcade_joystick_rpi-0.1.5/
```

3.b.4 - Compile and install the module:

```text
dkms build -m mk_arcade_joystick_rpi -v 0.1.5
dkms install -m mk_arcade_joystick_rpi -v 0.1.5
```

## Loading the driver

The driver is loaded with the modprobe command and receives a parameter called "map" representing the connected joysticks. When you need to load the driver, you will need to pass a list of parameters that represent the list of connected joysticks. The first parameter will be the joystick mapped to /dev/input/js0, the second to js1, etc.

If you have connected a joystick to the GPIO ports on the Raspberry Pi \(joystick 1 in the pinout image\), you must pass "map = 1" as a parameter. If you are in revision B + and connected 2 joysticks, you must pass map = "1,2" as a parameter.

If you have a joystick connected to your version of the Raspberry Pi B or B +, you will need to run the following command:

```text
sudo modprobe mk_arcade_joystick_rpi map=1
```

If you have two joysticks connected to your version of the Raspberry Pi B or B +, you will need to run the following command:

```text
sudo modprobe mk_arcade_joystick_rpi map=1,2
```

If you have a TFT screen connected to your Raspberry Pi B +, you will not be able to use all GPIO ports. You can run the following command to use only GPIOs not used by the TFT screen \(Note that not all TFT screens use the same pins. The GPIOs used with this card are: 21, 13, 26, 19, 5 , 6, 22, 4, 20, 17, 27, 16\):

```text
sudo modprobe mk_arcade_joystick_rpi map=4
```

If you don't want to use all the pins or if you want to use a custom **GPIO card:**

```text
sudo modprobe mk_arcade_joystick_rpi map=5 gpio=pin1,pin2,pin3,.....,pin12
```

Where _pinx_ is the number of the GPIO port you want. There are 12 possible GPIOs with **button control: Y-, Y +, X-, X +, start, select, a, b, tr, y, x, tl**. Use -1 for unused pins. For example `gpio=21,13,26,19,-1,-1,22,24,-1,-1,-1,-1,-1` uses GPIO ports 21, 13, 26, 19 for the axes and ports 22 and 24 for buttons A and B, the rest of the buttons are not used.

The actions of joystick 1 will be reported to the file "/dev/input/js0" and the actions of joystick 2 will be reported to the file "/dev/input/js1".

#### ​ <a id="undefined-4"></a>

### Automatic loading at startup

Open `/etc/modules` :

```text
sudo nano /etc/modules
```

and add the line you use to load the driver:

```text
mk_arcade_joystick_rpi
```

Then, create the `/etc/modprobe.d/mk_arcade_joystick.conf` file:

```text
sudo nano /etc/modprobe.d/mk_arcade_joystick.conf
```

and add the module configuration:

```text
options mk_arcade_joystick_rpi map=1,2
```

### ​Test

Use the following command to test the joystick actions:

```text
jstest /dev/input/js0
```

​

### Other joystick cases: MCP23017

Here is the summary of the MCP23017 pinout:

![](https://github.com/recalbox/mk_arcade_joystick_rpi/raw/master/wiki/images/mk_joystick_arcade_mcp23017.png)

#### ​ <a id="undefined-5"></a>

#### Preparing the Raspberry Pi for the MCP23017

Follow the instructions for installing the defaults.

Activate i2c on your Pi:

```text
sudo nano /etc/modules
```

Add the following lines to automatically load i2c modules:

```text
i2c-bcm2708 
i2c-dev
```

And if the `/etc/modprobe.d/raspi-blacklist.conf` file exists:

```text
sudo nano /etc/modprobe.d/raspi-blacklist.conf
```

Make sure you have a line with:

```text
i2c-bcm2708 
```

and add a \# \(hashtag\) at the beginning of the line to remove the blacklist 

Restart or load the two modules:

```text
modprobe i2c-bcm2708 i2c-dev
```

​

### Preparing the MCP23017 chip

You need to set pins A0, A1 and A2 to 0 or 1 to define the chip's i2c address.

If you have only one chip, connect all 3 pins to the ground. Simply connect one of the pins at 3.3V to set its state to 1 and change the MCP23017's i2c address.

You also need to connect the RESET pin to 3.3V.

​

### Configuration

When you want to load the driver, you need to check a list of parameters that represent the list of connected joysticks. The first parameter will be the joystick mapped to / dev / input / js0, the second to js1, etc.

If you connected a joystick to the GPIOs of Pi, you must enter "1" as a parameter.

If you connected one or more joysticks to the MCP23017 chip, you must enter the address of the connected I2C devices, which you can obtain with the command:

```text
sudo i2cdetect -y 1
```

The configuration of each MCP23017 is done by setting pads A0, A1 and A2 to 0 or 1.

If you configured your MCP23017 with A0, A1 and A2 connected to ground, the address returned by i2cdetect must be 0x20

Therefore, if you have a joystick connected to GPIOs on Pi and a joystick on an MCP23017 chip with address 0x20, to load the driver, run the following command:

```text
sudo modprobe mk_arcade_joystick_rpi map=1,0x20
```

The joystick actions on the GPIO will be reported in the "/ dev / input / js0" file and the joystick actions on the MCP23017 chip will be reported in the "/ dev / input / js1" file.

I tested up to 3 joysticks; one on GPIO ports, one on MCP23017 at address 0x20, one on MCP23017 at address 0x24:

```text
sudo modprobe mk_arcade_joystick_rpi map=1,0x20,0x24
```

## Known bugs

If you try to read or write to i2c with a tool like i2cget or i2cset when the driver is loaded, it will be very difficult...

If you try i2cdetect when the driver is running, it will show some strange device addresses...

The 256 MB version of the Raspberry Pi Model B is not supported by the current driver. If you want the driver to work on your old Pi, you will need to change the address from BSC1\_BASE to \(BCM2708\_PERI\_BASE + 0x205000\) to use the correct i2c address, and recompile.

