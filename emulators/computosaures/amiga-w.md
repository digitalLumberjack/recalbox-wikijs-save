---
description: Amiga & CD32 emulation using Amiberry
---

# Amiga \(w\)

![Amiga 500](https://s3-eu-west-1.amazonaws.com/forums.recalbox.com/f7c5336e-ff11-4946-ae58-a5fecf99ecb2.png)

## To All Amiga Fellows

## 

Here is a quick intro to the new Amiga emulator!

Amiberry has been upgraded to v2.25 on Raspberry 2, 3B\(+\) and Odroid XU4.  
This is a big bump, and the new version supports lots of new features!

## Sub-systems

## 

In Recalbox, Amiga machines have been split up in 3 virtual sub-systems:

* **Amiga 600 :** All OCS/ECS machines from A1000 up to the latest A600. 
* **Amiga 1200 :** All AGA machines, starting from the 1200. 
* **Amiga CD32 :** The only true console from the Amiga series.

  The CDTV is not yet supported, although the Recalbox theme and CDTV configurations are ready.  
  It will be added later as a new sub-system, as soon as Amiberry fully supports it.

## Supported "roms"

Here is a list of supported file format per sub-system:

* **Amiga600 & Amiga1200**: 
  * _**ADF**_ disks \(\*.adf\), the most popular disk format \(cannot embedd disk protections\). May be zipped or 7-zipped. 
  * _**IPF**_ disks \(\*.ipf\), mostly used by no-intro dumps \(_can_ embedd disk protections\). May be zipped. 
  * _**WHD**_ \(folders, \*.lha/lzh/lzx, \*.zip\), the well known format for hard-drive games. WHD folders are reconized using the inner \*.slave file, however it is _highly_ recommended to keep them packed in lha or zip format. Unpacked WHD are not faster and even worst they may make EmulationStation slow as hell :\) 
  * _**HDD FS**_, Hard drive on filesystem. Must be folders ending with ".hd" extensions. Rarely used. For true amiga fellows that backuped their Amiga HD. May be zipped, but not recommended. 
  * _**HDF**_ \(\*.hdf\), Hard drive images in a single file. May be zipped \(R/O!\) 
  * _**RP9**_ \(\*.rp9\), Amiga Forever all-in-one packages 
* **Amiga CD32**: _**ISO**_ \(\*.bin, \*.iso, w/ or w/o \*.cue\), CD dumps.


>**Information :**
>
>  
>May be zipped Other CD image formats _may_ be supported but haven't been tested by the recalbox team.
{.is-info}


>**Remarque :**
>
>When running zipped/7-zipped files, our configurator try to identify the rom type by seeking for specific extensions inside the archive.
>
>* ADF/IPF/BIN/ISO are fast to identify. 
>* WHD are fast, but LHA should be prefered. 
>* HDDFS may be longer to check and may lead to some misinterpretations. If you are using HDDFS, let them as regular files & folders and make the root folder name ending with **`.hd`** for fast identification.
{.is-warning}

## Overriding configurations

## 

As you can see, this new Amiberry supports **all** amiga "rom" formats.  
To make things easier for everyone, we have made a huge work to auto-magically configure the emulator regarding what you want to start.  
Recalbox build a default machine configuration per sub-system, however, in some situations you may want to override the auto-generated settings.

Recalbox generates config files in /tmp/amiga/conf.  
The most important is the uaeconfig.uae file, where you will find all keys defining the machine, disk drives, hard drives, etc.  
I cannot describe all keys here. If you're curious I recommend you to take a look at the appropriate Amiberry and UAE documentations.

You have two ways to override settings:

### **By system / Folder:**

Create a file named `/recalbox/share/roms/<amigasystem>/.uaeconfig.uae` \(`/recalbox/share/roms/amiga1200/.uaeconfig.uae` to override Amiga1200\) Set the key you want to override.  
For example, you can make a config file with: `show_leds=false` to disable LED display in the bottom right corner.



### **By game**

Create a file named exactly like your "rom" \(or folder\) but that ends with `.uae`.  
For exemple, in your rom folder, if you have a file named `Aladdin (AGA).ipf`, you may create an `Aladdin (AGA).uae` and override keys in this file.

Recalbox builds the configuration in the following order:

* Build the default config regarding the rom type and the sub-system. 
* Load `/recalbox/share/roms/<amigasystem>/.uaeconfig.uae` if the file exists, and add/overwrite the config keys. 
* Load `<game>.uae` if the file exists, and add/overwrite the config keys.



### In game

As in other emulators: **HoyKey + START** quit the emulator **HoyKey + B** run the Amiberry interface.

## BIOS

The new Recalbox comes with an open-source kickstart replacement, the AROS bios \(2019 version\).  
Our auto-magically configurator use this bios when no other BIOS is available in share/bios folder.  
Several games have been booted & tested successfully using the AROS bios.  
But keep in mind that this is a _**replacement**_.  
It is highly recommended to get the required bios.  
In particular if you want to run WHD games, because the Amiberry's WHDLoader may change bios settings and seek for the best available kickstart.

Here is the list of new required kickstart:

### _**Computers:**_

* **kick33180.A500.rom** \(Kickstart v1.2 rev 33.180 \(1986\)\(Commodore\)\(A500-A1000-A2000\).rom\) 
* **kick34005.A500.rom** \(Kickstart v1.3 rev 34.5 \(1987\)\(Commodore\)\(A500-A1000-A2000-CDTV\).rom\) 
* **kick37175.A500.rom** \(Kickstart v2.04 rev 37.175 \(1991\)\(Commodore\)\(A500+\).rom\) 
* **kick39106.A1200.rom** \(Kickstart v3.0 rev 39.106 \(1992\)\(Commodore\)\(A1200\)\[!\].rom\) 
* **kick40063.A600.rom** \(Kickstart v3.1 rev 40.63 \(1993\)\(Commodore\)\(A500-A600-A2000\) \[!\].rom\)
* **kick40068.A1200.rom** \(Kickstart v3.1 rev 40.68 \(1993\)\(Commodore\)\(A1200\).rom\) 
* **kick40068.A4000.rom** \(Kickstart v3.1 rev 40.68 \(1993\)\(Commodore\)\(A4000\).rom\)



Warning: The Amiga emulator does not work on the PC version, only on the raspberry Pi

To use the amiga emulator you'll need the following BIOS, rename them to the given name and copy the file to `/recalbox/share/bios`. It is critical to use the BIOS with the right MD5, otherwise the emulator might not start

| MD5 | original name | name to use on Recalbox | for system |
| :--- | :--- | :--- | :--- |
| 82a21c1890cae844b3df741f2762d48d | Kickstart v1.3 \(Rev. 34.005\) | kick13.rom | ADF on Amiga 600 |
| dc10d7bdd1b6f450773dfb558477c230 | Kickstart v2.04 \(Rev. 37.175\) | kick20.rom | WHDL on Amiga 600 |
| 646773759326fbac3b2311fd8c8793ee | Kickstart v3.1 \(Rev. 40.68\) | kick31.rom | ADF & WHDL on Amiga 1200 |

## Usage <a id="usage"></a>

### _**CD32:**_

* **kick40060.CD32.rom** \(Kickstart v3.1 rev 40.60 \(1993\)\(Commodore\)\(CD32\).rom\) 
* **kick40060.CD32.ext.rom** \(CD32 Extended-ROM rev 40.60 \(1993\)\(Commodore\)\(CD32\).rom\)





## Usage <a id="usage"></a>

##  <a id="usage"></a>

Amiga emulation comes in two flavors : Amiga 600 and Amiga 1200.  
Some games can be very touchy so try to use the two systems if a game is not working.

Games can be used in either ADF disk format or in WHDLoad format, using in that case a complementary UAE file.

Keyboard and mouse are somehow mandatory as many amiga games need custom key strokes to launch games.

## Special Commands <a id="special-commands"></a>

## 

* Enter GUI : Start or F12 
* Quit emulator : Hotkey or F12 then Q

## ADF games <a id="adf-games"></a>



Copy them to your amiga roms folder.  
Multi disks are automically loaded up to 4 for games using the standard naming "\(Disk 1 of X\)".

## WHD games <a id="whd-games"></a>

##  <a id="whd-games"></a>

WHD games are a little more tricky but it is not too complicated.

### Installation : <a id="installation"></a>

Unzip your WHDLoad game, delete the `.info` file at the same level than the folder, and copy only the folder to your roms folder \(you can use subfolders if you like.  
i.e. `/recalbox/share/roms/amiga1200/ShootEmUp)`



### Usage : <a id="usage-1"></a>

You need an `.uae` file at the same level than the folder with the same name, two solutions :

* Create an empty one. 
* Use a custom one wich will allow you to tweak configuration of the emulator \(see next paragraph\).

**By default I recommend first trying amiga1200 folder for any WHDL game, if some of them are too fast, you can try them in amiga600 folder.**

You can use the following script to massively generate uae files : [UaeGenerator](http://www89.zippyshare.com/v/80w859p5/file.html).

​

### WHDL games tweaking <a id="whdl-games-tweaking"></a>

#### .UAE file tweaking <a id="uae-file-tweaking"></a>

In the uae file, you can define `;hardware`, `;controls` and `;graphics` blocks to replace the standard configuration of the emulator.

**Each custom configuration parts of your .uae file will only be used if it starts with the right block name :** `;hardware`**,** `;controls` **or** `;graphics`

This can allow you to play with two joysticks for instance, use very specific hardware configuration for some games that are a little special, or define a custom resolution.

You can also erase everything in the uae file and default emulator configuration will then be used.

Examples of full custom uae files for both amiga600 and amiga1200 : [Custom UAEs](http://www100.zippyshare.com/v/1ttgYgks/file.html).​

Copy the one \(corresponding to the amiga model you want to use\) next to your WHDL game folder and rename it exactly like your WHDL game folder \(keep the `.uae` extension\).  
 i.e : if your game is a folder name `Rick Dangerous`, your uae file should be named `Rick Dangerous.uae` and be at the same level than the folder.



#### Startup-sequence tweaking \(for experts only\) <a id="startup-sequence-tweaking-for-experts-only"></a>

Standard generated launch sequence for WHDL games is `WHDload game.slave Preload` \(in `WHDL/S/Startup-Sequence`\).

But some few WHDL games \(like History Line : 1914-1918 \) may require additionnal parameters on launch or they simply crash.

You can add a second file \(totally optional\) containing those extra parameters, so you will have if we take History Line as example :

* HistoryLine \(folder of the WHDL game\) 
* HistoryLine.uae \(which can be empty or customized\) 
* HistoryLine.whdl \(optional, containing additional parameters here `CUSTOM1=1`\)

The game will then launch.

Here's a little list of games requiring those extra parameters.

| Game | extra parameter\(s\) / content of the file |
| :--- | :--- |
| HistoryLine 1914-1918 | `CUSTOM1=1` for intro, `CUSTOM1=2` for game |
| The Settlers / Die Siedlers | `CUSTOM1=1` skips intro |



## KNOWN BUGS <a id="known-bugs"></a>

##  <a id="known-bugs"></a>

* In a few cases \(two connected joysticks, ...\) the emulator can fail to detect the correct joystick to use. If this is the case, go into the 'Inputs' menu of the GUI and try to change the joystick in Port1. 
* WHDL games using several slaves can have intros shown after game itself. 
* For some games your keyboard will need to be configured as US in `recalbox.conf` for some games to launch. Remember, if you use an azerty keyboard, quitting the emulator will be done through F12 then A. 
* This solution uses the amiberry emulator, which issues are here : [https://github.com/midwan/amiberry/issues](https://github.com/midwan/amiberry/issues).

