---
title: Configurar o Interruptor Liga/Desliga Mausberry
---

# Configurar o Interruptor Liga/Desliga Mausberry

## Introdução <a id="introducao"></a>

Os circuitos Mausberry gerenciam a ativação e desativação do Raspberry Pi usando um botão liga/desliga. Este tipo de circuito pode ser usado para usar a chave liga/desliga de um NES e seu botão RESET, por exemplo.


>**Nota:**
>
>Este tutorial é dedicado à versão v4 no Raspberry Pi 2/3 do Recalbox
{.is-info}


>**ATENÇÃO!**
>
>Se você estiver usando uma versão mais recente do que v4.0.0 beta 3, siga as instruções para a versão V4B3.
>
>Se você estiver usando uma versão anterior a v4.0.0 beta 3, siga as instruções da versão V4B2.
{.is-danger}

## ​Tutorial V4B3​ <a id="tutorial-v-4-b3"></a>

### Conexões e fiação <a id="conexoes-e-fiacao"></a>

Para conexões no Pi, use as portas GPIO 23 e 24 \(pinos 16 e 18\). O Mausberry está operacional com o GPIO23 = OUT / IN = GPIO24. Você encontrará a figura nos anexos.

### Procedimento​ <a id="procedimento"></a>

#### Pré-requisitos <a id="pre-requisitos"></a>

1. Seu Raspberry Pi deve estar conectado à rede
2. Você deve saber o endereço IP do seu Raspberry Pi. Ele pode ser encontrado no menu Recalbox. O endereço IP deve ser semelhante a:`192.168.0.49` Você também pode seguir este link:\([https://recalbox.gitbook.io/tutorials/v/portugues/rede/ip/descubra-o-seu-ip-na-rede](https://recalbox.gitbook.io/tutorials/v/portugues/rede/ip/descubra-o-seu-ip-na-rede)\)

#### Etapas <a id="etapes-1"></a>

1. Vá para a interface da web do Recalbox a partir do exemplo do seu navegador de internet: `http://192.168.0.49`
2. Clique em`Ler e editar o arquivo de configuração do Recalbox`
3. Na seção: `A - System Options` não comentadas para obter:

`# ------------ A - System Options ----------- #` `# Uncomment the system.power.switch you use` `system.power.switch=MAUSBERRY # http://mausberry-circuits.myshopify.com/pages/setup`

Salve!

## Tuto V4B2​ <a id="tuto-v-4-b2"></a>

### Conexões e fiação <a id="conexoes-e-fiacao-1"></a>

Para conexões no Pi, use as portas GPIO 20 e 21. O Mausberry está operacional com GPIO20 = OUT / IN = GPIO21. Você encontrará a figura nos anexos.

### Procedimento​ <a id="procedimento-1"></a>

#### Pré-requisitos <a id="pre-requisitos-1"></a>

1. Seu Raspberry Pi deve estar conectado à rede
2. Você deve saber o endereço IP do seu Raspberry Pi. Ele pode ser encontrado no menu Recalbox. O endereço IP deve ser semelhante a:`192.168.0.49` Você também pode seguir este link:\([https://recalbox.gitbook.io/tutorials/v/portugues/rede/ip/descubra-o-seu-ip-na-rede](https://recalbox.gitbook.io/tutorials/v/portugues/rede/ip/descubra-o-seu-ip-na-rede)\)
3. Você deve ser capaz de se conectar ao seu Recalbox via SSH. No Windows, você pode usar softwares como [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) ou [Kitty](https://www.fosshub.com/KiTTY.html)​

### ​Etapas <a id="etapas"></a>

1. Conecte-se [via SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) ao seu Recalbox
2. Vá para a pasta System&gt; `cd /recalbox/share/system/`
3. Crie um arquivo setup.sh &gt; `nano setup.sh`
4. Copie o conteúdo do anexo setup.sh
5. Salve com este atalho &gt; `Ctrl + X`
6. Crie um arquivo S99maus &gt; `nano S99maus`
7. Copie o conteúdo do anexo **Script: S99maus** &gt; `nano S99maus`
8. Salve com este atalho &gt; `Ctrl + X`
9. Você precisa mudar temporariamente o sistema que está no modo somente leitura para o modo de leitura / gravação. Para fazer isso, execute o seguinte comando: `mount -o remount, rw /` O sistema reverterá para o modo somente leitura na próxima reinicialização
10. Execute o script setup.sh &gt; `bash setup.sh`
11. Encontre o novo script &gt; `nano /recalbox/scripts/mausberry.sh`
12. Copie o arquivo S99maus na pasta /etc/init.d/ &gt; `cp /recalbox/share/system/S99maus /etc/init.d/`
13. Conceda direitos de execução ao script&gt; `chmod 775 /etc/init.d/S99maus`
14. Execute o script&gt; `/etc/init.d/S99maus start`
15. Você receberá uma mensagem de erro como esta, mas o Mausberry estará funcional: `bad -o argument ‘command'`

​

## Anexos <a id="anexos"></a>

### ​Conexões e fiação <a id="conexoes-e-fiacao-2"></a>

![](http://www.windtopik.fr/wp-content/uploads/2014/11/RPI-GPIO-N-.png)

### Script : setup.sh <a id="script-setup-sh"></a>

```text
echo '#!/bin/bash

#C'est la broche GPIO connectée au fil de l'interrupteur marqué OUT
GPIOpin1=20

#C'est la broche GPIO connectée au fil de l'interrupteur marqué IN
GPIOpin2=21

echo "$GPIOpin1" > /sys/class/gpio/export
echo "in" > /sys/class/gpio/gpio$GPIOpin1/direction
echo "$GPIOpin2" > /sys/class/gpio/export
echo "out" > /sys/class/gpio/gpio$GPIOpin2/direction
echo "1" > /sys/class/gpio/gpio$GPIOpin2/value
while [ 1 = 1 ]; do
power=$(cat /sys/class/gpio/gpio$GPIOpin1/value)
if [ $power = 0 ]; then
sleep 1
else
poweroff
fi
done' > /recalbox/scripts/mausberry.sh
chmod 777 /recalbox/scripts/mausberry.sh
```

### ​Script : S99maus <a id="script-s-99-maus"></a>

```text
#!/bin/bash
### BEGIN INIT INFO
# Provides: mausberry.sh
# Required-Start: $network $local_fs $remote_fs
# Required-Stop: $network $local_fs $remote_fs
# Default-Start: 2 3 4 5
# Default-Stop: 0 1 6
# Short-Description: switch mausberry init script.
# Description: Starts and stops SwitchDaemon service.
### END INIT INFO

#VAR
RUN="/recalbox/scripts/mausberry.sh"
BTD_PID=$(ps -eo pid,command | grep "/bin/bash $RUN" | grep -v grep | awk '{print $1}')

serviceStatus() {
   if [ ! -z "$BTD_PID" ]; then
      echo -e '33[0mservice mausberry.sh ['$BTD_PID'] [33[33;32m OK 33[0m]'
   else
      echo -e '33[0mservice mausberry.sh [33[33;31m KO 33[0m]'
   fi
}

# Carry out specific functions when asked to by the system
case "$1" in
   start)
      echo "Starting script $RUN ..."
      if [ -z "$BTD_PID" ]; then
         nice -n 19 $RUN&

         if [ $? -eq 0 ]; then
            echo -e "33[0mscript $RUN [33[33;32m STARTED 33[0m]"
         fi
      else
         echo "script $RUN already started ['$BTD_PID']!"
      fi
      #serviceStatus
   ;;
   stop)
      echo "Stopping script $RUN ..."
      if [ ! -z "$BTD_PID" ]; then
         kill $BTD_PID

         if [ $? -eq 0 ]; then
            echo -e "33[0mscript $RUN [33[33;31m STOPPED 33[0m]"
         fi
      fi
      #serviceStatus
   ;;
   status)
      serviceStatus
   ;;
   *)
      echo "Usage: /etc/init.d/S99maus {start | stop | status}"
      exit 1
   ;;
esac

exit 0
```

