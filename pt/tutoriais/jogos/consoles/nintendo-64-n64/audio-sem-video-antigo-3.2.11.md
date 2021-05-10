---
title: Áudio sem vídeo \(Antigo 3.2.11\)
---

# Áudio sem vídeo \(Antigo 3.2.11\)


>Informação:
>
>O emulador para N64 está em **fase beta**. Alguns jogos **funcionam** perfeitamente; outros não.  
>Pode acontecer que, ao **iniciar um jogo**, você tenha **som, mas não tenha vídeo.**
{.is-info}

### Aqui está uma solução possível: <a id="aqui-esta-uma-solucao-possivel"></a>

* * **Digite os seguintes comandos:** - `cd ../recalbox/scripts`  - `nano emulatorlauncher.sh` para editar o arquivo
* **Encontre as seguintes linhas** e **substitua o "4" por um "2":**

  ```text
  if [[ "$emulator" == "n64" ]]; then
  /recalbox/scripts/runcommand.sh 4 "SDL_VIDEO_GL_DRIVER=/usr/lib/libGLESv2.so mupen64plus –corel
  ```

* **Pressione** **`CTRL+X`** para **sair do editor**; em seguida, pressione **`Y`** para **salvar as alterações.**
* **Use o comando:** `reboot` para **reiniciar** o Raspberry pi.



