---
title: Pular a tela inicial do Noobs
---

# Pular a tela inicial do Noobs


>Você pode **economizar segundos na inicialização** forçando o **NOOBS** a **inicializar diretamente** na partição **`boot`**.
{.is-info}

* **Coloque o seu cartão SD** no seu **computador** pessoal. **Abra a partição** `RECOVERY` e **crie um arquivo chamado** `autoboot.txt`
* **Edite** o arquivo e **adicione a linha:** 
* Com um Recalbox na **versão 3.3.0**

```text
boot_partition=5
```

* Com um Recalbox na **versão 4.0.0**

```text
boot_partition=6
```

​**Isso irá ignorar** a tela inicial do NOOBS e **você inicializará diretamente** no recalboxOS.

Se você deseja **reativar a tela do NOOBS**, basta **excluir o arquivo** `autoboot.txt`

