---
title: Entradas do teclado via GPIO
---

# Entradas do teclado via GPIO

**Recalbox** inclui o **módulo retrogame**, que pode ser encontrado em `/usr/bin/recalbox-retrogame`.

Este módulo **permitirá o uso de GPIOs** para reproduzir o comportamento **de um teclado USB real no Recalbox**.


>**Aviso:**  
>_**Só funciona se** encontrarmos a linha_ **`controllers.gpio.enabled=0`** _em_ [_**recalbox.conf**_](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)
{.is-danger}


>**Exemplos:**
>
>* Se você deseja **integrar um Raspberry Pi a um console antigo** e **reutilizar os botões** do painel frontal \(por exemplo: PAUSE / SELECT de um Atari 7800\)
>* **Conectar** \(em uma máquina de arcade/fliperama\) **um botão** que teria **o mesmo comportamento da tecla Esc no teclado**.
>* Ou simplesmente, usar sem um teclado.
{.is-success}

​

## Instalação​ <a id="instalacao"></a>

### Cabeamento <a id="cabeamento"></a>

Você deve usar os **botões de apertar** \(que sobem após pressionar\) e conectar **um terminal ao terra** \(GROUND\) e **o outro terminal ao GPIO**.

### ​Script <a id="script"></a>

Para **iniciar automaticamente o módulo quando o Recalbox for iniciado**, é importante **adicionar um script**.

* **Crie** um arquivo de texto "**S99Retrogame**" sem extensão
* **Adicione as duas linhas de códigos** a seguir:

```text
/usr/bin/recalbox-retrogame
exit 0
```

* **Dê os direitos:** `chmod 775 /etc/init.d/S99retrogame`
* **Coloque-o em:**`/etc/init.d/`
* **Reinicialize e verifique** no SSH \(via Putty, por exemplo\) se o módulo foi iniciado **usando o comando:**`ps aux|grep recalbox-retrogame`. Se o comando **retornar uma identificação**, você conseguiu!

