---
title: Odroid XU4: Ignorar o HDMI CEC
---

# Odroid XU4: Ignorar o HDMI CEC

Por padrão, o HDMI CEC está ativado no Odroid XU4. Isso significa que o cartão pode ser desligado automaticamente quando você desliga a TV / muda a fonte HDMI. Isso não é recomendado para o Recalbox, pois pode danificar o sistema.

Aqui está uma solução alternativa para desativar esse recurso e ignorar os controles HDMI CEC.

1. Conecte-se ao seu XU4 via SSH
2. Digite:

   ```text
   export TERM=xterm
   mount -o remount,rw /boot/
   cd /boot/
   nano boot.ini
   ```

Adicione as linhas abaixo logo após`setenv fdtbin exynos5422-odroidxu3.dt`:

```text
# --- HDMI CEC Configuration ---
# ------------------------------------------
setenv cecenable "false" # false or true
# set to true to enable HDMI CE
```

Em seguida, adicione as seguintes linhas depois: `fatload mmc 0:1 ${fdtbin_addr_r} ${fdtbin}`:

```text
fdt addr 0x44000000
if test "${cecenable}" = "false"; then fdt rm /cec@101B0000; fi
```

Seu arquivo `boot.ini` deve ficar parecido com isso:

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

1. Salve e saia,
2. Reinicie.

