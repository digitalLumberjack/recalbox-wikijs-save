---
title: Conectar um mecanismo comparativo de moedas a um Raspberry Pi \(todas as versões\)
---

# Conectar um mecanismo comparativo de moedas a um Raspberry Pi \(todas as versões\)

Antes de tudo, para este tutorial, peguei elementos do manual fornecido com o seguinte mecanismo de moeda exclusivo:

​[http://www.smallcab.net/monnayeur-comparatif-facade-p-902.html](http://www.smallcab.net/monnayeur-comparatif-facade-p-902.html)​

Além disso, esteja ciente de que, em nenhum caso, eu anuncio a marca acima, são apenas exemplos. Enfim, não posso ser responsabilizado no caso de um problema.

## 1 - Como funciona o mecanismo da moeda <a id="1-como-funciona-o-mecanismo-da-moeda"></a>

O mecanismo comparador de moedas funciona por comparação entre a moeda inserida e a chamada moeda "padrão" instalada permanentemente no mecanismo de moedas. O mecanismo da moeda analisa a assinatura eletrônica da moeda inserida e a compara com a assinatura eletrônica da moeda padrão.

Se a moeda inserida tem uma assinatura próxima à moeda padrão, a moeda é aceita → caso contrário, a moeda é recusada → Quando uma moeda é aceita, o mecanismo da moeda gera um impulso elétrico para o Raspberry Pi.

Esse impulso é reconhecido pelo Recalbox \(tecla **Select**\) e um crédito de jogo é concedido ao jogador.


>**Nota:** é possível usar _tokens_ de metal em vez de moedas.
{.is-info}

Muito simples a base de quatro cabos:

* Vermelho: + 12V a ser conectado a uma fonte de alimentação 12V / 1A.

​[https://www.amazon.fr/noir-s%C3%A9curit%C3%A9-CCTV-alimentation-cam%C3%A9ra/dp/B00B0T5D5W/ref=sr\_1\_1?ie=UTF8&qid=1481099754&sr=8-1&keywords=Alimentation+12V%2F1A](https://www.amazon.fr/noir-s%C3%A9curit%C3%A9-CCTV-alimentation-cam%C3%A9ra/dp/B00B0T5D5W/ref=sr_1_1?ie=UTF8&qid=1481099754&sr=8-1&keywords=Alimentation+12V%2F1A)\)

* Branco: "Inserir moeda" para conectar-se ao GPIO \(ou controlador USB\), correspondente ao botão **Select** do Recalbox.


>Obrigatório o uso de um "relé"!
{.is-danger}

* Preto: terra a ser conectado ao 0V da fonte de alimentação 12V / 1A.
* Cinza: Contador \(não usado aqui\)

## 2 - Instalação em um Raspberry Pi <a id="2-instalacao-em-um-raspberry-pi"></a>

Como você deve entender, o uso desse mecanismo de moeda com um Raspberry Pi requer necessariamente o uso de um componente eletrônico intermediário chamado "relé" ou "hack do teclado" para puristas.

Então, aqui está uma solução de baixo custo para você fazer esse "hack do teclado"

## 3 - Lista de equipamentos necessários <a id="3-lista-de-equipamentos-necessarios"></a>

```text
1 ferro de soldar bom, fio para fazer as trilhas, graxa de estanho e curva

1 relé de 12V (5 fios)
```

​[https://www.amazon.fr/%C3%A9lectromagn%C3%A9tique-montage-Electrom%C3%A9nager-contr%C3%B4le-BI084/dp/B013SPRXQC/ref=sr\_1\_13?ie=UTF8&qid=1481098401&sr=8-13&keywords=relais+12V](https://www.amazon.fr/%C3%A9lectromagn%C3%A9tique-montage-Electrom%C3%A9nager-contr%C3%B4le-BI084/dp/B013SPRXQC/ref=sr_1_13?ie=UTF8&qid=1481098401&sr=8-13&keywords=relais+12V)​

```text
1 placa de protótipo
```

​[https://www.amazon.fr/Pixnor-platine-Prototype-soudure-Circuit/dp/B01GUZ5L6G/ref=sr\_1\_6?ie=UTF8&qid=1481098476&sr=8-6&keywords=carte+pcb](https://www.amazon.fr/Pixnor-platine-Prototype-soudure-Circuit/dp/B01GUZ5L6G/ref=sr_1_6?ie=UTF8&qid=1481098476&sr=8-6&keywords=carte+pcb)​

```text
2 Terminais de Parafuso Do Bloco Conector
```

​[https://www.amazon.fr/SODIAL-poles-distance-Bornier-250V/dp/B00I00OHHY/ref=pd\_sim\_107\_1?\_encoding=UTF8&psc=1&refRID=NWQN6HYVB76TBMW7RVFP](https://www.amazon.fr/SODIAL-poles-distance-Bornier-250V/dp/B00I00OHHY/ref=pd_sim_107_1?_encoding=UTF8&psc=1&refRID=NWQN6HYVB76TBMW7RVFP)​

## 4 - Cabeamento <a id="4-cabeamento"></a>


>Não hesite em testar seu cartão ANTES de conectá-lo ao seu Raspberry e ao seu mecanismo de moedas
{.is-warning}

A conexão do mecanismo de moedas com um Raspberry Pi requer, portanto, a instalação deste "hack do teclado" ENTRE o mecanismo de moedas E o GPIO do seu Raspberry Pi.

Os 2 pinos do "Terminal 1" devem estar conectados:

* um no fio "0V" da fonte de alimentação 12V / 1A.
* o outro no fio "branco" do seu mecanismo de moedas.

Os 2 pinos do "Terminal 2" devem estar conectados:

* um no pino "GND" do conector Raspberry Pi GPIO.
* o outro em um pino "GPIOxx" do conector GPIO do Raspberry Pi. \(tecla Select\)


>Existem vários modelos / gerações de Raspberry Pi 
{.is-warning}

Consulte a documentação específica do seu modelo para identificar o conector GPIO do Raspberry Pi e a posição dos pinos "GND" e "GPIOxx" dentro deste conector:

• [https://pt.wikipedia.org/wiki/Raspberry\_Pi](https://pt.wikipedia.org/wiki/Raspberry_Pi)​

• [https://www.raspberrypi.org/](https://www.raspberrypi.org/)​

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzcIIKiUTJkoR6QgOtm%2F-LzcJioU5qb9FZhzDZNf%2F68747470733a2f2f73332d65752d776573742d312e616d617a6f6e6177732e636f6d2f666f72756d732e726563616c626f782e636f6d2f33643837316434632d663734322d346266372d393366632d3062383035613439666365312e6a7067.jpg?alt=media&token=11d964cb-5a54-4747-8b6f-7e0a7a0ac089)

