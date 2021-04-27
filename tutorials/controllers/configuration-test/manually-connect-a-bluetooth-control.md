# Manually connect a bluetooth control

You can connect your bluetooth joystick manually.

You will need [root access](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal) for this.

## If the Recalbox version is less than or equal to 4.0

Put your bluetooth joystick in association mode and type:  
`hcitool scan`

This will get the joystick's mac address:  
`aa:bb:cc:dd:ee:ff Name:Bluetooth HID`

Then create the connection to the joystick:  
`hidd --connect aa:bb:cc:dd:ee:ff`

And restart Emulationstation:  
`/etc/init.d/S31emulationstation start`

## If the Recalbox version is greater than or equal to 4.1

You have two options. One may not work, if it does, try the next one. Start your controller in pairing mode, make sure you have previously reset it and removed any existing associations. Attention: for now, you must start your Bluetooth control **after** EmulationStation is started.

​

### Using the simple-agent command

Find your control's mac address \(in capital format\) using:`/recalbox/scripts/bluetooth/test-device list`

Try several times if your controller does not appear on the list. If, after a few attempts, your control is still not listed, go to method B.

If your controller is listed, type:`/recalbox/scripts/bluetooth/simple-agent hci0 "AA:BB:CC:DD:EE:FF"`

Where **AA: BB: CC: DD: EE: FF is your device's mac address in uppercase.** A PIN code may be requested, see the documentation for your joystick. If you are still unable to pair, try the next method.

### ​Using the bluetoothctl command

Start `bluetoothctl` and type the following commands:

```text
agent on
default-agent
power on
scan on
```

Wait until `bluetoothctl` lists your device and:

```text
pair AA:BB:CC:DD:EE:FF
connect AA:BB:CC:DD:EE:FF
trust AA:BB:CC:DD:EE:FF
```

