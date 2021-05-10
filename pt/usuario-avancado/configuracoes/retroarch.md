---
title: Retroarch
---

# Retroarch

**RecalboxOS** usa [**RetroArch**](https://github.com/libretro/RetroArch), criado por [Twinaphex](https://github.com/twinaphex), como uma interface para emuladores.

Retroarch é o programa que alimenta a maioria dos emuladores do RecalBox.

## O que que é isso? <a id="o-que-que-e-isso"></a>

Retroarch é um front-end de libretro, o que significa que ele pode executar o conteúdo de núcleos do libretro, ele também unifica a forma como esses núcleos funcionam com o sistema.

Um núcleo é um programa adaptado para trabalhar com front-ends do libretro, neste caso a maioria deles são emuladores.

## Recursos <a id="recursos"></a>

Retroarch, por natureza, é um programa que executa outros pequenos programas, no entanto, também lhes diz como os comandos são configurados \(então você só precisará configurar seu controle uma vez para todos os núcleos, ao mesmo tempo, em vez de uma vez por núcleo\), a funcionalidade adicionada está geralmente disponível em vários núcleos e pode ser acessada da mesma maneira para cada um dos núcleos.

Resumindo, ele estabelece um padrão que os núcleos seguirão.

A interface do Retroarch permite que muitas configurações sejam alteradas, mas na maioria dos casos os padrões já devem estar corretos. No entanto, as opções do Núcleo, por exemplo, podem permitir que você altere a região do sistema em que está jogando no momento, se necessário. Como de costume, essas configurações não devem ser alteradas sem pensamento prévio.

Também inclui as funcionalidades básicas oferecidas por um emulador \(como _save states_, capturas de tela, troca de disco para sistemas baseados em CD, ...\), bem como parâmetros mais avançados \(shaders, rebobinamento e aceleração de quadros, netplay \(jogo em rede\), ...\) alguns dos quais podem ser acessados ​​usando **combinações com hotkey**.

## Requisitos <a id="requisitos"></a>

Embora Retroarch e Recalbox façam o possível para tornar as coisas mais fáceis para o usuário final, alguns núcleos têm requisitos para funcionar corretamente, como BIOS ou o formato de arquivo correto para um jogo; o webmanager pode informar qual BIOS você possui ou precisa para os diferentes sistemas emulados, e os arquivos `readme.txt` dentro de cada sistema dirão quais formatos são suportados para cada sistema.

Também recomendamos que você entenda o que está fazendo em certos sistemas \(como o arcade, por exemplo\), pois colocar arquivos aleatórios e esperar que funcionem pode simplesmente não funcionar, dependendo da situação.

