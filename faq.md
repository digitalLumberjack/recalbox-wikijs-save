# 💡 FAQ

## General troubleshooting

* **My Recalbox just crashed, should I unplug it and plug it back ?**

> No, in most cases, the system didn't fully crash, only EmulationStation did.  
> Here are multiple ways to deal with this situation, the easiest being the use of the webmanager debug functionnalities to either restart ES or to Shutdown Recalbox correctly.  
> Not doing so may corrupt your datas, especially if you're using a Raspberry Pi with an SD card.

## EmulationStation <a id="emulationstation"></a>

* **How to change the EmulationStation theme ?**

> Enter key on the keyboard or Start on the joystick → Interface settings → Theme \(at the very bottom\)

* **Where are the EmulationStation configuration files in the file system ?**

> /root/.emulationstation

* **Where are the themes of EmulationStation ?**

> /root/.emulationstation/themes

* **How to cut the music ?**

> Enter key on the keyboard or Start on the joystick → Sound parameter → Set to Off

## Emulation

* **Why are there multiple emulators for each system ?**

> Emulation is not a flawless operation, there is a balance between performances, features, and fidelity. Since emulation isn't perfect, it's better to have multiple options to deal with it, sometimes a faster emulator will be better but might have unexpected glitches, while a slower one might have an higher accuracy but won't support some specific features.

* **How to change the Default emulator for a given system ?**

> By pushing _Start_ on the gamepad, then going to _advanced settings_, then _emulators advanced configuration_, you can select the desired system, finally, you can switch the Emulator and Core settings \(Note that the Core setting won't change if the Emulator setting says Default\)

## Connectivity

### Windows 10 cannot access Recalbox from network share

* **Case n°1: No computer, including Recalbox, is visible from Windows network**

If you don't see any computer in Windows 10 network, it's because by default network discover is disabled and network configuration is set on "public".

You must go to network settings and set your network on "private". Case n°2: Recalbox is not accessible since Windows 10 update n°1709

Since this update, you can see Recalbox in your network, but you can't access it anymore.

Official explanation: [https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/](https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/) or [https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016](https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016)

Quick fix: Download and apply this patch

The patch will turn the guest security off in Windows to allow Recalbox access back.

* **Case n°2: Recalbox is not accessible since Windows 10 update n°1709**

Since this update, you can see Recalbox in your network, but you can't access it anymore.

Official explanation: [https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/](https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/) or [https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016](https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016)

Quick fix: Download and apply this patch

The patch will turn the guest security off in Windows to allow Recalbox access back.

* **Case n° 3**

Go to all settings / applications / programs and features / enable or disable windows features and check: SMB file sharing support 1.0 / CIFS / SMB1.0 / CIFS client ... then restart Windows.

