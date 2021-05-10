---
title: Monte a partição SHARE no formato ext4 em um Mac
---

# Monte a partição SHARE no formato ext4 em um Mac

## Instalação <a id="instalacao"></a>

Instale o software Paragon ExtFS disponível como um teste gratuito por 10 dias. Reinicie o seu Mac. Então, quando você inserir seu SD, todos os volumes Ext4 serão montados automaticamente na área de trabalho, incluindo a partição de compartilhamento. O link no site da Paragon: [https://www.paragon-software.com/home/extfs-mac/​](https://www.paragon-software.com/home/extfs-mac/)​

## Modificação da partição <a id="modificacao-da-particao"></a>


>**Importante:**
>
>Se você fez uma instalação básica, ou seja, gravou a imagem do Recalbox em um cartão microSD com Etcher, por exemplo, você não poderá modificar as partições.
{.is-info}

Se você quiser modificar as partições, você deve fazer uma instalação multiboot do Recalbox com PINN [https://sourceforge.net/projects/pinn/](https://sourceforge.net/projects/pinn/) que é uma alternativa ao NOOBS. Uma vez que o Recalbox está instalado, você desliga sua máquina, pega o microSD e o coloca no adaptador fornecido para conectar ao seu Mac. As partições aumentam e você pode modificá-las.

## Via rede <a id="via-rede"></a>

Inicie seu Recalbox. Vá ao Menu do Finder `Ir` vá até `Conectar ao Servidor` ou `cmd K`, digite o IP do Recalbox clique no botão`conectar como` na janela que se abre digite login: `root` Senha: `recalboxroot` escolher montar o volume SHARE.


>Observe que, para a transferência de muitos arquivos através do método de rede \(por exemplo, texturas de HD em pastas ocultas\), podem ocorrer erros relatados no Finder.
{.is-info}

