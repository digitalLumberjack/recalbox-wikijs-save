# Recalbox for your USB keyboard encoder

## Introduction

This tutorial is for Recalbox 4.0.0 Beta 2 or higher

Xarcade2jstick has been patched to support keyboard encoders. You may need to reconfigure a few keys on your encoder as unfortunately the Xarcade devices from X-gaming have not been mapped like the regular controllers from MAME.

## Adding your keyboard encoder

So far, only the first generation of IPAC has been included. If you have another keyboard encoder, follow these steps:

* Connect to your Recalbox locally or via [SSH](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal)
* Find the device name of your encoder with `ls /dev/input/by-id`. Usually the result is followed by a kbd. For example: _usb-Ultimarc\_IPAC\_2\_Ultimarc\_IPAC\_2\_9-if01-event-kbd_


>**NOTE** : A single encoder can have multiple possible names, so try them all for example:
>
>* usb-Cypress\_I-PAC\_Arcade\_Control\_Interface-event-kbd -&gt; works
>* usb-Cypress\_I-PAC\_Arcade\_Control\_Interface-if01-event-kbd -&gt; does not work
>
{.is-info}

* Now remount / in read-write mode `mount -o remount,rw /`
* Create an empty file with the same name as your keyboard device found 2 steps above `touch /recalbox/share_init/system/configs/xarcade2jstick/devicename`. In the previous example:`touch /recalbox/share_init/system/configs/xarcade2jstick/usb-Ultimarc_IPAC_2_Ultimarc_IPAC_2_9-if01-event-kbd`
* Edit [recalbox.conf ](/basic-manual/getting-started/the-recalbox.conf-file)and set to: `controllers.xarcade.enabled=1`
* Reboot by typing `reboot`

The Recalbox is now configured for these devices.

### Key mapping

### v4.0.0 - beta4 :

| Key | Player 1 | Player 2 |
| :--- | :--- | :--- |
| UP | Up key or Numeric keypad key 8 | R key |
| DOWN | Down key or Numeric keypad key 2 | F key |
| LEFT | Left key or Numeric keypad key 4 | D key |
| RIGHT | Right key or Numeric keypad key 6 | G key |
| A | Z key | E key |
| B | Left SHIFT key | W key |
| X | Left ALT key | S key |
| Y | Left CTRL key | A button |
| START | Numeric keypad key 1 | Numeric keypad key 2 |
| SELECT | Numeric keypad key 5 | Numeric keypad key 6 |
| L1 | Space bar | Q key |
| R1 | X key | \[ Or K key |
| HOTKEY | Numeric keypad key 3 or V key | Numeric keypad 4 key or L key |



### v4.0.0 - beta2 :

| Key | Player 1 | Player 2 |
| :--- | :--- | :--- |
| UP | Up key or Numeric keypad key 8 | R key |
| DOWN | Down key or Numeric keypad key 2 | F key |
| LEFT | Left key or Numeric keypad key 4 | D key |
| RIGHT | Right key or Numeric keypad key 6 | G key |
| A | Z key | E key |
| B | Left SHIFT key | W key |
| X | Left ALT key | S key |
| Y | Left CTRL key | A key |
| START | Numeric keypad key 1 | Numeric keypad key 2 |
| SELECT | Numeric keypad key 3 | Numeric keypad key 4 |
| L1 | Space bar | Q key |
| R1 | X key | \[ key |
| HOTKEY | C key | \] key |

