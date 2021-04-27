---
description: This page describe how to configure this device on Recalbox
---

# Waveshare wm8960 audio hat

## Introduction

This is the WM8960 Hi-Fi Sound Card HAT For Raspberry Pi. [https://www.waveshare.com/wm8960-audio-hat.htm](https://www.waveshare.com/wm8960-audio-hat.htm)

This is a sound card HAT designed for Raspberry Pi, low power consumption, supports stereo encoding / decoding, features Hi-Fi playing / recording, what's more, it can directly drive speakers to play music.

Since the 7.01 Recalbox release, this audio hat is supported thanks to a small configuration.

![Waveshare wm8960 audio hat bundle](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJkNAl5vw3d0btRnf-P%2F-MJkl8Qu_wSRN6k7IGRw%2Fimage.png?alt=media&token=4245fe18-5211-42c0-9395-cff302d32d54)

![Waveshare wm8960 audio hat mounted on a Raspberry Pi](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJkNAl5vw3d0btRnf-P%2F-MJklLFCtug7YhNAd2tW%2Fimage.png?alt=media&token=deb6a2c1-4b47-49d4-87b8-9abab3e84a68)

## Configuration

You need to modify the `/boot/config.txt` file as follows to add support for this new hardware an overlay and the activation of the I2C bus. To do this we pass the partitions to write :

```text
mount -o remount, rw /boot 
```

then edit the file `/boot/config.txt` and add the following at the end of the file using nano :

```text
dtparam=i2c1=on
dtparam=i2c_arm=on
dtoverlay=wm8960-soundcard
```

Just save the file and reboot. That 's it.

## Using the wm8960 audio output

In Emulationstation, go to the menu Sound Settings, and select one of the WM8960 device. After selecting, you sould hear the music through the speakers.

![Sound output selection in EmulationStation](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJkrS2FJcNnd9Xslafy%2F-MJkrxPR0U-JLy-8-OOy%2FIMG_20201002_181811.jpg?alt=media&token=f1dc679d-8d54-4840-9a7b-88fe2198d369)

![Sound output selection in EmulationStation](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJkrS2FJcNnd9Xslafy%2F-MJkroFCIC9IcfQlMMhk%2FIMG_20201002_181819.jpg?alt=media&token=21d7485e-7eb2-4d24-b01f-f6bf31b5e1c6)

{% embed url="https://youtu.be/0dCN-2YFroU" %}

