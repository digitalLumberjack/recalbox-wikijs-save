---
title: Emulador Amiga 600 & 1200 & AmigaCD32
description: A todos os amantes do Amiga!
---

# Emulador Amiga 600 & 1200 & AmigaCD32

Aqui está uma rápida introdução ao novo emulador Amiga.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LyGfKSLcIDCh_LGWdwY%2F-LyGjOUWj0iTtI56ZehI%2Ff7c5336e-ff11-4946-ae58-a5fecf99ecb2.png?alt=media&token=43324b57-aa51-4735-8b94-e67cf0015452)

**Amiberry foi atualizado para v2.24** no Raspberry 2, 3B \(+\) e Odroid XU4.

É uma grande mudança e a nova versão suporta **muitos recursos novos!**

## Subsistemas <a id="subsistemas"></a>

No Recalbox, as máquinas Amiga foram divididas em 3 subsistemas virtuais:

* **Amiga 600:** Todas as máquinas _OCS / ECS_ do **A1000** ao **A600** mais recente
* **Amiga 1200**: Todas as máquinas _AGA_, a partir da **1200**
* **Amiga CD32**: O único console real da série Amiga
  * O _CDTV_ **ainda não é compatível**, embora o tema Recalbox e as configurações do _CDTV_ estejam prontas. Ele **será adicionado posteriormente** como um novo subsistema, assim que **Amiberry** o suportar totalmente.

## ROMs suportadas​ <a id="roms-suportadas"></a>

Aqui está uma lista de formatos de arquivo suportados, classificados por subsistema:

* **Amiga600 e Amiga1200:**

  * Discos **ADF** \( _\*.adf\),_ o formato de disco mais popular \(não pode incluir proteções de disco\). Pode ser .zip ou .7-zip.
  * Discos **IPF** \( \*._ipf_\), os mais usados ​​por dumps sem introdução \(podem integrar proteções de disco\). Pode ser .zip.
  * **WHD** \(pastas, \*_.lha/lzh/lzx, \*.zip_\), o formato popular para jogos de disco rígido. As pastas _WHD_ são reconfiguradas usando o arquivo interno _\*.slave_; no entanto, é **altamente recomendável** armazená-los no formato _lha_ ou _zip_. _WHDs_ descompactados **não são mais rápidos** **e ainda pior:** podem tornar o EmulationStation extremamente lento :\)
  * **HDD FS**, disco rígido no sistema de arquivos. As pastas devem terminar com extensões do tipo "_.hd_". Raramente usado. Para verdadeiros entusiastas do Amiga que fizeram backup do Amiga HD. Pode ser compactado, mas não recomendado.
  * **HDF** \( \*_.hdf_\), Imagens do disco rígido em um arquivo. Pode ser compactado \(leitura / gravação!\)
  * **RP9** \( \*_.rp9_\), Pacotes "tudo-em-um" - Amiga Forever

  ​

* **Amiga CD32:**
  * **ISO** \( \*.bin, \*.iso, com ou sem \*_.cue_\), dumps de CD. Pode ser compactado.

Outros formatos de imagem de CD podem ser suportados, mas não foram testados pela equipe Recalbox.

Ao executar arquivos .zip/7-zip, nosso configurador tenta identificar o tipo de rom procurando por **extensões específicas** dentro do arquivo. _ADF / IPF / BIN / ISO_ são fáceis de identificar. _WHD_ são rápidos, mas _LHA_ deve ser preferenciado. O _HDDFS_ **pode demorar mais para verificar,** e pode levar a interpretações incorretas. Se você estiver usando _HDDFS_, deixe-os como arquivos e pastas normais e crie o nome da pasta raiz terminando em `.hd` para rápida identificação.

## Configurações prioritárias​ <a id="configuracoes-prioritarias"></a>

Como você pode ver, este novo **Amiberry suporta todos os formatos de ROM do Amiga**. Para tornar as coisas mais fáceis para todos, fizemos um grande trabalho de **configuração automática do emulador** com base no que você deseja iniciar.

O Recalbox cria uma configuração de máquina padrão por subsistema. No entanto, em algumas situações, **você pode querer substituir as configurações** geradas automaticamente.

O Recalbox gera os arquivos de configuração em `/tmp/amiga/conf`. O mais importante é o arquivo `uaeconfig.uae`, **no qual você encontrará todas as chaves** que definem a máquina, discos rígidos, etc.

Não consigo descrever todas as chaves aqui. Se você estiver curioso, **recomendo que dê uma olhada na documentação do Amiberry e do UAE.**

Você tem duas maneiras de substituir as configurações:

### Por sistema: <a id="por-sistema"></a>

Crie um arquivo chamado `/recalbox/share/system/configs/amiberry/.uae` \(`/recalbox/share/system/configs/amiberry/amiga1200.uae` para substituir o Amiga1200\)

* Defina a chave que você deseja ignorar.
* Por exemplo, você pode criar um arquivo de configuração com:

```text
show_leds=false
```

para **desligar o display LED** no canto inferior direito.

### Por jogo: <a id="por-jogo"></a>

Crie um arquivo com o mesmo nome de "rom" \(ou pasta\), mas terminando em `.uae`.

Por exemplo, em sua pasta rom, se você tiver um arquivo chamado `Aladdin (AGA).ipf`, você poderá criar um `Aladdin (AGA).uae` e substituir as chaves desse arquivo.

O Recalbox gera a configuração na seguinte ordem:

* Cria a configuração padrão relativa ao tipo de rom e ao subsistema.
* Carrega `/recalbox/share/configs/.uae`

   se o arquivo existir e adicione / substitua as chaves de configuração.

* Carrega`.uae` se o arquivo existir e adicione / sobrescreva as chaves de configuração.

## No jogo <a id="no-jogo"></a>

Como nos outros emuladores:

* **Hotkey + START**permite que você saia do emulador
* **Hotkey + B** inicia a interface do **Amiberry.**

## BIOS​ <a id="bios"></a>

O novo Recalbox vem com um **substituto do Kickstart de código aberto, a bios AROS** \(versão 2019\). Nosso configurador automático usa esta BIOS **quando nenhuma outra BIOS está disponível** na pasta `share/bios`. Vários jogos foram iniciados e testados com sucesso usando a BIOS **AROS**.

Mas lembre-se de que **esta é uma substituição**. É **altamente recomendável que você obtenha a BIOS necessária**. Especialmente se você quiser rodar jogos _WHD_, já que o _WHDLoader_ do **Amiberry** pode alterar as configurações do BIOS e **procurar o melhor Kickstart** disponível.

​

Aqui está a lista de novos Kickstarts necessários:

* Computadores:

**kick33180.A500.rom** \(Kickstart v1.2 rev 33.180 \(1986\)\(Commodore\)\(A500-A1000-A2000\).rom\)

**kick34005.A500.rom** \(Kickstart v1.3 rev 34.5 \(1987\)\(Commodore\)\(A500-A1000-A2000-CDTV\).rom\)

**kick37175.A500.rom** \(Kickstart v2.04 rev 37.175 \(1991\)\(Commodore\)\(A500+\).rom\)

**kick39106.A1200.rom** \(Kickstart v3.0 rev 39.106 \(1992\)\(Commodore\)\(A1200\)\[!\].rom\)

**kick40063.A600.rom** \(Kickstart v3.1 rev 40.63 \(1993\)\(Commodore\)\(A500-A600-A2000\)\[!\].rom\)

**kick40068.A1200.rom** \(Kickstart v3.1 rev 40.68 \(1993\)\(Commodore\)\(A1200\).rom\)

**kick40068.A4000.rom** \(Kickstart v3.1 rev 40.68 \(1993\)\(Commodore\)\(A4000\).rom\)

​

* CD32 :

**kick40060.CD32.rom** \(Kickstart v3.1 rev 40.60 \(1993\)\(Commodore\)\(CD32\).rom\)

**kick40060.CD32.ext.rom** \(CD32 Extended-ROM rev 40.60 \(1993\)\(Commodore\)\(CD32\).rom\)

​

Espero que isso possa te ajudar =\)

