---
title: Glossary
description: Lists of terms related to Recalbox
---

# Glossary

This section defines some technical terms related to Recalbox, if you're looking for a word you don't understand, this place should be the first stop.

## A

* **Arcade** : Arcade are mostly coin-operated video game systems being emulated. While consoles have a set hardware for a large library of games, which implies a single emulator can mimic said hardware without too much hassle, arcade systems are emulated using programs able to mimic different hardwares depending on the game, thus, it is strongly recommended to understand why throwing random files won't work. Also, in the context of Recalbox, Neogeo games are emulated with the same logic as arcade games.

## B

* **BIOS** : Files representing programs ran by the original hardware, required for some emulators.

## C

* **Changelog** : text file which contains the changes for each versions of a given software, see the [changelog](https://gitlab.com/recalbox/recalbox/raw/master/CHANGELOG.md) and [release-notes](https://gitlab.com/recalbox/recalbox/raw/master/RELEASE-NOTES.md) of recalbox.
* **Cheats** : In the context of Recalbox, cheats are a feature that reproduce the behavior of some "cheating devices", letting you toggle on and off pre-entered codes that affect how the game will react.
* **Checksum** : a simple string of information calculated from a file, if two files with the same size have the same checksums, they are very likely to be identical files, mostly referenced for netplay or BIOSes.
* **Core** : A specific program being loaded by Retroarch \(in most cases, an emulator\).
* **CRC** : a type of checksum used for netplay.
* **Cue** _\(or .cue\)_ : Files describing how raw datas are being laid out on a disc, mostly used for disc based systems along with bin files.

## D

* **Dat** _\(or .dat\)_ ****: Files used to check roms in batch to determine if they belong to a specific set, mostly referenced for Arcade emulation and Netplay. 
* **Demo mode** : A Recalbox feature, enabling EmulationStation to launch games at random when unused for a set amount of time.
* **DragonBlaze** : Name of the version 6.0 of Recalbox.

## E

* **EmulationStation** _\(or ES\)_ ****: The front-end \(aka. interface to access and manage games\) used in Recalbox.
* **Emulator** : Program mimicking the behavior of an actual hardware. 

## G

* **Gamelist** _\(or gamelist.xml\)_ : File specific to each system, listing informations for each game.
* **GPIO** _\(or General Purpose Input/Output\)_ : Pins accesible on a Raspberry Pi, which can be used for multiple purposes \(Mostly to attach buttons for Bartops and the likes for Recalbox\).

## H

* **Hash** : Calculates the checksum of the rom files for the netplay.
* **Hotkey** : Button used to perform button combinations triggering command shortcuts for the emulator, see [the hotkey commands](getting-started/#b-special-commands).

## I

* **Iso** _\(or .iso\)_ : Image files corresponding to physical discs.
* **Issue** : An issue \(as in Gitlab issue\) represents either a bug report or a feature request, you can read the status of issues or post one at this link \(keep in mind that a bug report will need a proper description to reproduce it\) : [https://gitlab.com/recalbox/recalbox/issues](https://gitlab.com/recalbox/recalbox/issues)

## K

* **KODI** : Media player embedded inside Recalbox.

## L

* **Libretro** : Cross-platform application API powering Retroarch.
* **License** : A license defines what can be done or not with a software or product, you can read Recalbox's license [here](https://gitlab.com/recalbox/recalbox/blob/master/LICENSE.md), keep in mind that Recalbox is distributed with other products which come with their own licenses too.
* **Link-Cable** : A cable used to link two handhelds together to achieve a multiplayer experience on supported games, some emulators can mimic this behavior.

## M

* **MD5** : a type of checksum, used for BIOSes.
* **MITM** _\(or Man In The Middle\)_ : Setting used for the netplay, using a remote server to synchronize games rather than a direct connection, at the cost of reliability and speed.
* **Multitap** : Add-on letting a system use more controller than originally intended for supported games, enabling 4-players games on systems with only two controller ports originally, some emulators can mimic this feature.

## N

* **Netplay** : A technology letting people play online, in the case of Recalbox, it enables several retro games to be played over a network. 
* **No-intro** : Reference romsets for most cartridge-based systems, mostly referenced for Netplay.

## O

* **Overlays** : Image displayed on top of the currently running game, mostly used for cosmetic reasons.

## P

* **PBP** _\(or .pbp\)_ : Image file corresponding to physical UMDs for the Playstation portable system, or to multi-disc games for the Playstation.

## R

* **Recalbox** : The Operating system itself, Based on Buildroot System from scratch.
* **Recalbox.conf** : File containing most Recalbox and emulators specific settings, see [recalbox.conf](getting-started/the-recalbox.conf-file.md).
* **Retroachievements** : A service which, for supported roms and emulators, will enable an Achievement/Trophy-Like system for retro games.
* **Retroarch** : The libretro front-end used behind-the-scene for some of Recalbox's emulators, see [Retroarch](../advanced-user/retroarch.md).
* **Rewind** : A setting allowing you to rewind time in supported emulators, at a performance cost.
* **Roms** : Numeric files that are images of physical games.
* **Romset** : A specific set of roms, mostly referenced for Netplay or Arcade emulation.

## S

* **Savestates** : Savestates \(or save states\) are a feature accessible in most emulators, letting you save the exact content of a given game, even if it doesn't support saves originally, it should be noted that regular game saves and savestates can conflict each other.
* **Scrapper** : Programs searching about games informations on the internet, while putting them in files EmulationStation will be able to understand.
* **Shaders** : Filters that will transform the in-game image at a performance cost, mostly used for cosmetic reasons.
* **Support Archive** : One of the options in the Webmanager, generating a debug link that can be helpful to the development team in case of issues.

## T

* **Themes** : Files that define the overall look of EmulationStation.

## V

* **Verbose** : In the context of Recalbox, it is a startup mode showing specific debug informations for some architectures, helping understand why the Operating System would not boot properly.

## W

* **Webmanager** : A network interface enabled by recalbox to fine-tune settings in an easier way, manage files, verify BIOSes and more.

