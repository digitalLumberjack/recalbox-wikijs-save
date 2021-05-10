---
title: Herunterladen und Installieren von Recalbox
description: Wie installieren man Recalbox
---

# Herunterladen und Installieren von Recalbox

Es ist möglich, Recalbox kann auf verschiedenen Gerätetypen installiert werden, wobei der bekannteste der Raspberry Pi \(0, 0w, 1, 2, 3 und 3B+\) ist. Recalbox ist auch mit dem Odroid \(C2, XU4 und XU4Q\) sowie mehreren 32- und 64-Bit-Computern kompatibel.



## Die erforderlichen Zubehörteile



Überprüfen Sie, ob Sie das erforderliche Speichergerät und die Stromversorgung für das ausgewählte Gerät haben.

| Produktkategorien | Raspberry 0/0w/1/2/3 | Odroid C2 | Odroid XU4 | PC \(32 oder 64 Bits\) |
| :---: | :---: | :---: | :---: | :---: |
| Speicherkapazität | Micro-SD Karte 8GB+ Class 10 \(pi1: SD\) | µSD Karte 8GB+ | µSD Karte 8GB+ | USB-Stick oder 8GB+ Festplatte |
|  Netzteil | µUSB **2.5A** \(gute Qualität\) | µUSB **2.5A** \(gute Qualität\) | Verwenden Sie das offizielle Netzteil Odroid. | Standard-PC-Netzteil |
| Vidéo |  HDMI-Kabel, ****HDMI/VGA oder HDMI/DVI Konverter | HDMI-Kabel | HDMI-Kabel | HDMI, VGA \(und wahrscheinlich DVI und DP\) |
| Controller | USB oder Bluetooth | USB oder Bluetooth | USB oder Bluetooth | USB oder Bluetooth |




>**Informationen :**  
>  
>Sie benötigen die folgenden Elemente, um Ihre Recalbox zu erstellen :  
>Besuchen Sie [unseren Shop](https://www.recalbox.com/de/shop/) !
{.is-info}



## Download <a id="telechargement"></a>

Der erste Schritt besteht darin, die **.img.xz**-Datei, die Ihrem Hardwaretyp entspricht, in [archive.recalbox.com](https://archive.recalbox.com/) **herunterzuladen**.


>**ACHTUNG :**  
>Nur die **letzte Version** von Recalbox ist **verfügbar**.  
>Die **alten Versionen** werden **weder heruntergeladen noch vom Entwicklungsteam unterstützt**.
{.is-danger}



## Flash das Image-Datei <a id="flasher-limage"></a>

Mit dem Programm balenaEtcher \(dieses Programm ist sehr einfach zu bedienen\) können Sie die Image-Datei auf die gewünschten Datenträger flashen \(z.B. eine microSD-Karte für einen Raspberry Pi\).



### Rpi


>Sie müssen mindestens eine 8 GB Micro-SD-Karte verwenden und wir empfehlen das **Modell Sandisk Ultra**.
{.is-danger}

* Starten Sie balenaEtcher
* Wählen Sie das Image-Datei aus
* Wählen Sie das richtige Laufwerk aus
* Und du beginnst mit dem Flash.

Sobald der Vorgang abgeschlossen ist.

* Sie können den Datenträger \(microSD-Karte\) auswerfen
* Stecken Sie es in das Gerät, mit dem Sie Recalbox verwenden möchten
* Starten Sie es und Sie sollten sehen, wie Recalbox zum Leben erwacht.


>**Hinweis :**
>
>Wenn Sie sich auf einem RPi 1 Modell B oder B + befinden, sollten Sie Ihren RPi wirklich übertakten, um die bestmögliche Leistung zu erzielen.
>
>* Gehen Sie zum Menü Systemeinstellungen.
>* Ändern Sie Ihre Übertaktungseinstellungen.
>
>Ich empfehle dringend die höchste Übertaktungseinstellung, "EXTREME" auf allen RPi1s, die Ihre Garantie aufheben kann, aber in Spielen unglaublich flüssiger ist als jede andere Konfiguration.
{.is-warning}



### Odroid / X86 / X86\_64


>**Information :**
>
>Sie können **recalboxOS** entweder auf einem **USB-Stick** oder auf einer **Festplatte** installieren.
>
>Wenn Sie eine Festplatte verwenden, müssen Sie sie entsprechend dieser Seite formatieren :  
>~~**link zum Fp-Format**~~
{.is-info}

* Starten Sie **balenaEtcher**
* Deaktivieren Sie **die Funktion "Unsafe-Modus"** in den **Einstellungen** \(oben rechts\)
* Wählen Sie das **Image-Datei** aus
* Wählen Sie das **richtige Laufwerk** aus
* Und Sie starten **den Flash**.

Sobald der Vorgang abgeschlossen ist.

* Sie können den Datenträger \(microSD-Karte\) auswerfen
* Stecken Sie es in das Gerät, mit dem Sie Recalbox verwenden möchten.

