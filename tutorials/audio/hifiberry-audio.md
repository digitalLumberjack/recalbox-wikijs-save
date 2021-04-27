# HiFiBerry Audio


>To get a **quality audio signal on Pi**, one solution is to use a **HiFiBerry DAC** \(Digital to Analog Converter\).
{.is-info}

Those **DAC** exist in several versions :

**Raspberry Pi A+, B+, 2 and 3**

* DAC+ Light
* DAC+ Standard RCA
* DAC+ Standard Phone
* DAC+ Pro

**Raspberry Pi A et B**

* DAC Standard version with RCA connectors

The characteristics of the different cards can be compared on [hifiberry.com](http://www.hifiberry.com).  
**DAC+ cards** can be **connected directly to the GPIO** of the Pi.  
Pins not used by the DAC can be reused for other uses, in which case additional pins must be soldered to the DAC+ card.

Below is the wiring diagram of a DAC+ HifiBerry :

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M4MJhLQO6S2oqnO487A%2F-M4MKkv1EquQT-H7eNn7%2Fimage.png?alt=media&token=8ca251e1-640a-4a7e-9c2e-ed3a8ba78e8c)


>The version for **Raspberry A and B** must be installed on **pin 5**, which requires some additional handling. Once the card is installed, there are a few more software configuration steps to make everything work.
{.is-info}

## Device configuration

* On recalbox, you just need to add the right **DTB** in `/boot/config.txt`, with the right parameters \(depending on your card\) :

**DAC/DAC+ Light**

`dtoverlay=hifiberry-dac`

**DAC+ Standard/Pro**

`dtoverlay=hifiberry-dacplus`     


* Then you have to **select the default sound card :** just **edit** `/etc/asound.conf` \(create the file if not already present\) **with the following content** :

`pcm.!default {`  
`type hw card 0`  
`}`  
`ctl.!default {`  
`type hw card 0`  
`}`

* **Reboot** your Pi.

Now you should hear the sound through your HiFiBerry card.


>**IMPORTANT:**  
>You cannot change the sound volume in EmulationStation only by Alsamixer/Amixer.
{.is-info}

## Alsamixer/Amixer <a id="alsamixer-amixer"></a>

**ALSA sound cards** \(and this is the case of HiFiBerry\) can be controlled by **Alsamixer**_,_ which is a **graphical user interface**, whereas **Amixer** works in text mode, especially for **scripts**.

Since **alsa-utils** is installed on Recalbox, HifiBerry will work **without additional utilities**.


>**IMPORTANT :**  
>The DAC+ Light and the old DAC won't have any settings available in ALSA.
{.is-danger}

With the `amixer` **command** you will get a text version of the **various DAC settings**. The best way to change the volume is to change the _Overall volume_. Its name may differ depending on the card: _PCM_, _Digital_, _Master_, just try one of them.

The following **commands** allow you to **change the volume via the terminal** :

* `amixer sset ‘Master’ -- 90%` \(not recommended because the scale is logarithmic\)
* `amixer sset ‘Master’ -- -3dB` \(in decibels, recommended setting\)
* `amixer sset ‘Master’ – 2000` \(unité empirique, déconseillé\)

Here is an **example** in **python** to **manage the volume**.

First, import the sub-process command :

```python
from subprocess import call


call(["amixer", "sset", "Digital", "--", str(YourDesiredVolume)+"dB"])
```

This script can especially be used to **change the volume** by using the **GPIO**

**Below are some available commands with** _**amixer**_ **:**

* `amixer sset 'PCM' 70%` \(percentage\)
* `amixer sset 'Master' 3dB` \(Decibel\)
* `amixer sset 'Mic' 4` \(hardware values\)
* `amixer sset 'PCM' 10%+` \(increase in the current value, the unit can be % or dB\)
* `amixer sset 'Line' cap` \(Recording on/off: cap, nocap\)
* `amixer sset 'Mic' mute` \(Playback on/off: mute, unmute\)
* `amixer sset 'Master' off` \(On/Off: on/off\)
* `amixer sset 'Mic Select' 'Mic1'` \(device name\)

See: [**wiki.ubuntuusers.de/amixer**](https://wiki.ubuntuusers.de/amixer/)


>You can also use Google to discover the available commands with the keywords: _amixer_, _alsamixer_.
{.is-info}

