---
title: Gerenciar jogos Multidisco no PSX
---

# Gerenciar jogos Multidisco no PSX


>Informação:
>
>É possível ter **um único arquivo** para seus jogos **multidisco**.
>
>**Lembramos** que você deve ter **suas próprias imagens de discos PSX**.
>
>Basta **criar um arquivo eboot** contendo suas imagens **iso, bin, img** por meio do software gratuito **psx2psp**.
{.is-info}

## Criando o arquivo eboot​ <a id="criando-o-arquivo-eboot"></a>

* Encontre na internet a versão **psx2psp v1.42**, **baixe** e **execute**.
* **Escolha** o **modo clássico** e, na parte esquerda, **carregue suas isos uma por uma**
* **Escolha** a pasta para salvar.
* **Clique** no **botão Converter** e **aguarde**.

**Carregue** sua pasta ou **renomeie** o arquivo **eboot criado** para seu Recalbox na pasta `/recalbox/share/roms/psx`

## Troca de CD​ <a id="troca-de-cd"></a>

Para **mudar o CD durante o jogo**, você precisa **ativar duas ou três** **opções** no menu **Retroarch**.

* **Abra** o menu Retroarch durante o jogo \(por padrão Hotkey + B\)
* **Vá** para **configurações/configurações gerais** e defina a opção de configuração **salvar ao sair como ativado**.


>Aviso:
>
>A partir de então, **todas as alterações** feitas **nas opções serão salvas** quando você **sair do menu Retroarch**.
{.is-danger}

* **Vá** para **configurações/configurações de entrada/Vínculos das teclas de atalhos** e **procure as opções** com o nome: **alternar ejeção de disco, próximo disco, disco anterior.** Você deve então **atribuir-lhes teclas** em seu controle **que ainda não tenham uma função especial atribuída \(o padrão é configurar nos gatilhos como L1,R1,L2,R2\)**.
* **Saia do Retroarch** e **volte ao jogo.**


>Notas:
>
>Quando você estiver **na tela de um jogo pedindo para você trocar o CD**, você terá que ejetar virtualmente o CD \(pressionando hotkey + o atalho atribuído à opção de ejetar disco\), **para trocar o CD e virtualmente fechar a unidade de CD**.  
>Seu jogo será iniciado automaticamente no próximo CD.
{.is-warning}

## Para mudar o cd no PCSX-reARMed \(r22\)​ <a id="para-mudar-o-cd-no-pcsx-rearmed-r-22"></a>

### Método para arquivos .bin <a id="metodo-para-arquivos-bin"></a>

* **Entre** no **menu Retroarch** \(Hotkey + B\)
* No **menu rápido** ache a **opção controle de disco**
* **Ejete o cd virtual** escolhendo a opção **índice atual do disco**.
* Em seguida, **procure a pasta onde o cd** que você deseja carregar está localizado \(logicamente em `/recalbox/share/roms/psx`\) com a **imagem do disco anexada**.

