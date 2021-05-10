---
title: Preparação e Instalação do Recalbox
description: Como instalar o Recalbox
---

# Preparação e Instalação do Recalbox

É possível instalar o Recalbox em diversos dispositivos, porém os mais comuns são os consagrados Raspberry Pi \(0, 0w, 1, 2, 3 e 3B+\). O Recalbox também é compatível com a Odroid C2 e XU4, assim como diversos [computadores 32 e 64 bits](/hardware-compatibility/compatible-pcs).

## Os acessórios necessários

Verifique se você possui o dispositivo de armazenamento necessário e a fonte de alimentação para o dispositivo escolhido.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Categoria</th>
      <th style="text-align:left">Raspberry 0/0w/1/2/3/3+</th>
      <th style="text-align:left">Odroid XU4/XU4Q</th>
      <th style="text-align:left">PC (32 ou 64 bits)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Alimenta&#xE7;&#xE3;o</b>
      </td>
      <td style="text-align:left">micro USB <b>2.5A </b>(de boa qualidade)</td>
      <td style="text-align:left">Usar alimenta&#xE7;&#xE3;o oficial Odroid</td>
      <td style="text-align:left">Alimenta&#xE7;&#xE3;o PC padr&#xE3;o</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>V&#xED;deo</b>
      </td>
      <td style="text-align:left">Cabo HDMI, HDMI2VGA, HDMI2DVI</td>
      <td style="text-align:left">Cabo HDMI</td>
      <td style="text-align:left">HDMI, VGA (e provavelmente DVI e DP)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Controles</b>
      </td>
      <td style="text-align:left">USB ou Bluetooth</td>
      <td style="text-align:left">USB ou Bluetooth</td>
      <td style="text-align:left">USB ou Bluetooth</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Armazenamento </b>Sistema</td>
      <td style="text-align:left">Cart&#xE3;o micro SD 8GB+
        <br />classe 10 (pi1: SD)</td>
      <td style="text-align:left">Cart&#xE3;o micro SD 8GB+</td>
      <td style="text-align:left">Pendrive ou Disco R&#xED;gido 8GB+</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Armazenamento<br /></b>Configura&#xE7;&#xF5;es</p>
        <p>BIOS e ROMs</p>
      </td>
      <td style="text-align:left">Disco r&#xED;gido externo com fonte de alimenta&#xE7;&#xE3;o pr&#xF3;pria</td>
      <td
      style="text-align:left">Disco r&#xED;gido externo com fonte de alimenta&#xE7;&#xE3;o pr&#xF3;pria</td>
        <td
        style="text-align:left">Disco r&#xED;gido interno ou Disco R&#xED;gido Externo USB (Conectado
          a placa-m&#xE3;e)</td>
    </tr>
  </tbody>
</table>




>**INFORMAÇÃO:**
>
>Você precisa dos seguintes itens para criar seu Recalbox:  
>Não hesite em visitar a [nossa loja](https://www.recalbox.com/fr/shop/)!
{.is-info}

## Download

O primeiro passo é baixar a imagem adequada para o seu tipo de hardware, na extensão .img.xz em [archive.recalbox.com](https://archive.recalbox.com).




>**IMPORTANTE :**
>
>Só a **última versão** da Recalbox está disponível.
>
>As **versões antigas** não estão disponíveis para **download, nem são suportadas** pela equipe de desenvolvedores.
{.is-danger}

## Gravando a imagem

Usando um programa para gravar a imagem do **Recalbox OS** em sua mídia de armazenamento \(cartão SD, cartão eMMC ou disco rígido\).


>**Notas:**
>
>Você deve usar mídia de 8 GB para o sistema \(recomendamos a **série** **Sandisk Ultra** para cartões SD\).
>
>* Para **instalação em um Rpi:**
>  * Como armazenamento: um **cartão SD**.
>* Para **instalação no Odroid**:
>  * Como armazenamento: um **cartão SD** **ou eMMC**.
>* Para **instalação em x86 e x86\_64**:
>  * Como armazenamento: um **disco rígido**.
{.is-warning}

[Tutorial Balena Etcher](https://recalbox.gitbook.io/tutorials/v/portugues/utilitarios/gravando-a-imagem/tutorial-balena-etcher)

[\[W\] Tutorial​ Rufus](https://recalbox.gitbook.io/tutorials/v/portugues/utilitarios/gravando-a-imagem/w-tutorial-rufus)

[\[W\] Tutorial Unebootin](https://recalbox.gitbook.io/tutorials/v/portugues/utilitarios/gravando-a-imagem/w-tutorial-unebootin)

## Instalação <a id="instalacao"></a>

### Rpi

* Insira o cartão microSD no dispositivo com o qual deseja usar o Recalbox.
* Inicie e você verá o Recalbox ganhar vida.

### Carcaça Retroflag GPI

Siga [este link](/v/portugues/manual-basico/primeiros-passos/preparacao-e-instalacao-do-recalbox/retroflag-gpi-case).

### Odroid <a id="odroid"></a>

* Insira seu cartão microSD ou eMMC no dispositivo com o qual deseja usar o Recalbox.
* Inicie e você verá o Recalbox ganhar vida.

### X86 / X86\_64


>**Notas:**
>
>A instalação em um dispositivo USB \(todos os materiais combinados\) é recomendada apenas para fins de teste, porque pode ocasionalmente causar bugs não presentes na  instalação no disco rígido.
>
>Portanto, direcionamos você para **uma instalação em discos rígidos:**
>
>* Um para o **Sistema**.
>* Um para **Armazenamento** de ROMs, BIOS, saves, etc...
{.is-warning}

* Insira seus **dois discos** rígidos \(sistema e armazenamento\) no computador desejado.
* Configure sua **BIOS** no modo **Legacy**.

  * Para configurar sua BIOS no Legacy, ao iniciar o computador, pressione a tecla de acesso à BIOS **`F*`** \(diferente dependendo do fabricante, geralmente F2, mas pode ser F1, DEL, etc, consulte o manual da sua placa mãe\).
  * Continue
  * Em seguida, atribua Legacy ativando-o com "**enabled**"

* Verifique se a **inicialização segura** está desativada.

  * Continue
  * Em seguida, atribua OFF ou Disable para Secure Boot.
  * Desligue o computador.

* Acesse o **menu de inicialização** dos discos rígidos.

  * Pressione **`F*`** para acessar o menu de inicialização dos discos rígidos \(geralmente F12\)
  * Selecione o **disco rígido do sistema** Recalbox.

* **Reinicie o computador** e você verá o Recalbox ganhar vida após alguns minutos \(dependendo do espaço de armazenamento do disco do sistema\).
* **\[Opcional: no caso de pc dedicado\]** Atribua a **ordem de inicialização** dos discos rígidos.
  * Continue
  * Em seguida, **atribua o disco rígido** que você deseja dedicar ao **sistema em primeiro lugar** e o de **armazenamento em segundo**.
  * **Reinicie** o computador. Atribuindo a ordem dos discos rígidos de sistema e armazenamento, você não precisa mais **acessar o menu de inicialização** durante a inicialização.



