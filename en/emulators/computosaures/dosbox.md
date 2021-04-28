---
title: DOSBox
---

# DOSBox

## What is DOSBox ? <a id="what-is-dosbox"></a>

##  <a id="what-is-dosbox"></a>

**DOSBox** is an emulator which emulates an **IBM PC compatible** computer running a **DOS** operating system. Many IBM PC compatible graphics and sound cards are also emulated.

It allows to run some old PC games on Recalbox.



## Which version of DOSBox is provided by Recalbox ? <a id="which-version-of-dosbox-is-provided-by-recalbox"></a>

##  <a id="which-version-of-dosbox-is-provided-by-recalbox"></a>

Good question: the last official version of DOSBox is 0.74 \(May 2010\). Hopefully, development continues in the SVN version to solve bugs or improve the emulator.

The version embedded in Recalbox is this **SVN version**, with some specific improvements:

* Use SDL2 library to improve graphics performance
* Allow to support hardware joysticks up to 8 axis. Done for mapping purpose \(all axis, hats and buttons are now mappable\).
* Allow to emulate a mouse \(movements + buttons\) from any key or joystick
* Allow to display a virtual keyboard \(for joystick-only systems\)



## How to use the virtual keyboard ? <a id="how-to-use-the-virtual-keyboard"></a>

##  <a id="how-to-use-the-virtual-keyboard"></a>

By default, the virtual keyboard opens with Ctrl-F2. But a new button is now available in the mapper \(Ctrl-F1 &gt; _Virt Keyb_\) to associate it to another event \(keyboard, mouse or joystick\).

Once opened, use the mouse or joystick to select and click on keys:

* Using the left mouse button or the first joystick button simulates a simple press-and-release of the key.
* Using the right mouse button or the second joystick button simulates a press-and-hold of the key \(the key is shown darker\). Click again with any mouse button or joystick to release it.

  This allows to make combination with Shift, Ctrl or Alt keys.

Finally, press the green "checked" button to close the virtual keyboard and send events to DOSBox. It is also possible to press the red "cross" button to cancel events and close the virtual keyboard.

Additional notes: 1. If you use an existing mapping file, the default Ctrl-F2 will not be configured 2. If you exit the virtual keyboard with a key still pressed-and-hold, the key will be constantly sent to DOSBox, until you open the virtual keyboard again ! 3. All configured mappings of joystick or mouse buttons are ignored when you are in the virtual keyboard



## How to emulate DOS games in Recalbox ? <a id="how-to-emulate-dos-games-in-recalbox"></a>

##  <a id="how-to-emulate-dos-games-in-recalbox"></a>

### Basic rundown

Here's a simple example with the game Alley Cat :

* Start by creating a folder for your game named `AlleyCat.pc`. The first part of the folder name before the '.' must have equal or less than 8 characters and avoid special characters.
* Inside it create a dosbox.bat file and edit it to call the executable of the game \(For big games it's better to install them on your computer before copying them to Recalbox\). Here for Alley Cat that gives us :
* ```text
  c: 
  CAT.EXE
  ```
* The C: harddrive is set by DOSBOX to your game folder \(so here C: is equal to the inside of `/recalbox/share/roms/dos/AlleyCat.pc`\). So is '.'
* Reboot or refresh your gamelist to see the game
* To exit the emulator, enter ctrl+F9 with your keyboard



### Advanced rundown

Adding a custom `dosbox.cfg` in your game folder alongside `dosbox.bat` will allow you to specify custom DOSBOX configuration for the game.

Either copy the `dosbox.conf` file from `\recalbox\share\system\configs\dosbox\dosbox.conf` \(warning : extension in the game folder must be cfg not conf\) or use the following one : [https://pastebin.com/13xrJdkw](https://pastebin.com/13xrJdkw)​

Inside this file, the line `mapperfile=mapper.map` will allow you to use a `mapper.map` file to map any control to your gamepad, including mouse ! It can be created from within your game by pressing ctrl+F1 at any time and will then be saved alongside your `dosbox.cfg` and `dosbox.bat` files.

Some parameters from `dosbox.cfg` can also be put instead at the beginning of your `dosbox.bat` if you don't want to use a custom `dosbox.cfg` but some of them won't work there, everything graphics seems to work, but mapperfile doesn't work for instance.



## Converting a game to be used on Recalbox

## 

How to convert a game already using DOSBox, like when bought on GOG or games from the excellent ExoDOS collection.

The first step is to copy the content of the game folder.

Then we need to adapt the content of the dosbox.cfg and the bat file used to launch the game. Let's take an example with WackyWheels

Do not directly copy the `dosbox.cfg` \(or .conf\) from the original folder as this can lead to crashing bugs not easily debugged, copy the standard one linked above and then if you encounter any trouble, just see if the original `dosbox.cfg` had any special configuration and try to use it to your `dosbox.cfg`

\`\`

First move the content of the `[autoexec]` part from the `doxbox.cfg` part to the beginning of your `dosbox.bat` and adapt paths. Here we have originally :

```text
[autoexec] 
cd .. 
cd .. 
mount c .\games\WackyWhe  
imgmount d .\games\WackyWhe\cd\wackywheels.iso -t cdrom 
c: 
cd wackycls
@ww
exit
```



and that will give us in our dosbox.bat on recalbox side :

```text
imgmount d .\cd\wackyw~1.iso -t cdrom
c: 
cd WACKY
pause
WW.EXE
```

###  <a id="explanations"></a>

### Explanations : <a id="explanations"></a>

* C: is already mounted by Recalbox DOSBox, so no need for that
* '.' is also set by Recalbox DOSBox to the game folder, by using relative paths your game won't be linked to a folder \(you can put in a subfolder or in a different distribution\)
* exit is removed because Recalbox DOSBox takes care of that too
* imagmount path is simplified but we have to convert the longer-than-8-chars name of the iso to a standard DOS name \(that is eight characters total with the last two changed to ~1 - ~2 and ~3 etc. if you have several long filenames starting alike\). Anyway maybe it's better to rename the filename in that case.
* Long names are not supported in .cue files either so you may have to rename some .cue/.bin files manually and edit the .cue file to set the correct new name for the bin in it. And it is very strict : no special chars, not even upper case characters
* pause command allow you to pause the screen and easily debug DOS instructions, you can remove it after everything works fine \(don't put it after the main executable call or you'll see nothing\)
* @ww is changed to WW.EXE \(just the executable file of the game\)

That's it ! Some games may use a bat file launcher wich you can adapt too, put its instruction after those of `dosbox.cfg`'s `[autoexec]` if the original game uses both files.



## Troubleshooting <a id="troubleshooting"></a>

## 

**Image isn't in the right ratio :** For older games, you may have to adjust the `aspect=false` parameter to `aspect=true` to get the correct 4/3 ratio. Be aware that on newer games this may lead to performance problems.

**Joystick is moving by itself :** Try modifying `timed=false` to `timed=true`. Can be caused by deadzone too and sadly there is no way to configure deadzone on joystick in DOSBox at the moment.

**D-pad is not usable on xbox360 controller through the mapper :** yeah, it is usable in the mapper, but it doesn't seem to work in-game.

**How an i set my joystick's deadzone :** Sadly it doesn't seem to be possible in standard dosbox at the moment.

**CD Not Found / CD Driver not present :** you likely forgot to rename cd files with non-dos names \(see adv. rundown\).

**I can get mount a or mount d to work :** contrary to imgmount, mount is not able to use 'virtual' path from inside the dosbox machine, so for the mount command to work, you need to only use a real local path from the recalbox file system. Given that '.' is set to the root / directory when DOSBox is launched you have to specify the full absolute path.

**The mapper is bugged, it erases my configuration or mix buttons** You're likely victim of the `buttonwrap` parameter in your dosbox.cfg conf file. When set to true, its wraps buttons with an upper id than the number of joystick buttons emulated, restarting to 0 \(5 will be rewrapped to 0, 6 to 1, etc...\) . Set it to false and everything should be fine.

