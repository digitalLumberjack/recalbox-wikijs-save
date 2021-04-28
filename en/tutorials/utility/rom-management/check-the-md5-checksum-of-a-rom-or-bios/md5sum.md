---
title: MD5sum
---

# MD5sum

To verify the MD5 checksum of a file.

## Online <a id="online"></a>

​​[HTML5 File Hash Online Calculator](https://md5file.com/calculator)​

## Offline <a id="no-windows"></a>

{% tabs %}
{% tab title="Windows" %}
* Download the [winmd5free](http://www.winmd5.com/download/winmd5free.zip)
* Instale-o e clique no botão "Browse"/Procurar para selecionar seu arquivo
* Encontre o checksum recomendado nesta página \([Adicionar BIOS](/v/portugues/manual-basico/gerenciamento-de-arquivos/adicionar-conteudo#ajouter-des-bios)\), coloque-o no campo "Original File MD5"/MD5 do arquivo original e clique em "Verify"/Verificar

### Alternative method 1:

From Powershell v4.0 \(Windows 8.1 or higher\), the command `get-filehash` allows you natively to verify the checksum of a file.

1. Launch powershell.exe
2. Execute the following command line:

```text
Get-FileHash "file to verify" -Algorithm MD5
```


>Tip:
>
>To verify all files recursively in a folder, execute the following command after you are in the folder:
>
>`Get-ChildItem -recurse | % {Get-FileHash $_.Fullname -Algorithm -MD5} | select Path,Hash | ft -AutoSize`
{.is-info}

### Alternative method 2:

You can also download this script : [HackCheck Shell Extension](http://code.kliu.org/hashcheck/) which allows you to add a new tab in the file properties window on Windows 10.
{% endtab %}

{% tab title="macOS / Linux" %}
Use the command `md5sum`.  
Into your terminal, to verify the checksum of your bios files, use the command line `shasum` following your file name.
{% endtab %}
{% endtabs %}



