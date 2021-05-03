---
title: Controller configuration
description: How to properly configure your controller
---

# Controller configuration

## Add and configure an USB controller

It's possible to add USB controllers on Recalbox. Most of them should be compatible \(see the [compatibility list](/hardware-compatibility/compatible-devices/controller)\).

* After plugging your USB controller \(or paired your Bluetooth controller\), 
* push **START** with an already configured controller \(or **ENTER** with a keyboard\), 
* select **CONTROLLER SETTINGS** then follow the instructions.

The button names are based on a Super Nintendo controller:

![A Super Nintendo \(SNES\) controller](/migration-images/basic-manual/getting-started/1000px-snes_cont.jpg)


>The L1, R1, L2, R2, L3, and R3 buttons are based on the Playstation 3 controller.
{.is-info}

The last button to set up,  **HOTKEY**, will be used to perform [special commands](during-the-game.md#special-commands) inside an emulator.

* For Xbox 360 and Xbox One controllers, the **HOTKEY** Button is set to the _HOME_ button.
* For PS3 and PS4 controllers, the **HOTKEY** Button is set to the _PS_ button.
* If there isn't a dedicated button, it is advised to set the **HOTKEY** Button to either _Select_ or _L3_ \(Left Joystick click\).


>To skip any button in the configuration \(except _Hotkey_\), press _Down_ to go to the next one.
{.is-info}

Once you're back to the configuration screen, you can assign the controller to a specific player. Your controller is now set up.

## Button mapping

* For 6 buttons controllers \(SNES, Arcade, ...\) the buttons are mapped according to a SNES layout \(see the above section\).
* For 2 buttons controllers \(NES, PC Engine, Gameboy, ...\) only the A and B buttons are used.

## Using a keyboard

If you cannot configure a controller, it's possible to plug an USB keyboard into Recalbox to set it up.

* **Start** = _Enter_
* **Select** = _Space_
* **Back** = _S_
* **Confirm** = _A_

## PS3 Controllers

In order to associate a _PS3 controller :_

* First connect the controller to the USB port 
* **Wait 10 seconds**. 
* After this you can now disconnect the controller 
* Press the Home button to initiate the wireless connection.


>For asian copies of the PS3 DualShock 3 \(such as GASIA or SHANWAN\), you will need to adust some settings.   
>See PS3 controllers drivers.
{.is-warning}


>**Warning :**   
>If unsure about the power supply and power consumption of the device, try to avoid charging the SixAxis on the RPi as this may cause stability issues.   
>  
>In this case plug the controller on the recalbox **only** to associate your controller with your recalbox.
{.is-danger}

If you understand the parameters involved or want to try using the SixAxis over a USB connection, you need to disable the ps3 bluetooth driver in recalbox.conf by setting `controllers.ps3.enabled=0`

Remember that the configuration of the controllers in recalbox is based on the SNES buttons assignment :



| ps3 pad | snes pad |
| :---: | :---: |
| x | B |
| ◯ | A |
| ⬜ | Y |
| △ | X |


>The default **HOTKEY** button is the **PS** button, the one in the middle of your controller.  
>For more info about HOTKEY actions like saving/loading see the [Special commands](during-the-game.md#special-commands) section.
{.is-info}

## Xbox 360 controllers


>**Note:**   
>XBox 360 Wireless controllers need specific wireless receiver hardware. Since 4.1, the Xbox configuration doesn't require you to enable any specific driver. It works just out of the box and can even be used along with DualShock pads \(which was not the case in 4.0\).
{.is-warning}

Remember that the configuration of the controllers in recalbox is based on the SNES buttons assignment :

| xbox pad | snes pad |
| :---: | :---: |
| A | B |
| B | A |
| X | Y |
| Y | X |


>The default **HOTKEY** button is the **HOME** button, the big one in the middle of your controller.   
>For more info about HOTKEY actions like saving/loading see the [Special commands](during-the-game.md#special-commands) section.
{.is-info}

## Add a Bluetooth Controller

To add a bluetooth controller, 

* Set your controller in pairing mode. 
* Go to the menu using the **START** button or a keyboard and select **Controller Settings**.
* Select **Pair a bluetooth Controller.**​

A list of **detected controllers** appears !

* Select yours and now the controller is paired! 
* Now you can configure it if it's not already a supported controller!


>For **8bitdo** users, see 8bitdo on recalbox.
{.is-info}

## GPIO controllers

* You can connect your arcade joysticks and buttons directly on the raspberry GPIOs. See GPIO controllers.
* You can connect original controllers from PSOne, Nes, Snes, Megradrive and other. See DB9 and Gamecon controllers.

## Virtual gamepads

With Miroof's [Virtual Gamepads](https://github.com/miroof/node-virtual-gamepads) you can add up to 4 controllers with your phones ! Virtual game pad is based on snes controller. 

* Just start your Internet Navigator on your phone
* Type the recalbox IP followed by the communication port \(port=8080\). 


>You can get the recalbox IP in the setting menu [NETWORK SETTINGS](emulationstation.md#6-network-settings)​
{.is-info}

![virtual gamepad touch zones](/migration-images/basic-manual/getting-started/virutalgamepad_touch_zones.png)

For more info see Virtual Gamepad.

