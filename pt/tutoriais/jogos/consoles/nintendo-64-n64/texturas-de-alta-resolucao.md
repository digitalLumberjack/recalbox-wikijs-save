---
title: Texturas de alta resolução
---

# Texturas de alta resolução

## Geral:​ <a id="geral"></a>

### O que são texturas de alta resolução? <a id="o-que-sao-texturas-de-alta-resolucao"></a>

**Texturas de alta resolução** \(Hi-res\) são **pacotes criados por fãs** com o objetivo de **embelezar as texturas** padrão de um jogo.

**Rice**, desenvolvedora do plugin **Rice Video**, foi **a primeira a tornar possível** extrair texturas de um jogo, modificá-las e reimportá-las em uma resolução maior. Agora é possível **substituir texturas borradas em jogos** por versões de **alta definição** ou uma versão **completamente diferente**. Empolgados com esta nova possibilidade, muitos designers gráficos começaram a criar texturas alternativas para seus jogos favoritos.

​

### Importante: <a id="importante"></a>

Quando você baixa um pacote de textura de alta resolução \(o Google é seu amigo\), procure no arquivo leia-me a descrição, as postagens do fórum ou qualquer outra coisa. Muitos desses pacotes funcionam apenas com um arquivo ROM específico. Por exemplo, rom \(U\) funciona, rom \(E\) não. Antes de começar, você precisa saber disso.​

### Configuração: <a id="configuracao"></a>

### Habilite o carregamento de arquivos de textura de alta resolução no Recalbox: <a id="habilite-o-carregamento-de-arquivos-de-textura-de-alta-resolucao-no-recalbox"></a>

Começamos editando o arquivo _mupen64plus.cfg_ para que possamos carregar texturas de alta resolução. O caminho para a pasta é`recalbox/share/system/configs/mupen64/`

Abra o arquivo _mupen64plus.cfg_ com um editor e edite a seguinte linha:

#### Opção 1 \(não para sistemas x86\): <a id="opcao-1-nao-para-sistemas-x-86"></a>

de:

```text
# Enable hi-resolution texture file loading
LoadHiResTextures = False
```

para:

```text
# Enable hi-resolution texture file loading
LoadHiResTextures = True
```

#### **​** <a id="undefined-1"></a>

Opção 2 \(para sistemas x86\):

de :

```text
# Hi-res texture pack format (0 for none, 1 for Rice)
ghq_hirs = 0
```

para:

```text
# Hi-res texture pack format (0 for none, 1 for Rice)
ghq_hirs = 1
```


>Mas também :
{.is-info}

de:

```text
# Compress hi-res texture cache
ghq_hirs_gz = True
```

para:

```text
# Compress hi-res texture cache
ghq_hirs_gz = False
```

#### **​** <a id="undefined-2"></a>

### **Copie** suas texturas de alta resolução para o Recalbox: <a id="copie-suas-texturas-de-alta-resolucao-para-o-recalbox"></a>

A localização é`recalbox/share/system/.local/share/mupen64plus/hires_texture/GAMENAME/`

Se a pasta **hires\_texture** não existir, crie uma. Se a pasta ... /.local não existir:

A pasta `.local` será criada se você iniciar um jogo N64 depois de mudar as linhas do arquivo `mupen64plus.cfg`.

#### Ative o emulador Mupen64Plus com o núcleo RICE \(em sistemas x86, use as configurações padrão\): <a id="ative-o-emulador-mupen-64-plus-com-o-nucleo-rice-em-sistemas-x-86-use-as-configuracoes-padrao"></a>

Você copiou o pacote de textura de alta resolução e a rom correta \(a rom de sua pasta rom n64\)? Ok, reinicie o sistema.

* Após a reinicialização, vá para Emulationstation em sua rom e pressione Select.
* Agora vá editar os metadados
* Mude o emulador de DEFAULT para MUPEN64PLUS
* Mude o núcleo de DEFAULT para RICE
* Salve

Quando o pacote de textura de alta resolução e a rom estiverem corretos, o jogo começará em alta resolução.​

## Solução de problemas:​ <a id="solucao-de-problemas"></a>

### Você seguiu as instruções acima corretamente e ainda não funciona? <a id="voce-seguiu-as-instrucoes-acima-corretamente-e-ainda-nao-funciona"></a>

Talvez seja **um problema de nome**... Muitos **desses pacotes de textura** vêm com **o nome de pasta correto**, mas **nem todos eles!** **O nome da pasta** deve ser exatamente **o nome interno de sua rom**.


>**Atenção:**
>
>O nome do arquivo é **Mario Kart 64 \(EUA\) .v64**, mas o nome interno da rom é **`MARIOKART64`**
{.is-danger}

### ​Como posso saber o nome interno da minha rom? <a id="como-posso-saber-o-nome-interno-da-minha-rom"></a>

**No Windows**, você pode, por exemplo, usar o **Tool64** \(o Google também é seu amigo aqui\).

* **Abra o** Tool64
* File -&gt; Open
* **Selecione** sua pasta de rom

![](https://cloud.githubusercontent.com/assets/21189571/24712193/7c626906-1a22-11e7-942b-d1701ebe6dc6.png)

* **Clique com o botão direito em uma rom** e em **Rom Properties**…

![](https://cloud.githubusercontent.com/assets/21189571/24712198/82bb47a0-1a22-11e7-9546-baa23e74b550.png)

**Procure** em Rom Info -&gt; Rom Name :

