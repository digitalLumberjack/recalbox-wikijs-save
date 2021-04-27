# ClrmamePro Tutorial

#### Definitions

* game : indicates the name of the game
* set : each game versions
* clone : version of a different game from the original
* rom : file contained in a set.
* rom set : set of files \(roms\) contained in a set

Example :

**What is a dat file ?**

Dat files are text files with information about games emulated with a specific version of MAME.  
In its dat-files you can find the information for particular sets such as :  
name of rom \(name\), year \(year\), manufacturer \(manufacturer\), merge information \(merge\), parent rom \(romof\) or clone of \(cloneof\), size of rom \(size\), CRC for each rom.  
CRC is an algorithm to check the integrity of a file, clrmamepro uses it to check your rom-sets.

Example : To be completed

Header indicates information such as emulator name with description, version and author information.

```markup
<datafile>
    <header>
        <name>MAME</name>
        <description>MAME 0.78</description>
        <category>EMULATION</category>
        <version>0.78</version>
        <date>-not specified-</date>
        <author>AntoPISA</author>
        <email>progettosnaps@gmail.com</email>
        <homepage>http://www.progettosnaps.net/</homepage>
        <url>-not specified-</url>
        <comment>-not specified-</comment>
        <clrmamepro/>
    </header>
```

ROM Information

```text
mettre exemple moins long.
```

**Table of versions available on Recalbox**

misses the RPI version I didn't mention imame4all and piFBA.

| Version | Emulator | Core | Dat Files | Path | Bios | Compatibility list |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 6.0 | Libretro | imame4all | [mame 0.37b5](https://github.com/recalbox/recalbox-buildroot/blob/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/imame4all/imame4all.dat) | /recalbox/share/roms/mame | Liste |  |
| 6.0 | Libretro | Mame2003 | [mame 0.78 dat](https://github.com/recalbox/recalbox-buildroot/blob/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/mame/clrmamepro/mame2003/mame2003.dat) | /recalbox/share/roms/mame | Liste |  |
| 6.0 | Libretro | Mame2003-plus | mame 0.78 + mame 0.188 | /recalbox/share/roms/mame | \[Liste\] |  |
| 6.0 | Libretro | Fba 0.2.97.44 | \[mame 0.189 dat\] | /recalbox/share/roms/fba\_libretro | Liste |  |
| 6.0 | Libretro | FBA 0.2.97.44 neogeo | \[mame 0.189 dat\] | /recalbox/share/roms/neogeo | neogeo.zip |  |
| 6.0 | Libretro | mame2003 neogeo | mame 0.78 dat | /recalbox/share/roms/neogeo | neogeo.zip |  |
| 6.0 | Standalone | piFBA | [mame 0.114 dat](https://raw.githubusercontent.com/digitalLumberjack/recalbox-os/master/wiki/dat/fba_029671_od_release_10_working_roms.dat) | /recalbox/share/roms/neogeo | Liste |  |
| 6.0 | Libretro | FBA 0.2.97.44 | \[mame 0.189 dat\] | /recalbox/share/roms/fba\_libretro | Liste |  |


>An arcade rom in zip format should never be unzipped or renamed.
>{% endhint %}
>
>{% hint style="info" %}
>**Note :** Other DATs files are available on this site [progretto-SNAPS Dats](http://www.progettosnaps.net/dats/) .
>{% endhint %}
>
>**Arcade BIOS**
>
>If you have recovered your romset, BIOS for some game publishers are available in this one. Here is the list of BIOS present in your romset that are necessary for some ROMs to work.
>
>| Name | Publishers | BIOS Name |
>| :---: | :---: | :---: |
>| Acclaim PSX | Acclaim | acpsx.zip |
>| Arcadia System BIOS | Arcadia Systems | ar\_bios.zip |
>| Atari PSX | Atari | atpsx.zip |
>| Atlus PSX | Atlus | atluspsx.zip |
>| Baby Phoenix/GV System | Konami | konamigx.zip |
>| Crystal System BIOS | BrezzaSoft | crysbios.zip |
>| DECO Cassette System | Data East Corporation | decocass.zip |
>| Hyper NeoGeo 64 Bios | SNK | hng64.zip |
>| Max-A-Flex | Exidy | maxaflex.zip |
>| Mega Play BIOS | Sega | megaplay.zip |
>| Mega-Tech | Sega | megatech.zip |
>| Multi Amenity Cassette System BIOS | I'Max | macsbios.zip |
>| Neo-Geo | SNK | **neogeo.zip** |
>| Nintendo Super System BIOS | Nintendo | nss.zip |
>| PGM \(Polygame Master\) System BIOS | IGS | **pgm.zip** |
>| PlayChoice-10 BIOS | Nintendo of America | **playch10.zip** |
>| PS Arcade 95 | Eighting / Raizing | psarc95.zip |
>| ST-V Bios | Sega | stvbios |
>| Super Kaneko Nova System BIOS | Kaneko | **skns.zip** |
>| System GX | Konami | **konamigx.zip** |
>| Taito FX1 | Taito | taitofx1.zip |
>| Taito GNET | Taito | taitogn.zip |
>| TPS | Tecmo | tps.zip |
>| ZN1 | Capcom | cpzn1.zip |
>| ZN2 | Capcom | cpzn2.zip |
>
>Source : [mamedb.com](http://www.mamedb.com/category/BIOS.html)  
>_****_  
>**in bold : required bios**
>
>#### ClrmamePro
>
>ClrmamePro is a tool to check and rebuild your arcade romsets according to an info file \(XML or dat format\).
>
>**Installation**
>
>1. Download ClrmamePro for Windows or MacOS ; on Linux, just use Wine. Note : the zip file is a portable version.
>2. Install it.
>3. Get the right arcade emulator dat file
>4. Execute ClrmamePro in admin mode \(right click &gt; Execute as an administrator\)
>
>{% hint style="warning" %}
>**Tip** : On Windows, right click on cmpro64.exe ou cmpro32.exe, then click on "Properties" &gt; Compatibility tab &gt; tick the box : Execute as an administrator. Validate clicking on Ok. The application will now always be executed in administrator mode.
>{% endhint %}
>
>### Parent and Clone Roms.
>
>There are two special rom formats, which are called **Parent Rom** and **Clone Rom**. A Clone Rom needs its Parent Clone to run properly.
>
>Example : _Metal Slug 4_
>
>```text
>Metal Slug 4 (NGH-2630)  (clone of: mslug4)          mslug4h.zip     
>Metal Slug 4 (NGM-2630)                              mslug4.zip
>```
>
>mslug4.zip it the parent rom, mslug4h.zip is a clone rom. The clone rom is dependent of its parent's. The clone rom name is usually followed with a letter, just to differentiate them from its parent's.
>
>#### Difference between Non-Merged set, Split Set and Merged-Set.
>
>There are 3 methods of roms classification used to manage those different versions of a game :
>
>* **Non Merged Sets** : each parent and clone will have their own zip file, containing the roms they need. This method is by far the method that takes up the most space on your hard drive, but you won't have to worry anymore about whether the clones are with their parents or not when you burn your roms for example.
>* **Split Sets** : the parent set has a zip file containing all the roms it needs. The clone set\(s\) ha\(ve\)s a zip file that contain\(s\) only the roms that are different from the parent set. However, clone sets will need some common roms, contained in the parent zip file, in order to work. This solution takes up the least amount of hard disk space, but if the clone sets are not in the same directory as the parent sets, they will not work.
>* **Merged Sets :** parents and clones of a game will be contained in one big zip file. Regarding the disk usage, it's an intermediate solution. Bigger than split's one and smaller than non merged. The parent/clone separation problem is also solved. The only drawback remains to update your roms if you're not interested in clones.
>
><table>
>  <thead>
>    <tr>
>      <th style="text-align:center">Mode</th>
>      <th style="text-align:center">Non-Merged</th>
>      <th style="text-align:center">Split-Merged</th>
>      <th style="text-align:center">Merged</th>
>    </tr>
>  </thead>
>  <tbody>
>    <tr>
>      <td style="text-align:center">parent</td>
>      <td style="text-align:center">
>        <ul>
>          <li>rom 1 nom : abcd crc : 1234</li>
>          <li>rom 2 nom : azerty crc : 789</li>
>        </ul>
>      </td>
>      <td style="text-align:center">
>        <ul>
>          <li>rom 1 nom : abcd crc : 1234</li>
>          <li>rom 2 nom : azerty crc : 789</li>
>        </ul>
>      </td>
>      <td style="text-align:center">
>        <ul>
>          <li>rom 1 nom : abcd crc : 1234</li>
>          <li>rom 2 nom : azerty crc : 789</li>
>          <li>rom 3 nom : bdce crc : 4444</li>
>          <li>rom 3&apos; nom : jklm crc : 5555</li>
>        </ul>
>      </td>
>    </tr>
>    <tr>
>      <td style="text-align:center">clone 1</td>
>      <td style="text-align:center">
>        <p></p>
>        <ul>
>          <li>rom 1 nom : abcd crc : 1234</li>
>          <li>rom 2 nom : azerty crc : 789</li>
>          <li>rom 3 nom : bdce crc : 4444</li>
>        </ul>
>      </td>
>      <td style="text-align:center">
>        <ul>
>          <li>rom 3 nom : bdce crc : 4444</li>
>        </ul>
>      </td>
>      <td style="text-align:center"></td>
>    </tr>
>    <tr>
>      <td style="text-align:center">clone 2</td>
>      <td style="text-align:center">
>        <p></p>
>        <ul>
>          <li>rom 1 nom : abcd crc : 1234</li>
>          <li>rom 2 nom : azerty crc : 789</li>
>          <li>rom 3 nom : jklm crc : 5555</li>
>        </ul>
>      </td>
>      <td style="text-align:center">
>        <ul>
>          <li>rom 3 nom : jklm crc : 5555</li>
>        </ul>
>      </td>
>      <td style="text-align:center"></td>
>    </tr>
>  </tbody>
></table>
>
>Source [detailed tutorial Clrmamepro \(fr\)](http://clrmamepro.free.fr/merger.php)
>
>### ClrmamePro Configuration 
>
>![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lxs1A-PJIlazZLj0r7W%2F-Lxs5oXHf0GNoe7lqAHj%2Fclrmamepro.png?alt=media&token=d1fd4a80-933b-47cd-b05b-4babb71badda)
>
>1. Profil creation
>
>Click on "Add DatFile" to load your dat file
>
>![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lxs1A-PJIlazZLj0r7W%2F-Lxs6-70gPqM-ARvrxmS%2Fadd_DatFile.png?alt=media&token=5e7087a1-61a5-4fef-8ac7-53379b3a99f4)
>
>     2. In this example : mame0.780.dat for mame2003.
>
>![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lxs1A-PJIlazZLj0r7W%2F-Lxs6QZRNqBsO51V-rm6%2Fdatfiles.png?alt=media&token=d0b74229-6b37-46b5-935e-a1c83ffb650d)
>
>Click on **Load/update**.  
>Then click **default**, wait during the scan, and click on OK ALL to let the process run.
>
>![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lxs1A-PJIlazZLj0r7W%2F-Lxs6_C42RWZ1Z6pOH-O%2Fok.png?alt=media&token=cd8ae580-a2ac-4633-96ff-e2859e7c4c75)
>
>     3. Click on the settings button.  
>Configuring the **ROM-Paths** \(1\), that indicates the path to your roms source directory.  
>Click on the **Add...** \(2\) button.  
>Then click on **Save As Def.** \(3\) - Validate your action clicking on OK.   
>
>![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwUxzaIbGBvIpUyQI6%2FSettings.png?alt=media&token=b76883cf-7bf1-46d9-ab61-34dae3ea4af6)
>
>Configuring the **Add-Paths**, that indicates the path to your roms destination directory.  
>Click on the **Add...** button.
>
>![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwV5u7QqP8WsWRUSsv%2Faddpath.png?alt=media&token=ef6f3ceb-29c8-4a97-a67d-cfcf9b182d91)
>
>Close the window.
>
>{% hint style="info" %}
>**Note** : you can add other paths to the samples directory for example.
>{% endhint %}
>
>#### Scanner Function : Checking your romset.
>
>1. Click on the Scanner button
>2. Check **Sets**, **ROMs**, and **Samples** if you configured the paths \(1\)
>3. Choose the right option, related to your romset \(non merged, split-merge, merged\) \(2\)
>4. Click on New Scan \(3\)   
>
>![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwVLAswxuyLKQLq6fW%2FScanner_.png?alt=media&token=8e131ef7-b8e1-4068-8db7-3eb1b18f1509)
>
>#### Rebuild Function : build your romset.
>
>{% hint style="warning" %}
>**Advice** : always work on a backup romset with this tool !
>
{.is-warning}

Example with mslug3

```text
mslug3.zip parent rom
mslug3b6.zip clone of mslug3.zip
mslug3h.zip clone of mslug3.zip
mslug3v.zip clone of mslug3.zip
```

Assuming you got an unmerged romset, i.e. it contains the parent roms with the clone roms. The rebuild function allows you to change the "mode" of your romset : from a non-merged romset to a merged or split romset and vise versa.

1. Click on the Scan button, uncheck samples, chd, and choose Non-Merged Set, close the window clicking on the cross in the upper right corner. 
2. Click on Rebuild Indicate the source path of your roms. Check the destination one. Choose Non-Merged Set, uncheck "Remove Matched Sourcefiles". Click on the Rebuild button.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwWM_MvnWtCEvCtj28%2FRebuilder_.png?alt=media&token=47abd07d-a6b3-4265-84d1-7051d5929eb5)

Just have a break, this step may take a little while ... :\)

### Dividing a romset according to its system \(bios\) from a complete romset

In recalboxOS, we divided the arcade roms into 3 groups : mame, fba\_libretro and neogeo.

Warning : for Neogeo, the default emulator is fba\_libretro ; if you want to use mame 2003 you will have to modify the default system emulator.  
_Emulationstation menu_ \(start button\) then _Game options_ &gt; _Advanced_ &gt; _neogeo_ &gt; modify the desired options.

To separate the neogeo roms contained in your mame or fba\_libretro romset, just launch "Scan" then click on the **Systems** button.

The number of systems may vary depending on the dat file you have loaded.

1. Click on the AutoAssign button - the systems are assigned to your roms folder.
2. Click on the None button to deselects all systems.
3. Check only the \[Bios\]Neo geo checkbox and choose a folder for neogeo.
4. In the Move Set to box, specify a folder for your neogeo roms.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwWs6-yB58HMt54ueA%2FSystems%20%26%20assigned%20System-Default-Paths.png?alt=media&token=6ca13fa3-041f-492d-adb8-6857b730e016)

Check your folder.

### Dividing a complete romset to get the parent roms only

Simply create a profile with the desired dat file. In this case, mame2003\_parent\_only.dat \(with or without neogeo, it's up to you\).

* rom-path \(folder containing all your roms\)   
* add samples-path \(if needed\)   
* Check the MAKE backups To Folder box and specify a backup folder. 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwX05Mjm-O9FsHtTtb%2Fbackup_folders.png?alt=media&token=f77eb0dc-8717-4703-b1f5-6ea684a33225)

* Use the Scanner function and configure as follows :
  * Click the systems button and click the Auto-assign button.
  * Check all the boxes in the check fix section.
  * To speed up the scan, uncheck the Ask before Fixing box. Once done, click on scan.
  * Click OK ALL if the question is asked during the scan.

Here you go : consult your source folder \(rom-path\) and you will see that the roms **not indicated** in your dat file have been moved to your backup folder.  
The backup folder contains :

* at its root the roms modified by the scan that weren't in the dat file,
* and a subdirectory named \_unknown with the roms not modified by the scan that were not in the dat file.

#### Create your dat file :

You have checked your romset with clrmamepro via the Scanner function. To create a custom dat file you can use the dir2dat function available in the Profile.

Example : mame0.78\_neogeo\_only.dat

1. Indicate the source-folder\(1\)
2. Choose the xml format \(2\)
3. Fill the Header Entries form \(3\)
4. Click on the Create button\(4\)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwXLJ2VnqUx1vaZrfQ%2FDir2Dat.png?alt=media&token=1a969ad7-65e3-45b6-8753-5326425b4219)

### Updating your romset

#### A. Prerequisite

* Having multiple versions of complete arcade romsets
* Possibly with all Mame 0.xxx to 0.xxxx Update Packs
* Download the appropriate required dat file \(see the table above\)
* Create a new profile with the previously downloaded dat file
* Make a backup of your romsets on an external hard drive, and always work on a backup of your romset to update.

#### B. Configuration

* rom-path \(the source-folder of your roms\)
* add-path \(add all the romsets folders you have, the more the better\)
* sample-path \(add the samples folder of your romsets \(optional because some sets have missing samples\)\)
* Set up a backup folder

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwXXe3PN341MWjQ6zy%2Fbackup_folders.png?alt=media&token=072312e4-54d0-4857-bd1d-7783cb2d0218)

#### C. Scan your romset

* Check the following options as on the capture 

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwXmcXW-qbo2-wyQ-d%2Fscanner_update.png?alt=media&token=c3b71d36-8ee0-4f79-b86a-8af171f27158)

Click on the **Systems** button , then on **Auto-Assign**

And finally click on the **New Scan...** button ; and wait as it may take a while ...

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwY-WeeVyrJKAvHdjc%2FSystem-Default-Paths.png?alt=media&token=801c9401-30c1-40e7-a0e4-bf5c0944ac93)

#### D. Analysis of statistics

What we're interested in here is the up part : **Missing**.  
This **Missing** part shows you the sets, roms and missing samples.  
Just read again the definitions above if needed.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwY8vtgOGP6Ev8TGNQ%2Fsatistic.png?alt=media&token=d7c272b9-197c-4362-bfc4-99c40adc5736)

Validate by clicking OK to close the window ; but which sets are missing ? In set information you have the list of missing sets and roms.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwYJbWc9edz7bt4yC_%2FScan%20Results.png?alt=media&token=96977294-3d12-406f-907b-8a2b2f3ae316)

To get a list of the missing sets, just click on the **Miss List...** button.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwYa6fO8SVukB1UBbG%2Fmisslist.png?alt=media&token=7603efd4-935b-43ec-a219-5cf584660337)

**How to fill in the missing sets :**

With the name written in the file you can search for the missing sets on different search engines with the following keywords: _mame filename.zip_

 Example with Touch & Go game \(touchgo.zip\) with these clones.

```text
touchgo
touchgoe
touchgok
touchgon
```

Chances are you'll come across sites with missing archives.  
Fetch them and put them in a folder named _missing_ for example.  
Once all the missing sets are retrieved, add the folder in the `settings > add-path` section.  
Restart a scan. If everything is ok, you should have reduced your missing sets. Repeat this as many times as necessary if you are stilling missing some.

**Filling in the missing roms :**

This is the longest and most tedious part of piecing together your complete romsets. For more ease, export the list of missing roms.

Analysis of a missing rom :

```text
Burger Time (Data East USA) [graphics issues, use parent romset!] [folder: btime3 - parent: btime - size: 56kb]
missing rom: ab03-3.6b [size: 2048] [CRC32: f699d797]
missing rom: ab04-3.9b [size: 4096] [CRC32: 5d90c696]
missing rom: ab05-3.10b [size: 4096] [CRC32: c2b44b7f]
missing rom: ab05a-3.12b [size: 4096] [CRC32: 12e9f58c]
missing rom: ab06-3.13b [size: 4096] [CRC32: e0b993ad]
missing rom: ab07-3.15b [size: 4096] [CRC32: 91986594]
```

* **Burger Time \(Data East USA\)** : name of the set    
* **\[graphics issues, use parent romset!\]** : this is a btime3.zip clone with graphical problems, it is advised to use the parent rom btime.zip.  
* **\[folder: btime3 - parent: btime - size: 56kb\]** :  remember earlier I told you that clone roms always came with a number or a letter. Here we're talking about a btime3.zip clone and its parent rom is btime.zip.
* **missing rom: ab03-3.6b** : information about the missing \(rom\) file in the archive  
* **\[size: 2048\] \[CRC32: f699d797\]** : information about the size/weight of this file with the CRC signature to identify it

Using the following information in your preferred search engine: **ab03-3.6b CRC32: f699d797**  
It is quite possible that you will find your missing rom, just redo the search on the other files.  
They may or may not already be contained in the recovered archive. Recover your missing files and place them in a missing folder as before.  
Once finished, don't forget to add the folder in `settings > add-path`.  
Restart your scan as many times as you want.

At the end you should have :

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwZFrJP24avHJjH5fW%2Fromsetcomplet.png?alt=media&token=af7b915d-408d-412d-9937-7f3c47efe4b6)

To obtain a file containing the missing roms, right-click on the Set information window and choose **Copy to Clipboard &gt; all list sets messages**. Open the clipboard and paste the result.

**Note :**

Move`https://github.com/recalbox/recalbox-buildroot/blob/rb-4.0.X/board/recalbox/fsoverlay/recalbox/share_init/roms/fba_libretro/FBA_libretro_NEOGEO_only.dat`  
dans le dossier `/recalbox/share_int/roms/neogeo/date file/FBA_libretro_NEOGEO_only.dat` et ajouter celle de mame2003 neogeo.

Réaliser Une PR avec les dats manquants.

Remerciements :  
Source :  
Consulter :

#### Travaux : Option set informations

Après configuration de clrmamepro, lancer le scan de votre romset.  
Une fenêtre nommé set information apparaît.  
Cliquer sur le bouton set information  
Pour créer un fichier dat contenant uniquement les roms parentes  
Cliquer sur le bouton avail.sets  
Décocher les cases clones et parent si cochées  
Entrer les informations suivantes: `%c=?*`  
Vous remarquerez que seuls les clones sont sélectionnés  
Cliquez sur le bouton invert ; la sélection est inversée et maintenant les roms parentes sont sélectionnées  
Cliquez sur le bouton export ; donner un nom à votre fichier dat \(mame2003\_parent\_only\)

#### \[WIP\] Télécharger les fichiers dat à partir de clrmamepro : www Mode

WWW Mode est un gestionnaire de téléchargements de fichiers dat.

* Ouvrir le logiciel clrmamepro
* Non obligatoire mais vous pouvez déjà créer votre dossier pour un profil \(exemple : mame 2003\) en faisant un clic droit sur \[PROFILES\] &gt; Create folder.  
* Cliquer sur le bouton WWW Mode   
* Cliquer sur le bouton Add Site...   
  * URL of Dat : mamedl.esy.es/dats/cmdats/recalbox\_arcade.zip   
  * Site Alias : Recalbox \(par exemple\)   
* Valider par OK Vous obtenez une liste de différentes fichiers dats disponibles.   

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LxwSXFnK1IR_BvL6Onm%2F-LxwZkZ_B6HAyQCl-9LV%2FwwwMode_list.png?alt=media&token=48d70210-6170-49d7-8121-232eb67f1d70)

* Clic droit sur le fichier, choisir Download File ou double clic sur le fichier ou cliquer sur le bouton download.
* Vous pouvez créer un dossier ou non en cliquant sur Create Dir si vous ne l'avez pas fait avant.   
* Sélectionner votre dossier puis cliquer sur OK.  
* Cliquer sur oui pour ouvrir le profil avec le fichier dat fraîchement téléchargé.   
* Cliquer sur Default Passer à la configuration \(_settings_\) de votre profil.

