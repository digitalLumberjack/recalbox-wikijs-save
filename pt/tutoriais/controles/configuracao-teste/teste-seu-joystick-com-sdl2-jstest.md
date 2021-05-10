---
title: Teste seu joystick com sdl2-jstest
---

# Teste seu joystick com sdl2-jstest


>**Informação:**
>
>Com a **versão Recalbox 4.1**, estamos usando o **SDL2** para a **configuração do controle**
{.is-info}

Para **testar seu controle**, você deve:

* **Iniciar** uma sessão **ssh via putty**
* Em seguida, **executar o seguinte comando**: `sdl2-jstest`

## Liste o número de seus joysticks com o seguinte comando:

```text
sdl2-jstest --list
```

Resultado:

```text
Joystick Name:     'Bigben Interactive Bigben Game Pad'
Joystick Path:     '/dev/input/event0'
Joystick GUID:     030000006b1400000209000011010000
Joystick Number:    0
Number of Axes:     4
Number of Buttons: 13
Number of Hats:     1
...
Button code  0:   304
Button code  1:   305
Button code  2:   306
...
```

## Teste seu joystick com o seguinte comando:

```text
sdl2-jstest -e 0
```

onde 0 é o número do seu controlador detectado com o comando sdl2-jstest --list

Exemplo com um controle de N64 clicando [aqui](https://forum.recalbox.com/topic/9016/a-lire-manettes-n64)​

