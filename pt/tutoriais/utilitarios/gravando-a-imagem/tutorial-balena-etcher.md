---
title: Tutorial Balena Etcher
---

# Tutorial Balena Etcher

Com o [BalenaEtcher](https://www.balena.io/etcher/) \(este programa é muito fácil de usar\), você pode gravar o arquivo de imagem na mídia desejada \(ex.: um cartão microSD para um Raspberry Pi\). A operação de gravar uma imagem exige somente alguns segundos de manipulação.

​

* **Escolha a imagem ISO que quer gravar:**
  * Clique em "**Select Image**"/"Selecionar imagem" e localize o arquivo que você quer gravar O nome da imagem aparecerá abaixo do primeiro ícone e uma pequena alteração mudará a seleção.
* **Conectando uma mídia de armazenamento:**

  O segundo ícone, que está na forma de armazenamento externo, acende.

  * Selecione uma mídia de armazenamento.

  O Etcher valida automaticamente o que detecta como um dispositivo USB. É possível alterar o destino pressionando a pequena tecla "alterar". O programa indica a capacidade do dispositivo e avisa se o dispositivo é muito pequeno para aceitar a imagem.


>**Nota :**
>
>Para **instalação em um Disco Rígido:**
>
>* Vá em **Configurações** \(Ícone de engrenagem no canto superior direito\)
>* Desabilite a função **"unsafe mode" / "modo inseguro"**.
>* Retorne ao **Menu Inicial.**
>* Selecione um **Disco Rígido**
{.is-warning}

![](https://farm3.staticflickr.com/2825/33298930764_c297e9dbf8_z.jpg)

* Pressione o botão "**Flash / Iniciar**" para iniciar o processo. Etcher irá cuidar de tudo, formatação, particionamento, copiar arquivos, etc...

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MCcvAJCFQtVvarS-f23%2F-MCcwpcbgH-EWpB6VRmi%2Fimage1.png?alt=media&token=e26c5446-8145-4f7d-88b8-bacc68fa265b)

* O programa indicará o progresso do trabalho, ele também especificará o tempo necessário para completar o processo e a informação de velocidade de transferência.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MCcvAJCFQtVvarS-f23%2F-MCcwstAqDOwGwhwetQP%2Fimage2.png?alt=media&token=81dbca59-f7bc-441d-8fff-2636cfb658be)

* Ele então validará a imagem.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MCcvAJCFQtVvarS-f23%2F-MCcwx3wHwz3nQS4htY4%2Fimage3.png?alt=media&token=85d343d0-f9ae-4c63-af53-4ffd7151535f)

* E finalmente sinalizará como bom - ou mal - progresso do procedimento. Dará a você um botão para checar a integridade do arquivo e oferecerá para você repetir o procedimento com a mesma imagem em um clique, ou com uma imagem ISO diferente.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MCcvAJCFQtVvarS-f23%2F-MCcx0bnzUjlglZiR4us%2Fimage4.png?alt=media&token=54b568e0-55cc-4d42-b7cc-d532bf45f906)

* Você pode ejetar a mídia de armazenamento.

Há uma tonelada de alternativas ao Etcher, especialmente [UNetbootin](https://unetbootin.github.io/) e [Rufus](https://rufus.ie/), que funcionam admiravelmente bem.

