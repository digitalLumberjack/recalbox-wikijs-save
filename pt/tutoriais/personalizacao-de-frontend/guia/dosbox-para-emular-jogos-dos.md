---
title: DOSbox para emular jogos DOS
---

# DOSbox para emular jogos DOS

## Funcionamento básico​ <a id="funcionamento-basico"></a>

Vamos dar um **exemplo** simples com o jogo _**Alley Cat**_:

* Comece **criando a pasta** para seu jogo com o nome `AlleyCat.pc`. A primeira parte do nome do diretório antes do '.' \(ponto\) deve ter **no máximo 8 caracteres** e não conter **caracteres especiais**;
* Copie seus arquivos de jogo para essa pasta \(para jogos grandes, instale-os em seu computador antes de copiá-los\)
* Dentro de _AlleyCat.pc_, crie um arquivo `dosbox.bat` e edite para invocar o executável do jogo.

Isso nos dá:

```text
c: 
CAT.EXE
```

* O disco C: é **posicionado pelo DOSBox no diretório do jogo** \(aqui C: equivalente a `/recalbox/share/roms/dos/AlleyCat.pc`\). O mesmo se aplica a '.'
* **Reinicie ou atualize** sua lista de jogos para ver o jogo
* Para sair do emulador, pressione **CTRL + F9** no teclado

## Funcionamento avançado​ <a id="funcionamento-avancado"></a>

**Adicionar** um arquivo`dosbox.cfg` na pasta do jogo **no mesmo nível** que `dosbox.bat`**permite que você defina uma configuração DOS específica** para esse jogo

Você pode copiar o arquivo`dosbox.conf` de `\recalbox\share\system\configs\dosbox\dosbox.conf` ou usar este: [https://pastebin.com/13xrJdkw](https://pastebin.com/13xrJdkw)​


>ATENÇÃO:
>
>A extensão na pasta do jogo deve ser**`.cfg`** não **`.conf`**!
{.is-danger}

Neste arquivo, a linha `mapperfile=mapper.map` **permite que você use** um arquivo `mapper.map` para **mapear qualquer tecla do teclado** ou **até mesmo o mouse para o seu gamepad**. Este arquivo pode ser **criado a partir do seu jogo** pressionando **CTRL + F1** a qualquer momento e será salvo junto com os arquivos `dosbox.cfg` e `dosbox.bat`.

**Alguns parâmetros** do arquivo`dosbox.cfg` **também podem ser colocados** no início do arquivo `dosbox.bat`se você não quiser usar um arquivo `dosbox.cfg`específico, mas alguns desses parâmetros não funcionarão no `dosbox.bat` ; qualquer coisa gráfica parece funcionar, mas o parâmetro _mapperfile_ não funciona, por exemplo.

## Converta um jogo para usar no Recalbox <a id="converta-um-jogo-para-usar-no-recalbox"></a>

Como faço para converter um jogo para uso no Recalbox, seja comprado no GOG ou na excelente coleção _ExoDOS_?

Primeiro, **copie o conteúdo da pasta do jogo** \(renomeie-o corretamente com .pc no final\).

Em seguida, precisamos **adaptar o conteúdo** do _dosbox.cfg_ e do arquivo bat usado para iniciar o jogo.

Vamos dar um exemplo com a versão _ExoDOS_ de **Wacky Wheels**

**Não copie diretamente** o `dosbox.cfg` \(ou .conf\) da pasta original, pois isso pode levar a bugs que são difíceis de encontrar. **Em vez disso, copie o arquivo** padrão **vinculado acima**, então apenas verifique se o `dosbox.cfg` tinha uma configuração especial e se sim, use-o em seu `dosbox.cfg`. Isso está na parte `[autoexec]` do arquivo.

**Primeiro** mova o **conteúdo desta parte** para o início do arquivo `dosbox.bat` e adapte os caminhos. Aqui temos:

```text
[autoexec] 
cd .. 
cd .. 
mount c .\games\WackyWhe  
imgmount d .\games\WackyWhe\cd\wackywheels.iso -t cdrom 
c: 
cd wacky
cls 
@ww
exit 
```

e isso, convertido para Recalbox, nos dará:

```text
imgmount d .\cd\wackyw~1.iso -t cdrom
c: 
cd WACKY
pause
WW.EXE
```

##  Explicações:​ <a id="explicacoes"></a>

* **C: já está montado** pelo _DOSBox_ \(na pasta do jogo\), não precisamos dele;
* '.' também é **posicionado** pelo _DOSBox_ **na mesma pasta** e usando caminhos relativos, **seu jogo não será configurado** em uma pasta \(você pode usá-lo em uma subpasta diferente ou com outra distribuição\);
* **exit é removido**, pois isso também é feito pelo _DOSBox_;
* O caminho usado por`imgmount`é simplificado e precisamos converter o nome iso para um nome DOS padrão \(**8 caracteres no máximo** com os dois últimos alterados para ~1, ~2, ~3 etc. se o caminho for mais longo e você tiver vários arquivos com o mesmo nome\). Nesse caso, é melhor alterar o nome do arquivo para algo simples de qualquer maneira;
* **Nomes longos também não são suportados** em arquivos **.cue**, então você pode ter que renomear os arquivos **.cue/.bin** manualmente e editar o arquivo **.cue** para fazer referência ao novo nome do arquivo **.bin** e o _DOSBox_ pode -ser bastante restrito: **sem caracteres especiais e, às vezes, sem caracteres maiúsculos**.
* O comando **pause permite que você congele a tela e depure** facilmente as instruções do DOS, você pode suprimi-lo assim que verificar se o comando _imgmount_ está funcionando \(**não use o pause após chamar o executável do jogo** ou você não verá nada\)
* _@ww_ torna-se **WW.EXE** \(esta é apenas a chamada do executável do jogo\)

E aí está! Alguns jogos também podem usar um inicializador `.bat`, copie suas instruções no final do seu `dosbox.bat` após as da parte `[autoexec]` do `dosbox.cfg`e adapte-as.

## Solução de problemas \(em `dosbox.cfg`\)​ <a id="solucao-de-problemas-em-dosbox-cfg"></a>

**A imagem está distorcida:** para alguns jogos mais antigos, pode ser necessário alterar a configuração `aspect=false` para `aspect=true` **para obter uma imagem de proporção 4/3**. Tenha cuidado com jogos mais recentes, isso pode levar a um problema de desempenho;

**O joystick se move por conta própria**: tente alterar`timed=false` para `timed=true`. Isso pode ser devido às _deadzones_ do joystick também e, **infelizmente, não há como configurar isso no DOSBox no momento;**

**Não podemos mapear o D-pad de um controlador xbox360:** Sim, o mapeador _**DOSBox**_ **permite configurar o D-PAD** mas não funciona no jogo, você pode tentar mudar o tipo de joystick;

**Como configurar a deadzone de um joystick:** Infelizmente, isso não é possível no DOSBox no momento;

**CD Not Found / CD Driver not present**: Você tem problemas para renomear seus **arquivos de cd** \(iso, cue, bin, edição do cue\) ou usar nomes que não respeitam o padrão DOS \(consulte adv. rundown\);

**Não consigo fazer o** **`mount a`** **ou o** **`mount d`** **funcionar:** Ao contrário do `imgmount`, o comando `mount` **não pode usar caminhos 'virtuais' de dentro** da máquina _DOSBox_. Para fazer `mount` funcionar, você só pode usar caminhos locais reais do sistema de arquivos Recalbox. Como '.' é definido como o diretório raiz / ao iniciar o _DOSBox_, é **obrigatório usar o caminho absoluto completo** para o arquivo ou pasta;

**O mapeador tem bugs, ele apaga meu arquivo ou confunde meus botões:** Você provavelmente é uma vítima do parâmetro `buttonwrap`. Quando definido como **true**, ele configura os botões do seu pad com um ID maior que o número de botões do joystick emulado a partir de zero \(5 será remapeado para 0, 6 para 1, etc ...\). Defina esse parâmetro como **false** e tudo ficará bem.

​

