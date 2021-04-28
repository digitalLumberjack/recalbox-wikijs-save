---
title: Display of systems
description: Customisation of the display of the systems. (Recalbox v6.1 and higher)
---

# Display of systems

## **D**isplay operation

The display of systems in the Recalbox menu is managed by the file "es\_systems.cfg". This file is located in the folder:


>./recalbox/**share\_init**/system/.emulationstation/es\_systems.cfg
{.is-info}

It contains the names of the different systems that are supported by your version of Recalbox. It is constructed as follows:

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Panasonic 3DO</fullname>
    <name>3do</name>
    <path>/recalbox/share/roms/3do</path>
    <extension>.iso .ISO .cue .CUE .chd .CHD</extension>
    <command>python /usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc %CONTROLLERSCONFIG% -system %SYSTEM% -rom %ROM% -emulator %EMULATOR% -core %CORE% -ratio %RATIO% %NETPLAY%</command>
    <platform>3do</platform>
    <theme>3do</theme>
    <emulators>
      <emulator name="libretro">
        <cores>
          <core>4do</core>
        </cores>
      </emulator>
    </emulators>
  </system>
  <system>
      [. . .]
  </system>
  [. . .]
</systemList>
```

The display of the systems respects the order in which they are listed in this file. It also contains the configuration of these systems.

## Change the display order


>**WARNING** :   
>**DO NOT MODIFY** the original "es\_systems.cfg" file \(which is in the "share\_init" directory\). If a future change caused the slightest problem, there remains the only source to recover your Recalbox and make it work properly again.
{.is-danger}

Should you modify the display order, it **MUST BE DONE ONLY**    
via the file "es\_systems.cfg" present in the following directory:


>./recalbox/**share**/system/.emulationstation/es\_systems.cfg
{.is-info}

**By default**, this file does not exist. Either copy the original file or create a new file. Once the new file is created, it is possible to organize the systems in the order you want. The system configuration will always be taken from the original "es\_systems.cfg", but the order of the systems will be that defined by the new file. 

If, in the new file, a system is absent or incorrectly specified, priority is given to the original file. For the new file, there are only 2 entry keys that are required: "fullname" and "platform", all the others are optional. The file must be constructed as follows:

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Nintendo Entertainment System</fullname>
    <platform>nes</platform>
  </system>
  <system>
    <fullname>Family Computer Disk System</fullname>
    <platform>fds</platform>
  </system>
  <system>
    <fullname>Super Nintendo Entertainment System</fullname>
    <platform>snes</platform>
  </system>
  <system>
    <fullname>Satellaview</fullname>
    <platform>satellaview</platform>
  </system> 
    [. . .]
  </system>
  [. . .]
</systemList>
```

## Add a "Custom" system


>**WARNING:**   
>**DO NOT MODIFY** the original "es\_systems.cfg" file \(which is in the "share\_init" directory\). If a future change caused the slightest problem, there remains the only source to recover your Recalbox and make it work properly again.
>
>This manipulation does not add a new emulator to Recalbox but adds a new system entry in the selection menu. 
>
>It is possible to combine the modification of the display of the systems and the addition of one or more custom systems.
{.is-danger}

As for the modification of the order of the systems, the addition of a "custom" system **must be done only** from the file "es\_systems.cfg" present in the following directory:


>./recalbox/**share**/system/.emulationstation/es\_systems.cfg
{.is-info}

**By default**, this file does not exist. Either copy the original file or create a new file. Once the new file is created, it is possible to organize the systems in the order you want. 

If a system is incorrectly entered in the new file, priority is given to the original file. For the new file, all entry keys are required. In order to create a new system, the simplest is to start from an existing system \(and corresponding to the roms that we want to include\) and modify only what is necessary:

* **"fullname":** Used to name the new system.
* **"path":** Used to indicate the directory containing the roms of the new system.
* **"theme":** Used to indicate which theme to use. You must first create this new theme \(logo, background, ...\)

**All other entries must not be changed.**

Here is an example of addition for a SNES-based system to include only translated roms:

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Super Nintendo Fan Trad</fullname>
    <name>snes</name>
    <path>/recalbox/share/roms/snestrad</path>
    <extension>.smc .sfc .SMC .SFC .mgd .MGD .zip .ZIP .7z .7Z</extension>
    <command>python /usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc %CONTROLLERSCONFIG% -system %SYSTEM% -rom %ROM% -emulator %EMULATOR% -core %CORE% -ratio %RATIO% %NETPLAY%</command>
    <platform>snes</platform>
    <theme>snestrad</theme>
    <emulators>
      <emulator name="libretro">
        <cores>
          <core>snes9x2005</core>
          <core>snes9x2010</core>
          <core>snes9x2002</core>
        </cores>
      </emulator>
    </emulators>
  </system>
</systemList>
```

