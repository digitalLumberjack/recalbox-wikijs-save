---
title: Konfiguration einer Controller
description: Wie konfigurieren Sie Ihren Controller ?
---

# Konfiguration einer Controller

## Hinzufügen und Konfigurieren eines USB-Controllers

Sie können USB-Controller auf Recalbox hinzufügen.  
Die meisten Modelle sind kompatibel \(siehe Kompatibilitätsliste\).

* Nach dem Anschluss Ihres USB-Controllers \(oder der Kopplung Ihres Bluetooth-Controllers\)
* Drücken Sie die **START**-Taste, wenn ein Controller bereits konfiguriert ist \(oder die **Eingabetaste**\).
* Wählen Sie "**CONTROLLER-EINSTELLUNGEN**" und folgen Sie den Anweisungen.

Die Namen, mit denen die Tasten zugewiesen werden, entsprechen denen des Super Nintendo-Controllers :​

![Super Nintendo Controller \(SNES\)](/migration-images/basis-handbuch/erste-schritte/manette-snes-all-psd.jpg)


>Die Tasten L1, R1, L2, R2, L3 und R3 basieren auf dem Playstation-Controller.
{.is-info}

Die letzte zu konfigurierende Taste \(**HOTKEY**\) ist diejenige, die verwendet wird, um die Sonderbestellungen zu aktivieren, wenn Sie sich in einem Emulator befinden :

* Bei Xbox 360 und Xbox One Controllern ist die _Hotkey_-Taste der _HOME_-Taste zugeordnet.
* Bei Ps3- und PS4-Controllern ist die _Hotkey_-Taste der _PS_-Taste zugeordnet.
* Wenn es keine dedizierte oder nicht zugewiesene Taste gibt, wird empfohlen, der _Select_- oder _L3_-Taste _Hotkey_ zuzuweisen \(Klicken Sie auf den linken Joystick\).


>Wenn Sie eine Taste \(außer _Hotkey_\) nicht konfigurieren möchten, drücken Sie die Taste Unten, um zur nächsten Taste zu gelangen.
{.is-info}

Zurück auf dem Konfigurationsbildschirm können Sie den Controller einem Spieler zuweisen. Ihr Controller ist nun konfiguriert.

## Zuweisen von Tasten

* Bei 6-Tasten-Controllern \(SNES, Arcade,...\) werden die Tasten entsprechend dem SNES-Controller \(siehe oben\) zugeordnet.
* Bei 2-Tasten-Controllern \(NES, PC Engine, Gameboy,...\) sind die Tasten A und B zugeordnet.

## Verwendung einer Tastatur

Wenn Sie Ihren Controller nicht konfigurieren können, können Sie eine verkabelte USB-Tastatur an Recalbox anschließen, um ihn zu konfigurieren.

* **START** = _EINGABE_
* **SELECT** = _LEERTASTE_
* **Zurück** = _S_
* **Bestätigen** = _A_

## PS3-Controller

Um einen PS3-Controller **zuzuordnen** :

* Schließen Sie den Controller zunächst an den USB-Anschluss an \(über ein geeignetes Kabel\)
* Warten Sie dann 10 Sekunden
* Danach können Sie die Steuerung trennen
* Dann die **PS**-Taste drücken, um die drahtlose Verbindung zu starten.


>**Hinweis :**  
>Für asiatische Kopien der PS3 Dualshock 3 \(wie GASIA oder SHANWAN\) müssen Sie einige zusätzliche Einstellungen vornehmen. Siehe \[\[PS3-Controller-Treiber\|PS3-Controller-Treiber-\(DE\)\]\]
{.is-warning}


>**Achtung :**  
>Wenn Sie Zweifel an der Stromversorgung und dem Stromverbrauch haben, ist es am besten, das Laden des PS3-Controllers auf dem Raspberry Pi zu vermeiden, da dies zu Stabilitätsproblemen führen kann.  
>  
>Bitte verbinden Sie den Controller mit dem Pi, nur um Ihren Controller mit Ihrer Recalbox zu verknüpfen.
{.is-danger}

Wenn Sie die beteiligten Einstellungen verstehen oder den Controller mit einer USB-Verbindung verwenden möchten :

* müssen Sie den PS3-Bluetooth-Treiber in recalbox.conf deaktivieren, indem Sie Folgendes definieren `controllers.ps3.enabled=0`

Denken Sie daran, dass die Konfiguration der Controller in Recalbox auf der Konfiguration der SNES-Tasten basiert :

| PS3-Controller | SNES-Controller |
| :---: | :---: |
| X | B |
| ◯ | A |
| ⬜ | Y |
| △ | X |


>**Information :**  
>Standardmäßig ist **HOTKEY** der **PS**-Taste zugeordnet \(die in der Mitte des Controllers\). Weitere Informationen über HOTKEY finden Sie unter Sonderbestellungen.
{.is-info}

## Xbox 360 Controller 


>**Hinweis :**  
>Xbox 360 Wireless-Controller erfordern einen speziellen Wireless-Empfangs-Dongle.
{.is-warning}

Denken Sie daran, dass die Konfiguration der Controller in Recalbox auf der Konfiguration der SNES-Tasten basiert :

| Xbox 360 Controller  | SNES-Controller |
| :---: | :---: |
| A | B |
| B | A |
| X | Y |
| Y | X |


>**Information :**  
>Standardmäßig ist **HOTKEY** der **HOME**-Taste zugeordnet \(die in der Mitte des Controllers\). Weitere Informationen über HOTKEY finden Sie unter Sonderbestellungen.
{.is-info}

## Fügen Sie einen Bluetooth-Controller hinzu.

Um einen Bluetooth-Controller hinzuzufügen :

* Stellen Sie Ihren Controller in den _Kopplungsmodus_.
* Drücken Sie dann die **START**-Taste und wählen Sie _CONTROLLEREINSTELLUNG_
* Dann _EINEN BLUETOOTH-CONTROLLER ZUORDEN._

Eine **Liste der** erkannten **Controller** erscheint !

* Wählen Sie einfach Ihren aus und Ihr Controller ist gepaart.
* Sie können es nun konfigurieren \(falls es nicht bereits von Recalbox unterstützt wird\).


>**Information :**  
>für **8bitdo**-Controller siehe \[\[8bitdo on recalbox\|8bitdo on-recalbox-\(DE\)\]\]
{.is-info}

## Allzweckeingabe/-ausgabe \(GPIO\) Controller

* Sie können Ihre Tasten und Arcade-Joysticks direkt an die GPIOs des Raspberry Pi anschließen \(siehe **GPIO-Controller**\).
* Sie können auch Original-Controller von PSOne, Nes, Snes, Megradrive,.... anschließen. \(Siehe **DB9-Controller** und **Gamecom-Controller**\).

## Virtuelle Gamepads

Mit dem Projekt unseres Freundes Miroof Virtuelle Gamepads, können Sie mit Ihren Smartphones/Tablets bis zu 4 Controller hinzufügen !

* Starten Sie den Webbrowser Ihres Smartphones
* Geben Sie dann die IP-Adresse Ihrer Recalbox gefolgt vom Kommunikationsport \(Port = 8080\) ein.


>**Information :**  
>Die IP-Adresse Ihrer Recalbox finden Sie im Menü **NETZWERKOPTIONEN**
{.is-info}

![Kontaktbereiche der virtuellen Controller](/migration-images/basis-handbuch/erste-schritte/virutalgamepad_touch_zones.png)

