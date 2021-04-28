---
title: Clrmamepro Tutorial - How to check your roms versions
---

# Clrmamepro Tutorial - How to check your roms versions

piFBA, libretro\_fba, mame 2003, mame 2003-plus, mame 2010 and iMame4all all accept different roms versions. To find out if your roms are compatible, you can use clrmamepro.

This software will use a .dat file that contains the roms informations for a given version, and will check if your roms match these. It uses CRC on all files in .zip archives, and will tell you which files are missing or do not match.

First get the .dat file corresponding to the emulator you want to use: 

* piFBA: [https://raw.githubusercontent.com/digitalLumberjack/recalbox-os/master/wiki/dat/fba\_029671\_od\_release\_10\_working\_roms.dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-os/master/wiki/dat/fba_029671_od_release_10_working_roms.dat)
* iMame4All: [https://github.com/libretro/mame2000-libretro/blob/master/metadata/MAME 0.37b5 XML.dat](https://github.com/libretro/mame2000-libretro/blob/master/metadata/MAME%200.37b5%20XML.dat)
* Fba 0.2.97.44 : [https://github.com/libretro/fbalpha/blob/master/dats/FB Alpha \(ClrMame Pro XML%2C Arcade only\).dat](https://github.com/libretro/fbalpha/blob/master/dats/FB%20Alpha%20%28ClrMame%20Pro%20XML%2C%20Arcade%20only%29.dat)
* Mame 2003: [https://github.com/libretro/mame2003-libretro/blob/master/metadata/mame2003.xml](https://github.com/libretro/mame2003-libretro/blob/master/metadata/mame2003.xml) 
* Mame 2003-plus: [https://github.com/libretro/mame2003-plus-libretro/blob/master/metadata/mame2003-plus.xml](https://github.com/libretro/mame2003-plus-libretro/blob/master/metadata/mame2003-plus.xml)
* Mame 2010: [https://github.com/libretro/mame2010-libretro/blob/master/metadata/mame2010.xml](https://github.com/libretro/mame2010-libretro/blob/master/metadata/mame2010.xml)

Download ClrmamePro :

* Windows user : [http://mamedev.emulab.it/clrmamepro/](http://mamedev.emulab.it/clrmamepro/) \(works in wine for linux users\)
* MacOS X user: [http://www.emulab.it/](http://www.emulab.it/), a beta version is available. 

Upload your .dat file in the "**Profiler**" section.

Go to **Settings** and set the "**rom path**" to your directory containing your roms. 

Finally, use the **Scanner** to scan your rom directory, and **check the logs** to see what files are missing.

