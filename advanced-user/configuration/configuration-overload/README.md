---
description: >-
  Here you will find a description of the local configuration overloads applied
  to specific games or to complete directories.
---

# Configuration overload


>**Recalbox 7.0 and higher!**
>
{.is-warning}

## Possibilities overview <a id="apercu-des-possibilites"></a>

Starting from Recalbox 7.0, you can overload the configuration of a game or an entire directory.

That means that by adding certain files in your ROMs directories, you will be able to modify the way Recalbox, Retroarch or the emulator behaves for a given game, or all the games in that directory.

Basically, you'll be able to modify:

* The Recalbox's configuration
* The Retroarch's general configuration
* The Retroarch's cores configuration

​You will also have the possibility of overloading the images and descriptions of the rom directories as they are displayed in EmulationStation, we will see why just a tad later.

We'll be able to, for a game or a group of games: 

* Define a particular emulator or core
* Define a particular video resolution
* Modify Retroarch's video configuration
* Modify core options
* etc

## Basics <a id="generalites"></a>

The overloads are going to apply on a base file. Those files are the files loaded first in the python launcher \(called **configgen**\) when we launch a game:

| Target | Configuration file |
| :--- | :--- |
| **Recalbox** | `/recalbox/share/system/recalbox.conf` |
| **Retroarch** | `/recalbox/share/system/configs/retroarch/retroarchcustom.cfg.origin` |
| **Cores** | `/recalbox/share/system/configs/retroarch/cores/retroarch-core-options.cfg` |

All the config files that we can overload are of type key/value. We'll then be able to modify the value of a key from the base file, or define a non-existent key.

We will even be able to overload overloads ! Indeed, the system allows you to define an overload per directory level. 

So it starts by loading the basic configuration, then apply successively all the overload files it will find in the directories, starting at the root and finishing with the game overload, if it exists.

​

Let's take an example, if we launch the game `/recalbox/share/roms/snes/platform/Aladdin (France).zip`, **configgen** will try to overload the retroarch configuration, loading in order:

1. `Base: /recalbox/share/system/configs/retroarch/retroarchcustom.cfg`
2. `Path: /.retroarch.cfg`
3. `Path: /recalbox/.retroarch.cfg`
4. `Path: /recalbox/share/.retroarch.cfg`
5. `Path: /recalbox/share/roms/.retroarch.cfg`
6. `Path: /recalbox/share/roms/snes/.retroarch.cfg`
7. `Path: /recalbox/share/roms/snes/platform/.retroarch.cfg`
8. `File: /recalbox/share/roms/snes/platform/Aladdin (France).zip.retroarch.cfg`

Of course, it's not really advisable to overload the configuration before reaching at least the directory of a system.

You will notice that to overload a directory, the overload files must be found **inside** the directory, starting with a dot \(.\), which makes them invisible to the linux system. 

Conversely, the overload of a game must be named exactly like the game, **including the file extension**, followed by the overload suffix, `.retroarch.cfg` in the example above.


>Since the overload files are inside your roms directories, they don't risk a Recalbox crash, an update that went wrong, or a crash of your SD-card \(provided you use external support of course\).
>
>They are also portable : Take your USB-drive with you to play at a friend's house, your configuration will apply automaticaly !
>
{.is-info}

## Overloading Recalbox <a id="surcharger-recalbox"></a>

Overloading the Recalbox configuration has two immediate benefits :

* Be able to select a particular video mode for a game or set of games. Aficionados of the _arcade pixel perfect_ will be delighted.
* Be able to choose a core or a standalone emulator for a game or a set of games.

There are other possibilities and no doubt you will find some.😉


>Overloading keys that aren't used by the **configgen** has no impact ! Don't expect to change the behavior of EmulationStation \(overloading the sorts for example\).
>
{.is-danger}


>**Reminder :**
>
>Directory overload : **`/path/to/your/roms/.recalbox.conf`**
>
>Rom overload : **`/path/to/your/roms/file.zip.recalbox.conf`**
>
{.is-warning}



### Example 1: Multiple versions of MAME <a id="exemple-1-multiple-versions-de-mame"></a>

Why settle for just one version of MAME when we could have them all ?

For example, you could have MAME 2003 Plus and MAME 2010, each romset in its own directory :

 `/recalbox/share/roms/mame/   
├── MAME2003Plus   
└── MAME2010`

​

Simply add the file :

```text
/recalbox/share/roms/mame/MAME2003Plus/.recalbox.conf
mame.emulator=libretro
mame.core=mame2003_plus
```

​And the file :

```text
/recalbox/share/roms/mame/MAME2010/.recalbox.conf
mame.emulator=libretro
mame.core=mame2010
```


>And there it's ! That's all. 
>
>Now, all the games in the MAME2003Plus directory will launch with the mame2003\_plus-libretro core, and those in the MAME2010 directory will launch with the mame2010-libretro core !
>
{.is-success}



### Example 2: Affect a particular core to a game <a id="exemple-2-affecter-un-core-particulier-a-un-jeu"></a>

Let's say for the sake of our example that my game `/recalbox/share/pcengine/1943 Kai (Japan).zip` works better with the core `mednafen_pce_fast_libretro` than with the default one `mednafen_supergrafx_libretro` .

Until now, it was possible to do it via EmulationStation, by editing the game's metadata. The information is then stored in the `gamelist.xml` file. But with one error in writing the file, an unfortunate scrap and it's all the configuration that is lost.

Here, simply add the file :

```text
/recalbox/share/roms/pcengine/1943Kai(Japan).zip.recalbox.conf
global.emulator=libretro
global.core=mednafen_pce_fast
```


>This time, there's no risk of losing configuration ! Of course, editing metadata via EmulationStation still works. On the other hand, an overload file will have higher priority than what is stored in the `gamelist.xml`.
>
{.is-success}



### Example 3: Modify the video mode for a game <a id="exemple-3-modifier-le-mode-video-pour-un-jeu"></a>

Once again let's take an example !  
  
On my Raspberry Pi2, the default video mode is CEA 4 HDMI.  
But on the **`Blazing Stars`** game on **FinalBurn Neo**, it runs a bit slowly. Turning it to 240p would certainly help, in addition to being pixel-perfect.

```text
/recalbox/share/roms/fba_libretro/blazstar.zip.recalbox.conf
global.videomode=CEA 8 HDMI
```


>And voila ! Next time I launch this particular game, my TV will to adjust to 240p, and I can now fully enjoy Blazing Stars.
>
{.is-success}

## Overloading Retroarch <a id="surcharger-retroarch"></a>

The Retroarch configurations concern Retroarch itself \(and the configuration options are very large !\) as well as the different cores, which each have specific options depending on the hardware they emulate.


>There are already specific mechanisms in Recalbox and Retroarch to overload either the command line that launches the emulator \(via Recalbox.conf\), or directly the Retroarch/Cores configurations \(via Retroarch menus\).
>
{.is-info}


>But none of these systems allowed to apply the overloads to entire directories and/or to keep these specific configurations in the same place as the roms. Which is especially interesting for people who use network shares to supply roms to several Recalboxes 
>
{.is-warning}



### Retroarch's configuration <a id="configuration-de-retroarch"></a>

The Retroarch configuration itself is extremely rich and covers a lot of different fields.

There's no need to expand more on this, if you have any question simply go directly to the RetroArch file, which is particularly well documented : [https://github.com/libretro/RetroArch/blob/master/retroarch.cfg](https://github.com/libretro/RetroArch/blob/master/retroarch.cfg)​

The possibilities offered by local overloads are huge ; among them are :

* Video setup : Ratio, Scale, Anti-aliasing, screen rotation or even shader selections, etc.
* Audio tuning for some tricky games
* Overlays
* Some options concerning the inputs : mouse selection, sensitivity, etc.
* Forcing specific NetPlay configurations
* Change Retroarch directories \(e.g. backup\)
* Setup various options : Rewind, Fast Forward, etc.
* ...

Like the Recalbox configuration overloads, we will be able to create `.retroarch.cfg` files for directories and for roms.


>**Reminder :**
>
>Directory overload : **`/path/to/your/roms/.retroarch.cfg`**
>
>Rom overload : **`/path/to/your/roms/file.zip.retroarch.cfg`**
>
{.is-info}

#### Example 1 ****: Force a video configuration <a id="exemple-1-forcer-une-configuration-video"></a>

#### Exemple 2 : Force a shader for an entire directory <a id="exemple-2-forcer-une-shader-pour-un-repertoire-complet"></a>

​

### Cores configuration <a id="configuration-des-cores"></a>

Overloading the cores options offers huge possibilities, _**among which a feature highly expected by fans of "outdated computers" : the ability to specify a directory per sub-system !**_


>Overloads of cores are added to the file _share/system/configs/retroarch/cores/retroarch-core-options.cfg_ at the launch of the concerned game, which means that once the game is closed, **they will be saved in this same file.**
>
>In order to avoid unpleasant surprises, we recommend overloading the keys in the folder with default values \(e.g. `fbneo-frameskip = "0"`\) if you want to overload a particular game with specific values \(e.g. `fbneo-frameskip = "2"`\).
>
>This way, you will keep your "base" values for files that don't have custom overloads.
>
{.is-danger}

It's especially interesting for multi-hardware cores, such as :

* **theodore**, which includes Thomson MO6, and TO8 up to TO9+.
* **atari800**, which includes all the Atari 8bits, from the first 800 series, to the XE, through the XL, up to the XE.
* **vice**, which now emulates C64, PET, Vic20, CBM2, ...
* **hatari**, which emulates from the first 520ST to the last Falcons...
* and many more...


>**Reminder :**
>
>Directory overload : **`/path/to/your/roms/.core.cfg`**
>
>Rom overload : **`/path/to/your/roms/file.zip.core.cfg`**
>
{.is-info}

​

#### Example 1:  Thomson sub-systems <a id="exemple-1-configurer-des-sous-systemes-thomson"></a>

The Thomsons, French 8bits computers of the 80s, have split into 2 series:

* The MOs, which gave the first MO5, then later the MO6 with its mechanical keyboard and integrated tape player,
* The TO, which gave the first TO7 and TO7-70, then later the TO8 and TO8D, with floppy disk drives, and the TO9 and TO9+ series, more professional-looking computers.

MO and TO games aren't compatible at all. Within the same series, there is upward compatibility : a MO6 will run the games of the MO5. 

Of course, we will try to emulate each game with the hardware closest to the original machine it was designed for, in order to avoid any problems and maximize the chances of having a perfect emulation.

If we take the TOSEC packs \([http://www.tosec.org](http://www.tosec.org)\), the Thomson games have been divided into 4 subsystems :

* MO5
* MO6
* TO7 \(TO7-70\)
* TO8, TO8D, TO9 et TO9+

​

We will therefore create a similar tree structure :

`recalbox/share/roms/thomson/  
├── MO5   
├── MO6   
├── TO7   
└── TO8,TO8D,TO9,TO9+`



In the root of the system, we will place a core overload file, to force some very cool options for everyone :

{% code title="/recalbox/share/roms/thomson/.core.cfg" %}
```text
theodore_rom = "Auto"
theodore_autorun = "enabled"
theodore_floppy_write_protect = "enabled"
theodore_tape_write_protect = "enabled"
```
{% endcode %}

If we add games in the root or in another directory, we indicate to the emulator to try to detect the best hardware. 

We also protect the default roms files by default and we start the autorun mechanism which is very useful when we don't know the original hardware very well.

Then in each sub-directory, we will add an overload on the `theodore_rom` key which determines the hardware.

{% code title="/recalbox/share/roms/thomson/MO5/.core.cfg" %}
```text
theodore_rom = "MO5"
```
{% endcode %}

{% code title="/recalbox/share/thomson/MO6/.core.cfg" %}
```text
theodore_rom = "MO6"
```
{% endcode %}

{% code title="/recalbox/share/thomson/TO7/.core.cfg" %}
```text
theodore_rom = "TO8"
```
{% endcode %}

{% code title="/recalbox/share/thomson/TO8,TO8D,TO9,TO9+.core.cfg" %}
```text
theodore_rom = "TO9+"
```
{% endcode %}

For the TO7 series, the closest hardware has been selected : the TO8.  
For the last series \(fully compatible\), the most powerful hardware has been selected : the TO9+.


>That's all ! You now have four Thomson subsystems. The emulator is no longer in automatic mode and the risk of choosing the wrong system or a default system vanishes.
>
>Of course, the Theodore core can sometimes "auto-detect" the hardware, but this isn't the case with some other cores that need to have the right subsystem at launch.
>
{.is-success}

## Overloading display of directories <a id="surcharger-laspect-des-repertoires"></a>

To improve the possibilities offered by the subsystem settings, for instance by overloading the Recalbox configuration for **MAME** or overloading the **Theodore** core to fully take advantage of the TO and MO hardware of that time, we have added the possibility to overload the image and description of a directory.

This allows for example, to have on a directory, the picture and the description of the hardware whose roms are in the directory.

To do this, we just need to add at least one image file in **PNG** format and named `.folder.picture.png` in the directory whose image we want to overload in EmulationStation. 

The resolution doesn't matter, but keep in mind that a resolution similar or close to your _scrap_ images is still recommended.

You may add an optional text description that will slide underneath the image, just like for _scraped_ games. The file must be a simple text file, named `.folder.description.txt`


>**Reminder :**
>
>Directory overload : **`/path/to/your/folder/.folder.picture.png`**
>
>Rom overload : **`/path/to/your/roms/.folder.description.txt`**
>
{.is-info}



### Example 1: from MO5 to TO9 <a id="exemple-1-du-mo5-au-to9"></a>

Let's go back to the **thomson** directory used earlier, which we had divided into 4 sub-systems as **TOSEC** did.

`/recalbox/share/roms/thomson/  
 ├── .core.cfg  
 ├── gamelist.xml  
 ├── media  
 │ ├── box3d  
 │ ├── images  
 │ └── videos  
 ├── MO5  
 │ ├── .core.cfg  
 │ ├── .folder.description.txt  
 │ ├── .folder.picture.png  
 │ ├── [FD]  
 │ ├── [K7]  
 │ ├── [M5]  
 │ ├── [QD]  
 │ ├── [SAP]  
 │ └── [WAV]  
 ├── MO6  
 │ ├── .core.cfg  
 │ ├── .folder.picture.png  
 │ ├── .folder.description.txt  
 │ └── [K7]  
 ├── TO7  
 │ ├── .core.cfg  
 │ ├── .folder.picture.png  
 │ ├── .folder.description.txt  
 │ ├── [K7]  
 │ └── [M7]  
 └── TO8, TO8D, TO9, TO9+  
   ├── .core.cfg  
   ├── .folder.picture.png  
   ├── .folder.description.txt  
   ├── [FD]  
   ├── [K7]  
   ├── [QD]  
   └── [SAP]`

​

The `.folder.picture.png` file in the **/recalbox/share/roms/thomson** directory contains an image of the hardware :

![MO5 Photo](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-Lo9zc7UGOw_EPL05mCC%2F-LoA3eJn4UNDXo7oJhJe%2F.folder.picture.png?alt=media&token=2366e182-a0a8-4cf1-a7f0-b1076bfdb8d1)

​

And the file `.folder.description.txt` contains :

{% code title="/recalbox/share/roms/thomson/MO5/.folder.description.txt" %}
```text
Brand:
    - Thomson (France)
CPU:
    - Motorola 6809E running at 1 MHz
RAM:
    - 48Kb (extensible)
ROM:
    - 16Kb
Graphics:
    - Text mode : 40 columns x 25 lines
    - Graphic mode: 320 x 200, 16 colors (proximity constraint)
Sound:
    - 1bit generator (6bit DAC module extention possible)
Input devices:
    - 57 keys integrated keyboard
    - Optical pen
    - Joysticks
Interfaces:
    - External power supply
    - DIN Connector (optical pen)
    - DIN Connector (tape drive)
    - Peritel (RGB)
    - Extension port
Software:
    - BASIC 1.0 Integrated
Standard devices:
    - Cartridge port (Mémo5)
    - External tape drive (MO5 specific model)
    - External disk drive
Dimensions:
    - 51 x 291 x 190 mm 
Weight:
    - 1.1 kg
Released:
    - 1984
    
```
{% endcode %}

​And here's how it looks in EmulationStation :

![EmulationStation](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-Lo9zc7UGOw_EPL05mCC%2F-LoA8iKMCZj3QWLA2UNk%2FCapture%20du%202019-09-07%2011-52-59.png?alt=media&token=bcc9014a-8699-4fa2-9aa0-0f46aaa4bc6b)

​

### Example 2 : MAME <a id="exemple-2-mame"></a>

In the same way, let's go back to our first example that shows how to get multiple versions of **MAME** in the MAME directory, we could imagine having nice MAME 2003 Plus and MAME 2010 logos, followed by a short text giving the amount of games, and the version of the corresponding MAME RomSet.

​

A little logo :

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-LoA8tUjoraIL5G-TUFl%2F-LoABzgL-dUQHM3ibkku%2F.folder.picture.png?alt=media&token=9627787d-fc60-4418-a61b-57c4a20fb7f7)



**/recalbox/share/roms/mame/MAME2003Plus/.folder.description.txt**

​

A little text :

```text
/recalbox/share/roms/mame/MAME2003Plus/.folder.description.txt

MAME 2003 Plus is an improved version of MAME 2003, with a whole lot of bug fixes and hundreds of new games.​

Special RomSet based on the MAME 0.78 RomSet

​4859 games total!
```



And there's the result :

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-LoA8tUjoraIL5G-TUFl%2F-LoAECkWbLykI_YkSAYZ%2FSans%20titre.png?alt=media&token=6f61b085-6921-465e-801e-04913b229a86)

## Standalone emulators <a id="emulateurs-standalone"></a>

We can't currently overload the configuration of standalone emulators except for Amiberry's and Amiga for ARM's, partially.

Adding these overloads isn't on the calendar, since they require code and specific tests. This more or less isn't doable for every emulator, but in any case, this will require a rather substantial amount of work time.

However, depending on the demand and its relevancy, we could eventually work on a per-case basis.

