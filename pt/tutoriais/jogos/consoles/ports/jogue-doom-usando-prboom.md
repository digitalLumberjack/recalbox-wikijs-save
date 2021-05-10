---
title: Jogue Doom usando PRBOOM
---

# Jogue Doom usando PRBOOM


>**Informação:**
>PrBoom é uma versão do motor gráfico Doom.  
>Ele pode executar **Doom 1** e **Doom 2**.
{.is-info}

## Jogue DOOM I ou II rapidamente​ <a id="jogue-doom-i-ou-ii-rapidamente"></a>

**Coloque** seus jogos **DOOM 1 e/ou 2**, bem **como os mods associados** na pasta: **`/recalbox/share/roms/prboom/`**


>Atenção:
>Os **jogos DOOM** devem ter **a extensão ".wad"  
>NÃO EXCLUA** O ARQUIVO "**prboom.wad**" que é necessário para a emulação.
{.is-danger}

## Tenha música no DOOM​ <a id="tenha-musica-no-doom"></a>

Coloque suas trilhas sonoras na pasta:**`/recalbox/share/roms/prboom/game-musics`**

Preencha o arquivo prboom.cfg​

┣ \#Music    
┣ mus\_bunny "./bunny.mp3"    
┣ mus\_e1m1 "./e1m1.mp3"    
┣ mus\_e1m2 "./e1m2.mp3"    
┣ mus\_e1m3 "./e1m3.mp3"    
┣ mus\_e1m4 "./e1m4.mp3"    
┣ mus\_e1m5 "./e1m5.mp3"    
┣ mus\_e1m6 "./e1m6.mp3"    
┣ mus\_e1m7 "./e1m7.mp3"    
┣ mus\_e1m8 "./e1m8.mp3"    
┣ mus\_e1m9 "./e1m9.mp3"    
┣ mus\_e2m1 "./e2m1.mp3"    
┣ mus\_e2m2 "./e2m2.mp3"    
┣ mus\_e2m3 "./e2m3.mp3"    
┣ mus\_e2m4 "./e2m4.mp3"    
┣ mus\_e2m5 "./e1m7.mp3" &lt;-- isso não é uma falha, existem vários duplicados na lista    
┣ mus\_e2m6 "./e2m6.mp3"    
┣ mus\_e2m7 "./e2m7.mp3"    
┣ mus\_e2m8 "./e2m8.mp3"    
┣ mus\_e2m9 "./e3m1.mp3"    
┣ mus\_e3m1 "./e3m1.mp3"    
┣ mus\_e3m2 "./e3m2.mp3"    
┣ mus\_e3m3 "./e3m3.mp3"    
┣ mus\_e3m4 "./e1m8.mp3"    
┣ mus\_e3m5 "./e1m7.mp3"    
┣ mus\_e3m6 "./e1m6.mp3"    
┣ mus\_e3m7 "./e2m7.mp3"    
┣ mus\_e3m8 "./e3m8.mp3"    
┣ mus\_e3m9 "./e1m9.mp3"    
┣ mus\_e4m1 "./e1m8.mp3"    
┣ mus\_e4m2 "./e3m2.mp3"    
┣ mus\_e4m3 "./e3m3.mp3"    
┣ mus\_e4m4 "./e1m5.mp3"    
┣ mus\_e4m5 "./e2m7.mp3"    
┣ mus\_e4m6 "./e2m4.mp3"    
┣ mus\_e4m7 "./e2m6.mp3"    
┣ mus\_e4m8 "./e1m7.mp3"    
┣ mus\_e4m9 "./e1m9.mp3"    
┣ mus\_inter "./e2m3.mp3"    
┣ mus\_introa "./intro.mp3"    
┣ mus\_intro "./intro.mp3"    
┣ mus\_victor "./victor.mp3"    
┣ mus\_adrian "./adrian.mp3"    
┣ mus\_ampie "./ampie.mp3"    
┣ mus\_betwee "./betwee.mp3"    
┣ mus\_count2 "./countd.mp3"    
┣ mus\_countd "./countd.mp3"    
┣ mus\_ddtbl2 "./ddtblu.mp3"    
┣ mus\_ddtbl3 "./ddtblu.mp3"    
┣ mus\_ddtblu "./ddtblu.mp3"    
┣ mus\_dead2 "./dead.mp3"    
┣ mus\_dead "./dead.mp3"    
┣ mus\_dm2int "./dm2int.mp3"    
┣ mus\_dm2ttl "./dm2ttl.mp3"    
┣ mus\_doom2 "./doom.mp3"    
┣ mus\_doom "./doom.mp3"    
┣ mus\_evil "./evil.mp3"    
┣ mus\_in\_cit "./in\_cit.mp3"    
┣ mus\_messag "./messag.mp3"    
┣ mus\_messg2 "./messag.mp3"    
┣ mus\_openin "./openin.mp3"    
┣ mus\_read\_m "./read\_m.mp3"    
┣ mus\_romer2 "./romero.mp3"    
┣ mus\_romero "./romero.mp3"    
┣ mus\_runni2 "./runnin.mp3"    
┣ mus\_runnin "./runnin.mp3"    
┣ mus\_shawn2 "./shawn.mp3"    
┣ mus\_shawn3 "./shawn.mp3"    
┣ mus\_shawn "./shawn.mp3"    
┣ mus\_stalks "./stalks.mp3"    
┣ mus\_stlks2 "./stalks.mp3"    
┣ mus\_stlks3 "./stalks.mp3"    
┣ mus\_tense "./tense.mp3"    
┣ mus\_theda2 "./the\_da.mp3"    
┣ mus\_theda3 "./the\_da.mp3"    
┣ mus\_the\_da "./the\_da.mp3"    
┣ mus\_ultima "./ultima.mp3"  

## Principais versões de Doom​ <a id="principais-versoes-de-doom"></a>

Para tornar filtrar todos os nomes que podem ser citados, uma pequena recapitulação:

* **Doom**, lançado em 1993, pela Id Software, tem 3 episódios de 9 níveis cada \(Knee-Deep in the Dead, The Shores of Hell e Inferno\)
* **Doom1** é a versão shareware para download gratuito, que inclui apenas EP1.
* **Doom II : Hell on Earth**, ançado em 1994, sequência de Doom, com 30 níveis consecutivos \(+2 ocultos\).
* **The Ultimate Doom**, lançado em 1995, = Doom + um 4º episódio de 9 níveis \(Thy Flesh Consumed\)
* **Master Levels for Doom II**, lançado em 1995, adicionou 21 níveis para Doom II.
* **Final Doom**, lançado em 1996, expansão para Doom II, com dois episódios separados:
  * **TNT Evilution** \(32 níveis\) e **The Plutonia Experiment** \(32 níveis\).
* **Sigil**, lançado em 2019, é um 5º episódio de Doom, criado por John Romero por ocasião do 25º aniversário de Doom... e, obviamente, muitos níveis adicionais para Doom ou Doom II !

## Algumas informações sobre wads​ <a id="algumas-informacoes-sobre-wads"></a>

Embora todos os arquivos tenham a extensão .wad, existem vários tipos:

* **IWAD**: é um wad que contém todos os dados e funciona sozinho \(por exemplo: doom.wad, doom2.wad, tnt.wad, plutonia.wad\)
* **PWAD**: é um wad 'add-on' que vai precisar de um IWAD para funcionar \(por exemplo: quase todos os níveis amadores criados pela comunidade do doom\)

Os wads também devem ser compatíveis com PrBoom. Alguns mods vão muito longe na modificação **\(como Brutal Doom, Doom Raider, Golden Eye, ...\)** mas não funcionam com PrBoom. Encontre informações sobre o wad que deseja jogar! Se um wad substituir um único nível, não será necessariamente o nível 1 do episódio 1. Você terá que atingir o nível certo ou usar um cheat para acessá-lo diretamente.

​

## Jogue um IWAD​ <a id="jogue-um-iwad"></a>

O arquivo `gamelist.xml` pode apontar diretamente para este IWAD. Por exemplo, teremos:

┣ &lt;game&gt;    
┣ &lt;path&gt;./plutonia/plutonia.wad&lt;/path&gt;    
┣ &lt;name&gt;\(1996\) Final Doom: The Plutonia Experiment&lt;/name&gt;    
┣ &lt;/game&gt;  

### ​Jogue um PWAD​ <a id="jogue-um-pwad"></a>

Se alguém tiver um método melhor do que o seguinte... Vamos dar um exemplo: Eu quero jogar SEWERS.WAD Vamos criar a subpasta **/recalbox/share/roms/prboom/sewers** Dentro, coloque SEWERS.WAD e doom.wad \(e não doom2.wad porque SEWERS.WAD é um nível para Doom 1\)

O arquivo gamelist.xml apontará para um IWAD \(doom.wad ou doom2.wad dependendo da versão do jogo necessária para o funcionamento do PWAD\). Para meu exemplo, teremos:

┣ &lt;game&gt;    
┣ &lt;path&gt;./sewers/doom.wad&lt;/path&gt;    
┣ &lt;desc&gt;Remplace E3M1.&lt;/desc&gt;    
┣ &lt;name&gt;\(1994\) E1M10: Sewers \(Xbox Doom\)&lt;/name&gt;    
┣ &lt;/game&gt;  

Inicie o jogo uma vez, Doom deve ser iniciado. Saia do jogo e vá para a pasta **/recalbox/share/saves/prboom/doom** que foi criada ao iniciar o jogo. Nesta pasta, há um arquivo prboom.cfg, abra-o e modifique a linha:

┣ \#\# Files    
┣ \#wadfile\_1 ""    
┣ \#wadfile\_2 ""    
┣ \#wadfile\_3 ""    
┣ \#wadfile\_4 ""  

para

┣ \#\# Files    
┣ \#wadfile\_1 "SEWERS.WAD" &lt;- Tenha cuidado: Respeite as letras maiúsculas/minúsculas!    
┣ \#wadfile\_2 ""    
┣ \#wadfile\_3 ""    
┣ \#wadfile\_4 ""  

Reinicie o jogo, escolha o Episódio 3 Inferno, o primeiro nível deve ser Sewers.

​

## Alterar os comandos do controle​ <a id="alterar-os-comandos-do-controle"></a>

Jogando em um 8bitdo NES30, nenhum botão me permitia trocar de armas, e isso é muito chato... O truque é ir até a configuração do Retroarch \[HOTKEY\] + \[B\] e então Controles&gt; Botão B \(ou Y\) para atribuir uma ação. Escolha, por exemplo, \[B\] = Next Weapon \(Próxima Arma\) e \[Y\] = Run \(Correr\). Em seguida, salve o remapeamento para o núcleo.

​

## Trapaças \(_cheats_\)​ <a id="trapacas-cheats"></a>

Você tem que configurar no RetroArch. Pressione \[HOTKEY\] + \[B\] e escolha o menu Trapaças \(_Cheats\)_. Em seguida, vá para "Carregar arquivo de trapaças", localize "Computer - Games", e escolha o arquivo DOOM.cht. Uma lista de 14 trapaças é carregada. Você apenas tem que ativar ou não a trapaça desejada e então aplicar as mudanças.

Parece que as trapaças não funcionam no modo NightMare! Os códigos de mudança de nível IDCLEV \#\# \(E \# M \# ou MAP \#\#\) não são implementados. Coloque-os por SSH em //recalbox/share\_init/cheats/cht/Computer - Games

Conteúdo de DOOM\_levels.cht:

┣ \# Doom    
┣ \# [http://doom.wikia.com/wiki/Doom\_cheat\_codes](http://doom.wikia.com/wiki/Doom_cheat_codes)  
┣ cheats = 36  
┣ cheat0\_desc = "E1M1: Hangar"    
┣ cheat0\_code = "idclev11"    
┣ cheat0\_enable = false  
┣ cheat1\_desc = "E1M2: Nuclear Plant"    
┣ cheat1\_code = "idclev12"    
┣ cheat1\_enable = false  
┣ cheat2\_desc = "E1M3: Toxin Refinery"    
┣ cheat2\_code = "idclev13"    
┣ cheat2\_enable = false  
┣ cheat3\_desc = "E1M4: Command Control"    
┣ cheat3\_code = "idclev14"    
┣ cheat3\_enable = false  
┣ cheat4\_desc = "E1M5: Phobos Lab"    
┣ cheat4\_code = "idclev15"    
┣ cheat4\_enable = false  
┣ cheat5\_desc = "E1M6: Central Processing"    
┣ cheat5\_code = "idclev16"    
┣ cheat5\_enable = false  
┣ cheat6\_desc = "E1M7: Computer Station"    
┣ cheat6\_code = "idclev17"    
┣ cheat6\_enable = false  
┣ cheat7\_desc = "E1M8: Phobos Anomaly"    
┣ cheat7\_code = "idclev18"    
┣ cheat7\_enable = false  
┣ cheat8\_desc = "E1M9: Military Base \(secret level\)"    
┣ cheat8\_code = "idclev19"    
┣ cheat8\_enable = false  
┣ cheat9\_desc = "E2M1: Deimos Anomaly"    
┣ cheat9\_code = "idclev21"    
┣ cheat9\_enable = false  
┣ cheat10\_desc = "E2M2: Containment Area"    
┣ cheat10\_code = "idclev22"    
┣ cheat10\_enable = false  
┣ cheat11\_desc = "E2M3: Refinery"    
┣ cheat11\_code = "idclev23"    
┣ cheat11\_enable = false  
┣ cheat12\_desc = "E2M4: Deimos Lab"    
┣ cheat12\_code = "idclev24"    
┣ cheat12\_enable = false  
┣ cheat13\_desc = "E2M5: Command Center"    
┣ cheat13\_code = "idclev25"    
┣ cheat13\_enable = false  
┣ cheat14\_desc = "E2M6: Halls of the Damned"    
┣ cheat14\_code = "idclev26"    
┣ cheat14\_enable = false  
┣ cheat15\_desc = "E2M7: Spawning Vats"    
┣ cheat15\_code = "idclev27"    
┣ cheat15\_enable = false  
┣ cheat16\_desc = "E2M8: Tower of Babel"    
┣ cheat16\_code = "idclev28"    
┣ cheat16\_enable = false  
┣ cheat17\_desc = "E2M9: Fortress of Mystery \(secret level\)"    
┣ cheat17\_code = "idclev29"    
┣ cheat17\_enable = false  
┣ cheat18\_desc = "E3M1: Hell Keep"    
┣ cheat18\_code = "idclev31"    
┣ cheat18\_enable = false  
┣ cheat19\_desc = "E3M2: Slough of Despair"    
┣ cheat19\_code = "idclev32"    
┣ cheat19\_enable = false  
┣ cheat20\_desc = "E3M3: Pandemonium"    
┣ cheat20\_code = "idclev33"    
┣ cheat20\_enable = false  
┣ cheat21\_desc = "E3M4: House of Pain"    
┣ cheat21\_code = "idclev34"    
┣ cheat21\_enable = false  
┣ cheat22\_desc = "E3M5: Unholy Cathedral"    
┣ cheat22\_code = "idclev35"    
┣ cheat22\_enable = false  
┣ cheat23\_desc = "E3M6: Mt. Erebus"    
┣ cheat23\_code = "idclev36"    
┣ cheat23\_enable = false  
┣ cheat24\_desc = "E3M7: Limbo"    
┣ cheat24\_code = "idclev37"    
┣ cheat24\_enable = false  
┣ cheat25\_desc = "E3M8: Dis"    
┣ cheat25\_code = "idclev38"    
┣ cheat25\_enable = false  
┣ cheat26\_desc = "E3M9: Warrens \(secret level\)"    
┣ cheat26\_code = "idclev39"    
┣ cheat26\_enable = false  
┣ cheat27\_desc = "E4M1: Hell Beneath"    
┣ cheat27\_code = "idclev41"    
┣ cheat27\_enable = false  
┣ cheat28\_desc = "E4M2: Perfect Hatred"    
┣ cheat28\_code = "idclev42"    
┣ cheat28\_enable = false  
┣ cheat29\_desc = "E4M3: Sever the Wicked"    
┣ cheat29\_code = "idclev43"    
┣ cheat29\_enable = false  
┣ cheat30\_desc = "E4M4: Unruly Evil"    
┣ cheat30\_code = "idclev44"    
┣ cheat30\_enable = false  
┣ cheat31\_desc = "E4M5: They Will Repent"    
┣ cheat31\_code = "idclev45"    
┣ cheat31\_enable = false  
┣ cheat32\_desc = "E4M6: Against Three Wickedly"    
┣ cheat32\_code = "idclev46"    
┣ cheat32\_enable = false  
┣ cheat33\_desc = "E4M7: And Hell Followed"    
┣ cheat33\_code = "idclev47"    
┣ cheat33\_enable = false  
┣ cheat34\_desc = "E4M8: Unto the Cruel"    
┣ cheat34\_code = "idclev48"    
┣ cheat34\_enable = false  
┣ cheat35\_desc = "E4M9: Fear \(secret level\)"    
┣ cheat35\_code = "idclev49"    
┣ cheat35\_enable = false  

## Organize tudo​ <a id="organize-tudo"></a>

Se você tiver muito wad, isso rapidamente se tornará uma bagunça em seus arquivos. Além disso, na pasta **/recalbox/share/saves/prboom/doom**, há apenas um arquivo prboom.cfg! Então o que fazemos para usar vários wads?!?

Se isso o inspira, aqui está meu armazenamento:

1. Em **/recalbox/share/roms/prboom/**, criei duas pastas DOOM e DOOM2 que conterão respectivamente os wads para DOOM e DOOM2
2. Em **/recalbox/share/roms/prboom/DOOM/**, criei uma pasta por wad, copio doom.wad \(que renomeei de passagem\) e o add-on wad

Por exemplo:

┣ roms  
┃ ┣ prboom  
┃ ┃ ┣ DOOM  
┃ ┃ ┃ ┣ 1993\_doom  
┃ ┃ ┃ ┃ ┣ doom\_1993.wad  

┃ ┃ ┃ ┣ 1994\_sewers\_\(e1m10\)  
┃ ┃ ┃ ┃ ┣ doom\_1994\_sewers.wad SEWERS.WAD  

┃ ┃ ┃ ┣ 2019\_doomep5  
┃ ┃ ┃ ┃ ┣ doom\_2019\_sigil.wad SIGIL\_v1\_21.wad  

┃ ┃ ┣ DOOM2  
┃ ┃ ┃ ┣ 1994\_doom2  
┃ ┃ ┃ ┃ ┣ doom2\_1994.wad  

┃ ┃ ┃ ┣ 1996\_plutonia  
┃ ┃ ┃ ┃ ┣ doom2\_1996\_plutonia.wad &lt;---- ici c'est plutonia.wad et non doom2.wad  

┃ ┃ ┃ ┣ 2011\_nuts  
┃ ┃ ┃ ┃ ┣ doom2\_2001\_nuts.wad NUTS.WAD  

Meu arquivo gamelist.xml se parece com este:

┣ &lt;?xml version="1.0" encoding="utf-8"?&gt;    
┣ &lt;gameList&gt;  

┣ &lt;folder&gt;    
┣ &lt;path&gt;./DOOM&lt;/path&gt;    
┣ &lt;name&gt;DOOM & mods&lt;/name&gt;    
┣ &lt;image&gt;./media/images/Doom\_folder.png&lt;/image&gt;    
┣ &lt;/folder&gt;  

┣ &lt;folder&gt;    
┣ &lt;path&gt;./DOOM2&lt;/path&gt;    
┣ &lt;name&gt;DOOM II & mods&lt;/name&gt;    
┣ &lt;image&gt;./media/images/Doom2\_folder.png&lt;/image&gt;    
┣ &lt;/folder&gt;  

┣ &lt;game&gt;    
┣ &lt;path&gt;./DOOM/1993\_doom/doom\_1993.wad&lt;/path&gt;    
┣ &lt;name&gt;\(1993\) The Ultimate Doom&lt;/name&gt;    
┣ &lt;/game&gt;  

┣ &lt;game&gt;    
┣ &lt;path&gt;./DOOM/1994\_sewers\_\(e1m10\)/doom\_1994\_sewers.wad&lt;/path&gt;    
┣ &lt;name&gt;\(1994\) E1M10: Sewers \(Xbox Doom\)&lt;/name&gt;    
┣ &lt;/game&gt;  

┣ &lt;game&gt;    
┣ &lt;path&gt;./DOOM/2019\_doomep5/doom\_2019\_sigil.wad&lt;/path&gt;    
┣ &lt;name&gt;\(2019\) Doom EP5 SIGIL&lt;/name&gt;    
┣ &lt;/game&gt;  

┣ &lt;game&gt;    
┣ &lt;path&gt;./DOOM2/1994\_doom2/doom2\_1994.wad&lt;/path&gt;    
┣ &lt;name&gt;\(1994\) Doom II: Hell On Earth&lt;/name&gt;    
┣ &lt;/game&gt;  

┣ &lt;game&gt;    
┣ &lt;path&gt;./DOOM2/1996\_plutonia/doom2\_1996\_plutonia.wad&lt;/path&gt;    
┣ &lt;name&gt;\(1996\) Final Doom: The Plutonia Experiment&lt;/name&gt;    
┣ &lt;/game&gt;  

┣ &lt;game&gt;    
┣ &lt;path&gt;./DOOM2/2011\_nuts/doom2\_2001\_nuts.wad&lt;/path&gt;    
┣ &lt;name&gt;\(2001\) Nuts&lt;/name&gt;    
┣ &lt;/game&gt;  

Em **/recalbox/share/saves/prboom/**, vamos encontrar vários arquivos assim que os wads forem iniciados pela primeira vez. Em seguida, edite o prboom.cfg

