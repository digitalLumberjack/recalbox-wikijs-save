---
title: Saída de áudio analógica no Pi Zero
---

# Saída de áudio analógica no Pi Zero

## Não há saída de áudio no Pi zero? Sério? <a id="nao-ha-saida-de-audio-no-pi-zero-serio"></a>

É verdade: para manter o Pi Zero pequeno e barato, o filtro de áudio do fone de ouvido não está incluído ... Não há tomada para obter música do Recalbox... Você ainda pode obter áudio digital via HDMI, por isso, se conectar o Pi ao um monitor com alto-falantes, funcionará bem.

Isso não importa se você conectou o Recalbox à TV na sua sala de estar, mas, em um terminal arcade, com uma monitor comum ou uma TV simples, não é possível ouvir o som do HDMI.

Bem, isso não é verdade. Se você optar por usar um conversor HDMI-VGA, poderá ter a sorte de conseguir uma que possua uma saída de áudio como esta: [https://www.amazon.com/MOKiN-Adapter-Converter-Powered-Laptop/dp/B01F1T9IS4/ref=pd\_lpo\_147\_tr\_t\_3/153-2977990-6201028?ie=UTF8&psc=1&refRID=GV8D910Z9HMW8BW4FR0P](https://www.amazon.com/MOKiN-Adapter-Converter-Powered-Laptop/dp/B01F1T9IS4/ref=pd_lpo_147_tr_t_3/153-2977990-6201028?ie=UTF8&psc=1&refRID=GV8D910Z9HMW8BW4FR0P)​

Mas se você usa um Pi zero, certamente deseja integrá-lo em um dispositivo pequeno, com uma pequena tela TFT no barramento SPI / I2C / DPI, e não terá espaço para esse conversor.

## Como o áudio é transmitido no Raspberry Pi <a id="como-o-audio-e-transmitido-no-raspberry-pi"></a>

Como descrito em [https://learn.adafruit.com/introducing-the-raspberry-pi-zero/audio-outputs](https://translate.google.com.br/translate?hl=pt-BR&tab=rT&sl=auto&tl=pt&u=https%3A%2F%2Flearn.adafruit.com%2Fintroducing-the-raspberry-pi-zero%2Faudio-outputs), outros Raspberry Pi usam 2 saídas PWM com um circuito de filtro para criar a saída de som. Nesta página, você encontrará o dispositivo eletrônico real incorporado ao Raspberry Pi para criar o som. 

Mas, se você ler atentamente, ele usa o PWM no GPIO 40 e 45, que não são destacados no Pi Zero.

A solução é usar PWM0 no GPIO 18 \(ALT5\) e PWM1 no GPIO 13 \(ALT0\) ou GPIO 19 \(ALT5\) e criar seu próprio circuito de filtro.

O manuseio é detalhado na página [https://learn.adafruit.com/adding-basic-audio-ouput-to-raspberry-pi-zero/pi-zero-pwm-audio](https://translate.google.com.br/translate?hl=pt-BR&tab=wT1&sl=auto&tl=pt&u=https%3A%2F%2Flearn.adafruit.com%2Fadding-basic-audio-ouput-to-raspberry-pi-zero%2Fpi-zero-pwm-audio).

Com o Recalbox, a maneira mais fácil é adicionar essa linha no arquivo config.txt :

```text
dtoverlay=pwm-2chan,pin=18,func=2,pin2=13,func2=4
```

Ele reconfigurará os pinos na inicialização sem nenhum software ou serviço externo. O PWMO estará no GPIO 18 \(pino 12 no conector\) e o PWM1 no GPIO 13 \(pino 33 no conector\).

Como descrito em [https://hackaday.io/project/9467-piboy-zero/log/35090-pi-zero-pwm-audio-device-tree-overlay](https://hackaday.io/project/9467-piboy-zero/log/35090-pi-zero-pwm-audio-device-tree-overlay), você pode fazer sua própria sobreposição com o seguinte código-fonte:

```text
/dts-v1/;
/plugin/;

/ {
  compatible = "brcm,bcm2708";

  fragment@0 {
    target = <&gpio>;
    __overlay__ {
      pinctrl-names = "default";
      pinctrl-0 = <&pwm_audio_pins>;

    pwm_audio_pins: pwm_audio_pins {
	brcm,pins = <13 18>;   /* gpio no ('BCM' number) */
	brcm,function = <4 2>; /* 0:in, 1:out, 2: alt5, 3: alt4, 4: alt0, 5: alt1, 6: alt2, 7: alt3 */
	brcm,pull = <0 0>;     /* 2:up 1:down 0:none */
      };
    };
  };
 };
```

Se você configurou o buildroot e já montou o Recalbox, é possível compilar os dts com:

```text
output/build/linux-FIRMWARE/scripts/dtc/dtc -@ -I dts -O dtb -o pwm-audio-pi-zero-overlay.dtbo pwm-audio-pi-zero-overlay.dts
```

e você copia o arquivo `pwm-audio-pi-zero-overlay.dtbo` em /boot/overlays do seu Recalbox. A configuração agora é mais simples:

```text
dtoverlay=pwm-audio-pi-zero
```

### Teste rápido de saída de som <a id="teste-rapido-de-saida-de-som"></a>

Você pode testar se isso funciona sem criar o circuito do filtro. Você pode conectar seus fones de ouvido diretamente entre o pino PWM e o terra, conforme mostrado na figura a seguir.

Deve funcionar, mas o som pode estar com defeito.

### Melhorando a qualidade do som

Para criar seu filtro, você precisará de certos componentes eletrônicos:

* 2 resistores de 270 Ohms
* 2 resistores de 150 Ohms
* 2 capacitores de 10µF
* 2 capacitores de 33nF \(pode ser substituído por capacitores de 22nF ou 10nF\)

Aqui está o esquema:

![](https://camo.githubusercontent.com/a8cdcb22c9c1ea3d74b9a19cebd2221f62505d78/687474703a2f2f696d616765732e6d6f726572652e65752f617564696f46696c7465725f62622e706e67)

E o filtro real:

![](https://camo.githubusercontent.com/4340ee9cb7edbed9f0cf0086c3ac8d470ecaadd6/687474703a2f2f696d616765732e6d6f726572652e65752f50695a65726f417564696f46696c7465722e6a7067)

Você terá que amplificar a saída porque os sinais são filtrados e têm níveis muito baixos.

##  Amplificação e controle de volume <a id="amplificacao-e-controle-de-volume"></a>

Você pode usar um pequeno amplificador de 5V 2x3W. Você também pode adicionar um potenciômetro de áudio estéreo para ajustar o volume.

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-Lzcoc4J5dudNcYgeHNG%2F-Lzcu6Q_D1r4PxVuKGSG%2F687474703a2f2f696d616765732e6d6f726572652e65752f617564696f416d706c692e6a7067.jpg?alt=media&token=b6215b91-a7af-4439-9816-ac0c0b8242fa)

