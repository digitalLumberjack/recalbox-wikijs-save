---
title: Ajouter un bouton on/off a votre recalbox
---

# Ajouter un bouton on/off a votre recalbox


>Vous pouvez maintenant ajouter un **bouton on/off** à votre **Recalbox**.  
>Le bouton peut être un **bouton poussoir** \(aussi appelé "_momentary switch"\)_ ou un **bouton** _**ON/OFF**_. 
{.is-info}

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJH8jdcYQLsGJvtswtn%2F-MJHA_HOg9wBtC_agqnR%2Fadd-a-start-stop-button-to-your-recalbox-en-recalboxrecalbox-os.jpg?alt=media&token=bccf6ecf-3c7e-4008-bba0-9dbb427910ab)

## Pour câbler le bouton au GPIO du Raspberry Pi

* Connectez une broche au **GPIO3** \(le **cinquième** gpio en partant d'en haut à gauche\), et l'autre au ground sur sa droite \(le **sixème** gpio\): ​

![](https://gblobscdn.gitbook.com/assets%2F-LdKTX4ollh_G72-pO8z%2F-MJH8jdcYQLsGJvtswtn%2F-MJHBikcKEvyxKFdtUAG%2FRaspberry%20Pi%2040-pin%20GPIO%20Layout.png?alt=media&token=49f0c74e-433e-40fb-81ca-06cec2f2efb7)

* Enfin, vous devez activer le support du bouton dans le[ recalbox.conf](/fr/usage-basique/premieres-notions/le-fichier-recalbox.conf) en ajoutant une de ces lignes :
  * `system.power.switch=PIN56ONOFF` pour un bouton ON/OFF 
  * `system.power.switch=PIN56PUSH` pour un bouton poussoir

Et vous avez une **Recalbox** qui peut être **éteinte/allumée par un simple bouton !**

## Rajouter un bouton reset et une LED.


>**Depuis Recalbox 4.0 beta 4**, il y a une autre option où vous pouvez rajouter un **bouton reset** et une **LED.**
{.is-info}

* Dans **recalbox.conf**, ajoutez/décommentez \(en enlevant le ; au début de la ligne\) la ligne suivante:

  `system.power.switch=PIN356ONOFFRESET` 

*  Pour câbler le **bouton reset au GPIO** du Raspberry Pi : Connectez une broche au **GPIO2** \(le **troisième** gpio en partant d'en haut à gauche\), et l'autre au même ground que le bouton on/off \(le **sixième** gpio\). **La LED** est connectée au **GPIO14** \(le _\*huitième_ gpio\) **ainsi qu'au ground.**

\*\*\*\*

#### Pour résumer:

* _Power+_ sur **GPIO 3** \(**PIN 5**\) 
* _Reset+_ sur **GPIO 2** \(**PIN 3**\) 
* _LED+_ sur **GPIO 14** \(**PIN 8**\) 
* _Power-_, _Reset-_ et _Led-_ sur l'un des **Ground** \(**PIN 6, 9, 14, 20, 25, 30, 34 ou 39**\)


>Notez que cela ne fonctionne qu'avec **un bouton poussoir pour le reset** et **un bouton ON/OFF pour l'alimentation**
{.is-info}

## Mise à jour Recalbox &gt; 18.02.09 <a id="mise-a-jour-recalbox-greater-than-18-02-09"></a>


>Depuis la mise à jour 18.02.09 _**\(lien mort !\)**_, les **power scripts ont évolué**, pour vous offrir plus de possibilités !  
>Désormais, en suivant la même méthode expliquée précédemment, vous allez pouvoir…
{.is-info}



### Avec le Bouton POWER \(PIN 5 + GROUND\) <a id="avec-le-bouton-power-pin-5-ground"></a>

* **Pression courte** _\(éteint\)_ : Allumer votre Recalbox 
* **Pression courte** _\(allumé\)_ : Quitter l’émulateur en cours et revenir au menu principal 
* **Pression longue** _\(allumé\)_ : Éteindre proprement votre Recalbox _\(équivaut à faire START &gt; Quitter &gt; Éteindre normalement\)_

\_\_

### Avec le Bouton RESET \(PIN 3 + GROUND\) <a id="avec-le-bouton-reset-pin-3-ground"></a>

* **Pression courte** _\(éteint\)_ : - 
* **Pression courte** _\(allumé\)_ : Reset le jeu, comme à l'époque sur la console 
* **Pression longue** _\(allumé\)_ : Redémarrer votre Recalbox _\(équivaut à faire START &gt; Quitter &gt; Redémarrer\)_

