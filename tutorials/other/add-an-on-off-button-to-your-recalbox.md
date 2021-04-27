# Add an ON/OFF button to your recalbox


>You can now add an **ON/OFF button** to your **Recalbox**. The button can be a **push button** \(also called a "momentary switch"\) or an **ON/OFF button**.
{.is-info}

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJH8jdcYQLsGJvtswtn%2F-MJHA_HOg9wBtC_agqnR%2Fadd-a-start-stop-button-to-your-recalbox-en-recalboxrecalbox-os.jpg?alt=media&token=bccf6ecf-3c7e-4008-bba0-9dbb427910ab)

## To wire the button to the Raspberry Pi GPIO

* Connect one pin to GPIO3 \(the fifth gpio from the top left\), and the other to the ground on its right \(the sixth gpio\):

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJH8jdcYQLsGJvtswtn%2F-MJHBikcKEvyxKFdtUAG%2FRaspberry%20Pi%2040-pin%20GPIO%20Layout.png?alt=media&token=49f0c74e-433e-40fb-81ca-06cec2f2efb7)

* Finally, you need to enable button support in [recalbox.conf](/basic-manual/getting-started/the-recalbox.conf-file) by adding one of these lines:
  * `system.power.switch=PIN56ONOFF` for an ON/OFF button
  * `system.power.switch=PIN56PUSH` for a push button

And you have a **Recalbox** which can be **turned OFF/ON with a single button**!

## Add a reset button and an LED​


>**Since Recalbox 4.0 beta 4**, there is another option where you can add a **reset button** and an **LED**.
{.is-info}

* In **recalbox.conf,** add / uncomment \(removing the; at the beginning of the line\) the following line: `system.power.switch=PIN356ONOFFRESET`​
* To wire the **reset button** to the Raspberry Pi's **GPIO**: Connect one pin to **GPIO2** \(the **third** gpio from the top left\), and the other to the same ground as the ON/OFF button \(the **sixth** gpio\). **The LED** is connected to **GPIO14** \(the \*eighth gpio\) **as well as to the ground.**  To sum up:
* _Power+_ on **GPIO 3** \(**PIN 5**\)
* _Reset+_ on **GPIO 2** \(**PIN 3**\)
* _LED+_ on **GPIO 14** \(**PIN 8**\)
* _Power-_, _Reset-_ and _Led-_ on one of the **Ground** \(**PIN 6, 9, 14, 20, 25, 30, 34 or 39**\)


>Note that this only works with a **push button for reset** and an **ON/OFF button for power.**
{.is-info}

## Recalbox update&gt; 02/18/09

Since update 18.02.09, the **power scripts have evolved**, to offer you more possibilities! Now, by following the same method explained previously, you will be able to... 

### With the POWER button \(PIN 5 GROUND\)

* **Short press** \(OFF\): Switch ON your Recalbox
* **Short press** \(ON\): Exit the current emulator and return to the main menu
* **Long press** \(ON\): Turn OFF your Recalbox properly \(equivalent to START&gt; Exit&gt; Shut down normally\) 

### With the RESET button \(PIN 3 GROUND\)

* **Short press** \(OFF\): -
* **Short press** \(ON\): Reset the game, as at the time on the console
* **Long press** \(ON\): Restart your Recalbox \(equivalent to START&gt; Exit&gt; Restart\)

