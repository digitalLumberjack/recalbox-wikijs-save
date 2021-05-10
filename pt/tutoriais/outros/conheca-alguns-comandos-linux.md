---
title: Conheça alguns Comandos Linux
---

# Conheça alguns Comandos Linux

## 1- Comandos comuns​ <a id="1-comandos-comuns"></a>

Aqui está uma **lista de comandos do Linux** que serão úteis para você **navegar** no **RecalboxOS** via **terminal ou putty**.

​

**Comando ls**

Seu equivalente no Windows é DIR. Ele permite que você liste o conteúdo de uma pasta. Consulte as opções disponíveis [nesta página](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-ls/).

**Comando cd**

Seu equivalente no Windows é CD. Permite que você mude de diretório \(CD = Change Directory\) Consulte as opções disponíveis [nesta página](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando/).

**Comando cp**

Seu equivalente no Windows é COPY. Permite copiar arquivos ou diretórios Consulte as opções disponíveis [nesta página](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-cp/).

**Comando mv**

Seu equivalente no Windows é mover ou ren. Permite mover ou renomear um arquivo ou diretório Consulte as opções disponíveis [nesta página](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-mv/).

**Comando mkdir**

Seu equivalente no Windows é mkdir ou md. Ele permite que você crie um diretório vazio. Consulte as opções disponíveis [nesta página](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-mkdir/).

**Comando rmdir**

Seu equivalente no Windows é rmdir ou rd. Ele permite que você exclua um diretório. Consulte as opções disponíveis [nesta página](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-rmdir/).

**Comando nano**

Nano é um pequeno editor de texto. Consulte as opções disponíveis [nesta página](https://nano-editor.org/dist/latest/nano.html).

**Comando chmod**

Permite que você modifique as permissões de acesso a um arquivo

syntaxe : `chmod 0775 /caminho/arquivo`

Consulte as opções disponíveis [nesta página](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-chmod/).

**Comando wget**

Permite baixar uma site disponível na internet. Consulte as opções disponíveis [nesta página](https://www.linuxforce.com.br/comandos-linux/comandos-linux-comando-wget/).

## 2 - Comandos específicos​ <a id="2-comandos-especificos"></a>

### Verifique a temperatura do processador Raspberry <a id="verifique-a-temperatura-do-processador-raspberry"></a>

Para verificar a **temperatura do processador** \(CPU\), execute o seguinte comando: `cat /sys/class/thermal/thermal_zone0/temp`

Em seguida, **divida o resultado por 1000** para obter a temperatura **em Celsius**.​

### Verifique as configurações de overclocking aplicadas <a id="verifique-as-configuracoes-de-overclocking-aplicadas"></a>

Para verificar os **valores de overclocking aplicados**, execute o seguinte comando: `cat /boot/config.txt`

Os parâmetros de seu interesse estão **no final do arquivo** \(veja o exemplo abaixo\):

```text
arm_freq=1050
core_freq=525
sdram_freq=480
force_turbo=0
over_voltage=4
over_voltage_sdram=2
gpu_freq=350
```

### ​Evite reiniciar o sistema se o emulador N64 \(Mupen64\) travar <a id="evite-reiniciar-o-sistema-se-o-emulador-n-64-mupen-64-travar"></a>

Se você encontrar problemas de travamento/congelamento com o emulador N64 \(Mupen64\), devido em particular a problemas de compatibilidade com ROMs, você pode facilmente "matar" o emulador em vez de reiniciar o Rapsberry. Para fazer isso, você deve identificar o identificador do processo Mupen64 com o seguinte comando: `ps aux | grep mupen64`.

Você deve obter uma lista semelhante a:

```text
**26193** root     mupen64plus --corelib /usr/lib/libmupen64plus.so.2.0.0 --gfx /usr/lib/mupen64plus/mupen64plus-video-gliden64.so --configdir /recalbox/configs/mupen64/ --datadir /recalbox/configs/mupen64/ /recalbox/share/roms/n64/007 - GoldenEye (Europe).n64
26196 root     grep mupen64
```

Nesse caso, o ID do processo Mupen64 \(PID\) é **26193**. Agora você pode eliminar o processo Mupen64 com o seguinte comando: `kill -1`

Ou para o nosso exemplo: `kill -1 26193`

Assim que o processo for encerrado, você retornará automaticamente à Emulationstation.

### ​Parar/Iniciar o Emulationstation <a id="parar-iniciar-o-emulationstation"></a>

Para **atualizar a lista de ROMS**, por exemplo, ou para **atualizar as imagens de jogos** recém-copiados de seu PC, você terá que parar e reiniciar o Emulationstation:

* Parar:

  `es stop` `/etc/init.d/S31emulationstation stop`

* Reiniciar/Iniciar:

  `es start` `/etc/init.d/S31emulationstation start`

