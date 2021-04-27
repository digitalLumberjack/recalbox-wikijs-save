# Play with your original controller using Gamecon

## 1 - Intro <a id="1-intro"></a>

**The driver** is designed **for use** with retro game controls **connected to the Raspberry Pi GPIOs**.  
**Up to 4 controls** can be used **at the same time** if they are of the following type:

* NES Control
* SNES control
* PSX / PS2 Control
* N64 Control
* Gamecube Control


>**The driver is based on the Gamecon driver**, but uses **different parameters and pinouts.** Therefore, **there is no guarantee that it will work**, so **do it at your own risk!**
>
{.is-info}

## 2 - Connect the controls

**PINS P1-01 and P1-06** are used for **3.3V power and ground**. They are **common** to all controls **connected to the GPIO**. Although **SNES / NES controls** are rated at **5V, they should work at 3.3V.**  
Therefore, **there is no need to use a converter** for data PINS. The **maximum intensity** \(50mA\) of the Raspberry should be sufficient **to power 4 controllers in the GPIO.**  
However, you must **use a high-performance Raspberry power supply** \(type 2.1A\) to prevent any **unwanted voltage drops**.

**The data PINs P1-03, 05, 07, 26** \(GPIO0, GPIO1, GPIO4 and GPIO7\) are **independent of each other** and **each control** uses a **unique PIN**.


>**Information:**
>
>* **PINS P1-03 and P1-05** correspond to **GPIO2 and GPIO3** on **boards rev.2**. This must be taken into account when loading the module, as explained in **section 3**.
>* **PINs P1-19 and P1-23** \(GPIO10 and 11\) are **signal PINs common** to all **NES / SNES** controls.
>* **PINS P1-08, P1-10 and P1-12** \(GPIO14, 15 and 18\) are **signal PINS common** to all **PSX / PS2** controls.
>
{.is-info}

​

### 2.1 NES / SNES controls

| RASPBERRY PIN | SNES control PIN | NES control PIN |
| :---: | :---: | :---: |
| P1-01 \(3.3V\) | 1 \(power - 5V\) | 1 \(power - 5V\) |
| GPIO10 | 2 \(clock\) | 5 \(clock\) |
| GPIO11 | 3 \(latch\) | 6 \(latch\) |
| GPIOXX | 4 \(data\) | 7 \(data\) |
| P1-06 \(GND\) | 7 \(ground\) | 4 \(ground\) |

#### PINOUT NES and SNES

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Ly12cOjJDyhW9cGp7Mt%2F-Ly13ct-lbBNlcPB5c54%2F68747470733a2f2f692e7761726f73752e6f72672f646174612f76722f696d672f303032372f32322f313434343135303236343635322e706e67.png?alt=media&token=a116d987-374d-4cb8-926c-f7334c6cdbe2)

**GPIOXXs** are **independent data PINs**.  
Refer to **section 3** to select the **correct GPIO** to be used.

​

### 2.2 N64 controls

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDqTCN9r2xAaAtGh2wb%2F-MDqWClO5IkPkFB9aT0b%2F993slmdi.bmp?alt=media&token=19b202af-888d-4eeb-bc2c-ad4049c429c3)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDqTCN9r2xAaAtGh2wb%2F-MDqXq8EVy-uQb3JtQgd%2Fn64_pinouts.png?alt=media&token=4ebb157b-1cef-4c4e-b291-ebd7831101f4)

### 2.3 Gamecube controls

| RASPBERRY PIN | GAMECUBE control PIN |
| :---: | :---: |
| P1-01 \(3.3V\) | 6 \(power/3.43V\) |
| GPIOXX | 3 \(data\) |
| P1-06 \(GND\) | 2&5 \(gnd\) |

**GPIOXXs** are **independent data PINs**.  
Refer to **section 3** to select the **correct GPIO** to be used.

​

![Gamecube Pinout](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDw-HeGvJLeeBwP6W2C%2F-MDw-ZjkI6ByZRMtRnej%2Fgcpad.png?alt=media&token=d996e413-79a4-4deb-abf9-188ee95dae9e)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDqTCN9r2xAaAtGh2wb%2F-MDqXrfiIaTP0ZeICxgf%2Fgc_pinouts.png?alt=media&token=d489aa27-ec65-4eda-8b76-fcfcd3568234)

### ​2.4 PSX / PS2 Controls <a id="2-4-psx-ps-2-controls"></a>

| RASPBERRY PIN | PSX / PS2 control PIN |
| :---: | :---: |
| P1-01 \(3.3V\) | 5 \(VCC\) |
| GPIO14 | 2 \(Command\) |
| GPIO15 | 6 \(ATT\) |
| GPIO18 | 7 \(CLK\) |
| GPIOXX | 1 \(Data\) |
| P1-06 \(GND\) | 4 \(ground\) |

**GPIOXXs** are **independent data PINs**.  
Refer to **section 3** to select the **correct GPIO** to be used.

![](http://www.geocities.ws/digitan000/Hardware/22/pinout.gif)

## 3 Configure the driver

### 3.1 Configure the controls

* **Activate the Gamecon driver** in the [recalbox.conf file](/basic-manual/getting-started/the-recalbox.conf-file) by **setting**`controllers.gamecon.enabled=1` \(if it exists, modify it. Otherwise, create it\).
* **Use the following index of the control** to define the configuration.

  `controllers.gamecon.args` : `map=<pad1/GPIO0>,<pad2/GPIO1>,<pad3/GPIO4>,<pad4/GPIO7>,<pad5/GPIO2>,<pad6/GPIO3>`

Where &lt;pad...&gt;  is the number that defines the type of control:

* 0 = no connection
* 1 = SNES control
* 2 = NES control
* 3 = Gamecube control
* 6 = N64 control
* 7 = PSX / PS2 control
* 8 = PSX DDR control
* 9 = SNES mouse

For example, if an **SNES control** is connected to **GPIO4** and an **N64 control** is connected to **GPIO7**, **the mapping will be** `map=0,0,1,6`.


>Information:
>
>* **pad1 and pad2** are used only with **a rev.1 card**
>* **pad5 and pad6** are used only with **a rev.2 card**
>* **PSX / PS2 controls** require a **pullup resistor.** **Pad5 \(GPIO2\) and pad6 \(GPIO3\)** have this **built-in resistor.**
>
{.is-info}

Therefore, if you have **a rev.2 card, pad1 and pad2** must be **set to 0**.

**The final index of the controls** \(used by the programs\) is assigned sequentially to the connected controls, **starting with 0.**   
Therefore, in the previous example, the **SNES control** would have an index **equal to 0** and the **N64 control** would have an index **equal to 1**.

* **Use the following command** to verify that the **module has loaded successfully:** `tail /var/log/kern.log`

​

### 3.2 Test the controls

**​**[Test your joystick using jtest](https://recalbox.gitbook.io/tutorials/obsolete/test-your-joystick-with-jstest).

### 3.3 Calibrate the analog axis of an N64 control

For **each N64 control, run the following command:**

```text
jscal -s 4,1,0,0,0,6972137,6972137,1,0,0,0,6547006,6468127,1,0,0,0,536854528,536854528,1,0,0,0,536854528,536854528 /dev/input/jsX
```

​

### 3.4 Setting the response time for PSX controllers

**The response time** for **PSX controllers is 10µs**, which **minimizes the delay** induced by the driver.  
However, **in some rare cases**, this is not enough **to have a stable entry**.  
**If you have reading problems** with the **PSX controls**, **increase the delay** by following the **"extra modbprobe"** parameter: **"psx\_delay ="**, where **"delay"** is the value in µs **between 1 and 50**.

## 4 To go further

Gamepad driver for multiple GPIO console:  
[https://www.raspberrypi.org/forums/viewtopic.php?f=78&t=15787](https://www.raspberrypi.org/forums/viewtopic.php?f=78&t=15787)​

Thanks to "**marqs**" for the driver and for allowing us to use "**README**" in Recalbox WIKI.

