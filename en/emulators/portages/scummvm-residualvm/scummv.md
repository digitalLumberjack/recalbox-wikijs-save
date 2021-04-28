---
title: ScummV
---

# ScummV

## What is SCUMM?

**Script Creation Utility for Maniac Mansion** \(SCUMM\) is a video game engine developed at Lucasfilm Games, later renamed LucasArts, to ease development on their first graphic adventure game Maniac Mansion \(1987\). It was subsequently used as the engine for later LucasArts adventure games.

It falls somewhere between a game engine and a programming language, allowing designers to create locations, items and dialogue sequences without writing code in the language in which the game source code ends up.

This also allowed the game's script and data files to be cross-platform, i.e., re-used across various platforms.

SCUMM is also a host for embedded game engines such as the Interactive MUsic Streaming Engine \(iMUSE\), the INteractive Streaming ANimation Engine \(INSANE\), CYST \(in-game animation engine\), FLEM \(places and names object inside a room\), and MMUCUS. SCUMM has been released on these platforms: 3DO, Amiga, Apple II, Atari ST, CDTV, Commodore 64, Fujitsu FM Towns & Marty, Apple Macintosh, Nintendo Entertainment System, DOS, Microsoft Windows, Sega CD \(Mega-CD\), and TurboGrafx-16/PC Engine.



## What is ScummVM?

ScummVM is a program which allows you to run certain classic graphical point-and-click adventure games, provided you already have their data files. The clever part about this: ScummVM just replaces the executables shipped with the games, allowing you to play them on systems for which they were never designed!



## How do I play SCUMM Games in Recalbox?

To add a Scummvm game, create a folder with the name of the game followed by the ".scummvm" extension and copy files of the game in it. In this folder, you will have to add a single file, named \[gameshortname\].scummvm

You can find short names for all supported games at [http://scummvm.org/compatibility/](http://scummvm.org/compatibility/)

Tip: Add the `Game Full Name` from the previous site inside \[gameshortname\].scummvm for the scraper to detect it easily.

For example, you can copy the game "Broken Sword" in the directory "Broken Sword 1.scummvm" under the scummvm directory. In this folder create a file named sword1.scummvm

```text
scummvm
|- Broken Sword 1.scummvm
|  |- sword1.scummvm
|  |- ... other files of the game
```

The name of your directory will be displayed as the name of the game in Recalbox menu. Selecting it will start the game.

You can quit the game and get Scummvm options by using the _Ctrl_ + _F5_ shortcut.



## Are all SCUMM Games compatible?

Please see the [Compatibility List](http://scummvm.org/compatibility/>) on the ScummVM website that contains an up to date list of which games work, and how well they work.



## How to configure Roland MT-32 emulation for ScummVM games?

Some games which contain MIDI music data also have improved tracks designed for the MT-32 sound module. ScummVM can now emulate this device, however you must provide original MT-32 ROMs to make it work.



### Activate the Roland MT-32 emulator in scummvm

* You will need to manually edit your ScummVM configuration file \(`/recalbox/share/system/.config/scummvm/scummvm.ini` or .scummvmrc\) and add following lines in `[scummvm]` section:

  ```text
  mt32_device=mt32
  music_driver=mt32
  ```

* Or Use the ScummVM Gui
* launch an scummVM game
* Press F5
* Return to launcher
* Options
* Audio tab
* Set Preferred device to MT32 emulator
* MT-32 tab_\*\*\_\__
* Set MT-32 Device to MT-32 Emulator
* Apply, ok
* Quit.



### Copy the MT32 and MT32 CM-32L ROMS

You have to copy MT32 ROMs \(**MT32\_CONTROL.ROM**, **MT32\_PCM.ROM**, **MT32\_PCM.ROM**, CM32L\_CONTROL.ROM\) in one directory.

* You can copy them directly to the scummvm folder : **/usr/share/scummvm**. You will need to mount the partition in RW mode to do that.
* You can also simply copy the four ROM files in the game directory.
* If you want to use a different folder like for instance /recalbox/share/bios. You will need to edit your ScummVM configuration file \(`/recalbox/share/system/.config/scummvm/scummvm.ini` or .scummvmrc\) and add following lines in `[scummvm]` section:

  ```text
  extrapath=/recalbox/share/bios
  ```



You have to use ROM files supported by ScummVM, for instance with following MD5 signature:

```text
5626206284b22c2734f3e9efefcd2675  MT32_CONTROL.ROM
89e42e386e82e0cacb4a2704a03706ca  MT32_PCM.ROM
BFFF32B6144C1D706109ACCB6E6B1113  CM32L_CONTROL.ROM
08CDCFA0ED93E9CB16AFA76E6AC5F0A4  CM32L_PCM.ROM
```

