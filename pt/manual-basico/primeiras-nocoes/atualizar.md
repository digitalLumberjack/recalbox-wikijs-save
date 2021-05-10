---
title: Atualizar
---

# Atualizar

## Processo de atualização <a id="processo-de-atualizacao"></a>


>**Informação:**
>
>Aqui estão as **possibilidades de atualização** do Recalbox.  
>Espero que este resumo o ajude e dê as respostas que você está procurando.
{.is-info}

### Verifique sua situação <a id="verifique-sua-situacao"></a>

**É possível atualizar do recalbox 4.1 para recalbox 6.0?**

_**Não**, não é possível atualizar esta versão muito antiga \(mais de um ano e meio\) para recalbox 6.0 RCx / Stable  
É necessária uma instalação limpa. Veja abaixo as instruções_

\*\*\*\*

**É possível atualizar do recalbox 18.07.xxxxx para recalbox 6.0 RCx/Stable?**

_**Não**, não é possível atualizar esta versão para a nova versão do recalbox 6.  
É necessária uma instalação limpa. Veja abaixo as instruções_

_​_

**É possível atualizar do recalbox beta** __ **para recalbox 6.0 RCx/Stable?**

_**Não**, não é possível atualizar esta versão para a nova versão do recalbox 6.  
É necessária uma instalação limpa. Veja abaixo as instruções_



**É possível atualizar o Recalbox 6 RCx para o Recalbox 6.0 estável?**

_**Sim**, é possível atualizar entre diferentes versões do recalbox 6.0 Release Candidate para a futura versão estável._

* Certifique-se de sempre ter espaço no disco rígido em seu microsd se você armazenar seus roms nele antes de atualizar
* Sempre faça um backup antes de realizar a atualização, nunca seja muito cuidadoso.
* Leia o changelog e, se for conveniente para você, faça sua atualização
* Após reiniciar, é aconselhado que você reconfigure seu controle.

​



**É possível atualizar o Recalbox 6.0 para o Recalbox 6.1?**

_**Sim**, é possível atualizar do Recalbox 6.0 para a versão 6.1._

* Certifique-se de sempre ter espaço no disco rígido em seu microsd se você armazenar seus roms nele antes de atualizar
* Sempre faça um backup antes de realizar a atualização, nunca seja muito cuidadoso.
* Leia o changelog e, se for conveniente para você, faça sua atualização
* Após reiniciar, é aconselhado que você reconfigure seu controle.



​

**É possível fazer multiboot com PINN ou NOOBS com Recalbox 6 RCxxx?**

**Não**. Não é possível fazer **multiboot** com as versões beta ou RC \(release candidate\) do Recalbox com Noobs.  
Será possível quando:

* O Recalbox 6 estiver em uma versão estável.
* O Noobs concorde em nos adicionar à sua lista. \*
* Parece que o PINN está acompanhando nosso desenvolvimento. \(Necessário Testar\)

​

**Por que meu controle funciona na Emulationstation, mas não quando executo os emuladores?**

Adicionamos um máximo de configuração de controles no Emulationstation, a fim de permitir que você navegue no Emulationstation, mas para muitos deles você tem que reconfigurá-los para funcionarem nos emuladores.

* Menu do Emulationstation \(botão START\)
* Configurações dos controles &gt; Configurar um controle.

​

**E se eu estiver usando um tema personalizado?**

* Certifique-se de estar atualizado no nível dos sistemas, arquivos de configuração para o seu tema.
* Contate o autor de seu tema ou assunto de seu tema para verificar se uma nova versão atualizada está disponível.
* Utilize um tema personalizado em 720p no raspberry, pois 1080p fará seu RPi sofrer.
* **Não oferecemos suporte a temas personalizados não oficiais do Recalbox.**
* **Por favor, use o tema padrão do Recalbox para verificar seus bugs antes de postar seu problema no fórum.**

**​**

**E se eu usar OVERLAYS?**

* Se você estiver usando o [screenscraper](https://www.screenscraper.fr/forum.php),verifique se os pacotes foram atualizados para o Recalbox 6.0
* Se você criou seus overlays, o Retroarch adicionou uma nova proporção de aspecto que muda alguns overlays :

  * teste com `22` ou `23` nesta linha:

  `aspect_ratio_index = 21`

​

**Os Arcades**

Desde o primeiro beta, o Recalbox atualizou os núcleos dos emuladores de arcade: mame & fba libretro e adicionou outros emuladores.

Portanto, você deve adaptar seus romsets:

* Os arquivos dat globais agora estão localizados em /bios/mame2003 ou /fba ou /mame2010 ou /advmame
* Para criar um dat somente-pai, neogeo somente-pai, etc... você só precisa usar este tutorial [datutil.exe](https://forum.recalbox.com/topic/4571/tutorial-datutil) para criá-los.
* Núcleo libretro Fba libretro : romset 0.2.97.44
* Núcleo libretroMame 2003 : romset mame 0.78
* Núcleo libretroMame 2010 : romset mame 0.139
* Emulador autônomo \(_standalone_\) advanceMame : romset mame 0.106 \(apenas para usuários avançados\)
* Mame 2003-plus : romset 0.78 e plus \([documentação](https://docs.libretro.com/library/mame2003_plus/#Building-romsets-for-MAME-2003-Plus)\) \([documentação para criar seu romset](https://github.com/libretro/mame2003-plus-libretro/wiki)\)
* [Mame 2003-plus](https://github.com/libretro/mame2003-plus-libretro/blob/master/CHANGELOG.md) é uma versão avançada do mame 2003 com opções adicionais não encontradas no mame 2003 e jogos adicionais.
* Consulte a documentação do [Arcade](https://recalbox.gitbook.io/tutorials/v/portugues/jogos/arcade)

​

**Seu RPI em uma carcaça \("**_**case"\)**_

* Certifique-se de ter uma boa ventilação
* Um bom cabo de alimentação
* Se você tiver alguma dúvida, tire o RPI da carcaça e teste o Recalbox sem ela.

​

### Nossos conselhos: <a id="nossos-conselhos"></a>

* Tenha um backup de seu recalbox em seu PC ou disco rígido externo
* Usando mídia removível \(Pendrive ou disco rígido externo\), você compreenderá rapidamente que a reinstalação é mais rápida.
* Use um scrapper extern
* Ter sempre 2 cartões micro SD de 8GB é o suficiente para o sistema \(um para a versão estável, outro para seus testes, ou para uma versão beta\) daí a utilidade em ter suas ROMs em uma mídia removível
* Instale dissipadores de calor ou ventiladores, se necessário, especialmente se
  * Se você fizer overlock em seu CM
  * Se o seu Recalbox estiver em uma carcaça/_case_.

## Comece a atualização <a id="comece-a-atualizacao"></a>


>**Informação:**
>
>A **atualização do Recalbox** pode ser acessada através do menu "**Atualização**" ao pressionar **START**.
{.is-info}

* **Configure seu wi-fi** ou **conecte um cabo de rede** em seu Recalbox
* Selecione **"CONFIGURAÇÕES DO SISTEMA"**
* Em seguida, **“Atualizar o Recalbox”**
* E **"Iniciar atualização"**.

O sistema **reinicia automaticamente** após a atualização!


>**Atenção:**
>
>Se você estiver usando uma versão do Recalbox **anterior à versão 6.0**, não será possível realizar uma atualização **automática.**
>
>Você precisará realizar uma [reinstalação limpa](/v/portugues/manual-basico/primeiras-nocoes/reinstalacao-limpa) para poder aproveitar a[ versão mais recente disponível](https://archive.recalbox.com/).
>
>Portanto, prossiga com o processo de atualização para **não perder** suas configurações, saves, ROMs e BIOS.
{.is-danger}

