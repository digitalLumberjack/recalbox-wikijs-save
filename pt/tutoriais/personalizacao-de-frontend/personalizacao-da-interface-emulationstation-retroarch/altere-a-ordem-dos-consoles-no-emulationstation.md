---
title: Altere a ordem dos consoles no EmulationStation
---

# Altere a ordem dos consoles no EmulationStation

## Etapas​ <a id="etapas"></a>

* **Conecte-se** em [SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) ao seu Recalbox.
* **Vá para** a pasta **EmulationStation** localizada em **share\_init** :`cd /recalbox/share_init/system/.emulationstation`
* **Pare o EmulationStation** &gt; `/etc/init.d/S31emulationstation stop`
* **Edite** o arquivo `es_system.cfg` &gt; `nano es_system.cfg` Neste arquivo você encontrará **todas as entradas para os consoles** que o Recalbox suporta. **Basta alterar a ordem das entradas** como deseja que **apareçam** no EmulationStation.
* **Salve** suas modificações.
* **Inicie novamente o EmulationStation** &gt; `/etc/init.d/S31emulationstation start`

​

## Observações​ <a id="observacoes"></a>

Infelizmente, atualmente **não é possível** colocar os "**Favoritos**" na **primeira posição.**

