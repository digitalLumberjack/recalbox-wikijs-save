---
title: Jogue dois jogos diferentes no modo Gamelink
---

# Jogue dois jogos diferentes no modo Gamelink

O TGBDual permite que você jogue Gameboy e Gameboy Color simulando um cabo gamelink para multiplayer, porém, para usar dois jogos diferentes, a manipulação a ser feita é mais complexa.

Este tutorial presumirá que você já sabe como rodar um jogo em dois Gameboys com TGBDual.


>Usar dois jogos diferentes permite que você use o salvamento de jogos para cada gameboy.
{.is-success}

## Dois jogos, um sistema <a id="dois-jogos-um-sistema"></a>

A configuração mais simples é jogar dois jogos diferentes no mesmo sistema \(gb + gb ou gbc + gbc\), pois isso não requer nenhuma manipulação de salvamento.

Para isso, a primeira coisa a fazer é rodar um jogo do sistema desejado \(gb ou gbc\) com o TGBDual.


>Não importa qual jogo é iniciado aqui com o **TGBDual**, desde que **comece corretamente** e esteja **armazenado na pasta do sistema desejado**.
{.is-warning}

Assim que o jogo for iniciado, pressione **Hotkey+B** para acessar o menu Retroarch:

![Menu r&#xE1;pido do Retroarch](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYAFNfcHufLOAweFEY%2Fimage.png?alt=media&token=4ad3d0ca-2df4-4012-a1f7-9d2d3c8f8e72)

Em seguida, pressione o botão Voltar \(**A** por padrão em um Pi3B\) para acessar o menu principal.

![Menu Principal do Retroarch](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYAgpTJbLxZ5ohGv5Y%2Fimage.png?alt=media&token=9575d729-7f69-454b-a210-b4203bc568d0)

Uma vez neste menu, vá para **Load 2 Player Game Boy Link** e valide com **B**.


>Abaixo desta opção está atualmente escrito "Conteúdo atual: GameBoy \# 1" 
{.is-info}

Agora você chega na pasta que contém o jogo que você lançou originalmente, você precisa ir para o jogo desejado no primeiro Game Boy a ser usado e confirme com **B**.

![Menu permitindo a escolha do primeiro jogo](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYBL1TUqTYCn6W2KfW%2Fimage.png?alt=media&token=b632cbbb-02b4-4a61-8499-409d442178d0)


>Se o jogo estiver compactado, você terá que pedir para Navegar no arquivo e abrir a rom contida nele.
{.is-danger}

![Caso de um jogo compactado: voc&#xEA; deve navegar no arquivo ...](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYBiEvD5S6lzOtFYBf%2Fimage.png?alt=media&token=92b92aa6-10db-47e8-b532-0a01f2c9d311)

![... em seguida, selecione a rom desejada.](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYBllRmAz8ypQU57k5%2Fimage.png?alt=media&token=b541a3bd-d9d4-48dc-a446-e00e78cbe1f2)

Em seguida, nos encontramos novamente no menu principal, e devemos selecionar novamente **Load 2 Player Game Boy Link**.

![Selecionamos a op&#xE7;&#xE3;o novamente.](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYCaAw4CvBnp5txCUv%2Fimage.png?alt=media&token=b05b52fb-46fb-4922-8098-5a45edb5e1a7)


>Desta vez, abaixo da opção, está escrito "Conteúdo atual: GameBoy \# 2", o que significa que iremos escolher o jogo do segundo Game Boy.
{.is-info}

Estamos novamente no menu de seleção de jogos, mas, desta vez selecionaremos o jogo do segundo Game Boy.

![Sele&#xE7;&#xE3;o do segundo jogo](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYD9FoELV_qoHw55Qa%2Fimage.png?alt=media&token=edfafe57-d237-4fed-adaa-64a44329a356)


>Novamente, se o jogo estiver compactado, você terá que navegar pelo arquivo e abrir a rom contida nele.
{.is-danger}

Finalmente, nos encontramos em frente ao menu principal do Retroarch, e desta vez devemos selecionar a opção **Start 2 Player Game Boy Link**.

![No menu principal, podemos finalmente escolher iniciar os dois jogos](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYDnfJm2J-_Ary7TYx%2Fimage.png?alt=media&token=0dbf2a82-3c4a-4b91-bc1e-210e9c03e5f1)


>Abaixo da opção, é fornecido um resumo dos jogos selecionados para cada game boy
{.is-info}

![Resultado final](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LpY4wdX5hG9R-Rbt56a%2F-LpYEBAjAgTFaE5tdtcc%2Fimage.png?alt=media&token=d5f41a42-e3ab-46a8-9fca-42f889eab1c0)

## Dois jogos, dois sistemas diferentes. <a id="dois-jogos-dois-sistemas-diferentes"></a>

No caso de querermos rodar dois jogos, mas um da Game Boy Color, e o outro do Game Boy Original. Uma etapa adicional é necessária: Colocar o save dos dois jogos na mesma pasta antes de começar.

Então, se você quiser iniciar o sistema GBC a partir do Emulationstation, você terá que mover o save do jogo GB desejado \(em **share\saves\gb**\) para a pasta **share\saves\gbc**.


>Assim, para o jogo **Pokémon - Versão Blue** na pasta gb, você deve mover os arquivos  
>**Pokémon - Versão Blue.rtc**  
>e  
>**Pokémon - Versão Blue.srm**  
>Da pasta:  
>**share\saves\gb**  
>Para a pasta:  
>**share\saves\gbc**  
>Em seguida, quando o jogo terminar e o emulador for fechado, você precisa para devolver estes mesmos arquivos para o local original.
{.is-info}

