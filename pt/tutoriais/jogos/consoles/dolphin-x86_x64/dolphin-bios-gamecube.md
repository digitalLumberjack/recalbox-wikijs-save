---
title: Dolphin bios GameCube
---

# Dolphin bios GameCube

Aqui está um tutorial para ter **a bios do GameCube quando você iniciar seus jogos!!**

* **Monte** seu Recalbox no [**modo de gravação:**](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesse-uma-particao-em-modo-gravacao) `mount -o remount, rw /`
* **Conecte-se no** [**ssh** e faça login:](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)  **login :**`root` **senha:**`recalboxroot`
* Você deve ir para a pasta`/usr/share/dolphin-emu/sys/GC`e criar três pastas:   
  **Digite**`cd /usr/share/dolphin-emu/sys/GC/`

  Em seguida, **crie estas três pastas:**  
  `mkdir USA  
  mkdir JAP  
  mkdir EUR`

* **Copie suas bios** na pasta correta:

`0cdda509e2da83c85bfe423dd87346cc` `IPL.bin` = bios da Europa  
`fc924a7c879b661abc37cec4f018fdf3` `IPL.bin` = bios do Japão  
`339848a0b7c2124cf155276c1e79cbd0` `IPL.bin` = bios dos EUA

​**Todos os nomes iguais** \(`IPL.bin`\), ou seja:

```text
|---- EUR ---- IPL.bin--(0cdda509e2da83c85bfe423dd87346cc)
|
|
|---- JAP ---- IPL.bin--(fc924a7c879b661abc37cec4f018fdf3)
|
|
|---- USA ----IPL.bin--(339848a0b7c2124cf155276c1e79cbd0)
```

* **Inicie** um jogo de gamecube; em seguida, **usando o teclado, tecle:** `alt+p`
* **Ou**, no controle:`hotkey+r2`
* O menu Dolphin abrirá. **Clique em**: `Stop` \(no menu superior\) para **parar o jogo em segundo plano.**
* **Em seguida**`Graphics`
* **Clique** na aba `Hacks`
*  E finalmente **desmarque**`Disable` \(External frame Buffer \(XFB\)\)
* Quando terminar, **saia do emulador** com `hotkey+a`

Agora na inicialização **a bios aparece!!**


>**Informação:**
>
>Permite a gestão dos saves como no console original!!!
{.is-info}

