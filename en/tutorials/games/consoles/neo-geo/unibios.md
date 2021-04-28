---
title: Unibios
---

# Unibios

## What Unibios does

* Change region \(Europe/USA/Japan\) and mode \(AES/MVS\)
* Access the soft dip to change game difficulty/life/time etc
* In-game Cheat database
* Jukebox music player... and a lot more!

## FinalBurn Neo

### Installation

Start a game and go inside RetroArch menu with **Hotkey + B**.



Go into Options



Change the setting labelled « Neo-Geo mode » from `Use bios specified in BIOS dipswitch below` to `Use UNIBIOS bios`.



Change the setting labelled « \[Dipswitch\] BIOS » from `MVS Asia/Europe ver. 6 (1 slot)` to `Universe BIOS ver. 4.0` or `Universe BIOS ver. 3.3`.



### Usage

* Start any Neo-Geo game, you will see the boot screen of the Universe BIOS.
* While you're on this screen, press and maintain the buttons **Y + B + A** to change the region and mode. Press **Y** to quit.

## piFBA

### Installation

1. Get it here \(version 3.2\): [http://unibios.free.fr/download.html](https://web.archive.org/web/20190615013124/http://unibios.free.fr/download.html)
2. Extract the downloaded file, rename uni-bios.rom to asia-s3.rom.
3. Open your own neogeo.zip, there should be a asia-s3.rom file inside, back it up if needed.
4. Put the new renamed asia-s3.rom into neogeo.zip, replace it with the old one.
5. Now upload the new neogeo.zip back to the Recalbox share folders, on both \bios and \finalburnalpha

### Usage

* Start up any neogeo game, you will see the new UNIVERSE BIOS v3.2 splash screen.
* During this startup screen, press and hold BXY for region/mode setup, or hold ABX for dip switch menu.
* To access the in-game menu, press and hold BXY+START at the same time.

## Dip switch

To access to the « dip switch » menu during UNIVERSE BIOS splash screen, hold **A + X + Y**.

### Setting up the soft dip

* To display blood:
  * Region Japan / Arcade mode
  * slot metal slug
  * blood &gt; on
  * Press **C \(Y\)** to exit.

## BIOS

Neo Geo requires a neogeo.zip BIOS file.

* It will be placed with your ROMs in

```text
/recalbox/share/roms/neogeo
or
/recalbox/share/roms/fbneo
```

* These are the contents of a verified working neogeo.zip BIOS file

```text
000-lo.lo
japan-j3.bin
neo-epo.bin
neo-po.bin
neodebug.bin
neopen.sp1
sfix.sfix
sm1.sm1
sp-1v1_3db8c.bin
sp-45.sp1
sp-e.sp1
sp-j2.sp1
sp-j3.sp1
sp-s.sp1
sp-s2.sp1
sp-s3.sp1
sp-u2.sp1
sp1-j3.bin
sp1-u2
sp1-u3.bin
sp1-u4.bin
sp1.jipan.1024
uni-bios_1_0.rom
uni-bios_1_1.rom
uni-bios_1_2.rom
uni-bios_1_2o.rom
uni-bios_1_3.rom
uni-bios_2_0.rom
uni-bios_2_1.rom
uni-bios_2_2.rom
uni-bios_2_3.rom
uni-bios_2_3o.rom
uni-bios_3_0.rom
uni-bios_3_1.rom
uni-bios_3_2.rom
uni-bios_3_3.rom
uni-bios_4_0.rom
vs-bios.rom
```

