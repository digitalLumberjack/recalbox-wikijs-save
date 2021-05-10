---
title: Update
---

# Update

## Aktualisierungsprozess

## 


>**Information :**
>
>Hier sind die **Möglichkeiten**, Recalbox **zu aktualisieren**. Ich hoffe, dass diese Zusammenfassung Ihnen hilft und Ihnen die Antworten gibt, die Sie suchen.
{.is-info}

### _Überprüfen Sie Ihre Situation_

**Ist es möglich, von recalbox 4.1 auf recalbox 6.0 zu aktualisieren ?**

_**Nein**, es ist nicht möglich, diese sehr alte Version \(mehr als anderthalb Jahre\) auf recalbox 6.0 RCx/Stable zu aktualisieren.  
Eine saubere Installation ist erforderlich. Siehe unten für Anweisungen._

\_\_

**Ist es möglich, von recalbox 18.07.xxxxx auf recalbox 6.0 RCx/Stable zu aktualisieren ?**

_**Nein**, es ist nicht möglich, diese Version auf die neue Version der recalbox 6 zu aktualisieren.  
Eine saubere Installation ist erforderlich. Siehe unten für Anweisungen._

\_\_

**Ist es möglich, von recalbox beta auf recalbox 6.0 RCx/Stable zu aktualisieren ?**

_**Nein**, es ist nicht möglich, diese Version auf die neue Version der recalbox 6 zu aktualisieren.  
Eine saubere Installation ist erforderlich. Siehe unten für Anweisungen._

\_\_

**Ist es möglich, die Recalbox 6 RCx auf die Recalbox 6.0 stable zu aktualisieren** _****_**?**

_**Ja**, es ist möglich, zwischen den verschiedenen Versionen von recalbox 6.0 Release Candidate auf die zukünftige stabile Version zu aktualisieren._

* Stellen Sie sicher, dass Sie immer Festplattenspeicher auf Ihrer Micro-SD haben, wenn Sie Ihre Roms vor dem Update darauf speichern.
* Machen Sie immer ein Backup, bevor Sie das Update durchführen: Sie können nie zu vorsichtig sein.
* Lesen Sie das Changelog, und wenn es Ihnen passt, führen Sie Ihr Update durch.
* Beim Neustart empfehle ich Ihnen, Ihren Controller neu zu konfigurieren.



**Ist es möglich, von recalbox 6.0 auf 6.1 zu aktualisieren ?**

_**Ja**, es ist möglich, von recalbox 6.0 auf 6.1 zu aktualisieren._

* Stellen Sie sicher, dass Sie immer Festplattenspeicher auf Ihrer Micro-SD haben, wenn Sie Ihre Roms vor dem Update darauf speichern.
* Machen Sie immer ein Backup, bevor Sie das Update durchführen: Sie können nie zu vorsichtig sein.
* Lesen Sie das Changelog, und wenn es Ihnen passt, führen Sie Ihr Update durch.
* Beim Neustart empfehle ich Ihnen, Ihren Controller neu zu konfigurieren.



**Ist es möglich, mit der Recalbox 6 RCxxx einen Multiboot mit PINN oder NOOBS durchzuführen ?**

\***Nein**, es ist nicht möglich, einen Multiboot mit den Beta- oder RC-Versionen \(Release Candidate\) von Recalbox durchzuführen, nur wenn :

* recalbox 6 wird in einer stabilen Version sein.
* dass NOOBS zustimmt, uns in seine Liste hinzuzufügen.\*
* Es scheint, dass PINN unserer Entwicklung folgt - Zu testen



**Mein Controller funktioniert in der Emulationstation, aber nicht wenn ich die Emulatoren benutze,  
warum ?**

\*Wir fügen in Emulationen so viele Controllerkonfigurationen wie möglich hinzu, damit Sie durch Emulationen navigieren können, aber für viele von ihnen müssen Sie sie neu konfigurieren, um in Emulatoren zu funktionieren.

* Emulations-Menü \(Start-Taste\)
* Controller-Optionen &gt; Konfigurieren Sie meinen Controller.\*



**Was passiert, wenn ich ein benutzerdefiniertes Design verwende ?**

* Stellen Sie sicher, dass Sie mit den Systemen und Konfigurationsdateien Ihres Designs auf dem neuesten Stand sind.
* Wenden Sie sich an den Autor Ihres Designs oder das Thema Ihres Designs, um zu prüfen, ob eine neue aktualisierte Version verfügbar ist.
* Verwenden Sie ein benutzerdefiniertes Design in 720p auf Raspberry, 1080p Ihr Rpi wird leiden.
* **Wir bieten keinen Support für inoffizielle personalisierte Recalbox-Designs.**
* **Bitte stellen Sie das Standard-Recalbox-Design ein, um Ihre Fehler zu überprüfen, bevor Sie Ihr Problem im Forum veröffentlichen.**



**Was soll ich tun, wenn ich OVERLAYS verwende ?**

* Wenn Sie [Screenscraper ](https://www.screenscraper.fr/index.php?action=changelangue&langue=de&gameid=0&plateforme=0)verwenden, überprüfen Sie, ob die Packs für recalbox 6.0 aktualisiert wurden.
* Wenn Sie Ihre Overlays erstellt haben, hat Retroarch ein neues Seitenverhältnis hinzugefügt, das einige Overlays verschiebt :

  * Test 22 oder 23 auf dieser Linie : 

  `aspect_ratio_index = 21`



**Die Arcaden**

Seit der ersten Beta hat recalbox die Coren der Arcade Emulatoren : mame & fba libretro aktualisiert und weitere Emulatoren hinzugefügt.

Daher ist es notwendig, Ihre Romsets anzupassen :

* die global dat-Dateien befinden sich nun in /bios/mame2003 oder /fba oder /mame2010 oder /advmame
* Um dat übergeordnete Ordner, neogeo übergeordnete Ordner usw... zu erstellen, müssen Sie nur dieses ~~Tutorial datutil.exe~~ verwenden, um sie zu erstellen.
* core libretro Fba libretro : romset 0.2.97.44
* core libretroMame 2003 : romset mame 0.78
* core libretroMame 2010 : romset mame 0.139
* eigenständiger Emulator advanceMame : romset mame 0.106 \(nur für erfahrene Benutzer\)
* Mame 2003-plus : romset 0.78 und höher \([Dokumentation](https://docs.libretro.com/library/mame2003_plus/#Building-romsets-for-MAME-2003-Plus)\) \([Dokumentation zur Erstellung Ihres romsets](https://github.com/libretro/mame2003-plus-libretro/wiki)\)
* [Mame 2003-plus](https://github.com/libretro/mame2003-plus-libretro/blob/master/CHANGELOG.md) ist eine erweiterte Version von mame 2003 mit zusätzlichen Optionen, die nicht in mame 2003 enthalten sind, und zusätzlichen Spielen.
* Lesen Sie die Arcade-Dokumentation.



**Ihr RPI in einer Box**

* für eine gute Belüftung sorgen
* ein gutes Netzkabel
* Wenn Sie technische Probleme haben, nehmen Sie Ihren RPI aus der Box und testen Sie recalbox 6 frei.



## 

### **Unsere Ratschläge :**

* ein Backup Ihrer Recalbox auf Ihrem PC oder einer externen Festplatte haben.
* verwenden Sie ein Wechselmedium \(USB-Stick oder externe Festplatte\), werden Sie schnell verstehen, dass eine Neuinstallation schneller ist.
* einen externen Scrapper verwenden
* Immer 2 Micro-SD 8GB haben ist genug für das System \(eine für die stabile Version, eine andere für Ihre Tests oder Beta-Tests\), daher das Interesse, Ihre Roms auf Wechselmedien zu haben.
* bei Bedarf Kühlkörper oder Lüfter installieren, insbesondere wenn :
  * wenn Sie Ihren CM überfrachten
  * wenn sich Ihre Recalbox in einer Box befindet.



## Starten Sie das Update

## 


>**Information :**  
>  
>Das **Update der Recalbox** ist über das Menü **"Update**" zugänglich, das durch Drücken der **START**-Taste zugänglich ist
{.is-info}

* **Konfigurieren Sie Ihr WLAN** oder **schließen** Sie **ein Netzwerkkabel** an Ihre Recalbox **an**, 
* Wählen Sie "**SYSTEMEINSTELLUNGEN**", 
* Nach "**Recalbox aktualisieren**" 
* Und "**Update starten**". 

Das System **startet** nach dem Update **automatisch neu** !  



>**Achtung :**  
>Wenn Sie eine Version von Recalbox **vor der Version 6.0** verwenden, ist es **nicht möglich,** ein **automatisches** Update durchzuführen.
>
>Sie müssen **eine komplette Installation** durchführen, um von der [neuesten verfügbaren Version](https://archive.recalbox.com/) profitieren zu können.
>
>Fahren Sie also mit diesem Updateprozess fort, um Ihre Einstellungen, Backups, Rom und Bios **nicht zu verlieren**.
{.is-danger}

