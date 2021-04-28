---
title: Connecting a LCD display with I2C to your recalbox
---

# Connecting a LCD display with I2C to your recalbox

## Prerequisite

An **I2c LCD screen** like model **Hd44780** in **A00** version \(ascii support + Japanese characters\) or **A02** version \(ascii support + European characters\)

![](http://i.imgur.com/YrDDhwUm.jpg)

## Installation

### I2C connection to GPIO Raspberry Pi 3

![](http://i.imgur.com/NKswbgr.png)

### ​I2C activation in Recalbox

* **Edit** `/etc/modules.conf`. **Add the following line at the end** of the file

```text
i2c-bcm2708
i2c-dev
```

* **Edit** `/boot/config.txt`. **Add the following lines**  :

```text
#Activate I2C
dtparam=i2c1=on
dtparam=i2c_arm=on
```

* **Edit** `/boot/cmdline.txt`. **Add the following line at the end** of the file :

```text
bcm2708.vc_i2c_override=1
```

* **Reboot** Recalbox

### Checking the I2C address <a id="verifier-ladresse-de-li-2-c"></a>

You will need to **know the address of your I2C** to run some **display scripts**. Typically, the address is `0x27` ****or `0x3f`.

* Run the next command ; just relax, it may take a while !
  * on the very old Raspberry models : `i2cdetect -y 0`
  * on recent Raspberry \(ft3, ft2\) : `i2cdetect -y 1`

```text

     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- 27 -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
```

The **address** returned by the order in the table tells us: `0x27`

## Display script available for Recalbox

​[https://forum.recalbox.com/topic/8689/script-clcd-display-on-recalbox](https://forum.recalbox.com/topic/8689/script-clcd-display-on-recalbox)​

![](http://i.imgur.com/fsXfArEm.jpg)

