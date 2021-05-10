---
title: Ajustando o tamanho da imagem usando overscan
---

# Ajustando o tamanho da imagem usando overscan

​A opção _overscan_ pode ser ativada se você tiver bordas pretas na imagem ou se a imagem estiver cortada. Você pode ativar a opção **Overscan** nas **CONFIGURAÇÕES DE INTERFACE**. Você deve reiniciar o Rapsberry Pi depois de alterar esta opção.

As opções de overscan são definidas pelo Noobs durante a primeira instalação. Se não corresponder à sua tela, você poderá alterar as configurações de cada borda no seu arquivo `config.txt` :

```text
disable_overscan=0
overscan_left=24
overscan_right=24
overscan_top=24
overscan_bottom=24
```

O valor especifica o número de pixels a serem ignorados na borda da tela. **Aumente** esse valor se a imagem estiver fora da borda da tela; **diminua-o** se houver uma borda preta entre a borda da tela e a imagem.

Se essas configurações não forem aplicadas corretamente nos emuladores ou no EmulationStation, tente adicionar o seguinte:

```text
overscan_scale=1
```

