---
title: Instalação automática do Recalbox sem teclado
---

# Instalação automática do Recalbox sem teclado

Você pode instalar o recalboxOS automaticamente no RapberryPi sem a necessidade de um teclado USB.

​Siga estas etapas:

1. **Baixe e descompacte** a versão mais recente do recalboxOS
2. **Exclua a pasta** em `os` **que não corresponde ao** seu RPi. Se você tiver um RPi1 remova o `recalboxOS-rpi2`, se você tiver um RPi2 remova o `recalboxOS-rpi`
3. Edite o arquivo `recovery.cmdline` e adicione `silentinstall` à lista de argumentos:`runinstaller quiet vt.cur_default=1 elevator=deadline` torna-se`runinstaller quiet vt.cur_default=1 elevator=deadline silentinstall`

​Quando você inicia o seu Pi usando um cartão SD contendo a versão modificada do recalbox que você acabou de criar, ele **instalará automaticamente** o recalboxOS e o inicializará após a **conclusão da instalação**.

