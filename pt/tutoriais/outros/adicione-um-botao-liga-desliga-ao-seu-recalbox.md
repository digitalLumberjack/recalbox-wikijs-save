---
title: Adicione um botão liga/desliga ao seu Recalbox
---

# Adicione um botão liga/desliga ao seu Recalbox


>Você pode adicionar um **botão liga/desliga** ao seu **Recalbox**.  
>O botão pode ser um **botão de pressão** \(também chamado de **"interruptor momentâneo"**\) ou um botão do tipo _**ON/OFF**_.
{.is-info}

​

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJH8jdcYQLsGJvtswtn%2F-MJHA_HOg9wBtC_agqnR%2Fadd-a-start-stop-button-to-your-recalbox-en-recalboxrecalbox-os.jpg?alt=media&token=bccf6ecf-3c7e-4008-bba0-9dbb427910ab)

## Para conectar o botão ao Raspberry Pi GPIO​ <a id="para-conectar-o-botao-ao-raspberry-pi-gpio"></a>

* Conecte um pino ao **GPIO3** \(o **quinto** gpio do canto superior esquerdo\) e o outro ao terra à sua direita \(o **sexto** gpio\):

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJH8jdcYQLsGJvtswtn%2F-MJHBikcKEvyxKFdtUAG%2FRaspberry%20Pi%2040-pin%20GPIO%20Layout.png?alt=media&token=49f0c74e-433e-40fb-81ca-06cec2f2efb7)

* Após isso, você deve habilitar o suporte ao botão no [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), adicionando uma destas linhas:
  * `system.power.switch=PIN56ONOFF` para um botão ON/OFF
  * `system.power.switch=PIN56PUSH` para um botão de pressão

E agora você tem um **Recalbox** que pode ser **ligado/desligado com um único botão!**

​

## Adicione um botão de reset e um LED <a id="adicione-um-botao-de-reset-e-um-led"></a>


>Desde o **Recalbox 4.0 beta 4**, existe outra opção onde você pode adicionar **um botão reset** e um **LED**.​
{.is-info}

* No [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), adicione/descomente \(removendo o `;` no início da linha\) a seguinte linha: `system.power.switch=PIN356ONOFFRESET`
* Para conectar o **botão reset ao GPIO** do Raspberry Pi: Conecte um pino ao **GPIO2** \(o **terceiro** gpio do canto superior esquerdo\) e o outro ao mesmo terra do botão liga/desliga \(o **sexto** gpio\).
* **O LED** deve ser conectado ao **GPIO14** \(o **oitavo** gpio\) e também ao terra \(o **sexto** gpio\).

### **​**Resumindo: <a id="resumindo"></a>

* _Power+_ no **GPIO 3 \(PINO 5\)**
* _Reset+_ no **GPIO 2 \(PINO 3\)**
* _LED+_ no **GPIO 14 \(PINO 8\)**
* _Power-_, _Reset-_ e _LED-_ em um do **Terras \(PINOS 6, 9, 14, 20, 25, 30, 34 ou 39\)**


>Observe que isso só funciona com **um botão de pressão para Reset** e **um botão ON/OFF para ligar**.​
{.is-info}

## Atualização do Recalbox &gt; 18.02.09 <a id="atualizacao-do-recalbox-greater-than-18-02-09"></a>


>Desde a atualização 18.02.09, Os **scripts de energia evoluíram**, para oferecer a você mais possibilidades!  
>Agora, seguindo o mesmo método explicado anteriormente, você será capaz de...
{.is-info}

* **Com um toque rápido** \(e _desligado_\): Liga o Recalbox
* **Com um toque rápido** \(_e ligado_\): sai do emulador atual e retorna ao menu principal
* **Com um toque longo** \(_e ligado_\): Desliga o Recalbox corretamente \(equivalente a INICIAR&gt; Sair&gt; Desligar normalmente\)_​_
* **Com um toque rápido** \(e _desligado_\): - \(não acontece nada\)
* **Com um toque rápido** \(_e ligado_\): Reinicia o jogo, como no momento no console
* **Com um toque longo** \(_e ligado_\): Reinicia o Recalbox \(equivalente a INICIAR&gt; Sair&gt; Reiniciar\)

