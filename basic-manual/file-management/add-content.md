# Add content

## Add games

You just need to **copy** your roms files into the folder **corresponding to the desired console** \(Example:`share/roms/snes` for Super Nintendo\).

You can use compressed ROMs \(.zip, .7z\) or uncompressed ROMs, **depending of the emulato**r.


>**Information:**
>
>For more information on the **formats of roms supported** by an emulator, **refer to the "Readme" file** present **in each roms folder.**
{.is-info}

To update the game list, go to **Menu**, **Interface options** and **Update gamelist.**

Do not hesitate to come and talk about your list of favorite games on the [Recalbox forum](https://forum.recalbox.com/category/5/international). 


>**Attention:**
>
>**Arcade**
>
> If you want to add **arcade games** to your recalbox, and / or, to learn how to check your romset, see the tutorials: [ClrmamePro Tutorial](https://recalbox.gitbook.io/tutorials/utility/rom-management/clrmamepro-tutorial) and [MD5SUM​ Tutorial](https://recalbox.gitbook.io/tutorials/utility/rom-management/md5sum-tutorial-check-the-md5-checksum-of-a-rom-or-bios).
>
>You can also activate [NeoGeo Unibios ](/tutorials/games/consoles/neo-geo/unibios)to get more options in your games.
{.is-danger}

### ​Add BIOS


>Some emulators require a BIOS to emulate games correctly.
{.is-info}

* If you want to add a BIOS to your system, open the BIOS folder shared by Samba or go directly to **`/recalbox/share/bios/`**
* Your **"BIOS names" and "CRC" code** must match the list in the Web Manager.

To verify **the checksum of a BIOS,** see the "[Tutorial MD5SUM](https://recalbox.gitbook.io/tutorials/utility/rom-management/md5sum-tutorial-check-the-md5-checksum-of-a-rom-or-bios)" page


>**Attention:**
>
>**Neo-Geo:** It is necessary to add the BIOS **neogeo.zip** inside the rom folder associated with the emulator used:  
>**/recalbox/share/roms/neogeo or /recalbox/share/roms/fbneo**
>
>**Neo-Geo CD:** It is necessary to add the BIOS **neogeo.zip** and **neogeocd.zip** inside the folder:  
>**/recalbox/share/bios**
{.is-danger}

**Example:**

The BIOS name and checksum must be the same as below \(for example, neogeo.zip must come from the requested romset version\):

```text
FBA and FBA Libretro
798e5538be8b6557e7c4529f52d2938c  neogeo.zip
Mame (Pimame4all)
12f370a3fc42c3e413c4a0771d6d089f  neogeo.zip
```

