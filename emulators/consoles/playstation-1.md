# Playstation 1

PlayStation \(プレイステーション, Purei Sutēshon\) is 5th generation console, created and owned by Sony Interactive Entertainment since December 3, 1994.

| Emulator | BIOS | Roms folder | Roms extension |
| :--- | :--- | :--- | :--- |
| ​[libretro-pcsx-rearmed](https://github.com/libretro/pcsx_rearmed)​ | SCPH1001.BIN | /recalbox/share/roms/psx | .zip, .iso, .bin & .cue, .bin.ecm, .m3u, .img, .pbp |
| libretro-medanfen |  | /recalbox/share/roms/psx |  |
| libretro-medanfen-hw |  | /recalbox/share/roms/psx |  |

## BIOS <a id="bios"></a>

The file SCPH1001.BIN is not include in original recalbox version. Although the games works without, It is suggested to add this file at your BIOS for improve the performances.

Place **SCPH1001.BIN** file in:

```text
/recalbox/share/bios
```

## Emulator <a id="emulateur"></a>

​[libretro-pcsx-rearmed](https://github.com/libretro/pcsx_rearmed) is a fork based on [pcsx-rearmed](https://github.com/notaz/pcsx_rearmed). This version was created to improve performance, for Pandora handheld, but is also usable on other devices as the Raspberry Pi.

## Multi-disk <a id="multi-disk"></a>

First of all we will see the different possibilities offered by Recalbox to swap disks.

### PSP mode <a id="psp-mode"></a>

Package all the disks in a single file eboot.pbp. You can change disc on the Retroarch menu.

Advantages:

* Controller shortcuts can be used to swap disk.
* There is a save file for all disks.

Disadvantages:

* The .sbi files can not be used in multi-disk games.
* Can not swap to a patched disk \(with LibCrypt protection fix\).
* It takes time to change all multi-disk games to eboot.pbp.



### PCSX-reARMed mode <a id="pcsx-rearmed-mode"></a>

The following disk is searched on the Retroarch menu through file system.

Advantages:

* Your games are in .bin/.cue format.

Disadvantages:

* This does not work currently.
* It's ugly and slow.
* Save files are not shared among the disks.
* Controller shortcuts can't be used to swap disk.

Therefore, games with LibCrypt protection and multi-disk are a pain in this two modes.



### Definitive mode <a id="definitive-mode"></a>

For this mode it is necessary to add the .m3u extension to the PSX part in "/recalbox/share\_init/system/.emulationstation/es\_systems.cfg" \(developers please, add this in the next version, thanks\). For this, you can use a virtual machine with Ubuntu \(for example\) and plug the sd to modify the file. The modified line would look something like this:

`<extension>.m3u .img .IMG .pbp .PBP .bin .BIN .cue .CUE .iso .ISO</extension>`

Once this is done, you only need to create an .m3u file for each multi-disk game. This file will contain the names of the .cue files. For example:![](https://i.imgur.com/Is91Q27.png)m3u

The final aspect would be this:

![psx folder](https://i.imgur.com/QlMnJAm.png)

As you can see, there are .cue/.bin/.sbi per disk and a .m3u per multi-disk game.

Advantages:

* Your games are in .bin/.cue format.
* Controller shortcuts can be used to swap disk.
* The .sbi files can be used.
* There is a save file for all disks.

Disadvantages:

* You have to change es\_systems.cfg file \(only once\).
* You have to hide the .cue files in Recalbox menu.

## Set controller shortcuts for disk swapping <a id="set-controller-shortcuts-for-disk-swapping"></a>

* In game, go to Retroarch menu \(Hotkey+B\).
* Press A to go to Main Menu.
* Go to Settings &gt; Input &gt; Input Hotkey binds.
* Set Disk eject toggle, Disk next and Disk prev with your favorite keys.
* Example: Disk eject toggle \(right-analog up\), Disk next \(right-analog right\) and Disk prev \(right-analog left\).
* Now in game you can press Hotkey+"key" to eject disk, swap disk and insert disk \(and reset game if it's necessary\).

## Multi-track games <a id="multi-track-games"></a>

Some games have several tracks per disk. This means that the .cue file need several entries \(one per track\).

Multi-track .cue example:

![Multi track cue](https://i.imgur.com/beUnV7Q.png)

The final aspect would be this:

![Multi-track game](https://i.imgur.com/CGpKEUb.png)

## FAQ <a id="faq"></a>

### What do I do with .ecm and .ape files? <a id="what-do-i-do-with-ecm-and-ape-files"></a>

You have to unzip them. See this [guide](https://www.epforums.org/showthread.php?57757-ECM-And-APE-Guide).

### How do I enable the Dualshock \(analogs\)? <a id="how-do-i-enable-the-dualshock-analogs"></a>

In game, go to RetroArch menu \(Hotkey+A\) and in Quick menu go to Options. There select _analog_ in **Pad 1 Type** option \(the same for every pad you want\). If Ape Escape \(PAL version\) menu doesn't work, check the .sbi file.

## Glossary <a id="glossary"></a>

* .ape: compressed file for .wav file.
* .bin: game data and music tracks.
* .ccd/.img/.sub: CloneCD files. You have to transform in .cue/.bin \(with IsoBuster for example\).
* .cue: file where the disc tracks are defined. One per data .bin.
* .ecm: compressed file for .bin file.
* .pbp: PSP file for PSX games.
* .ppf: patch file for games with LibCrypt protection.
* .sbi: file that contains the protection information and that are needed to run protected games in emulators. They must have the same name that .cue file.
* .wav: music track file. You have to rename to .bin.

## Interesting links <a id="interesting-links"></a>

* ​[ECM-APE Guide](https://www.epforums.org/showthread.php?57757-ECM-And-APE-Guide)​
* ​[PSX game list](https://psxdatacenter.com/pal_list.html)​
* ​[.sbi files](http://psxdatacenter.com/sbifiles.html)​
* ​[.cue maker](http://nielsbuus.dk/pg/psx_cue_maker/)​

To be continued...

