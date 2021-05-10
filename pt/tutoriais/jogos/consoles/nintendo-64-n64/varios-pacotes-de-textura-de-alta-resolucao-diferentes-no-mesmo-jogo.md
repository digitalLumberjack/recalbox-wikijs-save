---
title: Vários pacotes de textura de alta resolução diferentes no mesmo jogo
---

# Vários pacotes de textura de alta resolução diferentes no mesmo jogo

## Informação:​ <a id="informacao"></a>

No **guia**: [Texturas de alta resolução](https://recalbox.gitbook.io/tutorials/v/portugues/jogos/consoles/nintendo-64/texturas-de-alta-resolucao), Você aprendeu a **usar pacotes de textura de alta resolução.**

## Geral: <a id="geral"></a>

Para **alguns** jogos, **diferentes pacotes de textura** foram criados. **O problema** é que geralmente todos **têm o mesmo nome**. Se você quiser **usar várias versões**, siga **este guia**.

## Procedimento:​ <a id="procedimento"></a>

**Para cada versão** da textura de alta resolução, **modificamos o nome da rom interna**. Quando isso for feito, iremos editar os nomes das texturas de alta resolução.

## O que precisamos:​ <a id="o-que-precisamos"></a>

Neste guia, usaremos **N64 Rom Renamer** by Einstein II \(Google é seu amigo\), para **editar o nome interno** da rom. Você também precisará de um **software para renomear em lote** \(exemplo no Windows: AntRenamer\). Para este guia, usaremos **Better Rename** \(MAC OSX\).

## Vamos lá :​ <a id="vamos-la"></a>

### Edite o nome interno da rom <a id="edite-o-nome-interno-da-rom"></a>

* **Abra** o N64 Rom Renamer **com direitos de administrador** \(não funcionou sem isso para mim\).

![](https://cloud.githubusercontent.com/assets/21189571/24708781/34a419e8-1a18-11e7-8751-c46bc0f495d0.png)

* **Pressione** `F2` ou **vá para**`Tools - Headereditor F2`
* **Confirme** o aviso

![](https://cloud.githubusercontent.com/assets/21189571/24708944/ae3da576-1a18-11e7-9f43-0db16524c2f4.png)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LlEX5DYb-17IklPbtZ-%2F-LlEX8rcviyjOMTdk5Sy%2Fimage.png?alt=media&token=33b8d97c-fb70-4182-87bf-28e5cf37e3a0)

* **No canto superior esquerdo, clique** no ícone da pasta e **selecione** sua rom \(para nosso exemplo, usaremos Mario Kart 64\)

![](https://cloud.githubusercontent.com/assets/21189571/24709113/2c9691d0-1a19-11e7-8704-d9217ebf926a.png)

* Aqui você pode editar o nome interno da rom

### Atenção <a id="atencao"></a>

O nome **não pode ser muito longo**. **O comprimento** total **das letras e espaço**s deve ser respeitado. No nosso caso, vemos que **MARIOKART64** possui **nove espaços além do nome**, o que nos dá **o comprimento total possível** para o nome interno.

![](https://cloud.githubusercontent.com/assets/21189571/24709501/667ddcb8-1a1a-11e7-927f-e7b5276d766d.png)

* Em nosso exemplo, **removeremos quatro espaços** que serão **substituídos por quatro letras** \(SNES\)

![](https://cloud.githubusercontent.com/assets/21189571/24709636/d69617ae-1a1a-11e7-9ec6-5d9d43e1983b.png)

* **Salve** as modificações e clique em `Back`

O nome interno da rom **foi alterado com sucesso.**

**Em seguida**, renomeie **o arquivo rom**; exemplo: Mario Kart 64 SNES Edition.ext O nome do arquivo da rom **não é importante para texturas.**

### Edite o pacote de textura de alta resolução e os arquivos: <a id="edite-o-pacote-de-textura-de-alta-resolucao-e-os-arquivos"></a>

Nosso \(exemplo\) de **estrutura de arquivo do nosso pacote** de alta resolução **se parece com isto**:

![](https://cloud.githubusercontent.com/assets/21189571/24709885/a5b8cdba-1a1b-11e7-9623-d0ee243b5af3.png)

**A pasta e os arquivos** com o nome **MARIOKART64** agora estão **incorretos**, claro, após **termos alterado o nome interno da rom**. Precisamos **consertar isso**!

* Abra o _Better Rename \(o software de renomear em lote do nosso exemplo\)_
* Category: Text
* Action: Replace text
* Replace: **MARIOKART64**
* With: **MARIOKART64SNES**

![](https://cloud.githubusercontent.com/assets/21189571/24710019/1caa6e4c-1a1c-11e7-82da-1b7ddfa3d05d.png)

**Após renomear,** você precisa **verificar se todos os nomes correspondem. Se** o nome da pasta e os nomes dos arquivos **corresponderem**, você pode **copiar seu pacote de textura.**


>**Por precaução:**
>
>Antigo nome da pasta: MARIOKART64   
>Antigo nome do arquivo na pasta: MARIOKART64 \# ......
>
>Novo nome da pasta: MARIOKART64SNES  
>Novo nome do arquivo na pasta: MARIOKART64SNES \# ...
{.is-warning}

### FIM <a id="fin"></a>

**Siga** estas etapas para **cada pacote de textura de alta resolução** desejado.

