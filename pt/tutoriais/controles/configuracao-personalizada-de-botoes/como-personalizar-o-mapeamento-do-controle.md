---
title: Como personalizar o mapeamento do controle
---

# Como personalizar o mapeamento do controle


>Para quem deseja alterar o mapeamento de botões dos emuladores de núcleo do retroarch.
{.is-info}

* **Inicie um jogo** do referido emulador 
* **No menu do retroarch** \(hotkey + b\), vá para **"Configurações"** e depois "**Entrada do usuário 1 vinculado**" 
* **Reconfigure as teclas**, lembre-se de **ter um teclado disponível**, porque, enquanto você estiver remapeando o controle, ele pode ficar sem resposta, neste caso, você usa o teclado \("w" e "x" para validar e voltar\) 
* **Em seguida**, vá para "**Inserir teclas de atalho**" e **reconfigure as teclas como desejar** 
* **Volte ao primeiro menu do retroarch** e escolha "**Salvar nova configuração**" \(normalmente o nome da configuração é **nome\_do\_núcleo.cfg**, por exemplo **catsfc.cfg** se você estiver no **snes + catsfc**\) 
* **Conecte-se via ssh** ao Recalbox, e, **modifique o nome do arquivo de configuração** para obter algo mais significativo

Exemplo para **o emulador neogeo:**

`mv /recalbox/share/system/configs/retroarch/catsfc.cfg /recalbox/share/system/configs/retroarch/inputs/neogeocustom.cfg`

​

* **Modifique** o arquivo [**`recalbox.conf`**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)**adicionando a seguinte linha** para que funcione a nova configuração:`neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeocustom.cfg`

\*\*\*\*


>**Aviso:**
>
>Todas as outras configurações serão **o padrão**, portanto, sem **sombreamento/shader, trapaça/cheat ou qualquer outra coisa.**
{.is-danger}

​

