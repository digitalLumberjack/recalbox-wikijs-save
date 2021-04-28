---
title: Test your joystick with sdl2-jstest
---

# Test your joystick with sdl2-jstest


>**Information:**
>
>With **Recalbox 4.1 version**, we are using SDL2 to **configure the control**
{.is-info}

To **test your control,** you must:

* **Start** a **ssh session via putty**
* Then, **run the following command:** `sdl2-jstest`

## List the number of your joysticks with the following command:

```text
sdl2-jstest --list
```

Result:

```text
Joystick Name:     'Bigben Interactive Bigben Game Pad'
Joystick Path:     '/dev/input/event0'
Joystick GUID:     030000006b1400000209000011010000
Joystick Number:    0
Number of Axes:     4
Number of Buttons: 13
Number of Hats:     1
...
Button code  0:   304
Button code  1:   305
Button code  2:   306
...
```

## Test your joystick with the following command:

```text
sdl2-jstest -e 0
```

Where 0 is your controller number detected with the command sdl2-jstest --list

Example with an N64 control clicking [here](https://forum.recalbox.com/topic/9016/a-lire-manettes-n64).

