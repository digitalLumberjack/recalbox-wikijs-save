---
title: Adicione seu próprio script na inicialização
---

# Adicione seu próprio script na inicialização

Siga estas instruções se quiser criar seu próprio script de inicialização que será executado automaticamente quando você iniciar o **Recalbox**.

Todos os scripts de inicialização estão em `/etc/init.d`. Eles são executados um após o outro. Isso significa que o script`S31emulationstation` será processado antes de `S99MyScript`. Com base nos nomes dos arquivos, você pode determinar a ordem de execução.

O procedimento para iniciar um script será executado na inicialização e o procedimento de desligamento ao parar o Recalbox.​

## Etapas para criar seu próprio script de inicialização:​ <a id="etapas-para-criar-seu-proprio-script-de-inicializacao"></a>

* Faça login com [acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) ao seu **Recalbox**.
* O sistema é somente leitura por padrão. Você deve obter acesso de gravação com o seguinte comando: `mount -o remount rw, /`
* Mude a pasta para `/etc/init.d` com o seguinte comando:`cd /etc/init.d`
* Digite `ls` para ver todos os scripts disponíveis em `init.d`.
* Crie um novo script com `nano S99MyScript.py` \(é claro que você pode usar qualquer número, nome ou tipo de script \(.py, .sh, etc.\)\) e modifique-o conforme necessário. Para isso, pode-se usar a seguinte estrutura de script que já contém os métodos start, stop e restart / reload.

`#!/bin/bash`

```text
case "$1" in 
   start)  
         Add your startup code here!
         ;;  
   stop)  
         Add your shutdown code here!
         ;;  
   restart|reload)  
         Add your restart / reload code here!
         ;;  
   *)  
esac  

exit $?  
```

* Quando seu script estiver pronto, salve-o e feche-o com `STRG + X`
* Torne-o executável com o comando`chmod +x S99MyScript.py` \(ou qualquer que seja o nome do seu script\).
* Agora você pode reiniciar o **Recalbox** ou iniciar o script que você mesmo fez, com: `/etc/init.d/S99MyScript start`
* Pronto !

