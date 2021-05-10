---
title: \[W\] Tutorial Unebootin
---

# \[W\] Tutorial Unebootin

## Recursos <a id="recursos"></a>

​[UNetbootin](https://unetbootin.github.io/) pode criar um [disco USB inicializável](https://pt.wikipedia.org/wiki/Live_USB)​

Carrega distribuições baixando arquivos ISO \(imagem de CD\) para você, ou, usando um arquivo ISO já baixado por você.

![](https://unetbootin.github.io/screenshot1.jpg)

## Utilizando o Unetbootin <a id="utilizando-o-unetbootin"></a>

Selecione um arquivo ou distribuição ISO para baixar, escolha uma unidade de destino \(unidade USB ou disco rígido\), e reinicie quando terminar. Se a sua unidade USB não for reconhecida, reformate-a no formato FAT32.

![](https://unetbootin.github.io/screenshot2.jpg)

![](https://unetbootin.github.io/screenshot3.jpg)

![](https://unetbootin.github.io/screenshot4.jpg)

​

Se você estiver usando o modo de instalação "pen drive": após a reinicialização, inicialize a partir do pen drive. Nos PCs, geralmente é suficiente pressionar a tecla Esc ou F12 imediatamente após a reinicialização do computador, enquanto no Mac você deve pressionar a tecla Opção antes de iniciar o OSX.

Se você estiver usando o modo de instalação "Disco rígido": Após a reinicialização, selecione a entrada UNetbootin no menu de inicialização.

## Instruções de remoção \(aplicável apenas a instalações de disco rígido\) <a id="instrucoes-de-remocao-aplicavel-apenas-a-instalacoes-de-disco-rigido"></a>

Se você estiver usando o Windows, o UNetbootin deve se oferecer para excluí-lo da próxima vez que o Windows iniciar. Como alternativa, você pode removê-lo via Adicionar / Remover Programas no Painel de Controle.

Se você estiver usando Linux, reinicie o executável UNetbootin \(com privilégios de administrador\) e pressione OK quando solicitado a desinstalar.

A remoção é necessária apenas se você tiver usado o modo de instalação "Disco rígido"; Para excluir o carregador de inicialização de uma chave USB, salve seu conteúdo e depois reformate-o.

A desinstalação do UNetbootin simplesmente remove a entrada UNetbootin do seu menu Iniciar; se você instalou um sistema operacional em uma partição usando o UNetbootin, a remoção do UNetbootin não removerá o SO.

Para excluir manualmente uma instalação do Linux, você deve restaurar o carregador de inicialização do Windows usando "fixmbr" de um CD de recuperação e usar o Parted Magic para apagar a partição Linux e redimensionar a partição do Windows.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Licen&#xE7;a</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p></p>
        <p>O UNetbootin foi criado e escrito por <a href="http://www.gkovacs.com/">Geza Kovacs</a> (Github
          : <a href="http://github.com/gkovacs">gkovacs</a>, Launchpad : <a href="https://launchpad.net/~gezakovacs">gezakovacs</a>,
          <a
          href="http://wiki.ubuntu.com/GezaKovacs">informa&#xE7;&#xF5;es de contato</a>).</p>
        <p></p>
        <p>Os tradutores s&#xE3;o referenciados na <a href="https://github.com/unetbootin/unetbootin/wiki/translations">p&#xE1;gina de tradu&#xE7;&#xF5;es</a>.</p>
        <p></p>
        <p>UNetbootin &#xE9; distribu&#xED;do sob <a href="http://www.gnu.org/licenses/old-licenses/gpl-2.0.html">licen&#xE7;a publica geral GNU (GPL) vers&#xE3;o 2</a> ou
          <a
          href="http://www.gnu.org/copyleft/gpl.html">superior</a>. O conte&#xFA;do do site (documenta&#xE7;&#xE3;o, capturas
            de tela e logotipos) &#xE9; distribu&#xED;do sob a <a href="http://creativecommons.org/licenses/by-sa/3.0/">licen&#xE7;a Creative Commons - Compartilhamento nas mesmas condi&#xE7;&#xF5;es 3.0</a>.</p>
      </td>
    </tr>
  </tbody>
</table>

