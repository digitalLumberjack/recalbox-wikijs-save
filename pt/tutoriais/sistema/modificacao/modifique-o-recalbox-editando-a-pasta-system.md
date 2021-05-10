---
title: Modifique o Recalbox editando a pasta System
---

# Modifique o Recalbox editando a pasta System

O arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) permite configurar e personalizar seu Recalbox, mas você pode ir mais longe editando a **pasta System**.

Esta pasta pode ser interna \(no cartão micro-SD\)`/recalbox/share/system` ou, em um dispositivo externo \(chave usb\) na pasta `/recalbox/system`.

Esta pasta está disponível:

* Via Samba \(compartilhamento do Windows\) em `smb://recalbox.local/system` \(`\\recalbox.local/system` no Windows Explorer\)
* Via ssh \(`/recalbox/share`\) ou diretamente conectando o cartão micro-SD ou o dispositivo externo em um SO compatível com ext4

​

## Estrutura da pasta System​ <a id="estrutura-da-pasta-system"></a>

Nem todas essas pastas e arquivos estão presentes na pasta system por padrão.

Crie-as se quiser personalizá-las.

```text
bios
cheats
extractions
kodi 
roms
   /snes
   /...
saves
screenshots
shaders
system
   /bluetooth
   /configs
   /logs
   /recalbox.conf
   /upgrade
   /ssh
   /.config
   /.emulationstation
      /es_input.cfg
      /es_settings.cfg
      /es_systems.cfg
      /themes
   /.kodi
   /.ssh
```

## Utilização​ <a id="utilizacao"></a>

Os arquivos contidos na **pasta System** sempre têm prioridade sobre o diretório Recalbox padrão. **Quando um arquivo não for encontrado** na pasta do sistema, a pasta Recalbox\* padrão será usada.

**A pasta Recalbox padrão** tem a mesma estrutura da **pasta system**, permitindo que você a use facilmente para copiar arquivos, se necessário.

**A pasta Recalbox padrão** está disponível:

* Via ssh \(`/recalbox/share_init`\)​

| Pasta ou arquivo | Utilização | Inicialização na pasta System |
| :--- | :--- | :--- |
| bios | _Pasta das bios de emulação_ | copiada |
| cheats | _Pasta dos arquivos de trapaça_ | mesclada |
| extractions |  | copiada |
| kodi | _Músicas e vídeos_ | copiada |
| roms/snes\(1\) | _Roms do sistema de emulação_ | copiada |
| saves | _Saves de emulação_ | copiada |
| screenshots | _Capturas de telas_ | copiada |
| shaders | _Shaders/Sombreamentos_ | sistema |
| system/bluetooth | _Periféricos Bluetooth pareados_ | copiada |
| system/configs | _Configurações automáticas de emulação e do KODI_ | a melhor para Kodi, copiada para outros |
| system/logs | _Identificadores do Recalbox_  | copiada |
| system/recalbox.conf | _Arquivo de configuração do Recalbox_ | copiada |
| system/upgrade | _Localização para inicialização e root.tar.xz para atualização_ | criada conforme necessário |
| system/ssh | _Senha do servidor ssh do Recalbox_ | copiada |
| system/.config | _Configurações de aplicativos \(lirc\)_ | copiada |
| system/.emulationstation/es\_input.cfg | _Configuração do joystick_ | copiada |
| system/.emulationstation/es\_settings.cfg | _Configuração do EmulationStation_ | copiada |
| system/.emulationstation/es\_systems.cfg | _Definição dos Emuladores no Recalbox_ | a melhor |
| system/.emulationstation/themes | _Temas do EmulationStation_ | mesclada |
| system/.kodi | _Arquivos KODI_ | copiada |
| system/.ssh | _Senha do cliente ssh_ | copiada |


>**Legenda:**
>
>**\(1\)**: Quando novos sistemas estão disponíveis, uma nova pasta é criada. Se você quiser redefinir as ROMs de um sistema, exclua a pasta e reinicie.
>
>**copiada**: na inicialização, se a pasta não existir, ela é criada a partir da **pasta Recalbox padrão**. Você pode excluí-la para redefini-lo. Observe que quase todas as pastas copiadas estão vazias ou contêm apenas um arquivo leia-me.
>
>**mesclada**: as duas pastas, a **pasta System** e a **pasta padrão Recalbox** estão visíveis.
>
>**padrão**: a funcionalidade não é encerrada. Por exemplo, a personalização de shaders/sombreadores nem sempre é possível. Apenas a **pasta system** é levada em consideração.
>
>**a melhor**: use **a pasta system**, se houver, ou volte para a **pasta padrão do Recalbox**.
>
>"Mesclada" e "melhor" permite que os desenvolvedores do Recalbox atualizem os arquivos do sistema. No entanto, nem sempre isso é desejado ou possível sem muito trabalho.
{.is-success}

