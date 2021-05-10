---
title: Crie uma configuração personalizada por emulador
---

# Crie uma configuração personalizada por emulador

Você tem a possibilidade de **criar sua própria configuração personalizada para cada emulador** no Recalbox.

## Retroarch​ <a id="i-retroarch"></a>

**A configuração do RetroArch** pode ser criada **manualmente baseando-se na sua própria configuração** no [retroarch.cfg](/v/portugues/manual-basico/primeiros-passos/o-arquivo-recalbox.conf)​ padrão

ou **editando-o no menu RetroArch**. Você precisará **criar uma nova configuração** e **parametrizar** o novo arquivo de configuração [**recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) para que seja carregado pelo seu emulador.

### Usando o menu RetroArch <a id="usando-o-menu-retroarch"></a>

Vamos começar com o exemplo **da criação de um arquivo de configuração** específico para o **neogeo**.

* **Inicie um jogo** emulador que você **deseja personalizar** \(neste caso, neogeo\)
* **Entre no menu** Retroarch \(_**hotkey + b**_\)
* **Modifique** todas as configurações que desejar
* **Volte para a primeira entrada** do menu RetroArch, e escolha **`Salvar nova configuração`** \(o nome do arquivo de configuração deve se parecer com fba\_libretro.cfg / com o nome do núcleo que você está usando\)
* ​[No acesso root](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal), **altere o nome do arquivo de configuração** para algo mais fácil de lembrar. **Exemplo:**`mv /recalbox/share/system/configs/retroarch/fba_libretro.cfg /recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`
* **Adicione a seguinte linha** ao [**recalbox.conf**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf):`neogeo.configfile=/recalbox/share/system/configs/retroarch/inputs/neogeo_custom.cfg`

​

### Entradas <a id="entradas"></a>

### Edição manual <a id="edicao-manual"></a>

Desde a versão 4.1 do Recalbox, você pode adicionar arquivos de configuração específicos ao sistema e/ou ao jogo. É claro que há uma prioridade se o mesmo parâmetro aparecer em cada arquivo de configuração. Então **jogo &gt; sistema &gt; Retroarch**, o que significa que uma configuração existente em um arquivo .cfg do jogo será a usada em um sistema ou arquivo da Retroarch por padrão.

Aqui estão os arquivos que você pode editar \(ou criar, se não existirem\):

*  `~/configs/retroarch/.cfg`onde é o nome do sistema conforme aparece na pasta. Por exemplo: `~/configs/retroarch/snes.cfg`.
*  `~/configs/retroarch//.cfg` onde está o nome do sistema conforme aparece na pasta`roms` , e é o nome exato da ROM com a extensão do arquivo. Por exemplo: `~/configs/retroarch/snes/mario.zip.cfg`

