---
title: Converter iso+cue+wav/bin em bin+cue
---

# Converter iso+cue+wav/bin em bin+cue


>**Informações :**
>
>Os jogos **SegaCD** ou **PSX** podem estar em **diferentes formatos**:
>
>* iso+cue acompanhados por arquivos no formato wav, bin
>* iso
>* bin+cue
>* ccd+img+sub
>* bin somente
{.is-info}

**Exemplo :**

```text
Wonder Dog (1993)(Sega)(PAL)(Track 01 of 21)[!].iso
Wonder Dog (1993)(Sega)(PAL)(Track 02 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 03 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 04 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 05 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 06 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 07 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 08 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 09 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 10 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 11 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 12 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 13 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 14 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 15 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 16 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 17 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 18 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 19 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 20 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)(Track 21 of 21)[!].wav
Wonder Dog (1993)(Sega)(PAL)[!].cue   

Rockman 8 - Metal Heroes (Japan) (Track 1).bin   
Rockman 8 - Metal Heroes (Japan) (Track 2).bin   
Rockman 8 - Metal Heroes (Japan) (Track 3).bin   
Rockman 8 - Metal Heroes (Japan) (Track 4).bin   
Rockman 8 - Metal Heroes (Japan).cue
```


>**Informação :**
>
>Aqui está uma técnica para converter **iso + cue com arquivos wav** para aqueles que **não desejam criar pastas para conter todos os arquivos de um jogo**.
{.is-info}

**Esta técnica** é válida para PSX, SEGACD.

* **Baixe o** [Daemons Tools Lite \(gratuito\)](https://www.daemon-tools.cc/cpp/products/dtLite)
* **Instale** o software.
* **Escolha** imagens de disco e **clique** no sinal +**​**
* **Selecione** o arquivo **\*.CUE**
* Em seguida, **pressione ENTER** OU **clique com o botão direito** do mouse para escolher montar para criar a unidade virtual.
* Monte a imagem
* **Baixe o** [ImgBurn](http://imgburn.com/)**​**
* **Baixe** o arquivo de linguagem em português-brasileiro clicando [neste link](http://download.imgburn.com/translations/portuguese_brazil.zip)
* **Instale** o software
* **Descompacte** o arquivo de idioma e **coloque-o** na pasta: Arquivos de Programas \(x86\) / imgburn / languages
* **Execute** o software em português.
* **Escolha** Criar imagem do disco / Criar imagem do disco
* **Escolha** a unidade virtual **como fonte**
* **Escolha** uma pasta de destino para criar o BIN e o CUE.
* **Clique** no botão **Read / Ler**
* **Por favor, espere.**

Após a **conclusão da conversão**, você pode **desmontar a unidade virtual** \(clique com o botão direito do mouse no ícone do Daemon Tools e depois desmonte\)

## Crie um arquivo .cue ausente para seu único arquivo .bin



**Exemplo :** r-type.bin

* **Abra o** [Notepad++](https://notepad-plus-plus.org/downloads/) a 1ª linha deve conter o **BINARY**

`FILE "nom.bin" BINARY`

* A **2ª** as pistas em **MODE2/2352**

`TRACK 01 MODE2/2352`

* A **3ª** o índice **01**

`INDEX 01 00:00:00`

* **Você irá obtém** algo parecido com isto que deve funcionar:

  ```text
  FILE "r-type.bin" BINARY
  TRACK 01 MODE2/2352
  INDEX 01 00:00:00
  ```

* **Salve** com a extensão .**cue** : `r-type.cue`  
* Agora você só precisa **copiar seu .bin e .cue**

