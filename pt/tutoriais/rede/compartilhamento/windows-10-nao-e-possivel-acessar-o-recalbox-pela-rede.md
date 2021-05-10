---
title: Windows 10 - Não é possível acessar o Recalbox pela rede
---

# Windows 10 - Não é possível acessar o Recalbox pela rede

## Caso n ° 1: Nenhum computador, incluindo Recalbox, é visível no Windows​ <a id="caso-n-1-nenhum-computador-incluindo-recalbox-e-visivel-no-windows"></a>

Se você **não consegue ver um computador** na rede do **Windows 10**, é porque:

* **A descoberta de rede está desabilitada** por padrão e **a configuração de rede está definida como "pública"** OU
* Porque **"tornar este PC detectável"** está definido como **"desativado"**.

Você tem que **ir para as configurações de rede** e **colocar sua rede** no modo **"particular"**, ou colocar **"tornar este PC detectável"** como **"ativado"**.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MFQS9R8ZJNsrvyLM98N%2F-MFQXSTKtgbTyIwEDaod%2F1.png?alt=media&token=cd5f0d2c-3fff-43a8-8c81-ad0b8a66e8f5)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MFQS9R8ZJNsrvyLM98N%2F-MFQXXWJiZ_pGet3Xe64%2F2.png?alt=media&token=f1306d37-c032-417f-8f59-73324e814876)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MFQS9R8ZJNsrvyLM98N%2F-MFQXdCxJLhEZ4ySZR0D%2F3.png?alt=media&token=2a5306e6-abec-49d3-93f0-d652723d747d)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MFQS9R8ZJNsrvyLM98N%2F-MFQXh5xWPt2xMdn6560%2F4.png?alt=media&token=da2b536a-8381-4337-b704-283cc9627ac7)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MFQS9R8ZJNsrvyLM98N%2F-MFQXh5yaRRwgsku9Cxp%2F5.png?alt=media&token=c14fe2ba-4541-4f88-95f6-7500066de32c)

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MFQS9R8ZJNsrvyLM98N%2F-MFQXh5zyoI0eABAyyvG%2F6.png?alt=media&token=9d76f90f-44b2-4525-9dc8-1e01e1909625)

## Caso nº 2: Recalbox não está mais acessível desde a atualização do Windows 10 nº 1709 <a id="caso-no-2-recalbox-nao-esta-mais-acessivel-desde-a-atualizacao-do-windows-10-no-1709"></a>

\*\*\*\*


>**Nota:**
>
>**Depois** esta atualização, **você vê o Recalbox** em sua rede, mas **não consegue mais acessá-lo**.
{.is-warning}

* **Explicação oficial** \(em inglês\): [https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/](https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/)  ou [ ](https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016)[https://support.microsoft.com/pt-br/help/4046019/guest-access-in-smb2-disabled-by-default-in-windows-10-and-windows-ser](https://support.microsoft.com/pt-br/help/4046019/guest-access-in-smb2-disabled-by-default-in-windows-10-and-windows-ser)
* **Reparo rápido:** Baixe e aplique [este patch](https://mega.nz/#!rUA3xDgI!a14w9TqQWinLriLANpk7BF_WkoNg8mw6fHloyPEZMPg)


>**Informação:**
>
>Este patch irá **desativar a segurança no acesso anônimo** à rede no Windows, **para restaurar o acesso ao Recalbox**.
{.is-info}

## Caso n°3 <a id="caso-n-3"></a>

* ​**Vá** para:`Configurações / Aplicativos / Programas e recursos / Ativar ou desativar recursos do Windows`
* Ative **marcando**: `Suporte para compartilhamento de arquivos SMB 1.0 / CIFS / cliente SMB1.0 / CIFS ...`
* Em seguida, **reinicie o Windows.**

