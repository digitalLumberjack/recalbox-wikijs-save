---
title: Pastas e comandos SSH
---

# Pastas e comandos SSH

## Comandos SSH <a id="comandos-ssh"></a>

### Acesso root

```text
ssh root@[IP address of Recalbox]
```

### **​**Monte o Recalbox em modo de leitura / gravação

```text
mount -o remount,rw / 
```

### **​**Parar EmulationStation

```text
es stop
```

### Iniciar **Emulationstation**

```text
es start
```

### **​**Reiniciar **Emulationstation**

```text
es restart
```

### **​**Alterar a senha de root

```text
passwd
```

### **​**Reiniciar **Recalbox**

```text
reboot
```

### **​**Desligar **Recalbox**

```text
poweroff
```

### **​**Faça uma captura de tela

```text
raspi2png
```

Ele fará uma captura de tela e criará um arquivo em `/recalbox/share/system/` com o nome **snapshot.png**

Você também pode alterar sua captura para um nome personalizado com `-p filename.png`

### Informação de Rede

```text
ifconfig
```

### **​**Verifique a temperatura da CPU

```text
cat /sys/class/thermal/thermal_zone0/temp  
```

Em seguida, divida o resultado por 1000 para obter a temperatura em Celsius.

## Arquivos

Configuração específica do Raspberry Pi, como configurações de overscan, overclocking, modo de vídeo padrão, etc.

```text
nano /boot/config.txt  
```

### **​**Arquivo de configuração do Recalbox

```text
nano /recalbox/share/system/recalbox.conf
```

