---
description: (Page only available in English)
---

# Compatible PCs


>**Information :**
>
>If you **don't see your PC** in the charts, it **hasn't been tested yet**.  
>****You can also test a hardware with the latest version if it has not been done, so that we can update the information in the charts. \(Please inform us if that's the case\).
>
>* Specify the **brand** and **model.** 
>* If it' s an assembled PC, specify the processor and graphics processor. 
>* Do not hesitate to add **details about the overall performance** of your configuration. 
>* If you have any problem or a comment, Please let us know.
{.is-info}

## PC Model <a id="pc-model"></a>

### Dell

| Name | Status | Recalbox version | Notes |
| :---: | :---: | :---: | :---: |
| Dell Optiplex 390 i5-2400 3.10GHz | ✅ | 6.0 Rc3 | 100% Compatible |
| Dell Optiplex 990 i3 2100 | ✅ | 13.07.18 | 100% Compatible |
| Dell Optiplex 990 USFF i5 2400S 2.5GHZ | ✅ | 6.0.1 | 100% Compatible |
| Dell Optiplex 3020 micro i3 4150T | ✅ | 6.0 Rc3 | 100% Compatible |



### Intel

| Name | Status | Recalbox version | Notes |
| :---: | :---: | :---: | :---: |
| Intel NUC7i3BNK | ✅ | 4.1 | i3-7100U / HD Graphics 620 / BIOS 0036:OK / BIOS 0052:No temp probe |
| Intel NUC7i5BNH | ✅ | 6.1 | Fully compatible, Around 60 FPS for all consoles, CPU Core i5-7260U, graphics Intel IRIS Plus 640 |
| Intel NUC6I7KYK | ✅ | 4.1 | Fully compatible, Around 60 FPS for all consoles, latest bios 0050, all hardwares are ok: CPU Core i7-6770HQ, graphics Intel IRIS PRO 580 fully supported, wifi, bluetooth, sound, usbs, SSD SATA Samsung 1TB |
| Intel NUC8i7BEH | ✅ | 6.1 | Fully compatible, Around 60 FPS for all consoles, CPU Core i7-8559U, graphics Intel IRIS Plus 655 |

### Miscellaneous

| Name | Status | Recalbox version | Notes |
| :---: | :---: | :---: | :---: |
| HP Slim Desktop 270-P026 i3-7100T | ✅ | 18.07.13 | 100% Compatible |
| Laptop 17.3" MSI GP72M 7RDX-871XFR | ✅ | 4.1 | Around 60 FPS for all consoles on x64 version with defaults parameters, latest bios flashed, all hardwares are ok: CPU Core i7-7700HQ, graphics Intel HD Graphics 630 fully supported, wifi, bluetooth, sound \(on laptop speakers+headphones+HDMI\), usbs, SSD SATA Samsung 1TB, all ok! Since it have a battery, games are no longer interrupted ! \(only drawback is that it doesn't support the GPU Nvidia GTX 1050 yet due to the current used linux kernel\) |
| Taichi  Z270 + I5 7500 | ✅ | 4.1 | Around 60 FPS for all consoles on x64 |
| ZOTAC  ZBOX Nano AD10 | ✅ | 4.1 | Wii/NGC ok but not playable |



### Apple Mac Model

| Name | Status | Recalbox version | Notes |
| :---: | :---: | :---: | :---: |
| MacBook Pro  \(13-inch, Early 2011\) | ✅ | 4.1 | 100% Compatible |
| iMac \(21.5-inch, Mid 2011\) | ✅ | 4.1 | 100% Compatible, some minor graphic bugs on the menu |
| Mac Pro \(Late 2013\) | ❌ | 4.1 | Not Working. Can't even boot |

## CPU <a id="cpu"></a>

### Intel

| Name | Status | Recalbox version | Notes |
| :---: | :---: | :---: | :---: |
| Intel i3-4150T 3.00GHz | ✅ | 6.0 Rc3 | Around 60 FPS for all consoles on x64 version with default parameters dolphin work great with default parameters |
| Intel Core i3-7100T | ✅ | 18.07.13 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel Core i3-7100U | ✅ | 4.1 | ​ |
| Intel Core i5-2400 3.10 GHz | ✅ | 4.1 | Working fine for all emulators except for gamecube's and wii's emulators \(best perfomance with graphics card\) |
| Intel Core i5-2400S 2.5 GHZ | ✅ | 7.0.1 |  |
| Intel Core i5-3570K 3.40 GHz | ✅ | 6.0 Rc3 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel Core i5-4570S | ✅ | ​4.1 |  |
| Intel Core i5-6500 | ✅ | ​4.1 |  |
| Intel Core i5-7500 | ✅ | ​4.1 |  |
| Intel Core i7-2600K | ✅ | 4.1 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel Core i7-6770HQ | ✅ | 4.1 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel Core i7-7700HQ | ✅ | 4.1 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel Pentium G2130 3.20GHZ | ✅ | 4.1 | ​ |
| Intel G4600 | ✅ | 18.04.20 | Around 60 FPS for all consoles on x64 version with default parameters |



### Amd

| Name | Status | Recalbox version | Notes |
| :---: | :---: | :---: | :---: |
| AMD X2 4850B | ✅ | 4.1 |  |

## GPU


>**Warning :**  
>Keep in mind that a GPU driver is not enough, the linux kernel contained in Recalbox must also be able to manage the device.
{.is-danger}

### Nouveau

Nouveau is a project of the X.Org foundation and Freedesktop.org aimed at producing free drivers for Nvidia graphics cards by reverse engineering

Nouveau is based on the free \(but obscured\) nv drivers maintained by Nvidia for 2D management. 

To support OpenGL, the project used Mesa 3D, but changed in February 2008 for its successor Gallium3D4.5. OpenCL support also goes through Gallium3D. 

#### Process used 

The project uses the reverse engineering technique on Nvidia graphics cards by studying the behavior of current 3D Linux drivers, supplied by the manufacturer \(under proprietary license\), without touching the drivers themselves. This way of doing things allows the project to avoid any conflict with the Nvidia license.

* According to the [nouveau features page](https://nouveau.freedesktop.org/wiki/FeatureMatrix/)
* Compatibility with NVIDIA \([NVidia codenames](https://nouveau.freedesktop.org/wiki/CodeNames/)\)
* Recalbox current Nouveau driver \(Version 1.0.15\)


>**Notes:**  
>Nouveau drivers are used by default, when an Nvidia graphics card or circuit is detected but not compatible with official drivers.
{.is-warning}



### **NVIDIA**

Nvidia graphics cards are compatible via **the official driver** in version 460.67 of which here is [the compatibility list](https://gitlab.com/recalbox/recalbox-hardware/blob/master/videocard/nvidiacheckcompatibility-460.txt).

### Intel

List of graphics card integrated into processor.

Their [source code website](https://cgit.freedesktop.org/xorg/driver/xf86-video-intel/tree/?id=b57abe20e81f4b8e4dd203b6a9eda7ff441bc8ce) at the current Recalbox version isn't very explicit regarding supported GPUs.

| GPU | Status | Recalbox version | Notes |
| :---: | :---: | :---: | :---: |
| Intel® HD Graphics 630 | ✅ | 4.1 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel® HD Graphics 3000 | ✅ | 4.1 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel® Iris™ Plus Graphics 620 | ✅ | 4.1 | ​ |
| Intel® Iris™ Pro Graphics 580 | ✅ | 4.1 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel® HD Graphics 4600 | ✅ | 4.1 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel® HD Graphics 4400 | ✅ | 6.0 rc3 | Around 60 FPS for all consoles on x64 version with default parameters |
| Intel® HD Graphics 4850 | ✅ | 6.0 DragonBlaze | Around 60 FPS for all consoles on x64 version with default parameters |



### AMD

Their [source code website](https://cgit.freedesktop.org/xorg/driver/xf86-video-amdgpu/tree/?h=xf86-video-amdgpu-1.4.0) at the current Recalbox version isn't very explicit regarding supported GPUs.

| GPU | Status | Recalbox version | Notes |
| :--- | :---: | :---: | :---: |
| AMD Radeon HD 4850 512mo | ✅ | 6.0 Rc3 | work with CPU intel i5-3570K |
| AMD Radeon HD 4890 1Go | ✅ | 4.1 | ​ |
| AMD Radeon HD 6750M | ✅ | 4.1 | some minor graphic bugs on the menu |
| AMD Radeon HD 7970 3G | ❌ | 18.04.20 | Not working \(menu is very slow and unplayable\) |
| AMD Radeon HD 8280E | ❌ | 18.07.13 | Not working \(menu is very slow and unplayable\) |
| AMD Radeon Rx 480 8gb | ❌ | 6.0 RC2 | Not working \(menu is very slow and unplayable\) |

