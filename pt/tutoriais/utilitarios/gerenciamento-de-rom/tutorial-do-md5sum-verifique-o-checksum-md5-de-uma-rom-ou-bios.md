---
title: Tutorial do MD5SUM - Verifique o checksum MD5 de uma ROM ou BIOS
---

# Tutorial do MD5SUM - Verifique o checksum MD5 de uma ROM ou BIOS

## Online <a id="online"></a>

​​[HTML5 File Hash Online Calculator](https://md5file.com/calculator)​

## ​No Windows <a id="no-windows"></a>

* Baixe o [winmd5free](http://www.winmd5.com/download/winmd5free.zip)
* Instale-o e clique no botão "Browse"/Procurar para selecionar seu arquivo
* Encontre o checksum recomendado nesta página \([Adicionar BIOS](/v/portugues/manual-basico/gerenciamento-de-arquivos/adicionar-conteudo#adicionar-bios)\), coloque-o no campo "Original File MD5"/MD5 do arquivo original e clique em "Verify"/Verificar

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MDAYNn868tt0J8P6PBt%2F-MDAjWA5uLYmeRiYR5J8%2Fs7nytq17.bmp?alt=media&token=4254c638-7de8-4e2f-88af-ea384aed54cd)

### **​Método alternativo** <a id="metodo-alternativo"></a>

Desde o Powershell v4.0 \(Windows 8.1 e superior\), o comando get-filehash permite verificar nativamente o checksum de um arquivo.

1. Inicie o powershell.exe
2. Execute o comando :`Get-FileHash -Algorithm MD5`

**Dica:** para testar todos os arquivos em uma pasta \(recursivamente/infinitamente\), após definir a pasta, execute o comando:`Get-ChildItem -recurse | % {Get-FileHash $_.Fullname -Algorithm MD5} | select Path,Hash | ft -AutoSize`

### **Método alternativo 2** <a id="metodo-alternativo-2"></a>

Você também pode baixar este script: [HackCheck Shell Extension](http://code.kliu.org/hashcheck/), que permite adicionar uma guia adicional nas propriedades de um arquivo para o Windows 10.

## Linux / MacOSX <a id="linux-macosx"></a>

Use o comando `md5sum`. No terminal, para verificar o checksum dos arquivos BIOS, use o comando `shasum` seguido pelo nome do arquivo.

