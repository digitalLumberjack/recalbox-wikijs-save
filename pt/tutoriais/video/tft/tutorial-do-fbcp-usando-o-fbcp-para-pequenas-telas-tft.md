---
title: Tutorial do FBCP - Usando o FBCP para pequenas telas TFT
---

# Tutorial do FBCP - Usando o FBCP para pequenas telas TFT

Está página ainda está sendo construída. Sinta-se livre para corrigi-la e adicionar informações ;\)

## O que é FBCP? <a id="o-que-e-fbcp"></a>

​[https://github.com/tasanakorn/rpi-fbcp](https://github.com/tasanakorn/rpi-fbcp)​

Este programa é usado para copiar o framebuffer primário no framebuffer secundário \(por exemplo, FBTFT\). Requer o firmware mais recente do Raspberry Pi \(em 11 de julho de 2013\) para funcionar corretamente.

O FBCP tira um registro instantâneo \(_snapshot_\) de `/dev/fb0`, copia isso para `/dev/fb1` e aguarda 25ms antes de se repetir. O registro instantâneo \(_snapshot_\) leva cerca de 10ms e, com um atraso de 25ms, fornece cerca de 1000 / \(10 + 25\) = 28fps; Uso da CPU: cerca de 2%.


>**Nota :**
>
>O registro instantâneo \(_snapshot_\) e a atualização do driver /dev/fb1 não são sincronizadas.
{.is-info}

## Por que você precisa do FBCP <a id="por-que-voce-precisa-do-fbcp"></a>

Como o Recalbox não usa o Xorg ou qualquer outro servidor gráfico, todas as exibições são feitas no primeiro framebuffer \(`/dev/fb0`\) \(HDMI ou Saída Composta\), que utiliza a energia da GPU e a aceleração do hardware.

No caso de usar o Xorg, podemos redirecionar facilmente a exibição para /dev/fb1. Isso não é tão simples com o modo buffer de quadros do Recalbox. Mesmo que seja possível em alguns programas, graças à variável de ambiente em alguns casos [https://github.com/notro/fbtft/wiki/Framebuffer-use](https://github.com/notro/fbtft/wiki/Framebuffer-use).

No caso do uso de uma tela TFT SPI/I2C, essa nova tela recebe o segundo framebuffer \(`/dev/fb1`\), e não tira proveito da GPU.

E, no caso do Recalbox, todos os programas enviam sua exibição para`/dev/fb0`. Portanto, se você tentar usá-lo com uma pequena tela I2C/TFT, não receberá nenhuma exibição, mesmo que a tela esteja configurada e ativada corretamente.

Portanto, o FBCP permite exibir o conteúdo de `/dev/fb0` usando um registro instantâneo \(_snapshot_\).

Este método não é necessário para telas que usam o modo de exibição DPI [https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md](https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md)​

## Versão modificada do programa FBCP Recalbox <a id="versao-modificada-do-programa-fbcp-recalbox"></a>

​[https://github.com/ian57/rpi-fbcp](https://github.com/ian57/rpi-fbcp)​

De fato, o FBCP ainda não está incluído no Recalbox, mas deve estar disponível na versão 4.1. O programa original foi modificado para tentar obter mais de 28 FPS, com uma redução do tempo de espera:

```text
//usleep(25 * 1000);
usleep(5 * 1000); //only 5 ms to try to get 60fps
```

Se você quiser experimentá-lo, poderá compilá-lo ou obter o arquivo binário correto em[https://github.com/ian57/rpi-fbcp](https://github.com/ian57/rpi-fbcp) dependendo da sua versão do Pi.

Para compilá-lo, você pode obter o rb-4.1.X-fbcp ou simplesmente adicionar a pasta `rpi-fbcp` no diretório do pacote [https://github.com/ian57/recalbox-buildroot/tree/rb-4.1.X-fbcp/package/rpi-fbcp](https://github.com/ian57/recalbox-buildroot/tree/rb-4.1.X-fbcp/package/rpi-fbcp) \(link quebrado!\) com seus 2 makefiles para experimentá-lo.

Este programa não requer muita dependência e deve compilar nas versões 4.0 e 4.1. Para criar e instalar o programa na árvore Recalbox da buildroot, basta executar`make rpi-fbcp` no diretório raiz da sua árvore Recalbox da buildroot. Você terá o programa`fbcp` na pasta de saída `/target/usr/bin` quando a construção estiver concluída.

Em seguida, basta executar o usual comando `make` para criar o arquivo img Recalbox com o programa FBCP, ou simplesmente copie-o para a pasta `/usr/bin` da partição Recalbox no seu cartão SD.

Depois disso, leia [https://recalbox.gitbook.io/tutorials/v/portugues/video/tft/configurando-sua-pequena-tela-tft-no-barramento-spi](configurando-sua-pequena-tela-tft-no-barramento-spi.md) para configurar sua tela e iniciar-lá junto com a inicialização do sistema.

