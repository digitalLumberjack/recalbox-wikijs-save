---
title: Tradução no jogo \(Retroarch AI\)
description: Traduza seus jogos ao vivo!
---

# Tradução no jogo \(Retroarch AI\)

## Retroarch Ai, o que é? <a id="retroarch-ai-o-que-e"></a>

Bem vindo ao futuro!

Há já algum tempo, RetroArch permite a utilização de um serviço de tradução denominado "[OCR](/v/portugues/manual-basico/glossario)" \(Reconhecimento Ótico de Caracteres\) e **Síntese de Voz**, que lhe permitirá traduzir os seus jogos estrangeiros quase instantaneamente! Esta função requer uma conexão com a internet!


>Esta função requer conexão com a internet!
{.is-danger}

![Antes](https://gblobscdn.gitbook.com/assets%2F-LdKWTKrrUvJVmGP83hw%2F-LpvzgwFPllYtLYDeW30%2F-Lpw2MjA1IWr7hjwyTfV%2Focr1.png?alt=media&token=186f4a7d-6c99-43f7-b433-47fdae207163)

![Depois](/migration-images/manual-basico/funcionalidades/ocr2.jpg)

## Configuração: <a id="configuracao"></a>

Como você sabe, tudo é feito para tornar a configuração deste tipo de serviço o mais simples possível.


>Este serviço requer registro com uma API.
>
>Recalbox usará [Ztranslate.net](https://ztranslate.net/) por padrão, mas outras APIs podem ser configuradas!
{.is-warning}

* Depois de registrado e conectado ao site, vá para a seção de configurações para recuperar sua `API KEY`
* Abra seu arquivo [`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)\`\`
  * Encontre a linha`;global.translate.apikey=YOUR_API_KEY_HERE`
  * Exclua o `;` do começo da linha, cole sua  `API KEY` no lugar de `YOUR_API_KEY_HERE`


>O Recalbox irá detectar automaticamente o idioma do seu jogo e traduzir para o idioma definido no menu principal.
{.is-success}

## Vamos lá!

Mime-se e esqueça a frustração, inicie um jogo 100% japonês 😆​

* Para ativar a tradução, não tem como ser mais simples:`HOTKEY + ALAVANCA-ESQUERDA BAIXO` , o jogo será pausado e mostra uma imagem com o texto de substituição.
* Pressione a tecla de atalho AI Service novamente para reiniciar o jogo.

Por padrão, o Recalbox usa o modo de imagem em vez da síntese de voz para usar o último, uma simples [sobrecarga de configuração](/v/portugues/usuario-avancado/configuracoes/sobrecargas-de-configuracoes)!

