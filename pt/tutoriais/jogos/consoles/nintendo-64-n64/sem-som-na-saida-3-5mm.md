---
title: Sem som na saída 3,5mm
---

# Sem som na saída 3,5mm

Se você estiver **usando o conector 3,5mm** do rpi **como saída de som** \(ao invés do som via HDMI\), e o som **não estiver funcionando** no emulador **N64**, siga o seguinte procedimento.

* **Conecte-se** [**via root**](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)
* **Edite** o arquivo de configuração do **mupen64plus** com o seguinte comando:

`nano /recalbox/configs/mupen64/mupen64plus.cfg`

* Em seguida, **modifique a linha**:

```text
# Audio output to go to (0) Analogue jack, (1) HDMI OUTPUT_PORT = 1
```

**Para:**

```text
# Audio output to go to (0) Analogue jack, (1) HDMI OUTPUT_PORT = 0
```

* Em seguida, basta **salvar o arquivo** com `ctrl+x` **depois** `y` , **seguido de**`enter`, e reiniciar o rpi com **o comando**`reboot`.

O som deve **funcionar** agora.


>Esta modificação **também pode ser feita** a partir do [WinSCP](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp), se você for alérgico **ao terminal.**
{.is-info}

