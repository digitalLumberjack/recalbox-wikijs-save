---
title: Editar o arquivo config.txt
---

# Editar o arquivo config.txt


>Primeiro, acesse a partição boot em modo gravação \([https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesse-uma-particao-em-modo-gravacao](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesse-uma-particao-em-modo-gravacao)\)
{.is-warning}

Ele está localizado em `/boot/config.txt`

Existem duas maneiras de editar o arquivo **config.txt.**

## **SSH**​ <a id="ssh"></a>

* [Se conecte via ssh](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) 
* Use o nano para editar o arquivo /boot/config.txt:

  `nano /boot/config.txt`

​

## **Noobs**​ <a id="noobs"></a>

* **Conecte um teclado USB** e pressione **Shift** durante a **inicialização do recalbox** para acessar o **menu de Recuperação/Recovery.**
* **Pressione "e"** para obter o **menu de edição** e você poderá fazer alterações diretamente no arquivo. Você pode **alterar o idioma do teclado** pressionando **"l" e "k"**.

