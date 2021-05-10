---
title: Crie um Dual Boot Raspbian / Recalbox
---

# Crie um Dual Boot Raspbian / Recalbox

Zhitom compartilhou sua experiência para criar um dual boot com raspbian e recalbox-OS no Noobs

1. Baixe o **Noobs** "Offline and network install" \(contém a última versão do Raspbian\) no seguinte endereço: [https://www.raspberrypi.org/downloads/](https://www.raspberrypi.org/downloads/)  
2. Descompacte o arquivo zip e copie todos os arquivos para a raiz do cartão SD formatado anteriormente, no Windows, com o software **SDFormatter** : [https://www.sdcard.org/downloads/formatter/eula\_windows/SDCardFormatterv5\_WinEN.zip](https://www.sdcard.org/downloads/formatter/eula_windows/SDCardFormatterv5_WinEN.zip) ou no **Linux** , crie uma partição \(com fdisk, por exemplo\), em seguida, formate-a: \`sudo mkfs.fat /dev/sdX\` onde \`/dev/sdX\` corresponde à partição criada anteriormente, então monte a partição: \`sudo mount /dev/sdX /mnt/yourmountpoint\`
3. Baixe a versão mais recente do **Recalbox** no seguinte endereço: [https://github.com/digitalLumberjack/recalbox-os/releases/latest](https://archive.recalbox.com/)
4. Descompacte o arquivo e copie a pasta « **recalboxOS-rpi2** » \(ou outro “recalboxOS” dependendo da versão que você tem, por exemplo **recalboxOS-rpi3** para um Raspberry Pi 3\) localizado na pasta “os ”para cole-o na pasta "os" na raiz do cartão SD. No Linux, uma vez feito isso, não se esqueça de “desmontar” o cartão SD com \`sudo umount /mnt/yourmountpoint\`
5. O cartão SD está pronto, basta inseri-lo no Raspberry!
6. Na primeira inicialização após a tela inicial, você tem uma janela que aparece com a escolha do sistema operacional a ser instalado. Marque Raspbian e Recalbox e clique em « Install » \(ou digite i\). Você só precisa esperar cerca de dez minutos para que a instalação seja concluída.
7. Ao reiniciar após a tela inicial, uma nova janela aparece com a escolha do sistema operacional a ser iniciado. Escolha Raspbian ou Recalbox e pronto!

Por padrão, o tempo da janela para a seleção do sistema operacional é de dez segundos e, após esse tempo, o sistema iniciará automaticamente o último osso inicializado anteriormente.


>**Informação:**
>
>Ao fazer Dual Boot em um cartão µsd de 16 GB, a alocação de espaço livre padrão é a seguinte: 4,1 GB para raspbian e 3 GB para recalbox.
>
>Ao fazer Dual Boot em um cartão µsd de 32 GB, a distribuição padrão de espaço livre é a seguinte: 1,5 GB para NOOBS \(instalação + imagens de recuperação\), 16,1 GB para raspbian e 14,1 GB para recalbox.
{.is-info}

