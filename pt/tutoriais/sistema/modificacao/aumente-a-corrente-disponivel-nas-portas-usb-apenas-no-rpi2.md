---
title: Aumente a corrente disponível nas portas USB \(apenas no RPi2\)
---

# Aumente a corrente disponível nas portas USB \(apenas no RPi2\)

Com as **configurações padrão**, o Raspberry Pi **2** limita a corrente a **600mA** **para todas as 4 portas USB.** A modificação de software proposta aqui **estenderá esse limite para 1200mA**.


>**Notas importantes:**
>
>* Essa mudança **não é apenas** para o Recalbox.
>* Esta modificação **é reversível**.
>* O uso de uma fonte de alimentação de **2000mA é sempre recomendado**, qualquer que seja o uso do Raspberry **Pi 2**.
>* A **corrente máxima** admissível pelo Raspberry **Pi 2** é **2000mA**.
{.is-warning}

## Motivo para fazer esta mudança:​ <a id="motivo-para-fazer-esta-mudanca"></a>

**Precisar conectar**, sem usar um hub USB com alimentação própria, periféricos USB gananciosos, sem exceder a nova corrente máxima de 1200mA nas 4 portas USB.

**Por exemplo:** Um disco rígido USB de 2,5 polegadas auto-alimentado.

## Exemplo de uso:​ <a id="exemplo-de-uso"></a>

* Uso de um **SSD USB auto-alimentado** para armazenar todas as roms, bios e saves.
* **Dongle USB WiFi**
* Carregar/usar **vários controles USB simultaneamente**

## Como fazer : <a id="como-fazer"></a>

* ​[Edite o arquivo config.txt](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/modificacao/editar-o-arquivo-config.txt)
* **Verifique** a presença da linha "`max_usb_current=...`"
* **Adicione** a seguinte linha "`max_usb_current=1`" ou **altere seu valor para 1** se ele já existir.
* **Salve** o arquivo **config.txt**
* **Reinicie** o Raspberry Pi 2


>**Nota:**
>
>Este truque também funciona no Raspberry Pi 3, mas a linha `max_usb_current = ...` não existe no arquivo config.txt; portanto, terá que ser adicionada manualmente.
{.is-info}

