---
title: Daphne
---

# Daphne

## What is Daphne ? <a id="what-is-daphne"></a>

**Daphne** is an emulator written by Matt Ownby which lets you play LaserDisc arcade games, like **Dragon's Lair**, **Badlands**, **Cobra Command**, **Space Ace** to mention but a few.

## And what is Hypseus ? <a id="and-what-is-hypseus"></a>

**Hypseus** is the Jeffrey Clark's fork of Daphne which adds some improvements to it:

* Updated MPEG2 decoder
* SDL2 support
* ...

Recalbox chose Hypseus for LaserDisc arcade games emulation.

## What is a LaserDisc game ? <a id="what-is-a-laserdisc-game"></a>

A LaserDisc video game is a game that uses pre-recorded video \(either movie or animation\) played from a LaserDisc, either as the entirety of the graphics, or as part of the graphics. Some games featured live-action videos over which sprites \(cars, space-ships, ...\) were superimposed. But the most popular LaserDisc games were interactive movies or cartoons, in which the player had to press a specific button or move the joystick in the right direction at the right moment to advance to the next scene.

## How do I play LaserDisc Games in Recalbox? <a id="how-do-i-play-laserdisc-games-in-recalbox"></a>

To add a LaserDisc game, you need the two components of the game:

* the image of the original LaserDisc, which contains the video and audio content
* the ROM file, which is the game program

The ROM is a simple ZIP file which must be copied under the sub-directory `daphne/roms`.

The LaserDisc image is composed of multiple files:

* one or more video files \(`*.m2v`\)
* one or more audio files \(`*.ogg`\)
* one or more index files \(`*.dat`\) - can be created by the emulator at the first run \(slow operation\)
* one frame file \(`.txt`\), to associate frame numbers to video files

All these files must be copied under a directory with `.daphne` extension, under the `daphne` directory.

The first line of your txt file is also a path and should be . \(just point character\), modify it if this is not the case

You can also create a file with `.commands` extension to pass some game specific parameters to the emulator. See below for more details.

**The directory, the frame file and the commands file must have the same name than the ROM file !** \(only extensions differ\)

Here is an example of the expected structure for Dragon's Lair:

```text
daphne|- roms|  |- dle21.zip|- dle21.daphne|  |- dle21.txt|  |- dle21.commands|  |- *.m2v|  |- *.ogg|  |- ...
```

### What is the commands file ? <a id="what-is-the-commands-file"></a>

As explained before, this file must be created in the directory of the game, with the same name than the ROM file but with a `.commands` extension. It allows you to pass additional parameters to the emulator for a specific game. Most of the time, it is filled with the `-bank` option, which defines settings of the game \(also known as DIP switch\):

* number of credit for a game
* number of lives for one credit
* difficulty level
* ...

Recommended values for popular games are described below, but you can consult the site [LaserDisc Game Tech Center](http://www.dragons-lair-project.com/tech/%3E) for complete information. **Please also note that, for a same game, the DIP switch can vary from a ROM version to another.**

Other parameters are also possible. Check [Daphne Wiki](http://www.daphne-emu.com/mediawiki/index.php/CmdLine%3E) for more details.

Example for Dragon's Lair \(DLE 2.x\): `-bank 1 00110111 -bank 0 10011000` using this page [http://www.dragons-lair-project.com/tech/dips/dle20.asp](http://www.dragons-lair-project.com/tech/dips/dle20.asp), indicates:

* sound is always on, with narrator voice \(even when not playing\)
* 1 coin = 1 credit
* 1 credit = 5 lives
* no test or diagnostics
* game mode = standard

## Joystick buttons <a id="joystick-buttons"></a>

Only one joystick is supported, player 1 only.

Use the left stick to move and standard buttons for actions. For most games, only the **B** button is used \(A for Xbox controllers, X for Playstation\). Add a coin with **select/back** button and start the game with **start** button. To quit the emulator, press the **hotkey** button. If hotkey is mapped to an already used button \(select, for instance\), the **pagedown** button is used instead to quit.

## Where can I find games ? <a id="where-can-i-find-games"></a>

Some games can be directly and legally downloaded by the **DaphneLoader** tool of the [Daphne's Windows distribution](http://www.daphne-emu.com/site3/index_hi.php%3E). For some others \(Dragon's Lair, Dragon's Lair II, Space Ace, ...\), you have to prove that you have a valid license of the game \(DVD version for instance\).

Once downloaded, simply copy needed files \(ROM and LaserDisc image files\) to your Recalbox as explained above.

## Supported games and recommended configuration <a id="supported-games-and-recommended-configuration"></a>

For each game, the following table describes:

* the level of compatibility with the emulator
* the ROM recommended to use for best experience
* the recommended content of the commands file: for normal difficulty, 5 lives, minimum credit, ...

| Game name | Compatibility | Recommended ROM | Recommended commands |
| :--- | :--- | :--- | :--- |
| Astron Belt | \*\* | astron.zip | `-bank 0 00000000 -bank 1 01000000` |
| Badlands | _\*_ | badlands.zip | `-bank 0 00000000 -bank 1 10000010` |
| Bega's Battle | **\*** | bega.zip | `-bank 0 00000000 -bank 1 00000001` |
| Cobra Command | _\*\*_ | cobraconv.zip | `-bank 0 11010000 -bank 1 00010001` |
| Dragon's Lair | **\*** | dle21.zip | `-bank 1 00110111 -bank 0 10011000` |
| Dragon's Lair II | _\*\*_ | lair2.zip | ​ |
| Esh's Aurunmilla | _\*\*_ | esh.zip | ​ |
| Galaxy Ranger | **\*** | galaxy.zip | `-bank 0 00000000 -bank 1 00000000` |
| GP World | \* | gpworld.zip | ​ |
| Interstellar Laser Fantasy | **\*** | interstellar.zip | `-bank 0 00100001 -bank 1 00000000` |
| M.A.C.H. 3 | **\*** | mach3.zip | `-bank 0 01000100` |
| Road Blaster | **\*** | roadblaster.zip | ​ |
| Space Ace | _\*\*_ | sae.zip | `-bank 1 01100111 -bank 0 10011000` |
| Super Don Quix-Ote | **\*** | sdq.zip | `-bank 0 00100001 -bank 1 00000000` |
| Us Vs Them | **\*** | uvt.zip | `-bank 0 00000000` |
| Other games | not tested | ​ | ​ |

Feel free to complete or update this list !

