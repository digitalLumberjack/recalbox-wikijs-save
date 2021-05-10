---
title: Use um dispositivo de armazenamento USB no Recalbox
---

# Use um dispositivo de armazenamento USB no Recalbox

## Introdução <a id="introducao"></a>

Você pode usar facilmente um dispositivo de armazenamento USB \(Pen Drive, HD externo com alimentação própria, etc.\) para armazenar suas ROMs, arquivos pessoais, etc.

* Primeiro, você deve usar um dispositivo que use o seguinte sistema de arquivos: FAT32, EXT4 ou NTFS \(as taxas de transferência podem ser lentas no caso de NTFS, por isso tome cuidado\). Desde a versão 4.1, você também pode usar o sistema de arquivos EXTFAT. Certifique-se também de que o sistema de arquivos escolhido é compatível com o sistema operacional do seu PC. O RecalboxOS não formatará seu dispositivo, apenas criará novos arquivos nele.

O Recalbox pode sincronizar manualmente o seu dispositivo USB com o cartão SD. Esta etapa é opcional, mas deve ser executada antes de alterar as configurações de armazenamento USB. Aqui estão as etapas:

1. Inicie o seu Recalbox.
2. Conecte seu dispositivo USB sempre que desejar.
3. [Conecte-se em SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) com seu pi.
4. Digite `cd /recalbox/scripts`
5. O comando `./recalbox-sync.sh list` fornecerá a lista de dispositivos disponíveis. Por exemplo :

   ```text
   # ./recalbox-sync.sh list
   INTERNAL
   DEV A80A-27A5 NO_NAME
   ```

Portanto, o nome do meu PEn Drive é NO\_NAME, o número do dispositivo é A80A-27A5. Posso sincronizá-lo com 6.

```text
# ./recalbox-sync.sh sync A80A-27A5
sending incremental file list
./
.keep
bios/
bios/lisez-moi.txt
bios/readme.txt

...

sent 111,817,693 bytes  received 8,256 bytes  9,723,995.57 bytes/sec
total size is 111,758,686  speedup is 1.00
rsync error: some files/attrs were not transferred (see previous errors) (code 23) at main.c(1178) [sender=3.1.2]
```

Aí está você! Não se preocupe com erros! Agora o seu dispositivo USB contém a cópia dos dados do seu cartão SD. Você pode continuar com a próxima etapa.

## Configure o Recalbox para usar um dispositivo de armazenamento USB <a id="configure-o-recalbox-para-usar-um-dispositivo-de-armazenamento-usb"></a>

* Conecte seu dispositivo ao Recalbox e ligue-o. Uma vez na interface do Recalbox, pressione o botão Start em seu controle, vá para as Opções do Sistema e para a mídia de armazenamento. Agora selecione seu dispositivo na lista, valide e espere o sistema reiniciar. Durante esta fase de reinicialização, o recalboxOS criará na raiz do seu dispositivo, uma nova pasta chamada `recalbox` que conterá toda a estrutura de árvore de sua partição `/share`.
* Para adicionar seus arquivos \(ROMs, saves de jogos, BIOS, capinhas, etc...\) para o seu dispositivo de armazenamento, você deve desligar o Recalbox. Em seguida, conecte seu dispositivo ao PC. Tudo o que você precisa fazer é copiar seus arquivos pessoais do PC para o dispositivo, sem usar a rede local. Assim que a transferência for concluída, tudo o que você precisa fazer é reconectar o dispositivo ao seu Recalbox, ligá-lo e jogar.

Com este método, o sistema \(no cartão SD\) e a partição SHARE \(no dispositivo\) são separados. Portanto, se você fosse reinstalar seu sistema, manteria todos os seus dados de usuário. Você só terá que reconectar seu dispositivo ao Recalbox, selecioná-lo no sistema e jogar.

## O que fazer se após reiniciar o Recalbox ainda não conseguir ver o armazenamento externo? <a id="o-que-fazer-se-apos-reiniciar-o-recalbox-ainda-nao-conseguir-ver-o-armazenamento-externo"></a>

Às vezes, após selecionar o dispositivo no EmulationStation e reiniciá-lo, o Recalbox falha ao criar o sistema de arquivos nele. Em seguida, ele continua a usar os arquivos do cartão SD. Isso acontece especialmente com alguns discos rígidos que demoram para inicializar.

O que você pode fazer:

1. ​[Conecte-se em SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)
2. Digite estes comandos:

   ```text
   mount -o remount, rw /boot
   cd /boot
   nano recalbox-boot.conf
   ```

3. Adicione esta linha:`sharewait=30`
4. Salve com `Ctrl X`, `Y`, `Enter`
5. Digite `reboot` e valide, o Recalbox reiniciará.

Se isso ainda não funcionar, aumente o valor de `sharewait`.

