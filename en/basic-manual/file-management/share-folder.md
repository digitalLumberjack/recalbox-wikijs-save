---
title: Share folder
---

# Share folder




>The **Share** folder allows you to **manage** the content of your Recalbox, it is available **via the network** by connecting to your recalbox using a **file manager,**  
{.is-info}


>On an **external storage** the folder is named **"Recalbox".**
{.is-warning}

![](/migration-images/basic-manual/file-management/image%20%2822%29.png)

There you can **manage** most files and subfolders intended for a average user, it contains the following folders:

* **Bios**

![](/migration-images/basic-manual/file-management/image%20%2838%29.png)

The bios folder has to contain the BIOSes files used by Recalbox consoles emulators, please note that **some** emulator **do not** require any BIOS to work.


>Arcade and neogeo emulators **need their BIOS to be put in the same folder as the games requiring them,** and so should not be put in the bios folder.
{.is-warning}

* **Cheats** Cheats downloadable via the Retroarch menu.



* **Extractions** This is where your zipped roms will unzipp before launching the game.



* **Kodi** Place the **media** you want to play with Kodi here in the corresponding sub-directories. 
  * music
  * movie
  * picture



* **Lost+Found** When a disk crashes we use the fsck program to repair \(equivalent to scandisk\); this is where he deposits the fragments of lost files.



* **Music** Place your files here to replace the default background music in emulationstation.


>**Notes**  
>The files **must be** in **:**
>
>* Mp3 or ogg formats
>* Have a sampling rate of 44100Hz 
>* A bit rate higher than 256 kb / s.
{.is-warning}



* **Overlays** Place your overlays here to customise the outline of your screen when a game is launched.



* **Roms** Place your roms here in the sub-directories corresponding.  The roms folder contains multiple subfolders, one for each supported system, each of them contains a readme.txt file describing the supported game format for each system.  The games are meant to be inside those, you also have gamelist.xml files, and potential media subfolders.   The gamelist.xml contains informations for each game, in a way EmulationStation can understand, and the media subfolders contains images or videos to be displayed along the games in the game select screen.


>If a specific system folder is not present in your roms folder \(for exemple: dreamcast\), that means that **it isn't supported** for your architecture, **creating the folder won't make a difference.**
{.is-danger}

\*\*\*\*

* **Saves** Directory where your game saves are stored.


>The saves folder will fill itself as you play your games, it will contain subfolders \(one for each system\), with each of them having savestates files as well as original saves for each game involved.
{.is-info}



* **screenshots** Directory where your game screenshots are stored



* **System** Recalbox configuration and system directory.



* **Themes** Place your themes here for the EmulationStation interface of your Recalbox.

## Game related folders

The folowing folders are related to the games, and should be backup frequently to prevent any loss, it is also wise to back them up before updating just in case.

* bios
* roms
* saves

## EmulationStation customisation folders

The music and themes folder can be used to customise your EmulationStation.

By putting musics in a ogg vorbis format inside the music folder, EmulationStation will use those musics instead of the default ones.

You can also put custom themes inside EmulationStation and enable them using the system menu.



