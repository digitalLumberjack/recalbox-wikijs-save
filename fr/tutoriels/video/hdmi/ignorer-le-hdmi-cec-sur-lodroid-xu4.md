---
title: Ignorer le HDMI CEC sur l'Odroid XU4
---

# Ignorer le HDMI CEC sur l'Odroid XU4

Par défaut, HDMI CEC est activé sur Odroid XU4. Cela signifie que la carte peut être éteinte automatiquement lorsque vous éteignez votre téléviseur / changer de source HDMI. Ceci n'est pas recommandé pour Recalbox car cela peut corrompre le système.

Voici une solution de contournement pour désactiver cette fonction et ignorer les commandes HDMI CEC.

1. Connectez-vous à votre XU4 par SSH et tapez :

```text
export TERM=xterm
mount -o remount,rw /boot/
cd /boot/
nano boot.ini
```

Ajoutez ceci juste après `setenv fdtbin exynos5422-odroidxu3.dtb`:

```text
# --- HDMI CEC Configuration ---
# ------------------------------------------
setenv cecenable "false" # false or true
# set to true to enable HDMI CE
```

Ajoutez ceci juste après `fatload mmc 0:1 ${fdtbin_addr_r} ${fdtbin}`:

```text
fdt addr 0x44000000
if test "${cecenable}" = "false"; then fdt rm /cec@101B0000; fi
```

Votre fichier `boot.ini` devrait être comme ceci :

```text
ODROIDXU-UBOOT-CONFIG

# U-Boot Parameters (DO NOT MODIFY)
setenv version 3.10
setenv zimage zImage
setenv fdtbin exynos5422-odroidxu3.dtb

# --- HDMI CEC Configuration ---
# ------------------------------------------
setenv cecenable "false" # false or true
# set to true to enable HDMI CEC

setenv zimage_addr_r 0x40008000
setenv fdtbin_addr_r 0x44000000

setenv fdt_high "0xffffffff"

# Default boot argument
setenv bootrootfs "root=/dev/mmcblk0p2 rootwait ro"
setenv console "console=ttySAC2,115200n8 consoleblank=0 vt.global_cursor_default=0"

setenv bootargs "${bootrootfs} ${console}"

# boot commands
fatload mmc 0:1 ${zimage_addr_r} ${zimage}
fatload mmc 0:1 ${fdtbin_addr_r} ${fdtbin}

fdt addr 0x44000000
if test "${cecenable}" = "false"; then fdt rm /cec@101B0000; fi

bootz ${zimage_addr_r} - ${fdtbin_addr_r}"
```

1. Sauvegardez et quittez, puis redémarrez.

