---
title: RetroFlag GPi-Box
---

# RetroFlag GPi-Box

## Flash und starten !

![GPi Case](/migration-images/hardware-kompatibilitat/image%20%28202%29.png)

So einfach ist das ! _**Recalbox erkennt und installiert alles,**_ was für den Betrieb Ihrer GPI-Box _**automatisch notwendig ist**_.

* Bootfähig einfach die neueste Version von Recalbox für Raspberry Pi1 / Pi0 auf deiner Micro-SD-Karte, steck sie in die Kartusche deines GPI und schalte sie ein ! 
* Warte ein paar Sekunden, dann solltest du dieses Bild auf deinem Bildschirm sehen :

![Installations-Image](/migration-images/hardware-kompatibilitat/image%20%28197%29.png)

* Warten Sie noch ein paar Sekunden \(bei hochkapazitiven micro-SD-Karten kann es länger dauern\), bevor die EmulationStation mit ihrem üblichen Bildschirm startet :

![Emulationsstation startet ...](/migration-images/hardware-kompatibilitat/image%20%28218%29.png)

* Sobald Sie das getan haben, genießen Sie ein optimiertes Design, das Ihre Erfahrung reich, glatt und unterhaltsam macht !

## Spiele installieren

## 

![](/migration-images/hardware-kompatibilitat/image%20%28164%29.png)



## Was ändert sich im Vergleich zu einer normalen Recalbox ?

## 

Wenn Recalbox die für die GPI-Box spezifischen Dinge erkennt und installiert, ändert es auch einige Einstellungen, damit Sie schnell spielen können.  
  
Natürlich sind alle Parameter über das **START**-Menü verfügbar und Sie können danach alles neu konfigurieren.



#### Hier ist eine Liste der geänderten Parameter :

* Alle Videomodi sind `default` eingestellt, um unnötige Änderungen der HDMI-Auflösung zu vermeiden 
* Der Hostname der GPI ist auf **RECALBOXGPI** konfiguriert ****
* Kodi und die X-Taste sind deaktiviert 
* Der virtuelle Controller ist deaktiviert 
* Updates sind deaktiviert 
* Netplay ist deaktiviert 
* Bluetooth ist deaktiviert 
* XArcade- und PS3-Treiber sind deaktiviert 
* Das Musik-Popup ist deaktiviert 
* Die XBOX360-Konfiguration wurde durch die GPI-Konfiguration ersetzt \(Ja, die GPI-Controller ist auch eine Xbox 360 Controller !\) 
* Unser optimiertes Design recalbox-gpicase ist bereits in `/recalbox/share/themes` kopiert und aktiviert



#### Und sind auch installiert :

* dpi-pizero-gpicase.dtbo : Treiber des GPI-Bildschirms 
* pwm-audio-pizero-gpicase.dtbo : GPI-Soundtreiber 
* Ein spezielles Schließskript für den GPI, das von Retroflag an der Basis erstellt und stark modifiziert wurde, so dass der GPI schnell wieder ausgeschaltet wird.



## Konfiguration der WIFI-Verbindung

## 

Sie können weiterhin das START-Menü verwenden, zu den Netzwerk-Untermenüs gehen und das WIFI konfigurieren.

Auf dem GPi haben Sie jedoch keine andere Wahl, als Ihr Passwort über den Controller und die virtuelle Tastatur einzugeben. Je komplexer das Passwort, desto schneller kann es sich in eine komplizierte Aufgabe verwandeln. Dies ist eine schnelle, schrittweise Lösung.

* Bootfähigt und start ihre GPi. Wenn EmulationStation gestartet ist, drücken Sie die **START**-Taste, gehen Sie ins Netzwerkmenü, aktivieren Sie das WIFI und wählen Sie Ihre SSID. 
* Schalten Sie Ihren GPi über das **SELECT**-Menü / Option Halt aus und warten Sie, _bis Recalbox ausgeschaltet ist !_ 
* Entfernen Sie die micro-SD-Karte und greifen Sie auf die **Boot**partition Ihres PCs zu. 
* Öffnen Sie die Datei recalbox-backup.conf, gehen Sie zur Zeile beginnend mit `;wifi.key=`  
* Entfernen Sie das `;` und fügen Sie Ihr WIFI-Passwort nach dem `=` hinzu.

* Speichern Sie alles, stecken Sie die micro-SD-Karte in den GPI und starten Sie sie. 
* Sobald EmlulationStation gestartet ist, sollten Sie im WIFI angeschlossen sein. 
* Öffnen Sie die Datei \\recalboxgpi\share\system\recalbox.conf und ändern Sie die `;wifi.key`-Zeile erneut. Du kannst nano auch in ssh verwenden, wenn du willst. 
* Speichern. Das ist alles, dein Gpi ist konfiguriert.

## Spiele installieren

## 

Jetzt, da Sie mit dem Internet angeschlossen sind, können Sie Ihre Spiele wie gewohnt installieren, indem Sie die SAMBA-Freigabe \( `\\recalboxgpi\share` in einem Datei-Explorer\) oder über den WebManager \( `http://recalboxgpi` in einem Web-Client\) verwenden.

Wenn Ihr GPI nicht angeschlossen ist und Sie Windows auf Ihrem PC ausführen, können Sie :

* Booten Sie auf einer Linux-Live-System-CD und greifen Sie auf Ihre Festplatten und die Share-Partition Ihrer micro-SD-Karte zu, damit Sie kopieren können, was Sie wollen. 
* Installieren Sie dann die Paragon-Software, um auf die EXT4-Linux-Partition der micro-SD-Karte zuzugreifen \([https://www.paragon-software.com/de/home/linuxfs-windows/\#](https://www.paragon-software.com/de/home/linuxfs-windows/#)\)

Viel Spaß mit deinen Lieblingsspielen !



## Was du wissen solltest...

## 

### Welche Art von Spielen kann ich auf dem GPI spielen ?


>**Informationen :**  
>Sie können jedes Spiel von 8/16-Bit-Konsolen und Computern bis die Arcade ausführen.  
>Ja, wirklich ! :-\)
{.is-info}

Für die Arcade haben Sie **PiFBA**, eine ARM-optimierte Version von FBA, die ein Romset 0.2.96.37 benötigt. **FBNeo** \(ehemals FBAlpha\), **MAME2000** bis **MAME2003plus** laufen ebenfalls sehr gut und viele Spiele sind kompatibel.

Einige **GBA/SNES**-Spiele sowie einige Arkade-Spiele können unter Verzögerungen oder Verlangsamungen leiden. In diesem Fall können Sie versuchen, die Option "Zurückspulen \(rewind\)" in den erweiterten Optionen des Emulators zu deaktivieren.  
Dennoch laufen einige Spiele trotz optimierter Optionen nicht mit voller Geschwindigkeit.

Natürlich empfehle ich nicht, speziell für Computer entwickelte Spiele zu installieren, da sie oft eine Tastatur und/oder Maus zum Starten benötigen.



## 

### Kann ich meinen Pi0 übertakten ?

Leider ist der Raspberry Pi0 nicht einfach zu übertakten. Darüber hinaus enthält die GPi-Kartusche keine Lüftungsöffnungen, damit heiße Luft entweichen kann \(zumindest bei der derzeit verwendeten GPi v1-Box\).

_**Du kannst jedoch immer noch mit den Übertaktungsoptionen spielen, auf eigene Gefahr !**_


>Wenn Ihr GPI nach der Auswahl einer Übertaktungsoption nicht stabil ist, bis zu dem Punkt, an dem Sie die Optionen nicht mehr ändern können, stecken Sie die micro-SD-Karte in Ihren PC und entfernen Sie die Übertaktungslinien aus der Datei`config.txt`
{.is-danger}

Sie können einen kleinen Kupferradiator hinzufügen, wie in der Abbildung unten gezeigt. Seine Dicke sollte 2 mm nicht überschreiten.

![](/migration-images/hardware-kompatibilitat/img_20190616_174526.jpg)



## 

### Wie lange hält die Batterie ?

Die ersten Tests zeigen, dass Sie mit einer vollen Ladung etwa 2 Stunden Spielzeit haben werden.

Denken Sie daran, dass Ihre GPI-Box über einen USB-Anschluss verfügt. Verwenden Sie das USB-Kabel im Auto oder zu Hause.


>Wenn die Rückseite der Kartusche anfängt, sehr heiß zu werden, empfehlen wir, den GPI zu stoppen und kurz abkühlen zu lassen.
{.is-info}



## 

### Wie kann ich meine Spiele scrapen ?

Du kannst den internen scraper für einige Spiele weiterhin verwenden. Aber es ist konfiguriert, um große Dateien zu scrapen, um sie in einer normalen Recalbox anzuzeigen. Die Nutzung auf WIFI kann auch langsam und ineffizient sein.

_**Wir empfehlen dringend, einen externen scraper zu verwenden.**_ Es wird besser und schneller sein. Sie können die maximale Bildgröße auch auf 170x170 einstellen, um Platz zu sparen und die Geschwindigkeit für EmulationStation zu erhöhen.



## Fehlerbehebung

## 

Wenn Sie sich in einer der folgenden Situationen befinden :

* Beim ersten Start ist auch nach einer kurzen Wartezeit nichts auf dem Bildschirm zu sehen 
* Sie können das WIFI nicht konfigurieren



Kontaktieren Sie uns auf dem Discord-Server oder im Forum und geben Sie uns die folgenden Dateien \(verfügbar in der BOOT-Partition Ihrer micro-SD-Karte\) :

* `config.txt` 
* `recalbox-backup.conf`  
* `hardware.log`


>**Hinweis :**  
>Bei anderen Problemen verwenden Sie die grundlegenden Methoden :  
>[Forum](https://forum.recalbox.com/category/22/deutsch) ou [Gitlab issues](https://gitlab.com/recalbox/recalbox/issues)
{.is-warning}



