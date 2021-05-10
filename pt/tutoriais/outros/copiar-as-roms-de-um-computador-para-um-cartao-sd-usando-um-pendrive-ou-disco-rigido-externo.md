---
title: Copiar as ROMs de um computador para um cartão SD usando um pendrive \(ou disco rígido externo\)
---

# Copiar as ROMs de um computador para um cartão SD usando um pendrive \(ou disco rígido externo\)

Se o seu sistema operacional não permite que você copie diretamente suas roms para o cartão SD, você pode primeiro copiá-los do seu computador para um dispositivo USB e, em seguida, fazer o mesmo do dispositivo USB para o cartão SD executando RecalboxOS.

Para fazer isso, siga as seguintes etapas:

1. Formate sua unidade USB em FAT32, NTFS ou EXT4. Compatível com ExFAT desde Recalbox 4.1.
2. Crie em seu dispositivo USB uma pasta chamada `share`, dentro dela, uma outra pasta chamada `roms` e copie suas pastas rom \(cheias de roms\) do seu computador para a pasta ROM que você acabou de criar no dispositivo USB.
3. Faça [acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) no seu Recalbox
4. Se você planeja transferir scrapes, pare o EmulationStation com o comando `/etc/init.d/S31emulationstation stop`
5. Liste as partições montadas com o comando `df -h`
6. Conecte sua unidade USB em seu Raspberry Pi e execute `df -h` novamente para encontrar a partição recém-montada. Neste caso, a unidade USB foi montada em `/media/usb0`.
7. Para copiar seus roms, execute o seguinte comando: `cp -rv /media/usb0/share /recalbox/` e aguarde a conclusão. Dependendo de quantas ROMs você está copiando, isso pode demorar um pouco. Você verá o símbolo `#` quando terminar.
8. Finalmente, digite `reboot`

