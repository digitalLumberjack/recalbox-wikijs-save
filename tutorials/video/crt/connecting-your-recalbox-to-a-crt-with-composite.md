# Connecting your recalbox to a CRT with composite

If you want to **connect your** **recalbox to a CRT**, you will need a **mini-jack to RCA** like this one:

![RPi Audio/Video Socket](https://image.ibb.co/mQCKDJ/rpi_AV_socket.jpg)


>Caution, on **camcorder cables, the video output may be on the right** \(red\) audio jack.  
>  
>Also, the type of cable required is not really common.  
>It is preferable to **test with a Multimeter**, in order to be sure that the cable you plan to use is corresponding to the diagram proposed above \(an inversion of Ground and video on the jack leads to a jumping black & white image, sign of an unsuitable cable\).
>{% endhint %}
>
>{% hint style="warning" %}
>**In Recalbox 4.0.0** you have to make the partition writable.
>{% endhint %}
>
>* [Modify /boot/config.txt](https://recalbox.gitbook.io/tutorials/v/francais/xi-systeme/modification/editer-le-fichier-config.txt)
>
>  **commenting each line starting with** `hdmi_` **with** `#`, and **adding the supported sdtv\_mode :**
>
>```text
>sdtv_mode=0    Normal NTSC   
>sdtv_mode=1    Japanese version of NTSC – no pedestal  
>sdtv_mode=2    Normal PAL   
>sdtv_mode=3    Brazilian version of PAL – 525/60 rather than 625/50, different subcarrier
>```
>
>* To get a **better sound through the composite output**, activate the experimental audio driver for the Raspberry pi
>
>```text
>audio_pwm_mode=2
>```
>
>{% hint style="danger" %}
>**Warning**, this mode can create an **overall slowdown** of the Recalbox.
>
{.is-danger}

* If this is the case, comment the previous line and force the audio output to the jack

```text
#audio_pwm_mode=2
hdmi_drive=1
```

* Finally, **add**`hdmi_ignore_hotplug=1` to **force the composite output**.

If you are on Recalbox OS 4.0 or higher, the file system is read-only. You will have to use Noobs to modify the configuration file. Plug in a USB keyboard and press the Shift key at startup to access the recovery menu. Then press "e" to get the edit menu, and make your changes here. You can change the language and keyboard configuration by pressing "l" and "k". [https://recalbox.gitbook.io/tutorials/v/francais/xi-systeme/modification/editer-le-fichier-config.txt](https://recalbox.gitbook.io/tutorials/v/francais/xi-systeme/modification/editer-le-fichier-config.txt)

Your **config.txt** should look like below :

```text
sdtv_mode=2
hdmi_ignore_hotplug=1
audio_pwm_mode=2
```

* Then **edite** [recalbox.conf](/v/francais/manuel-de-base/premiers-pas/le-fichier-recalbox.conf) and change`global.videomode` to `default`:

```text
global.videomode=default
```

* If you are using the **n64 emulator**, please comment this line as well:

```text
n64.videomode=DMT 9 HDMI
```

* and uncomment this one :

```text
n64.videomode=default
```

* Finally, disable game smoothing and all shaders in the EmulationStation menu \(START -&gt; GAME OPTIONS\) which will allow you to have the original rendering on all systems!

## Everything's slow in composite mode

`audio_pwm_mode=2` improves the sound but can slow down the system in composite mode, especially on Pi zero. In this case, use the following mode:

```text
audio_pwm_mode=0
```

