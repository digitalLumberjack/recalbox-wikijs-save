---
title: Libretro Mednafen\_PSX\_HW
---

# Libretro Mednafen\_PSX\_HW

[Beetle PSX](https://github.com/libretro/beetle-psx-libretro)  est un fork du module PSX de [Mednafen](https://mednafen.github.io/) pour Libretro, il fonctionne actuellement sous Linux, macOS et Windows, ce core est disponible en version `mednafen-psx-hw` qui exige OpenGL 3.3 pour le moteur de rendu OpenGL.

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv2**](https://github.com/libretro/beetle-psx-libretro/blob/master/COPYING).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI4-100 | ODROID XU4 | PC x86 | PC x86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ |

## ![](./cogwheel-145804_640.png) Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Redémarrage | ✔ |
| Sauvegardes | ✔ |
| Sauvegardes d'état | ✔ |
| Options du core | ✔ |
| RetroAchievements | ✔ |
| Cheats RetroArch | ✔ |
| Contrôles | ✔ |
| Remapping | ✔ |
| Multi-Mouse | ✔ |
| Vibration | ✔ |
| Contrôle de disque | ✔ |

## ![](./tqfp32.svg) BIOS

### Liste des bios obligatoires

| **Nom de fichier** | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| scph5500.bin | BIOS PS1 japonais - requis pour les jeux japonais | 8dd7d5296a650fac7319bce665a6a53c | ❌ |
| scph5501.bin | BIOS PS1 américain - requis pour les jeux américains | 490f666e1afb15b7362b406ed1cea246 | ❌ |
| scph5502.bin | BIOS PS1 européen - requis pour les jeux européens | 32736f17079d0b2b7024407c39bd3050 | ❌ |

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 🗒 scph5500.bin
> > > >
> > > > 🗒 scph5501.bin
> > > >
> > > > 🗒 scph5502.bin

## \*\*\*\*![](./rom-30098_640.png) **Roms**

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .bin/.cue
* .bin/.toc
* .m3u
* .img/.ccd/.sub
* .exe
* .pbp
* .chd

### Emplacement

Placez les isos comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 roms
> > >
> > > > 📁 psx
> > > >
> > > > > 🗒 fichier.cue


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configuration personnalisé lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/fr/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder aux options

Vous pouvez configurer diverses options de deux façons différentes.

* Via le Menu Retroarch :

> 📁Menu RetroArch
>
> > 📁Options du core
> >
> > > 🧩Name\_option

* Via le fichier `retroarch-core-options.cfg`:

> 📁recalbox
>
> > 📁share
> >
> > > 📁system
> > >
> > > > 📁configs
> > > >
> > > > > 📁retroarch
> > > > >
> > > > > > 📁cores
> > > > > >
> > > > > > > 🧩**retroarch-core-options.cfg**

### Options du core

`beetle_psx_hw_adaptive_smoothing = "enabled"  
beetle_psx_hw_analog_calibration = "disabled"  
beetle_psx_hw_analog_toggle = "disabled"  
beetle_psx_hw_cd_access_method = "async"                                   beetle_psx_hw_cd_fastload = "4x"  
beetle_psx_hw_cpu_freq_scale = "120%"  
beetle_psx_hw_crop_overscan = "enabled"  
beetle_psx_hw_depth = "dithered 16bpp (native)" beetle_psx_hw_display_internal_fps = "disabled"  
beetle_psx_hw_display_vram = "disabled"  
beetle_psx_hw_dither_mode = "1x(native)"  
beetle_psx_hw_enable_memcard1 = "enabled"  
beetle_psx_hw_enable_multitap_port1 = "disabled" beetle_psx_hw_enable_multitap_port2 = "disabled"  
beetle_psx_hw_filter = "nearest"  
beetle_psx_hw_frame_duping = "disabled"                               beetle_psx_hw_gpu_overclock = "1x(native)"  
beetle_psx_hw_gte_overclock = "disabled"  
beetle_psx_hw_gun_cursor = "Cross"  
beetle_psx_hw_gun_input_mode = "Lightgun"  
beetle_psx_hw_image_crop = "disabled"  
beetle_psx_hw_image_offset = "disabled"  
beetle_psx_hw_initial_scanline = "0"  
beetle_psx_hw_initial_scanline_pal = "0"  
beetle_psx_hw_internal_resolution = "4x"  
beetle_psx_hw_last_scanline = "239"  
beetle_psx_hw_last_scanline_pal = "287"  
beetle_psx_hw_lineRender = "default"  
beetle_psx_hw_mdec_yuv = "disabled"  
beetle_psx_hw_mouse_sensitivity = "100%"  
beetle_psx_hw_msaa = "1x"  
beetle_psx_hw_negcon_deadzone = "0"  
beetle_psx_hw_negcon_response = "linear"  
beetle_psx_hw_pgxp_mode = "memory only"  
beetle_psx_hw_pgxp_texture = "disabled"  
beetle_psx_hw_pgxp_vertex = "enabled"  
beetle_psx_hw_renderer = "hardware"  
beetle_psx_hw_renderer_software_fb = "enabled"  
beetle_psx_hw_shared_memory_cards = "disabled"  
beetle_psx_hw_skip_bios = "disabled"  
beetle_psx_hw_super_sampling = "disabled" beetle_psx_hw_use_mednafen_memcard0_method = "libretro" beetle_psx_hw_widescreen_hack = "disabled"  
beetle_psx_hw_wireframe = "disabled"`

## \*\*\*\*![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) **Liens externes**

* **Github utilisé** : [https://github.com/libretro/beetle-psx-libretro/](https://github.com/libretro/beetle-psx-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/beetle\_psx\_hw/](https://docs.libretro.com/library/beetle_psx_hw/)

