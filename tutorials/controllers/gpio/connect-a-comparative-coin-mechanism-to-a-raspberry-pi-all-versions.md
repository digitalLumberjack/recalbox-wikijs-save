# Connect a Comparative Coin Mechanism to a Raspberry Pi \(all versions\)

First of all, for this tutorial, I took elements of the manual supplied with the following exclusive coin mechanism:

​[http://www.smallcab.net/monnayeur-comparatif-facade-p-902.html](http://www.smallcab.net/monnayeur-comparatif-facade-p-902.html)​

Also, please be aware that in no case do I advertise the above signs, these are just examples. Finally, I cannot be held responsible in the event of a problem.

## 1 - Operation principle of the coin mechanism

The comparator coin mechanism works by comparison between the inserted coin and the so-called "standard" coin permanently installed in the coin mechanism. The coin mechanism analyzes the electronic signature of the inserted coin and compares it with the electronic signature of the standard coin.

If the inserted coin has a signature close to the standard coin, the coin is accepted → otherwise the coin is refused → When a coin is accepted, the coin mechanism generates an electrical impulse for the Raspberry Pi. 

This impulse is recognized by Recalbox \(Select button\) and a game credit is then granted to the player.


>**Note:** it is possible to use metal tokens instead of coins.
>
{.is-info}

Very simple based on four threads:

* Red: + 12V to be connected to a 12V / 1A power supply.

​[https://www.amazon.fr/noir-s%C3%A9curit%C3%A9-CCTV-alimentation-cam%C3%A9ra/dp/B00B0T5D5W/ref=sr\_1\_1?ie=UTF8&qid=1481099754&sr=8-1&keywords=Alimentation+12V%2F1A](https://www.amazon.fr/noir-s%C3%A9curit%C3%A9-CCTV-alimentation-cam%C3%A9ra/dp/B00B0T5D5W/ref=sr_1_1?ie=UTF8&qid=1481099754&sr=8-1&keywords=Alimentation+12V%2F1A)\)

* White: "Insert coin" to connect to the GPIO \(or USB controller\), corresponding to the **Select** button under Recalbox.


>The use of a "relay" is mandatory!
>
{.is-danger}

* Black: ground to be connected to the 0V of the 12V / 1A power supply.
* Gray: Counter \(not used here\)

## 2 - Installation on a Raspberry Pi

As you may understand, the use of this currency mechanism with a Raspberry Pi necessarily requires the use of an intermediate electronic component called "relay" or "keyboard hack" for purists.

So, here's a low-cost solution for you to do this "keyboard hack"

## 3 - List of necessary equipment

```text
1 good soldering iron, wire to make the tracks, tin grease and curve

1 12V relay (5 wires)
```

​[https://www.amazon.fr/%C3%A9lectromagn%C3%A9tique-montage-Electrom%C3%A9nager-contr%C3%B4le-BI084/dp/B013SPRXQC/ref=sr\_1\_13?ie=UTF8&qid=1481098401&sr=8-13&keywords=relais+12V](https://www.amazon.fr/%C3%A9lectromagn%C3%A9tique-montage-Electrom%C3%A9nager-contr%C3%B4le-BI084/dp/B013SPRXQC/ref=sr_1_13?ie=UTF8&qid=1481098401&sr=8-13&keywords=relais+12V)​

```text
1 Prototype Card
```

​[https://www.amazon.fr/Pixnor-platine-Prototype-soudure-Circuit/dp/B01GUZ5L6G/ref=sr\_1\_6?ie=UTF8&qid=1481098476&sr=8-6&keywords=carte+pcb](https://www.amazon.fr/Pixnor-platine-Prototype-soudure-Circuit/dp/B01GUZ5L6G/ref=sr_1_6?ie=UTF8&qid=1481098476&sr=8-6&keywords=carte+pcb)​

```text
2 terminal blocks
```

​[https://www.amazon.fr/SODIAL-poles-distance-Bornier-250V/dp/B00I00OHHY/ref=pd\_sim\_107\_1?\_encoding=UTF8&psc=1&refRID=NWQN6HYVB76TBMW7RVFP](https://www.amazon.fr/SODIAL-poles-distance-Bornier-250V/dp/B00I00OHHY/ref=pd_sim_107_1?_encoding=UTF8&psc=1&refRID=NWQN6HYVB76TBMW7RVFP)​

## 4 - Wiring


>Don't hesitate to test your card BEFORE connecting it to your Raspberry and your coin mechanism
>
{.is-warning}

The connection of the coin mechanism to a Raspberry Pi therefore requires the installation of this "keyboard hack" BETWEEN the coin mechanism AND the GPIO of your Raspberry Pi.

The 2 pins of "Terminal 1" must be connected:

* one on the "0V" wire of the 12V / 1A power supply.
* the other on the "white" wire of your coin mechanism.

The 2 pins of "Terminal 2" must be connected: 

* one on the "GND" pin on the Raspberry Pi GPIO connector.
* the other on a "GPIOxx" pin on the Raspberry Pi GPIO connector. \(Select button\)


>There are several models / generations of Raspberry Pi
>
{.is-warning}

Refer to your model-specific documentation to identify the Raspberry Pi GPIO connector and the position of the "GND" and "GPIOxx" pins inside this connector:

• [https://en.wikipedia.org/wiki/Raspberry\_Pi](https://en.wikipedia.org/wiki/Raspberry_Pi)

• [https://www.raspberrypi.org/](https://www.raspberrypi.org/)​

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-LzcIIKiUTJkoR6QgOtm%2F-LzcJioU5qb9FZhzDZNf%2F68747470733a2f2f73332d65752d776573742d312e616d617a6f6e6177732e636f6d2f666f72756d732e726563616c626f782e636f6d2f33643837316434632d663734322d346266372d393366632d3062383035613439666365312e6a7067.jpg?alt=media&token=11d964cb-5a54-4747-8b6f-7e0a7a0ac089)

