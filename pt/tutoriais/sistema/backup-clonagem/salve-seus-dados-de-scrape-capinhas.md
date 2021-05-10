---
title: Salve seus dados de scrape \(capinhas\)
---

# Salve seus dados de scrape \(capinhas\)

* **Consiga** [acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)
* Crie uma pasta:`mkdir /recalbox/share/system/backup_scrape/`
* **Use este comando** para salvar suas várias pastas de scrape colocadas na partição compartilhada \(SHARE\).

`cp -r /root/.emulationstation/downloaded_images /recalbox/share/system/backup_scrape/downloaded_images && cp -r /root/.emulationstation/gamelists /recalbox/share/system/backup_scrape/`


>Dependendo da quantidade total de scrape que você coletou, pode acontecer que a exibição dos conjuntos salvos demore. Seja paciente!
{.is-info}

​Em seguida, vá para o diretório **backup\_scrape** do sistema e copie o conteúdo do **backup\_scrape** para o seu PC ou armazenamento local.**​**

**Para restaurar** este backup em seu sistema Recalbox, adicione seu backup no diretório **backup\_scrape** na pasta do sistema e use o seguinte comando:

`cp -r /recalbox/share/system/backup_scrape/downloaded_images /root/.emulationstation/ && cp -r /recalbox/share/system/backup_scrape/gamelists /root/.emulationstation/`

Assim que a cópia for concluída, reinicie seu Recalbox e seus scrapes aparecerão.

