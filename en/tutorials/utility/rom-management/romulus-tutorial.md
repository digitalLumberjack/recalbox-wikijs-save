---
title: Romulus Tutorial
---

# Romulus Tutorial

## What you need to know ...

### Specific terms

_**DAT files**_ : Is a file that contains information about filename, size, checksum, etc of one or more files and can be imported using Romulus to display all this information and check your ROMs. Romulus supports all kind of DAT files like XML format, Clrmame pro, Romcenter, Offlinelist and many others.  
  
 _**ROMs**_ : Read Only Memory. Are files extracted from this kind of chips and can be used with emulators to display this games, applications or something like the original system. Today are called ROMs files extracted from other kind of systems like cassetes, floppy disks, etc.  


_**ISOs**_ : Same as ROMs but extracted from optical disks like CDs, DVDs  
  
 _**Compressed files**_ : Is not necessary to explain that are files that contains file/s that using complex operations can reduce the size of file/s contained inside. Romulus can handle compressed files of ZIP ![](data:image/webp;base64,UklGRuoAAABXRUJQVlA4IN4AAACwAwCdASoQABAAAgA0JbACdD3mdKk9k4iFv1s6UA26qv4C3/1I8AD+65FunLL+G8D3VMRRa1NA9PGQLjtRfGedFLGDZfR/fT1ka9O9w6Y5/mC1yvVkDVi5ey5odsCmHPJ/yIf8uy8wrybT4XnM4igbSx8UEP0sd/F0LWY+smzP+PfyOMpcwyY7M7EK94avxSQJlsJmFbzctj0MHtf/PlwUq9c/5///IqQp4ijR3X1/yZv/FX4Lb0Jnu1z98/fP6/86dyHl0cSv3ZRTnUeZq08x6pMdeTFy9Dw1sKOAAAA=), RAR ![](data:image/webp;base64,UklGRtwAAABXRUJQVlA4INAAAADQAgCdASoQABAAAgA0JbACdH8AjYDyfu6ITtq+N17QAP7SrHjfsLWgSq5V2urQt2ZrJhsRr/CDtpiIrMX9r6A2o/qR+LwvNLcLclCpms7S6fHdHe7PguZ+BpSb2H4bg09loX/FX2RKXMgTvkKPysiJKj0FOrCiWZTn/CfJzfk/c+6m/5Z1Vt/maLQbPAp/3Xgnf4x8PCLrX5LI/3d53y7dKX3mCU55velBSe2cl9bcDJNPMyw+ACZyEG3+Zn//NgzEfEUP3Nlx//0Ob/+uBAAA) and 7z ![](data:image/webp;base64,UklGRvoAAABXRUJQVlA4IO4AAACwBQCdASoQABAAAgA0JZgC7AsWbUANQB/Hfsz99f9j+4D2g6gH6T/5fgHf0gOywcTZS/+z7UAA/sq5W2OFz71g8l2eikUrywzTmdxyh+v7PJ7Gs1vm1/S/z/+Sc6SHf0W6LG138c+v1z5/TuKIY5NX3j4G96FE/+MLaXi6YwqTF4Qn5yvrvsYmmw/w2Fsd15HjvCuAQ5/nB0IQ/inmYXSKkWpdAsOJyjY4vOkAIGNOPLVZdaKKqFNBb/i3fTcDYDh5LwE1tgcI+qmmoTVhz1R4C9XDZs3Rwj369ir1HIBJsQfbjiTdXHAMkdA4AAAA) format, represented in Romulus with the showed images.  
  
 _**Checksums**_ : Is a mathematic calculation of a file used to generate an special word combining numbers and letters unique for this file. Romulus can handle different kind of checksums CRC32, MD5 and SHA1. Is important to know that Romulus checks CRC32 and size without ask and is a very secure method. MD5 and SHA1 checksums are optional and available if DAT file contains enought information and if are activated will decrease the speed of scanning or rebuilding files. Compressed files has information about CRC32 and size of files inside but not for MD5 and SHA1 by this reason to check them is necessary to extract from compressed file and apply the checkums decreasing more the speed.  
 Saying this you must know that is more fast to scan compressed files than uncompressed files if MD5 and SHA1 is not activated.  
  
 _**Scan files**_ ![](https://romulus.cc/tutorial/imgs/xscan.jpg.pagespeed.ic.mzZZnU4qez.webp) : Is the process to check the ROMs of a folder to compare to the profile information to know if checksums, sizes and file names are equals.  
  
 _**Rebuild files**_ ![](https://romulus.cc/tutorial/imgs/xrebuild.jpg.pagespeed.ic.kVHKBqZ3i4.webp) : Is the process to check ROMs of other folder different than ROMs folder to compare with the profile and agregate in correct place of ROMs folder the files that can be necessary to add because are not available in ROMs folder.

_**TorrentZip & Torrent7z**_ : Are compressed files in Zip or 7z but using an special application that makes for all users the compressed files with same checksum if inside compressed file are same. This is usefull to resume large sets of roms with **Bittorrent P2P** clients.  
  
 _**File modes**_ : Some DAT files contains information of more than 1 mode to sort your ROMs. In general DAT files contains information about **SETNAME** that is the folder of compressed file that contains **ROMNAMEs**.  
 But maybe the DAT contains information about **MASTER** and **CLONE** Setnames, for example when a game contains files that in other game are the same very usual in Arcade games with different versions of each game.

##  **The three possible file modes**

_**Not split**_ : All clone sets if exists are placed in file or folder of father set. If no clones exists is the only filemode you can select

_**Split / Merged**_ : Every sets are in own file or folders and maybe needs the files from father set to be runned

_**Split / Not merged**_ : Every sets are in own file or folders and always have all files needed to be runned \(More space in disk is used\)

Example**:**

| _**Split / Not merged**_ | _**Split / Merged**_ | _**Not split**_ |
| :---: | :---: | :---: |
| ![](https://romulus.cc/tutorial/imgs/splitnotmerged.jpg) | ![](https://romulus.cc/tutorial/imgs/xsplitmerged.jpg.pagespeed.ic.IACAU5BECh.webp) | ![](https://romulus.cc/tutorial/imgs/notsplit.jpg) |

##  **The first run**

Romulus uses a database to save the information of your imported DAT files, ROMs directories, configurations etc. The first run you will see a message about creation of database with name "default.rml".

##  **Main menu options** \(Are located at the top of Romulus application\)

  
 ****[![](https://romulus.cc/tutorial/imgs/profiles.jpg)](https://romulus.cc/tutorial/tutorial.php#Profiles) ****[![](https://romulus.cc/tutorial/imgs/scanner.jpg)](https://romulus.cc/tutorial/tutorial.php#Scanner) ****[![](https://romulus.cc/tutorial/imgs/builder.jpg)](https://romulus.cc/tutorial/tutorial.php#Builder) ****[![](https://romulus.cc/tutorial/imgs/updater.jpg)](https://romulus.cc/tutorial/tutorial.php#Updater) [![](https://romulus.cc/tutorial/imgs/Statistics.jpg)](https://romulus.cc/tutorial/tutorial.php#Statistics) [![](https://romulus.cc/tutorial/imgs/settings.jpg)](https://romulus.cc/tutorial/tutorial.php#Settings) [![](https://romulus.cc/tutorial/imgs/help.jpg)](https://romulus.cc/tutorial/tutorial.php#Help)  


### ![](https://romulus.cc/tutorial/imgs/profiles.jpg)Profiles - The first step

Add new DAT files to the right list. You can press ![](https://romulus.cc/tutorial/imgs/xopendat.jpg.pagespeed.ic.9rfBQi2CNh.webp) button and select them or **drag n drop** your DATs to the right list, DATs can be compressed files or uncompressed.  
 You can extract a DAT file and import it from **MAME based EXE** using this button ![](https://romulus.cc/tutorial/imgs/xcreatemamedat.jpg.pagespeed.ic.h2VgXn4mg_.webp)  
  
 When process is finished you will see at right list the main information about your imported DAT files, if you wish you can delete the old DAT files now.  
  
 Every profiles contains 2 images, one for the **profile status** and other for **DAT origin kind**.

![](https://romulus.cc/tutorial/imgs/smiles.jpg)

 _**Green face status**_ : Your profile is complete before scan it.  
 _**Yellow face status**_ : Your profile contains one or more correct files but is not complete.  
 _**Red face status**_ : Your profile is scanned but no contain any correct file.  
 _**Grey face status**_ : Your profile is not scanned yet.  
  
 The profiles list can be **filtered** using the faces button at bottom of window.  
  
 Now just **double click to load the profile** and see all information at Scanner option.

Profiles left list is a tree of folders that can be moved, deleted or edited to organize your profiles.  
 For example you can make a folder called ARCADE for your "Arcade" profiles, another for consoles, etc.  
 Just use **second mouse button** inside this list to see the different available options.  
 You can **drag n drop** profiles to this folders to organize them too. Is possible to create folders inside folders, and remember if no folder is selected when you add a new DAT, this new profile will be added in the no editable, no removable purple folder called "**DEFAULT**".  
 

#### **More profiles options**

  
**** At top buttons menu is possible to find ![](https://romulus.cc/tutorial/imgs/xopendb.jpg.pagespeed.ic.RKwXzevVh2.webp) the open database button that can be used to open other existing Romulus database in your computer or ![](https://romulus.cc/tutorial/imgs/xnewdb.jpg.pagespeed.ic.1Aztu7HCqP.webp) new Romulus database button to create an empty new one database.  
**** Also you can save profiles list on HTML, DOC or TXT formats using ![](https://romulus.cc/tutorial/imgs/xlog.jpg.pagespeed.ic.QxzUTyuFr7.webp) log button.  
  
**** Using second mouse button in profiles list you can view more options like delete selected profiles, select all in list, invert selection. Make ![](https://romulus.cc/tutorial/imgs/xscanb.jpg.pagespeed.ic.daXwU_1IDl.webp) **scan or** ![](https://romulus.cc/tutorial/imgs/xrebuildb.jpg.pagespeed.ic.id1uIR8wVt.webp) **rebuild automatic** for 1 or more profiles at same time or view properties using the scan in batch or rebuild in batch option.  
 You can ![](https://romulus.cc/tutorial/imgs/xsendgen.jpg.pagespeed.ic.PVD-MXeWLB.webp) **send to builder** a profile. An interesting option to edit a profile. This option will explained later.  
 You can **automatic** **create or set the ROMs path** for the selected profiles using the ![](https://romulus.cc/tutorial/imgs/xdircreator.jpg.pagespeed.ic.kuB2IUfpzv.webp) **Directories maker** option.  
 For this option just set the **base folder** where the ROMs path must be and the **rules you wish** and the name of folders you wish to set from **Description profile column** or **Name profile column**.  


![ Directories maker window](https://romulus.cc/tutorial/imgs/xdircpic.jpg.pagespeed.ic.F2ttHWWUFT.webp)

 Properties ![](https://romulus.cc/tutorial/imgs/xproperties_.jpg.pagespeed.ic.DwLT4r9skx.webp) is an option to modify some profiles main information like description, email, homepage or **file mode. This option is also available at Scanner menu.**

![ Properties window](https://romulus.cc/tutorial/imgs/properties.jpg)

###  ****![](https://romulus.cc/tutorial/imgs/scanner.jpg)**Scanner -** The place to scan and rebuild your ROMs 

Here can display all information of profiles and more things to will be explained. The information will be showed as **File mode** defined by user in properties option available in the buttons menu and available too in popup menu of profiles main list.  
  
 In lists you will find 2 images for line, one for completion status of set and other for master or clone indication.

![](https://romulus.cc/tutorial/imgs/setsstatus.jpg)

 _**Green folder**_ : All set is complete  
 _**Yellow folder**_ : Incomplete set  
 _**Red folder**_ : Nothing of this set  
  
 ![](https://romulus.cc/images/asterisk.gif.pagespeed.ce.HYJ_KTak3M.gif) At **Offlinelist** profiles dont exists master or clones sets and images are changed for **region flags,** and in columns list will displayed addition information for this kind of DATs. Offlinelist already has information about **updates** and **images** for this profile that can be applyed using the ![](https://romulus.cc/tutorial/imgs/xoffupdater.jpg.pagespeed.ic.kuIkKHisml.webp) **Offlinelist Updater button**.

![Offlinelist Updater Window](https://romulus.cc/tutorial/imgs/offupic.jpg)

 ![](https://romulus.cc/tutorial/imgs/xscan.jpg.pagespeed.ic.mzZZnU4qez.webp) The scan button shows the screen with necesary information to start to scan your ROMs.  
 ![](https://romulus.cc/tutorial/imgs/xscanb.jpg.pagespeed.ic.daXwU_1IDl.webp) The scan process can be automatic for all loaded profiles in Scanner option.  
 ![](https://romulus.cc/tutorial/imgs/xrebuild.jpg.pagespeed.ic.kVHKBqZ3i4.webp) The rebuild button shows same screen that scan but search for other folder to detect and insert new ROMs files to the main ROMs folder. You can also make a rebuild with **drag n drop folder/files** to the loaded profile list.  
 ![](https://romulus.cc/tutorial/imgs/xrebuildb.jpg.pagespeed.ic.id1uIR8wVt.webp) The rebuild can be automatic for all loaded profiles in Scanner option, pressing this button Romulus will ask the folder to rebuild. 

![Scan / Rebuild window](https://romulus.cc/tutorial/imgs/scanscreen.jpg)

  
 **ROMs path** can be defined pressing double mouse click on directories list or pressing ![](https://romulus.cc/tutorial/imgs/xfolder.jpg.pagespeed.ic.dJO5gzzT7J.webp) folder button.  
 Compression method can be defined using this button ![](https://romulus.cc/tutorial/imgs/xcompmode.jpg.pagespeed.ic.NP1G2INoV3.webp), and the number displayed in directories list is the **compression level** \(0 for stored - 9 for maximum\).  
 ![](https://romulus.cc/images/asterisk.gif.pagespeed.ce.HYJ_KTak3M.gif) Sometimes if profile has the information you will see a selection of **SAMPLES** or **CHDs** in Directories, if that are empty Romulus will use the ROMs Path as default for this kind of files.  
  
 **Backup path** is the directory where not detected ROMs will be placed.  
  
 After scan / rebuild you can activate to check **MD5** or **SHA1** checksums, **Torrentzip** or **Torrent7z**.  
  
 **Headers**, are rules to convert ROMs for be valid for the available checksums. For example one ROM can be the same game but can have different checksums, why? Sometimes unnecesary information is inserted in ROMs getting different checksums.  
 Headers can remove or modify this information to make checksum same as profiles. Remember if this option is activated will decrease the speed of only rebuilding or fixing ROMs process. Header files must be inside Headers folder of Romulus EXE.  
 More info about headers available in : [http://hg.nih.at/ckmame/?f=40f0fc92e8f0;file=docs/xmlheaders.txt](http://hg.nih.at/ckmame/?f=40f0fc92e8f0;file=docs/xmlheaders.txt)

Now just press **Start** to iniciate scan / rebuild process.  
  
 Returning to Scanner option more options are available:  
 ![](https://romulus.cc/tutorial/imgs/xemulators.jpg.pagespeed.ic.XZLkCxt63b.webp) Configure **emulators** to run for the listed games.You can configure maximum 10 emulators to run your roms for loaded  
 profile. Later you can run it selection your game with right mouse button click in your list and select the configured emulator.

![ Emulators configuration window](https://romulus.cc/tutorial/imgs/emupic.jpg)

 ![](https://romulus.cc/tutorial/imgs/xffix.jpg.pagespeed.ic.-aXb2cxA-T.webp) Make **friendfixes**. Is a DAT that contains only the files you need for example to send to a friend and rebuild to obtain your missing files. This process can be automatic for all loaded profiles using ![](https://romulus.cc/tutorial/imgs/xffixplus.jpg.pagespeed.ic.zMk7P_9TU6.webp) this button.  
 ![](https://romulus.cc/tutorial/imgs/xproperties_.jpg.pagespeed.ic.DwLT4r9skx.webp) Properties. Modify some information about loaded profiles. **This option is also available at Profiles menu.**  
 ![](https://romulus.cc/tutorial/imgs/xlog.jpg.pagespeed.ic.QxzUTyuFr7.webp) Save list in different formats.

### ![](https://romulus.cc/tutorial/imgs/builder.jpg)Builder - Build your own DATs

  
 Here you can create your **own DATs in XML format** to share with your friends or use yourselfs.  
 Just **drag n drop a folder** to the list or use the ![](https://romulus.cc/tutorial/imgs/xhash.jpg.pagespeed.ic.5eyJOTax7a.webp) hash from folder button to start process.  
 You can force check ![](https://romulus.cc/tutorial/imgs/xmd5.jpg.pagespeed.ic.qdBx0Ng8RS.webp) **MD5** or ![](https://romulus.cc/tutorial/imgs/xsha1.jpg.pagespeed.ic.zrKzpkkg8-.webp) **SHA1** checksums pressing the showed buttons or **force to check inside compressed files** or **hash as single file** using this button ![](https://romulus.cc/tutorial/imgs/xcompmode.jpg.pagespeed.ic.NP1G2INoV3.webp).  
 When process is finished you can **export** the information with the ![](https://romulus.cc/tutorial/imgs/xffix.jpg.pagespeed.ic.-aXb2cxA-T.webp) **Create XML DAT** file button.  
 The list that can be exported can be edited, removing **complete sets** or **only files** using the checkboxes

### ![](https://romulus.cc/tutorial/imgs/updater.jpg) **Updater -** Find new and updates for DATs

  
 This interesting option bring the possibility to view a list of **hundred of profiles** to know the current versions of it.  
 Romulus automatic detects if the **listed profiles** are not available, outdated or uptodate comparing with profiles available in your current database using flags to indicate it.



| ![](https://romulus.cc/tutorial/imgs/uptodate.jpg)​ | ​![](https://romulus.cc/tutorial/imgs/outdated.jpg)​ | ​![](https://romulus.cc/tutorial/imgs/notfound.jpg)​ |
| :---: | :---: | :---: |


_**Green flag**_ : Uptodate profile  
 _**Yellow flag**_ : Outdated profile  
 _**Purple flag**_ : New or not found profile

![](https://romulus.cc/tutorial/imgs/updaterpic.jpg)

  
   
 You can already filter list pressing the flags buttons.  
 Pressing doubleclick from the selected profile you can navigate to the homepage of DATs but if profile is an **Offlinelist profile** you with see the updater window for offlinelist and you can update it or get new images.

###  ![](https://romulus.cc/tutorial/imgs/Statistics.jpg) **Statistics -** Try to get all if you can

 Nothing special, information of your **completion status** as you can see in the pic.

![](https://romulus.cc/tutorial/imgs/statpic.jpg)

 In this case no ROMs found for the profiles available and I have the 100% not completed : P  


### ![](https://romulus.cc/tutorial/imgs/settings.jpg) **Settings -** Configure and customize

  
 Choose your language, modify some visual aspects of Romulus, default compression for new added profiles, select your desired DAT groups to find at **Updater** menu, and others. ****

![Settings Window](https://romulus.cc/tutorial/imgs/setpic.jpg)

### ![](https://romulus.cc/tutorial/imgs/help.jpg) **Help -** Click on this option to go to the [Romulus home page](https://romulus.cc/index.php).

**Source:**  [Romulus Rom Manager © **Coded by F0XHOUND 2010 - 2020**](https://romulus.cc/tutorial/tutorial.php)

