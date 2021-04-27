# Updating your Recalbox

## Before Updating


>**Information:**   
>Here are the possibilities for upgrading Recalbox.   
>We hope this summary will help you and bring you the answers you seek.
>{% endhint %}
>
>### Check your situation
>
>**Is it possible to update from recalbox 4.1 to recalbox 6.0 ?**  
>**No**, _it is not possible to update this very very old version \(over a year and a half\) to recalbox 6.0 RCx / Stable Clean installation is required. See below for instructions_
>
>**Is it possible to update from recalbox 18.07.xxxxx to recalbox 6.0 RCx / Stable?   
>No,** _it is not possible to update this version to the new version of recalbox 6. Clean installation is required. See below for instructions._
>
>**Is it possible to update from recalbox beta to recalbox 6.0 RCx / Stable?   
>No**, _it is not possible to update this version to the new version of recalbox 6. Clean installation is required. See below for instructions._
>
>**Is it possible to update Recalbox 6 RCx to Recalbox 6.0 stable ?   
>Yes,** _it is possible to update between the different versions of recalbox 6.0 Release Candidate to the future stable version._   
>
>
>{% hint style="info" %}
>* Make sure you always have hard drive space on your microsd if you store your roms on it before updating
>* Always make a backup before performing the update, you can never be too careful. 
>* Read the changelog, and if it suits you proceed to update 
>* After reboot, reconfigure your controller.
>{% endhint %}
>
>**Is it possible to update recalbox 6.0 to 6.1?   
>Yes,** _it is possible to update from recalbox 6.0 to 6.1._ 
>
>{% hint style="info" %}
>* Make sure you always have hard drive space on your microsd if you store your roms on it before updating
>* Always make a backup before performing the update, you can never be too careful. 
>* Read the changelog, and if it suits you proceed to update 
>* After reboot, reconfigure your controller.
>{% endhint %}
>
>**Is it possible to multiboot with PINN or NOOBS with Recalbox 6 RCxxx?**   
>__**No.** _Noobs, it is not possible to do a multiboot with beta, or RC \(release candidate\) versions of Recalbox,  
>It will be only and only when:_ 
>
>* Recalbox 6 will be in stable version
>* Noobs agrees to add us to their list. 
>* \* It looks like PINN is following our development - To be tested
>
>**My controller works in Emulationstation but not when I launch the emulators why?**   
>_We add a maximum configuration of joysticks in emulationstation, to allow you to navigate in Emulationstation, but for many of them, you have to reconfigure them so that it works in emulators_. 
>
>* Emulationstation menu \(start button\) 
>* Controllers Options&gt; Configure my controller.
>
>**What if I use a custom theme** **?**
>
>* Make sure you are up to date. 
>* Contact the author of your theme or the subject of your theme to check if a new updated version is available. 
>* Use a custom theme in 720p on raspberry, 1080p your rpi will suffer. 
>* **We do not provide support for unofficial custom themes from recalbox.** 
>* **Please set the default recalbox theme to check your bugs before posting your problem on the forum.**
>
>**What if I use OVERLAYS?** 
>
>* If you use those of screenscraper, go to check if the packs were updated for recalbox 6.0 
>* If you have created your overlays, retroarch has added a new aspect ratio which shifts certain overlays: 
>  * test 22 or 23 on this line: `aspect_ratio_index = 21`
>
>**Arcades** 
>
>Since the 1st beta, recalbox has updated the cores of the arcade emulators: mame & fba libretro and added other emulators. 
>
>You must adapt your romsets: 
>
>* Global dat files are now in / bios / mame2003 or / fba or / mame2010 or / advmame 
>* To make parent-only dat, neogeo parent only etc ... you just need to use this tutorial datutil.exe to create them. 
>* core libretro Fba libretro: romset 0.2.97.44 
>* core libretroMame 2003: romset mame 0.78 
>* core libretroMame 2010: romset mame 0.139 
>* standalone advanceMame emulator: romset mame 0.106 \(reserved for experienced users\) 
>* Mame 2003-plus: romset 0.78 and above \(documentation\) \(documentation to create your romset\) 
>* Mame 2003-plus is an advanced version of mame 2003 offering additional options missing from mame 2003 and additional games. 
>* Consult the arcade documentation
>
>#### Your RPI in a box 
>
>* Make sure you have good ventilation
>* A good power cable 
>* If you have any concerns, take your RPI out of your box and test recalbox 6 vanilla.
>
>### Our advices 
>
>* Have a backup of your recalbox on your PC or external hard drive
>* Using removable media \(usb stick or external hard drive\) you will quickly understand that a reinstallation is faster. 
>* Use an external scrapper 
>* Having 2 microsd 8GB is enough for the system \(one for the stable version, another for your tests, or beta tests\) hence the interest to have its roms on removable media 
>* Install heat sinks or fan if necessary, especially if 
>  * If you overlock your CM 
>  * If your recalbox is in a case.
>
>## Starting the Update
>
>{% hint style="info" %}
> ****The recalbox update can be done via the frontend menu.
>{% endhint %}
>
>* Configure the wifi or plug an ethernet cable on the recalbox
>* Press Start and select "SYSTEM SETTINGS" with A
>* "UPDATES" and "START UPDATE"
>* After the update, the system will **reboot.**
>
>{% hint style="danger" %}
>**Warning :**   
>If you are using a version of Recalbox **earlier than version 6.0,** it is **not possible** to perform an Update **automatically.**   
>  
>You will need to perform a **complete reinstall** to take advantage of the latest version available.
>
>In order to proceed to the update process and **keep** your settings, backups, roms and bios.
>
{.is-info}

