---
title: Odroid XU4 : Ignoring HDMI CEC
---

# Odroid XU4 : Ignoring HDMI CEC

By default, HDMI CEC is enabled on Odroid XU4. This means that the card can be turned off automatically when you turn off your TV / change HDMI source. This is not recommended for the Recalbox as it may corrupt the system.

Here's a workaround to disable this feature and ignore the HDMI CEC controls.

1. Connect to your XU4 via SSH
2. Type in :

```text
export TERM=xterm
mount -o remount,rw /boot/
cd /boot/
nano boot.ini
```

Add the following lines after `setenv fdtbin exynos5422-odroidxu3.dtb`:

```text
# --- HDMI CEC Configuration ---
# ------------------------------------------
setenv cecenable "false" # false or true
# set to true to enable HDMI CE
```

Then add the following lines after : `fatload mmc 0:1 ${fdtbin_addr_r} ${fdtbin}`:

```text
fdt addr 0x44000000
if test "${cecenable}" = "false"; then fdt rm /cec@101B0000; fi
```

Your `boot.ini` file should look like this :

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

1. Save & quit,
2. Reboot.

