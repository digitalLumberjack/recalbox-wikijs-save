---
title: Adicionar conteúdo
---

# Adicionar conteúdo

## Adicionar jogos <a id="adicionar-jogos"></a>

Você apenas precisa **copiar** seus arquivos roms na pasta **correspondente ao console desejado** \(Exemplo: `share/roms/snes` para o Super Nintendo\).

Você pode usar ROMs compactadas \(.zip, .7z\) ou ROMs descompactadas, **dependendo do emulador**.


>**Informação:**
>
>Para obter mais informações sobre os **formatos de roms suportados** por um emulador, **consulte o arquivo "Leia-me"** presente **em cada pasta de roms.**
{.is-info}

Para atualizar a lista de jogos, vá ao **Menu**, **Opções de interface** e **Atualizar listas de jogos**

Não hesite em vir falar sobre sua lista de jogos favoritos no [fórum do Recalbox](https://forum.recalbox.com/).


>**Atenção:**
>
>**Arcade**
>
> Se você deseja adicionar **jogos de arcade** ao seu recalbox,  e/ou, para aprender a verificar seu romset, veja os tutoriais: [Tutorial ClrmamePro](https://recalbox.gitbook.io/tutorials/v/portugues/utilitarios/gerenciamento-de-rom/tutorial-clrmamepro) e [Tutorial do MD5SUM](https://recalbox.gitbook.io/tutorials/v/portugues/utilitarios/gerenciamento-de-rom/tutorial-do-md5sum-verifique-o-checksum-md5-de-uma-rom-ou-bios)
>
>Também é possível ativar a [Unibios NeoGeo](https://recalbox.gitbook.io/tutorials/v/portugues/jogos/consoles/neo-geo/neogeo-unibios-arcade) para obter mais opções em seus jogos.
{.is-danger}

​

## Adicionar BIOS <a id="adicionar-bios"></a>


>Alguns emuladores exigem um BIOS para emular os jogos corretamente.
{.is-info}

* Se você deseja **adicionar uma BIOS** ao seu sistema, abra **a pasta BIOS** compartilhada pelo Samba ou vá diretamente para **`/recalbox/share/bios/`**
* Seus **"nomes de BIOS" e código "CRC"** devem corresponder à lista no Gerenciador da Web.

Para verificar **a assinatura de uma BIOS,** consulte a página "[Tutorial MD5SUM](https://recalbox.gitbook.io/tutorials/v/portugues/utilitarios/gerenciamento-de-rom/tutorial-do-md5sum-verifique-o-checksum-md5-de-uma-rom-ou-bios)"


>**Atenção:**
>
>**Neo-Geo:** É necessário adicionar a BIOS **neogeo.zip** dentro da pasta rom associada ao emulador usado:  
>**/recalbox/share/roms/neogeo ou /recalbox/share/roms/fbneo**
>
>**Neo-Geo CD:** É necessário adicionar a BIOS **neogeo.zip**  e **neogeocd.zip** dentro da pasta :  
>**/recalbox/share/bios**
{.is-danger}

**Exemplo**

O nome da BIOS e o checksum devem ser os mesmos que abaixo \(por exemplo, neogeo.zip deve vir da versão romset solicitada\):

```text
FBA and FBA Libretro
798e5538be8b6557e7c4529f52d2938c  neogeo.zip
Mame (Pimame4all)
12f370a3fc42c3e413c4a0771d6d089f  neogeo.zip
```

