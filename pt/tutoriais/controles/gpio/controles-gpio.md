---
title: Controles GPIO
---

# Controles GPIO


>O Recalbox é compilado com o driver mk\_arcade\_joystick\_gpio, que permite gerenciar um controlador conectado diretamente aos GPIOs do rpi.  
>Portanto, se você planeja construir um **Bartop**, uma **Máquina Arcade** ou **Joystick Portátil de Arcade**, não precisa investir em um controlador USB.
>
>O driver pode gerenciar até **2 controles**, cada um composto por um **joystick de 4 direções** e **9 botões**.
>
>Se você estiver usando a **revisão B do RPi1**, consulte: mk\_arcade\_joystick pinout.
{.is-info}

## Pinagem <a id="pinagem"></a>

Vamos tomar como exemplo **um painel de 7 botões** com este layout:

```text
 ↑   Ⓨ Ⓧ Ⓛ  
← →     Ⓑ Ⓐ Ⓡ Ⓗ
 ↓  
```

**Onde**

```text
Ⓡ = Gatilho direito = TR
Ⓛ = Gatilho esquerdo = TL
Ⓗ = HK = Hotkey (Tecla de atalho)
```

​

No **RPI B+, RPI2 e RPi3,** você deve conectar seus botões seguindo esta pinagem:

![Pinagem do Rpi2](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LkUFvu3yt-NWo65aPpY%2F-LkUIh76x_R_LdMYBlVY%2Fimage.png?alt=media&token=7c3424bb-6e03-44cc-bb27-0dcd811cd42f)


>**A parte inferior da imagem é o lado do Pi, onde as portas USB estão localizadas.**
{.is-info}

Você pode **conectar** seus botões **diretamente ao terra**, pois o **driver ativa** os _**pullups internos do gpio**_.

## Configuração <a id="configuracao"></a>

* No arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf)
* Ative o driver GPIO, configurando a seguinte linha como 1:`controllers.gpio.enabled=1`
* E você já pode jogar!

**Os GPIOs** são configurados nativamente **na interface** e nos **diferentes sistemas** emulados.

