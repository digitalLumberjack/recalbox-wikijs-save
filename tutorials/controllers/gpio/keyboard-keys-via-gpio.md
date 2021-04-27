# Keyboard keys via GPIO

**Recalbox** includes the **retrogame module**, which can be found in `/usr/bin/recalbox-retrogame`.

This module **will allow the use of GPIOs** to reproduce the behavior of **a real USB keyboard in Recalbox.**


>**Warning:**  
>**It only works if** we find the line**`controllers.gpio.enabled=0`**in [recalbox.conf](/basic-manual/getting-started/the-recalbox.conf-file)
>{% endhint %}
>
>{% hint style="info" %}
>**Examples:**
>
>* If you want to **integrate a Raspberry Pi with an old console** and **reuse the buttons** on the front panel \(for example: PAUSE / SELECT of an Atari 7800\)
>* **Connect** \(on an arcade / arcade machine\) **a button** that would have **the same behavior as the Esc key on the keyboard.**
>* Or simply, use without a keyboard.
>
{.is-danger}

## Installation

### Cabling

You must use the **push buttons** \(which go up after pressing\) and connect **one terminal to the ground** and the **other terminal to the GPIO.**

### ​Script <a id="script"></a>

To **automatically start the module when Recalbox starts**, it is important to **add a script.**

* **Create** a text file "**S99Retrogame**" without extension
* **Add the following two lines** of code:

```text
/usr/bin/recalbox-retrogame
exit 0
```

* **Give the rights:**`chmod 775 /etc/init.d/S99retrogame`
* **Put it in:**`/etc/init.d/`
* **Reboot and check** in SSH \(via Putty, for example\) to see if the module was started **using the command**:`ps aux|grep recalbox-retrogame`. If the command **returns an ID**, you've done it!

