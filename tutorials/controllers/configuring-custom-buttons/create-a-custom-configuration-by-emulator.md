# Create a custom configuration by emulator

You have the possibility to create your own custom configuration for each emulator on Recalbox.

## I - Retroarch <a id="i-retroarch"></a>

**RetroArch configuration** can be created by hand by **basing your own configuration on the** [retroarch.cfg](/basic-manual/getting-started/the-recalbox.conf-file) standard or **by editing it in the RetroArch menu**. You will then need **to create a new configuration and configure** the new **recalbox.conf** config file so that it is loaded by your emulator

Let's start with the example of **creating a specific config** file for the **neogeo.**

* **Launch an game** from emulator that you want to customize \(neogeo inthis c\)
* **Enter** the Retroarch menu \(**hotkey + b**\)
* **Modify** all the configurations as you wish
* **Go back to the first** RetroArch menu entry, then do **`Save new config`** \(the name of the config file **should look like fba\_libretro.cfg**, with the name of the core you are using\)
* In[ root access,](https://recalbox.gitbook.io/tutorials/access/root-access-via-terminal) **change the name of the config** file to something easier to remember.  
  **Example:** 

  `mv /recalbox/share/system/configs/retroarch/fba_libretro.cfg /recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`

* **Add the following line** to **recalbox.conf:** `neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`

### ​​Inputs​_**​**_

### Manual editing

Since version 4.1 of Recalbox, you can add configuration files specific to the system and / or the game. There is of course a priority if the same parameter appears in each configuration file. So **game&gt; system&gt; Retroarch**, which means that an existing setting in a game .cfg file will be the one used on a system or Retroarch's file by default.

Here are the files you can edit \(or create if they don't exist\):

* `~/configs/retroarch/.cfg` where is the name of the system as it appears in the folder. For example: `~/configs/retroarch/snes.cfg`
*  `~/configs/retroarch//.cfg` where is the name of the system as it appears in the roms folder, and is the exact name of the rom with the file extension. For example: `~/configs/retroarch/snes/mario.zip.cfg`

## II - piFBA <a id="ii-pifba"></a>

