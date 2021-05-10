---
title: �� FAQ
---

# �� FAQ

## Geral <a id="emulationstation"></a>

* **Onde posso instalar o Recalbox OS?**

  > - Raspberry Pi 1 \(B/B+\)  
  > - Raspberry Pi Zero  
  > - Raspberry Pi 2  
  > - Raspberry Pi 3 \(B/B+\)  
  > - Odroid XU4  
  > - PC \(x86/x86\_64\)

* **Como posso participar?**

  > - Você pode fazer uma doação:  
  >  - Você pode relatar bugs ou ideias para melhorias em nosso [Gitlab](https://gitlab.com/recalbox/recalbox/issues).  
  >  - Você pode participar dos fóruns Recalbox.com  
  >  - Você pode continuar traduzindo o Gitbook entrando em contato com Lionsquall no Discord.

* **Onde posso ver o andamento do desenvolvimento do Recalbox?**

  > No gitlab do Recalbox-os.  
  > Você pode acessar:  
  > - os '[issues](https://gitlab.com/recalbox/recalbox/issues)' que são as tarefas atuais.  
  > - nos 'milestones' poderá ver as tarefas que ainda estão por desenvolver e as que já foram concluídas

* **Onde posso encontrar as instruções de uso?**

  > Você pode encontrar o guia do usuário aqui no Gitbook na [Documentação](/fr/).

* **Quantos jogos o Recalbox tem?**

  > Tentamos adicionar o máximo possível de jogos grátis à distribuição, para que você possa aproveitar a experiência do Recalbox desde o primeiro lançamento!  
  > Vá para[https://forum.recalbox.com/topic/52/homebrews-sur-la-recalbox](https://forum.recalbox.com/topic/52/homebrews-sur-la-recalbox) para enviar seus homebrews!

* **Posso usar o Recalbox em um bartop/Fliperama?**

O sistema Recalbox OS também foi projetado para integração em terminais e bartops.  
- Você pode conectar os botões e joysticks diretamente aos GPIOs do Raspberry.  
- Você pode desativar os menus para evitar qualquer manuseio incorreto.  
- Também é possível usar as saídas HDMI/DVI/VGA \(com adaptador\) ou RCA.  
- Mais informações na página [específica da wiki.](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/instalacao/configuracao-do-recalbox-para-um-bartop-terminal-arcade)​

* **O Recalbox suporta cerca de trinta consoles, mas só vejo alguns na interface, o que devo fazer?**

Apenas sistemas com jogos disponíveis são exibidos.  
Tente adicionar suas roms \([veja aqui](/v/portugues/manual-basico/gerenciamento-de-arquivos/adicionar-conteudo)\) via rede e reinicie o Recalbox para ver os novos sistemas aparecerem. Além disso, alguns hardwares não oferecem suporte a todos os consoles.  
Mais informações sobre: [aqui.](/compatibility/emulators-compatibility)​

* **Devo fazer overclock no meu Raspberry Pi?**

No Raspberry Pi 1 \(e também no zero\), é altamente recomendável fazer um overclock do Raspberry no modo EXTREMO \(você perde a garantia, mas o ganho de desempenho é fenomenal\).

## Solução de Problemas Diversos <a id="solucao-de-problemas-diversos"></a>

* **Meu Recalbox acabou de travar, devo desliga-lo e liga-lo novamente?**

  > Não, na maioria dos casos o sistema não travou completamente, apenas o EmulationStation travou.
  >
  >
  >
  > Existem várias maneiras de lidar com esta situação, a mais fácil é usar os recursos de depuração do web manager para reiniciar o ES ou para desligar o Recalbox de maneira adequada.
  >
  >
  >
  > Não fazer isso pode corromper seus dados, especialmente se você estiver usando um Raspberry Pi com um cartão SD.

## Emulationstation <a id="emulationstation-1"></a>

* **Como mudar a aparência do tema do EmulationStation ?**

> Tecla Enter no teclado ou Start no controle → Configurações de interface → Tema \(na parte inferior\)

* **Como parar a música de fundo ?**

> Tecla Enter no teclado ou Start no controle → Configuração de som → Mude para Off

* **Onde estão os arquivos de configuração do Emulationstation no sistema de arquivos?**

> /root/.emulationstation

* **Onde estão os temas do Emulationstation?**

> /root/.emulationstation/themes

## Emulação <a id="emulation"></a>

* **Por que existem vários emuladores para cada sistema?**

> A emulação não é uma operação perfeita, há um equilíbrio entre desempenho, recursos e fidelidade. Como a emulação não é perfeita, é melhor ter várias opções para lidar com isso. Às vezes, um emulador mais rápido será melhor, mas pode ter falhas inesperadas, enquanto um mais lento pode ter uma precisão maior, mas não suporta alguns recursos específicos.

* **Como alterar o emulador padrão para um determinado sistema?**

> Pressione Start no controle, vá para as Configurações avançadas e, em seguida, para Configuração avançada dos emuladores, você pode selecionar o sistema desejado, finalmente, você pode alternar as configurações do Emulador e do Núcleo \(Observe que a configuração do Núcleo não mudará se a configuração do Emulador disser "Padrão"\)

## Sistema <a id="sistema"></a>

* **O Recalbox suporta mais de trinta consoles, mas eu só vejo alguns, seja na interface do EmulationStation ou na pasta de SHARE?**

> Dependendo da placa que você usa, você terá emuladores compatíveis com ele.  
> Consulte a [lista de compatibilidades de acordo com as placas](/compatibility/emulators-compatibility).

* **Por que em alguns sistemas como o GBA, meus jogos exibem uma tela preta e voltam para o ES?**

Alguns sistemas requerem BIOS para funcionar.  
Mais informações na página [wiki dedicada.](/v/portugues/manual-basico/gerenciamento-de-arquivos/adicionar-conteudo#adicionar-bios)​

## Conectividade <a id="conectividade"></a>

### Windows 10 - impossível de conectar o Recalbox pela rede <a id="windows-10-impossivel-de-conectar-o-recalbox-pela-rede"></a>

#### Caso n°1: Nenhum computador é visível, incluindo Recalbox, a partir do Windows <a id="caso-n-1-nenhum-computador-e-visivel-incluindo-recalbox-a-partir-do-windows"></a>

Se você não vir nenhum computador à partir da rede de Windows 10, é porque a descoberta de rede está desativada por padrão e a configuração de rede está definida como "pública" ou "tornar este PC detectável" está definido como "desativado" "

Você deve aceder as configurações de rede e colocar sua rede no modo "privado" ou colocar "tornar este PC detectável" como "ativado".

#### Caso n°2: O Recalbox não está mais acessível desde a atualização 1709 do Windows 10 <a id="caso-n-2-o-recalbox-nao-esta-mais-acessivel-desde-a-atualizacao-1709-do-windows-10"></a>

Desde essa atualização, você vê o Recalbox na sua rede, mas não pode mais acessá-lo.

Explicação oficial \(em emglês\): [https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/](https://tech.nicolonsky.ch/windows-10-1709-cannot-access-smb2-share-guest-access/) ou [https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016](https://support.microsoft.com/fr-fr/help/4046019/guest-access-smb2-disabled-by-default-in-windows-10-server-2016)​

Reparo rápido: faça o download e aplique este [patch](https://mega.nz/#!rUA3xDgI!a14w9TqQWinLriLANpk7BF_WkoNg8mw6fHloyPEZMPg)​

Este patch desativará a segurança no acesso anônimo à rede no Windows para restaurar o acesso ao Recalbox.

#### Caso n° 3 \(caso o mais comum\) <a id="caso-n-3-caso-o-mais-comum"></a>

* ​**Vá** para:`Configurações / Aplicativos / Programas e recursos / Ativar ou desativar recursos do Windows`
* Ative **marcando**: `Suporte para compartilhamento de arquivos SMB 1.0 / CIFS / cliente SMB1.0 / CIFS ...`
* Em seguida, **reinicie o Windows.**

