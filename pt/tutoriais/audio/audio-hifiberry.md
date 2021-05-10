---
title: Áudio HiFiBerry
---

# Áudio HiFiBerry


>Para obter um **sinal de áudio de qualidade no Pi**, uma solução é usar um **HiFiBerry DAC** \(Digital - Analog Converter = Conversor Digital para Analógico\).
{.is-info}

Esses **DAC** existem em várias versões:

**Raspberry Pi A+, B+, 2 e 3**

* DAC+ Light
* DAC+ Padrão RCA
* DAC+ Padrão Fone
* DAC+ Pro

**Raspberry Pi A e B**

* DAC Padrão com conectores RCA

As características das diferentes placas podem ser comparadas no [hifiberry.com](http://www.hifiberry.com/). **As placas DAC+** podem ser **conectadas diretamente ao GPIO** do Pi. Os pinos não utilizados pelo DAC podem ser reutilizados para outros usos; nesse caso, pinos adicionais devem ser soldados na placa DAC +.

Abaixo está o diagrama de fiação de um DAC + HifiBerry:

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-M4MJhLQO6S2oqnO487A%2F-M4MKkv1EquQT-H7eNn7%2Fimage.png?alt=media&token=8ca251e1-640a-4a7e-9c2e-ed3a8ba78e8c)


>A versão para **Raspberry A e B** deve ser instalada no **pino 5**, o que requer um tratamento adicional. Depois que a placa é instalada, há mais algumas etapas de configuração do software para fazer tudo funcionar.
{.is-info}

## Configuração do Dispositivo <a id="configuracao-do-dispositivo"></a>

* No recalbox, você só precisa adicionar o direito **DTB** em `/boot/config.txt`, com os parâmetros corretos \(dependendo do seu cartão\) :

**DAC/DAC+ Light**

`dtoverlay=hifiberry-dac`

**DAC+ Padrão/Pro**

`dtoverlay=hifiberry-dacplus`

* Então você precisa **selecionar a placa de som padrão: basta editar**`/etc/asound.conf` \(crie o arquivo se ainda não existir\) **com o seguinte conteúdo**:

`pcm.!default {`   
`type hw card 0`   
`}`   
`ctl.!default {`   
`type hw card 0` `}`

* **Reinicie** seu Pi.

Agora você deve ouvir o som através da sua placa HiFiBerry.


>**IMPORTANTE:** Você não pode alterar o volume do som no EmulationStation apenas pelo Alsamixer / Amixer.Alsamixer/Amixer
{.is-info}

## Alsamixer/Amixer <a id="alsamixer-amixer"></a>

**Placas de som ALSA** \(e este é o caso do HiFiBerry\) podem ser controladas pelo **Alsamixer**, que é uma interface gráfica do usuário, enquanto o **Amixer** trabalha no modo de texto, especialmente por **scripts**.

Como o **alsa-utils** está instalado no Recalbox, HifiBerry funcionará **sem utilitários adicionais**.


>**IMPORTANTE:**  
>O DAC + Light e o antigo DAC não possuem configurações disponíveis no ALSA.
{.is-danger}

Com o **comando** `amixer` , você receberá uma versão em texto das várias configurações do DAC. A **melhor maneira** de alterar o volume é alterar o "**Volume Geral**"/**"Overall volume"**. Seu nome pode diferir dependendo do cartão: PCM, Digital, Master, tente um deles.

Os seguintes **comandos** te permitem **alterar o volume através do terminal** :

* `amixer sset ‘Master’ -- 90%` \(não recomendado porque a escala é logarítmica\)
* `amixer sset ‘Master’ -- -3dB` \(em decibéis, configuração recomendada\)
* `amixer sset ‘Master’ – 2000` \(unidade empírica, obsoleta\)

Aqui está um **exemplo** em **python** para **gerenciar o volume**.

Primeiro, importe o comando do subprocesso :

```text
from subprocess import call


call(["amixer", "sset", "Digital", "--", str(YourDesiredVolume)+"dB"])
```

**Esse script** pode ser usado especialmente para **alterar o volume** usando o G**PIO**

**Abaixo estão alguns comandos disponíveis com o amixer:**

* `amixer sset 'PCM' 70%` \(percentagem\)
* `amixer sset 'Master' 3dB` \(Decibéis\)
* `amixer sset 'Mic' 4` \(valores de hardware\)
* `amixer sset 'PCM' 10%+` \(aumento no valor atual, a unidade pode ser % ou dB\)
* `amixer sset 'Line' cap` \(Gravação on/off: cap, nocap\)
* `amixer sset 'Mic' mute` \(Playback on/off: mudo, não-mudo\)
* `amixer sset 'Master' off` \(On/Off: on/off\)
* `amixer sset 'Mic Select' 'Mic1'` \(nome do dispositivo\)

Veja: [**wiki.ubuntuusers.de/amixer**​](https://translate.google.com.br/translate?hl=pt-BR&sl=de&tl=pt&u=https%3A%2F%2Fwiki.ubuntuusers.de%2Famixer%2F)​


>Você também pode usar o Google para descobrir os comandos disponíveis com as palavras-chave: _amixer_, _alsamixer_.
{.is-info}

