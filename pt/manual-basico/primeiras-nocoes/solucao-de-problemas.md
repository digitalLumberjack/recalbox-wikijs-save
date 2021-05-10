---
title: Solução de problemas
---

# Solução de problemas

## Controles <a id="controles"></a>

### O controle PS3 pisca, mas não emparelha. <a id="o-controle-ps-3-pisca-mas-nao-emparelha"></a>

* Conecte um controle ao Recalbox e aguarde 10 segundos.
* Agora você pode desconectar o controle e pressionar o botão Home.

### O controle PS3 parece morto <a id="o-controle-ps-3-parece-morto"></a>

* Você precisa restaurar as configurações de fábrica do controle. Faça isso apertando o pequeno botão atrás dele \(em um pequeno orifício\), com um clipe de papel.

## Exibição <a id="exibicao"></a>

### Borda preta, imagem muito grande

* Use sua TV para localizar o menu de imagem e definir o tamanho da imagem em 1: 1 pixel ou total.

Se isso não funcionar, tente ativar o overscan na caixa de seleção de configurações do sistema de menu.

Mais informações sobre como [ajustar o tamanho da imagem usando Overscan.](https://recalbox.gitbook.io/tutorials/v/portugues/video/configuracao-de-exibicao/ajustando-o-tamanho-da-imagem-usando-overscan)

### ​Tela preta no monitor do PC

Se você tiver uma tela preta no monitor do PC \(hdmi ou dvi\), edite o arquivo config.txt \(atualização na inicialização\) e exclua a linha `hdmi_drive=2`.

Mais informações em [Conecte seu Recalbox a um monitor DVI.](https://recalbox.gitbook.io/tutorials/v/portugues/video/lcd/conectando-o-recalbox-a-um-monitor-dvi)

## Sistema <a id="sistema"></a>

### Restaurar Padrões \(Hard Reset\) <a id="restaurar-padroes-hard-reset"></a>

Se você deseja reiniciar o sistema totalmente.

* Conecte um teclado USB e pressione a tecla Shift durante a inicialização.
* Você pode reinstalar o recalboxOS a partir daqui.

Todos os seus dados serão apagados.

​

### Acesso root <a id="acesso-root"></a>

Use como nome de usuário `root` e a senha `recalboxroot`

* Você pode se conectar via ssh ao recalbox.
* Você pode acessar um terminal saindo do emulationstation com F4 e, em seguida, pressionando ALT + F2.

Mais informações em [Acesso Root via terminal.](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)

