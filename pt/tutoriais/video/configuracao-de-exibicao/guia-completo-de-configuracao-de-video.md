---
title: Guia Completo de Configuração de Vídeo
---

# Guia Completo de Configuração de Vídeo

Essas são as melhores recomendações para configurar o vídeo para caber na sua tela. Existem três níveis de configuração: sistema, modo de vídeo padrão do emulador e modo de vídeo específico do emulador. Lembre-se de que a resolução da tela pode ter um impacto significativo na taxa de quadros, especialmente nos emuladores com uso intenso de CPU \(N64, PSX e outros\). A maior parte deste guia se concentrará na saída HDMI e irá expor os 3 casos com a maior frequência possível: HDMI puro, HDMI para DVI, HDMI para VGA.

## Quais são os possíveis modos de vídeo? <a id="quais-sao-os-possiveis-modos-de-video"></a>

Antes de tudo, você deve entender o básico da resolução da tela: um número de pixels de largura por um número de pixels de altura com uma determinada taxa de atualização em Hertz. Por exemplo: 1280x1024@60, que é uma resolução de tela comum de 4x3 para monitores de 19 ". As TVs de hoje exibem Full HD a 1080p \(e mais\), como 1920x1080@60Hz. Não vamos passar pelos modos entrelaçado ou progressivo, isso não vem ao caso. Consulte o manual do fabricante do seu monitor para obter a resolução nativa.

Existem dois grupos de modos de vídeo \(videomode\): CEA e DMT. Todos esses modos estão listados [aqui](https://elinux.org/RPiconfig) ou [aqui](https://www.raspberrypi.org/documentation/configuration/config-txt/README.md). Verifique se o modo é compatível com a resolução de tela nativa. Uma regra básica simples: CEA é para o modo TV, DMT é para todos os outros modos.

Os modos mais comuns são :

* DMT 4 : 640x480@60
* DMT 9 : 800x600@60
* DMT 16 : 1024x768@60
* DMT 35 : 1280x1024@60
* DMT 57 : 1680x1050@60
* 720p : CEA 4
* 1080p : CEA 16

Neste tutorial, abordaremos 3 casos :

* Uma televisão normal de 1080p. Vamos chamá-la de 1080pTV
* Um monitor 720p VGA conectado com adaptador HDMI para VGA. Apelido: 720pVGA
* Um bom e velho DVI de 17 "capaz de exibir 1280x1024 a 60. Codinome... DVIboy. Não se esqueça de consultar o Tutorial para monitores DVI [https://recalbox.gitbook.io/tutorials/v/portugues/video/lcd/conectando-o-recalbox-a-um-monitor-dvi](https://recalbox.gitbook.io/tutorials/v/portugues/video/lcd/conectando-o-recalbox-a-um-monitor-dvi)​

Com o que você já sabe sobre os modos de tela, estas são as configurações mais comuns:

* 1080pTV corresponds to CEA 16
* 720pVGA corresponds to CEA 4
* DVIboy corresponds to DMT 35

## Seu sistema inicia <a id="seu-sistema-inicia"></a>

Na inicialização, o Pi solicitará ao seu monitor sua resolução de tela preferida. Seu monitor envia seu EDID \(\(Extended Display Identification Data / Dados de Identificação de Exibição Estendidos\) e o Raspberry seleciona a resolução da tela anotada como "preferida". É aqui que o primeiro problema ocorre:

* a maioria - se não todos - os monitores HDMI nativos \(TVs, monitores\) devem enviar o EDID correto
* HDMI para DVI também deve funcionar
* Os adaptadores HDMI para VGA podem ser um pouco complicados e fornecer um EDID impreciso...

Agora que você sabe um pouco mais sobre o que pode acontecer, veja alguns exemplos:

* O 1080pTV é um bom garoto e receberá seu 1080p imediatamente,
* O 720pVGA possui um HDMI para VGA de baixa qualidade que corresponde ao "DMT 16" como modo preferido,
* O DVIboy ajusta seu DMT 35 perfeitamente.

Como a tela detectada na inicialização é a que exibe o EmulationStation com sua resolução preferida, o 720pVGA terá uma exibição terrível. Felizmente, isso pode ser corrigido editando o arquivo`/boot/config.txt`.

Aqui estão as linhas que você precisa editar:

```text
#hdmi_group=1
#hdmi_mode=1
```

**hdmi\_group** : 1 para CEA, 2 para DMT

**hdmi\_mode** : consulte as linhas acima; então, para nosso 720pVGA, veja como publicamos`/boot/config.txt` :

```text
hdmi_group=1
hdmi_mode=4
```


>**Por favor, note:**
>
>* O sinal "\#" \(Hashtag\) foi excluído, o termo técnico para isso é "não comentado". Uma linha que começa com um \# é um comentário, não um comando.
>* hdmi\_group=1 significa CEA
>* hdmi\_mode=4 significa 720p
{.is-info}

Agora que terminamos, todas as três telas estão configuradas.

Vamos seguir em frente!

## Modo de Vídeo Global para Emuladores \(Global video mode\) <a id="modo-de-video-global-para-emuladores-global-video-mode"></a>

Agora que o EmulationStation está sendo executado em tela cheia, sua mão está ansiosa para testar um jogo... A principal coisa que você precisa saber aqui é que a resolução da tela é alterada antes de executar um emulador. Mas para qual resolução? Verifique seu [`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) e leia a configuração `global.videomode`. Seu valor padrão é`CEA 4 HDMI`. Isso significa que a resolução da tela será alterada para 720p antes de iniciar o emulador.

Hora de conferir alguns exemplos:

* 1080pTV pode exibir 720p lindamente
* 720pVGA pode exibir o 720p sem riscos
* DVIboy é... mmm... bom..., não consegue exibir 720p. Então apenas edite [`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) e defina `global.videomode` ao seu modo de vídeo nativo:`global.videomode=DMT 35 HDMI`


>**Dica:**
>
>Com sorte, deseja salvar uma alteração na resolução da tela? Então, defina `global.videomode=default`: Recalbox não alterará a resolução da tela antes de executar um emulador. Mas cuidado: isso pode ter um impacto considerável no desempenho. Estender uma imagem da resolução nativa do emulador para 1080p pode ser muito exigente na CPU e retardar a emulação. Não recomendo a configuração padrão se o seu monitor puder exibir uma resolução maior que o CEA 4.
{.is-info}

## Modo de vídeo por emulador <a id="modo-de-video-por-emulador"></a>

Finalmente, o modo de vídeo pode ser definido especificamente para o emulador de sua escolha. Por exemplo, se você ler o arquivo [`recalbox.conf`](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) , você notará que`n64.videomode=DMT 4 HDMI` significa que estamos substituindo o arquivo global.videomode pelo do emulador N64.

Espero que este guia tenha ajudado a entender como a resolução da tela é tratada no Pi e no Recalbox.

Sinta-se à vontade para fazer suas perguntas no [Fórum](https://forum.recalbox.com/) \([Em Português, se preferir](https://forum.recalbox.com/category/25/portugu%C3%AAs)\) ou no [Discord](https://discord.gg/NbQFbGM).

## Conselho prático <a id="conselho-pratico"></a>

### tvservice <a id="tvservice"></a>

tvservice é uma excelente ferramenta para diagnosticar sua saída:

```text
# tvservice --help
Utilisation : tvservice [OPTIONS]...
  -p, --preferred                   Allumer le HDMI avec les paramètres préférés
  -e, --explicit="GROUP MODE DRIVE" Mise en route de l'HDMI avec GROUPE explicite (CEA, DMT, CEA_3D_SBS, CEA_3D_TB, CEA_3D_FP, CEA_3D_FS)
                                      MODE (voir --modes) et DRIVE (HDMI, DVI)
  -t, --ntsc                        Utiliser la fréquence NTSC pour le mode HDMI (par exemple 59,94Hz au lieu de 60Hz)
  -c, --sdtvon="MODE ASPECT"        Mise en route de la SDTV avec MODE (PAL ou NTSC) et ASPECT (4:3, 14:9 ou 16:9)
  -o, --off                         Éteindre l'écran
  -m, --modes=GROUP                 Obtenir les modes GROUPE supportés (CEA, DMT)
  -M, --monitor                     Suivre les événements HDMI
  -s, --status                      Obtenir le statut HDMI
  -a, --audio                       Obtenir des informations sur le support audio
  -d, --dumpedid <filename>         Vider les informations EDID dans le fichier
  -j, --json                        Utiliser le format JSON pour les modes de sortie
  -n, --name                        Afficher l'ID de l'appareil à partir de l'EDID
  -h, --help                        Afficher cette information
```

Os comutadores mais usados:

* `tvservice -s` fornece informações atuais de exibição
* `tvservice -m CEA` or `tvservice -m DMT` : lista de modos CEA ou DMT suportados

