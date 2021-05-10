---
title: Tutorial Romulus
---

# Tutorial Romulus

## O que você precisa saber... <a id="o-que-voce-precisa-saber"></a>

### ​_Termos específicos_ <a id="termos-especificos"></a>

​_**Arquivo DAT**_: é um arquivo que contém informações sobre nome, tamanho, checksum, etc., de um ou mais arquivos, e pode ser importado usando o Romulus para exibir todas essas informações e verificar suas ROMs. O Romulus suporta todos os tipos de arquivos DAT, como formato XML, Clrmame pro, Romcenter, Offlinelist e muitos mais.

_**ROMs**_: Memória somente leitura. Esses arquivos são extraídos desse tipo de chip e podem ser usados ​​com emuladores para exibir jogos, aplicativos ou outras coisas como o sistema original. Hoje, chamamos de ROMs os arquivos extraídos de outros tipos de sistemas, como cassetes, disquetes, etc.

_**ISOs**_: Idêntico às ROMs, mas, extraídos de discos ópticos, como CDs, DVDs

_**Arquivos compactados**_: Não é necessário explicar que esses arquivos contêm um ou mais arquivos e que o uso de operações complexas pode reduzir o tamanho dos arquivos contidos nele. Romulus pode lidar com arquivos compactados nos formatos ZIP ![](https://romulus.cc/tutorial/imgs/zip.jpg), RAR ![](https://romulus.cc/tutorial/imgs/rar.jpg) e 7z ![](https://romulus.cc/tutorial/imgs/7z.jpg) representados no Romulus por meio das imagens exibidas.

_**Checksums**_ : É um cálculo matemático de um arquivo usado para gerar uma palavra especial combinando números e letras exclusivas para esse arquivo. Romulus pode lidar com diferentes tipos de checksums: CRC32, MD5 e SHA1. É importante saber que Romulus verifica o CRC32 e o tamanho sem perguntar, e é um método muito seguro. Os checksums MD5 e SHA1 são opcionais e disponíveis se o arquivo DAT contiver informações suficientes e, se ativadas, reduzirão a velocidade de varredura ou reconstrução de arquivos. Os arquivos compactados contêm informações sobre CRC32 e tamanho do arquivo, mas não MD5 e SHA1. É por isso que é necessário verificá-los para extraí-los do arquivo compactado e aplicar os checksums a eles, o que reduz ainda mais a velocidade. Dito isso, você deve saber que é mais rápido verificar arquivos compactados do que arquivos não compactados se o MD5 e o SHA1 não estiverem ativados.

_**Escanear os arquivos**_ ![](https://romulus.cc/tutorial/imgs/scan.jpg) : Este é o processo de verificar as ROMs em uma pasta com as informações no perfil para verificar se os checksums, tamanhos e nomes de arquivos são os mesmos.

_**Reconstrução de Arquivos**_ ![](https://romulus.cc/tutorial/imgs/rebuild.jpg) : O processo consiste em verificar as ROMs de uma pasta diferente da pasta ROMs para compará-las com o perfil inicial e agregar no local correto da pasta ROMs, os arquivos que talvez precisem ser adicionados porque não estão disponíveis na pasta ROMs.

_**TorrentZip & Torrent7z**_: Esses são arquivos compactados no formato Zip ou 7z, mas usando um aplicativo especial que atribui a todos os usuários o mesmo checksum se os arquivos compactados forem idênticos. Isso é útil para recuperar grandes conjuntos de roms com clientes **P2P Bittorrent**.

_**Modos de arquivos**_: Alguns arquivos DAT contêm informações de mais de uma maneira de classificar suas ROMs. Normalmente, os arquivos DAT contêm informações sobre a pasta **SETNAME**, que é a pasta do arquivo compactado que contém os **ROMNAMES**. Mas o DAT pode conter informações sobre os nomes dos parâmetros **MASTER** e **CLONE**, por exemplo, quando um jogo contém arquivos que em outro jogo são os mesmos, o que é muito comum em jogos de arcade, com versões diferentes de cada jogo.

​

## Os três modos de arquivo possíveis <a id="os-tres-modos-de-arquivo-possiveis"></a>

​_**Split / Not merged \(Dividido/Não-Mesclado\):**_ Todos os conjuntos estão em arquivos ou pastas próprios e sempre têm todos os arquivos necessários para serem executados \(mais espaço no disco é usado\)

_**Split / Merged \(Dividido/Mesclado\)**_ : Todos os conjuntos estão em seu próprio arquivo ou pasta e talvez precise que os arquivos do conjunto pai sejam executados

_**Not split \(Não dividido\)**_: todos os conjuntos de clones, se existentes, são colocados no arquivo ou na pasta do conjunto pai. Se não houver clones, é o único modo de arquivo que você pode selecionar

Exemplos :

| _**Split / Not merged \(Dividido/Não-Mesclado\)**_ | _**Split / Merged \(Dividido/Mesclado\)**_ | _**Not split \(Não dividido\)**_ |
| :--- | :--- | :--- |
| ​![](https://romulus.cc/tutorial/imgs/splitnotmerged.jpg)​ | ​![](https://romulus.cc/tutorial/imgs/xsplitmerged.jpg.pagespeed.ic.IACAU5BECh.webp)​ | ​![](https://romulus.cc/tutorial/imgs/notsplit.jpg) |

## **​**A primeira utilização​ <a id="a-primeira-utilizacao"></a>

Romulus usa um banco de dados para salvar as informações de seus arquivos DAT importados, diretórios de ROMs, configurações etc.

Na primeira execução, você verá uma mensagem sobre a criação do banco de dados com o nome "default.rml".​

##  Opções do menu principal \(Estão localizadas na parte superior do aplicativo Romulus\)  [​![](https://romulus.cc/tutorial/imgs/profiles.jpg)​](https://romulus.cc/tutorial/tutorial.php#Profiles) [​![](https://romulus.cc/tutorial/imgs/scanner.jpg)​](https://romulus.cc/tutorial/tutorial.php#Scanner) [​![](https://romulus.cc/tutorial/imgs/builder.jpg)​](https://romulus.cc/tutorial/tutorial.php#Builder) [​![](https://romulus.cc/tutorial/imgs/updater.jpg)​](https://romulus.cc/tutorial/tutorial.php#Updater) [​![](https://romulus.cc/tutorial/imgs/Statistics.jpg)​](https://romulus.cc/tutorial/tutorial.php#Statistics) [​![](data:image/webp;base64,UklGRgwEAABXRUJQVlA4IAAEAACwFQCdASpaACYAPpFCmEklpCIhJzv9sLASCWM7h6A32bOAkKXGVCYVeQIXZ3JHAAL/fyAaf+O3TsfrN/fPZ83t7b88fS12K4nN4Mld/kfWw+d8wPp3/gPQp4n35Z5g/XZ7u/73/iv2A+AP+V/1n/k9bX0O/1mPGAUePNLH9jNJVBsEZQnEvuCJ1itf2D1gMhiIYZnAXv629xCQgoBjv6MzntCfZZNyJd7+GBb9iSpXBhmqCueyAAD+9nv96LO/JnpRHVzMOtB0cJKMtXKY3LrFt+HauOcqu7b7eTqWdm07DC3einQsDyWgxCaoSfD6+Ve/FNnP5jN3p+TJoX9+/G9/Hrv4ahwKOjZDvOqwB9NX6c/p+b33MeXUGWmkTTN/sCdomXjBm1v9be39z160zruocaC5h0TDpbs8ymUT5Mkdhxa8gsg63wYEpEC9xC2qGAxhwLDAYw4GKiZmbZtm2cHAJX/AR5/BsmCcLyvrrroSjYAp4LO5mJexHcLttPFmHVjQHSd64XQfS84ohrW5mDLkZ9jOBiTp9MngMx6Ji6BGTvMY6IesyIrTlDPNPqDi+kQfn9PQKueFEuBMRjElC0PThltRuiNavfHiw1YmhfPAHUYmknS8tLW6NvhQnwTXqhkZ21/W4yArS6v3mZ9rUoT2K4HCiiKo79Vd40+Z369aSIqHku4o2kNtyWn65FR+yYHlT85x/zzTAwldJ58LF3qpy36vuRbojSZkz1JprmyfZ4H8klzgzMbZwfcuw+nkf73LRFfyLXH3tHqhedovys+f0ZFrY0j0g5tmOBuyrvct3ac7Y8uXOfGXVaedbEXBrIP+f8RVG/hi49N8W25AONEfln3XR3ZK/3kOa4cGM4azs3fzstxOnXjcSNx/m+tra+fYA0YYo2dSn6Yirs01GD1L/wugJIn24qD81bP96R7+ZhhshIU7lDXrj69i+TjRf7ztVb6Ge/DuPC35n/vIzc3G2gFHt+4n//Nvio82XJZf6L/sWO15hPkxdfWRw85qtPZJbFLtXtI5dwveZOlju7+g9ga2tigTkR4o2OICnFAgQLIS58gTaxdWB6OHsZ3cAbw0WPHw17s7/5NvQO7PdCWKNmOZB6FZJ/afXz2KBl7yruxvQBZWRUvdn2hcjq4gGWXWS/b5MjHzkwt7SG5qrKq4KEB2rFgkIc3ejCf6PMWRhvtkEX5uWL2rACshdpbnUb8L0PfohJVDrtfU6U3L2TLrM9P3jO+1RhKqYkb9tp+78r26LI75iXH1KqXTmqjy3O3+qzcXTC8g1AUvXxQkK+9uyfGw0sGvlqaraWDXzgReNhn6TvswAIkT9Xnnu2MM4F69kpcfLZ0ozWyOS5yUYAAA)​](https://romulus.cc/tutorial/tutorial.php#Settings) [​![](https://romulus.cc/tutorial/imgs/help.jpg)](https://romulus.cc/tutorial/tutorial.php#Help)



###  ![](https://romulus.cc/tutorial/imgs/profiles.jpg)\(_Profiles/Perfis_ : A primeira etapa\) <a id="profiles-perfis-a-primeira-etapa"></a>

Adicione os novos arquivos DAT à lista à direita. Você pode pressionar o botão ![](https://romulus.cc/tutorial/imgs/opendat.jpg) e selecioná-los ou **arrastar e soltar** seus DATs na lista correta. Eles podem ser arquivos compactados ou descompactados. Você pode extrair um arquivo DAT e importá-lo do **EXE baseado em MAME** usando este botão ![](https://romulus.cc/tutorial/imgs/createmamedat.jpg)​

Quando o processo estiver concluído, você verá na lista à direita as principais informações sobre os arquivos DAT importados, se desejar, pode excluir os arquivos DAT antigos agora.

Todos os perfis contêm 2 imagens, uma para o **status do perfil** e outra para o **tipo de origem DAT**.​

![](https://romulus.cc/tutorial/imgs/smiles.jpg)

**​Status do rosto verde:** seu perfil está completo antes de digitalizá-lo. **Status do rosto amarelo:** seu perfil contém um ou mais arquivos corretos, mas não está completo. **Status do rosto vermelho:** seu perfil foi verificado, mas não contém nenhum arquivo correto. **Status do rosto cinza:** seu perfil ainda não foi verificado.

A lista de perfis pode ser **filtrada** usando o botão de faces na parte inferior da janela.

Agora basta **clicar duas vezes para carregar o perfil** e ver todas as informações na opção Scanner.

A lista de perfis à esquerda é uma árvore de pastas que podem ser movidas, excluídas ou editadas para organizar seus perfis. Por exemplo, você pode criar uma pasta chamada ARCADE para seus perfis "Arcade", outra para consoles etc. Basta usar o **botão direito do mouse** dentro desta lista para ver as diferentes opções disponíveis. Você pode **arrastar e soltar** perfis para essas pastas para organizá-los também. É possível criar pastas dentro de pastas, e lembre-se: se nenhuma pasta for selecionada quando você adicionar um novo DAT, esse novo perfil será adicionado na pasta roxa não editável e removível chamada "**DEFAULT**" \("PADRÃO"\).

#### Mais opções de perfis <a id="autres-options-de-profils"></a>

No menu dos botões superiores é possível encontrar ![](https://romulus.cc/tutorial/imgs/opendb.jpg) o botão abrir banco de dados, que pode ser usado para abrir outro banco de dados Romulus existente no seu computador ou, ![](https://romulus.cc/tutorial/imgs/newdb.jpg)o botão novo de banco de dados Romulus, para criar um novo banco de dados vazio.

Também é possível salvar a lista de perfis nos formatos HTML, DOC ou TXT usando ![](https://romulus.cc/tutorial/imgs/log.jpg) o botão "log".

Usando o botão direito do mouse na lista de perfis, você pode ver mais opções, como excluir perfis selecionados, selecionar tudo na lista, inverter a seleção. Fazer ![](https://romulus.cc/tutorial/imgs/scanb.jpg) um **scan ou** ![](https://romulus.cc/tutorial/imgs/rebuildb.jpg) **reconstruir automaticamente** para 1 ou mais perfis ao mesmo tempo ou visualize propriedades usando a opção escanear em lote ou reconstruir em lote.

Você pode ![](https://romulus.cc/tutorial/imgs/sendgen.jpg) **enviar ao construtor** um perfil. Uma opção interessante para editar um perfil. Esta opção será explicada mais tarde. Você pode **criar ou definir automaticamente o caminho das ROMs** para os perfis selecionados usando o ![](https://romulus.cc/tutorial/imgs/dircreator.jpg) **Criador de pastas**.

Para esta opção, apenas defina a **pasta base** onde deve estar o caminho das ROMs e as **regras que você deseja** e o nome das pastas que deseja definir na **coluna Descrição do perfil** ou na **coluna Nome do perfil.**

![Janela &quot;Criador de Pastas&quot;](https://romulus.cc/tutorial/imgs/xdircpic.jpg.pagespeed.ic.F2ttHWWUFT.webp)

**Propriedades** ![](https://romulus.cc/tutorial/imgs/properties_.jpg) é uma opção para modificar as informações principais de alguns perfis, como descrição, email, página inicial ou **modo de arquivo. Esta opção também está disponível no menu Escanear.**

![Janela &quot;Propriedades&quot;](https://romulus.cc/tutorial/imgs/properties.jpg)

### ​![](https://romulus.cc/tutorial/imgs/scanner.jpg)\(_Escâner_ : O local para verificar e reconstruir suas ROMs\) <a id="escaner-o-local-para-verificar-e-reconstruir-suas-roms"></a>

Aqui pode exibir todas as informações de perfis e mais coisas a serem explicadas. As informações serão mostradas como **modo de arquivo** definido pelo usuário, nas opções de propriedades disponíveis no menu de botões, e, também disponíveis no menu pop-up da lista principal de perfis.

Nas listas, você encontrará 2 imagens para a linha, uma para o status de conclusão do conjunto e outra para a indicação de mestre ou clone.

![](https://romulus.cc/tutorial/imgs/setsstatus.jpg)

**Pasta verde**: todo o conjunto está completo **Pasta amarela**: conjunto incompleto **Pasta vermelha**: nada deste conjunto

 ![](https://romulus.cc/images/asterisk.gif) Nos perfis **Offlinelist/Lista off-line,** não existem conjuntos de clones ou mestre e as imagens são alteradas para **sinalizadores de região** e, na lista de colunas, serão exibidas informações adicionais para esse tipo de DATs. A lista off-line já possui informações sobre **atualizações** e **imagens** para esse perfil que podem ser aplicadas usando o ![](https://romulus.cc/tutorial/imgs/offupdater.jpg) Botão **Atualizar Lista off-line**.

![Bot&#xE3;o &quot;Atualizar Lista off-line&quot;](https://romulus.cc/tutorial/imgs/offupic.jpg)

​![](https://romulus.cc/tutorial/imgs/scan.jpg) O botão de escanear mostra a tela com as informações necessárias para começar a verificar suas ROMs. ![](https://romulus.cc/tutorial/imgs/scanb.jpg) O processo de verificação pode ser automático para todos os perfis carregados na opção Escaner. ![](https://romulus.cc/tutorial/imgs/rebuild.jpg) O botão reconstruir mostra a mesma tela que o escaner, mas procura outra pasta para detectar e inserir novos arquivos de ROMs na pasta principal de ROMs. Você também pode fazer uma reconstrução com **arrastar e soltar** **pastas/arquivos** para a lista de perfis carregados. ![](https://romulus.cc/tutorial/imgs/rebuildb.jpg) A reconstrução pode ser automática para todos os perfis carregados na opção Escanear. Ao pressionar este botão, o Romulus solicitará que a pasta para reconstruir.

![Janela &quot;Escanear/Reconstruir&quot;](https://romulus.cc/tutorial/imgs/scanscreen.jpg)

O **caminho das ROMs** pode ser definido ao clicar duas vezes com o mouse na lista de pastas ou pressionar ![](https://romulus.cc/tutorial/imgs/folder.jpg) o botão da pasta.

O método de compressão pode ser definido usando este botão![](https://romulus.cc/tutorial/imgs/compmode.jpg), e o número exibido na lista de diretórios é o nível de compactação \(0 para armazenado - 9 para máximo\). ![](https://romulus.cc/images/asterisk.gif) Às vezes, se o perfil tiver as informações, você verá uma seleção de **SAMPLES/AMOSTRAS** ou **CHDs** nas pastas, se estas informações não estiverem preenchidas, Romulus usará o caminho das ROMs como padrão para esse tipo de arquivo.

 **Backup path/Local do backup** é a pasta em que as ROMs não detectadas serão colocadas.

Após a verificação/reconstrução, você pode ativar a verificação dos checksums **MD5** ou **SHA1**, **Torrentzip** ou **Torrent7z**.

**Headers/Cabeçalhos**, são regras para a conversão de ROMs válidas para os checksums disponíveis. Por exemplo, uma ROM pode ser o mesmo jogo, mas pode ter checksums diferentes, por quê? Às vezes, informações desnecessárias são inseridas nas ROMs, obtendo checksums diferentes. Os cabeçalhos podem remover ou modificar essas informações para tornar o checksum igual aos perfis. Lembre-se de que se esta opção está ativada, diminuirá a velocidade de apenas reconstruir ou corrigir o processo de ROMs. Os arquivos de cabeçalho devem estar dentro da pasta Headers/Cabeçalhos do Romulus EXE.

Agora, basta apertar **Start** para iniciar o processo de verificação/reconstrução.

Voltando à opção Escâner, há mais opções disponíveis: ![](https://romulus.cc/tutorial/imgs/emulators.jpg) Configure **emuladores** para rodar nos jogos listados. Você pode configurar no máximo 10 emuladores para rodar suas roms para o perfil carregado. Mais tarde, você pode executá-lo e selecionar seu jogo com o botão direito do mouse na sua lista e selecionar o emulador configurado.

![Janela &quot;Configurar Emuladores&quot;](https://romulus.cc/tutorial/imgs/emupic.jpg)

​![](https://romulus.cc/tutorial/imgs/ffix.jpg)Faça **friendfixes/correções para amigos**. É um DAT que contém apenas os arquivos que você precisa, por exemplo, para enviar a um amigo e reconstruir para obter os arquivos ausentes. Esse processo pode ser automático para todos os perfis carregados usando![](https://romulus.cc/tutorial/imgs/ffixplus.jpg) este botão. ![](https://romulus.cc/tutorial/imgs/properties_.jpg) Propriedades. Modifique algumas informações sobre perfis carregados. **Esta opção também está disponível no menu Perfis.** ![](https://romulus.cc/tutorial/imgs/log.jpg) Salve a lista em diferentes formatos.

​

### ​![](https://romulus.cc/tutorial/imgs/builder.jpg)\(_Construtor:_ crie seus próprios DATs\) <a id="construtor-crie-seus-proprios-dats"></a>

Aqui você pode criar seu **próprio DATs no formato XML** para compartilhar com seus amigos ou usar para si mesmo. Basta **arrastar e soltar uma pasta** na lista ou usar o![](https://romulus.cc/tutorial/imgs/hash.jpg) botão hash/resumir da pasta, para iniciar o processo.

Você pode forçar a verificação dos checksums![](https://romulus.cc/tutorial/imgs/md5.jpg)**MD5** ou **SHA1**![](https://romulus.cc/tutorial/imgs/sha1.jpg), pressionando os botões exibidos ou **forçar a verificação de arquivos compactados** ou **hash/resumir como um único arquivo** usando este botão![](https://romulus.cc/tutorial/imgs/compmode.jpg).

Quando o processo estiver concluído, você pode **exportar** as informações com o![](https://romulus.cc/tutorial/imgs/ffix.jpg)Botão **Criar arquivo XML DAT**. A lista que pode ser exportada pode ser editada, removendo **conjuntos completos** ou **apenas arquivos** usando as caixas de seleção

​

### ​![](https://romulus.cc/tutorial/imgs/updater.jpg)\(_Atualizar_ : Encontre novos e atualizações para DATs\) <a id="atualizar-encontre-novos-e-atualizacoes-para-dats"></a>

Essa opção interessante oferece a possibilidade de visualizar uma lista de **centenas de perfis** para conhecer as versões atuais.

O Romulus detecta automaticamente se os **perfis listados** não estão disponíveis, desatualizados ou atualizados comparando com os perfis disponíveis no banco de dados atual, usando sinalizadores para indicá-lo.

| ![](https://romulus.cc/tutorial/imgs/uptodate.jpg) | ![](https://romulus.cc/tutorial/imgs/outdated.jpg) | ![](https://romulus.cc/tutorial/imgs/notfound.jpg) |
| :---: | :---: | :---: |


**Bandeira verde:** perfil atualizado  
**Bandeira amarela:** Perfil desatualizado  
**Bandeira roxa:** perfil novo ou não encontrado

![](https://romulus.cc/tutorial/imgs/updaterpic.jpg)

Você já pode filtrar a lista pressionando os botões de bandeiras. Clicando duas vezes no perfil selecionado, você pode navegar para a página inicial dos DATs, mas se o perfil for um **perfil da Lista off-line**, você verá a janela do atualizador para a Lista off-line e poderá atualizá-lo ou obter novas imagens.

​

### ​![](https://romulus.cc/tutorial/imgs/Statistics.jpg)\(_Estatísticas_ : Tente obter tudo, se puder\) <a id="estatisticas-tente-obter-tudo-se-puder"></a>

Nada de especial, informações sobre seu **status de conclusão**, como você pode ver na foto.

![](https://romulus.cc/tutorial/imgs/statpic.jpg)

Nesse caso, nenhuma ROM foi encontrada para os perfis disponíveis e eu tenho os 100% não concluídos

### ​![](https://romulus.cc/tutorial/imgs/settings.jpg)\(_Configurações_ : Configurar e personalizar\) <a id="configuracoes-configurar-e-personalizar"></a>

Escolha seu idioma, modifique alguns aspectos visuais do Romulus, compactação padrão para novos perfis adicionados, selecione os grupos DAT desejados para encontrar no menu **Atualizar**, e outras coisas.

![Janela &quot;Configura&#xE7;&#xF5;es&quot;](https://romulus.cc/tutorial/imgs/setpic.jpg)

###  ![](https://romulus.cc/tutorial/imgs/help.jpg)\(_Ajuda_ : uma opção para ir ao site do Romulus\) <a id="ajuda-uma-opcao-para-ir-ao-site-do-romulus"></a>

Clique nesta opção para ir para a [página inicial do Romulus](https://romulus.cc/index.php).

​**Fonte:** [Romulus Rom Manager © **Coded by F0XHOUND 2010 - 2020**](https://romulus.cc/tutorial/tutorial.php)**​**

