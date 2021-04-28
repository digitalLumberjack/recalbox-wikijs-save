---
title: Test your joystick with jstest
---

# Test your joystick with jstest

To test your controls, you can use the `jstest` command, which allows you to list information about your controls.

* You must first have [root access via terminal](/tutorials/system/access/root-access-via-terminal) 
* To find out if your controls have been detected by the system, use the following command:

```
cat /proc/bus/input/devices
```

* After your controllers are detected, a special event is created for each of them in `/dev/input`, you can see them listing them with this command:

```
ls /dev/input/js*
```

* You can now start a special command to test your control's buttons and axes. For example, to test your first control on the system:

```
jstest /dev/input/js0
```

* You should get the following answer:

```
Driver version is 2.1.0.
Joystick (Logitech Logitech Cordless RumblePad 2)
has 6 axes (X, Y, Z, Rz, Hat0X, Hat0Y)
and 12 buttons (BtnX, BtnY, BtnZ, BtnTL, BtnTR, BtnTL2, BtnTR2, BtnSelect, BtnStart, BtnMode, BtnThumbL, BtnThumbR).
Testing ... (interrupt to exit)
Axes:  0:     0  1:     0  Buttons:  0:off  1:off  2:off  3:off  4:off  5:off  6:off  7:off  8:off  9:off 10:off 11:off
```

**Now,** you can watch **the response of all buttons and axes on your controls.**

