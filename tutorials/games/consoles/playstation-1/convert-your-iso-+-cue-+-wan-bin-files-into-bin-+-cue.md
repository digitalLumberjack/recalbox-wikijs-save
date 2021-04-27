# Convert your ISO + CUE + WAN/BIN files into BIN + CUE


>**Informations :**
>
>SegaCD or PSX games can use different formats:
>
>* iso+cue with tracks using wav or bin formats
>* iso
>* bin+cue
>* ccd+img+sub
>* bin alone
>{% endhint %}
>
>**Exemple:**
>
>```text
>Wonder Dog (1993)(Sega)(PAL)(Track 01 of 21)[!].iso
>Wonder Dog (1993)(Sega)(PAL)(Track 02 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 03 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 04 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 05 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 06 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 07 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 08 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 09 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 10 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 11 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 12 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 13 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 14 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 15 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 16 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 17 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 18 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 19 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 20 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)(Track 21 of 21)[!].wav
>Wonder Dog (1993)(Sega)(PAL)[!].cue   
>
>Rockman 8 - Metal Heroes (Japan) (Track 1).bin   
>Rockman 8 - Metal Heroes (Japan) (Track 2).bin   
>Rockman 8 - Metal Heroes (Japan) (Track 3).bin   
>Rockman 8 - Metal Heroes (Japan) (Track 4).bin   
>Rockman 8 - Metal Heroes (Japan).cue
>```
>
>There is a technique to convert iso+cue with wav files for anyone who doesn't want to create folders to contain all game files.
>
>{% hint style="info" %}
>**Note:**
>
>This technique is valid for PSX and SEGACD.
>
{.is-info}

* Download [Daemon Tools Lite](https://daemon-tools.cc/products/dtLite) \(free\).
* Install the software.
* Select the disc files you would like to convert then click on the `+` sign.
  * Select the \*.CUE file then press `Enter`. OR
  * Do a right click and select `Mount` in the contextual menu to create a virtual disk.
* Download [ImgBurn](https://imgburn.com).
* Install the software.
* Open the same software.
* Click on the `Create image file from disk` button.
* Select the virtual disk as source.
* Select the destination folder to create BIN and CUE files.
* Click on `Read` button and wait.

Once the conversion is done, you can unmount the virtual disk \(right click to the icon in **Daemon Tools** then click on `Unmount`\).

