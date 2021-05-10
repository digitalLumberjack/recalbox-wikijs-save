---
title: Retroachievements
---

# Retroachievements

## Desafio/Conquistas com **retroarch :** <a id="challenge-succes-avec-retroarch"></a>

O site [retroachievements.org](http://www.retroachievements.org/) oferece **desafios/conquistas/troféus** em plataformas como NES, SNES, GB, GBC, GBA, Megadrive / Genenis, PCengine, em breve FBA libretro, N64, GameGear.

## Crie a sua conta: <a id="creation-dun-compte"></a>

* **Você precisa** [criar uma conta](http://retroachievements.org/createaccount.php) no site [retroachievements.org](http://www.retroachievements.org/).
* **Anote seu nome de usuário** e **senha** em algum lugar, pois eles serão usados ​​para **configurar os Retroachievements no retroarch.**

## **Ativação da conta no Emulationstation do RecalboxOS**  <a id="activation-du-compte-dans-emulationstation-sous-recalboxos"></a>

* Conecte seu teclado seu teclado
* **Abra o menu** Emulationstation \(botão START\)
* Em seguida, **vá para:**`Configurações de Jogos > Opções de Retroachievements`

![](https://raw.githubusercontent.com/wiki/recalbox/recalbox-os/images/menu_es_retroachievements1.png)

* **Edite** assim: `Retroachievements > ON` `Nome de Usuário > coloque o nome de usuário que você criou` `Senha > coloque a senha`

## **A**tivação da conta manualmente no recalboxOS <a id="activation-du-compte-manuellement-sous-recalboxos"></a>

Você precisa editar o arquivo [**recalbox.conf:**](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)\*\*\*\*

* \*\*\*\*[**Via ssh**](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal) com putty e o nano`nano /recalbox/share/system/recalbox.conf` ou [winscp](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp) com o editor Notepad ++
* **Adicione essas 3 linhas**, substituindo usuário e senha por aqueles criados durante o seu registro.

  ```text
  ## Enable retroarchievements (0,1)
  ## Set your www.retroachievements.org username/password
  ## Escape your special chars (# ; $) with a backslash : $ => \$
  global.retroachievements=1
  global.retroachievements.hardcore=0
  global.retroachievements.username=
  global.retroachievements.password=
  ```


>**Informação:**
>
>**O modo hardcore desativa as funções** de rebobinar, crédito ilimitado, etc...
{.is-info}

* **Salve** seu **recalbox.conf**
* **Reinicie** seu Recalbox.

## **C**onfiguração de emuladores/núcleos compatíveis com Retroachievements. <a id="configuration-des-emulateurs-core-compatible-avec-retroachievements"></a>


>**Nota:**
>
>**Nem todos os núcleos** libretro **são compatíveis** com **Retroachievements.**
{.is-warning}

​

Aqui está a **lista de emuladores/núcleos** que funcionam com **Retroarch/Retoachievements**:

* **Abra o menu** do Emulationstation \(botão START\)
  * **Depois** `Configurações de Jogos > avançado >`
* NES &gt; EMULADOR LIBRETRO &gt; NÚCLEOS QUICKNES / FCEUMM
* SNES &gt; EMULADOR LIBRETRO &gt; NÚCLEO SNES9X\_NEXT
* GB/GBC/GBA &gt; PADRÃO _\(DEFAULT\)_
* MEGADRIVE &gt; PADRÃO _\(DEFAULT\)_ \(picodrive\)
* PCENGINE &gt; PADRÃO _\(DEFAULT\)_ \(no momento não é suportado pelo núcleo libretro principal\)
* FBA Libtreto / Neogeo FBA Libretro &gt; PADRÃO _\(DEFAULT\)_ \(em breve versão 2018.x.x\)
* GameGear &gt; Genesis \(PADRÃO _\(DEFAULT\)_ \) \(em breve versão 2018.x.x\)
* N64 &gt; Emulador \(Libretro\) , Glupen64 \(núcleo\) \(em breve versão 2018.x.x\)

​


>**Informação:**
>
>Para **visualizar os desafios/troféus** no **Retroach**, basta **ativar o menu Retroarch** \(Hotkey + B\)  
>`Menu rápido> Lista de conquistas` 
>
>A **lista de jogos compatíveis** está disponível  [nesta página](http://retroachievements.org/gameList.php)​
{.is-info}

## Quais roms são compatíveis? <a id="quelles-roms-sont-compatibles"></a>

Em geral, **ROMs No-Intro na versão dos EUA** funcionam melhor para **Retroachievements,** com algumas raras exceções onde **você também pode ter algumas roms européias.**

Você pode encontrar uma lista de roms com seus HASHES \(MD5\), ou seja, sua **assinatura digital**, acessando **a página do jogo** e **clicando no link à direita:**  
`HASHES LINKED TO THIS GAME` .

Você verá **uma lista de assinaturas de ROMs compatíveis** com seus Retroachievements.

