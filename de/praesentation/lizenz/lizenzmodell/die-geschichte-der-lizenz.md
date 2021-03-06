---
title: Die Geschichte der Lizenz
description: 'Vor und nach dem Lizenzwechsel: 27. Oktober 2017'
---

# Die Geschichte der Lizenz

## Alte Lizenz

Bis zur Validierung von 3247e3f2 war Recalbox ein abgeleitetes Projekt von Buildroot.

> Dieses Verzeichnis enthält den Quellcode, der recalboxOS für verschiedene Karten kompiliert.
>
> Recalbox ist ein Open-Source-Projekt. Wir hoffen, dass Sie dazu beitragen und uns helfen werden, dieses Betriebssystem zu verbessern.
>
> Aber wenn Sie an einer Fork \(Abzweigung\) arbeiten, bitten wir Sie aus Respekt vor unserer Arbeit, unsere laufende Arbeit, die sich in anderen Zweigen als dem Hauptzweig befindet, nicht zu integrieren.

> Danke, dass Sie auf eine Fusion mit der Hauptzweig.
>
> Bitte verwenden Sie **Issues** in den entsprechenden Projekten, um einen Fehler zu melden oder ein Feature anzufordern. 

Es wird daher von Buildroot geerbt und ist durch dessen Lizenz geschützt : [GNU General Public License v2.0](https://spdx.org/licenses/GPL-2.0-or-later.html) oder später \(SPDX-Kennung : `GPL-2.0-oder später`\).



### Wie von der Lizenz gefordert, veröffentlicht Recalbox :

* den vollständigen Quellcode des abgeleiteten Werkes, einschließlich der vollständigen Toolkette :

> Vollständiger Quellcode bedeutet den gesamten Quellcode aller darin enthaltenen Module sowie die zugehörigen Schnittstellen-Definitionsdateien und die Skripte, die zur Steuerung der Kompilierung und Installation der ausführbaren Datei verwendet werden.
>
> Quelle : [GNU General Public License v2.0 oder höher](https://spdx.org/licenses/GPL-2.0-or-later.html)

* [Eine Kopie der Lizenz selbst](https://spdx.org/licenses/GPL-2.0-or-later.html) mit dem Quellcode.



### Darüber hinaus veröffentlicht Recalbox, [wie von den Buildroot-Entwicklern vorgeschlagen](https://buildroot.org/downloads/manual/manual.html#legal-info-buildroot), auch :

* den vollständigen Quellcode von Buildroot selbst.

## Licence actuelle

Beginnend mit Validierung [**ed05dff8**](https://gitlab.com/recalbox/recalbox/commit/ed05dff8) \(das ein direkter Abkömmling des oben erwähnten commit [**3247e3f2** ](https://gitlab.com/recalbox/recalbox/commit/3247e3f2d3dc60a926673d54b3dff3604e640763)ist\), haben wir eine [neue benutzerdefinierte Lizenz implementiert](https://gitlab.com/recalbox/recalbox/blob/master/LICENSE.md), die besagt :

> Die Weiterverbreitung und Verwendung des RECALBOX-Codes oder abgeleiteter Werke ist erlaubt, sofern die folgenden Bedingungen erfüllt bzw. eingehalten werden :
>
> * Umverteilungen dürfen nicht ohne Genehmigung verkauft werden, noch dürfen sie in einem Produkt oder einer kommerziellen Aktivität verwendet werden.
> * Redistributionen, die von der ursprünglichen Quelle modifiziert werden, müssen den vollständigen Quellcode enthalten, einschließlich des Quellcodes aller Komponenten, die von einer aus der modifizierten Quelle erstellten Binärdistribution verwendet werden.
> * Weiterverbreitungen müssen den obigen Copyright-Hinweis, diese Liste der Bedingungen und den folgenden Haftungsausschluss in der Dokumentation und/oder anderen Materialien, die mit der Verteilung zur Verfügung gestellt werden, wiedergeben.
>
> DIESE SOFTWARE WIRD VON DEN URHEBERRECHTSINHABERN UND MITARBEITERN "PER SE" ZUR VERFÜGUNG GESTELLT, UND JEGLICHE AUSDRÜCKLICHE ODER IMPLIZITE GEWÄHRLEISTUNG, EINSCHLIESSLICH, ABER NICHT BESCHRÄNKT AUF DIE IMPLIZITE GEWÄHRLEISTUNG DER MARKTGÄNGIGKEIT UND EIGNUNG FÜR EINEN BESTIMMTEN ZWECK, WIRD ABGELEHNT. DER URHEBERRECHTSINHABER ODER DIE MITWIRKENDEN SIND IN KEINEM FALL FÜR DIREKTE, INDIREKTE, ZUFÄLLIGE, BESONDERE, EXEMPLARISCHE ODER FOLGESCHÄDEN HAFTBAR \(EINSCHLIEßLICH, ABER NICHT BESCHRÄNKT AUF DIE BESCHAFFUNG VON ERSATZGÜTERN ODER -DIENSTLEISTUNGEN; NUTZUNGS-, DATEN- ODER GEWINNVERLUST; ODER GESCHÄFTSUNTERBRECHUNG\), UNABHÄNGIG VON DER URSACHE UND NACH JEDER HAFTUNGSTHEORIE, OB VERTRAGLICH, VERSCHULDENSUNABHÄNGIG ODER DELIKTISCH \(EINSCHLIEßLICH FAHRLÄSSIGKEIT ODER ANDERWEITIG\), DIE SICH IN IRGENDEINER WEISE AUS DER NUTZUNG DIESER SOFTWARE ERGIBT, SELBST WENN SIE IM VORAUS AUF DIE MÖGLICHKEIT SOLCHER SCHÄDEN HINGEWIESEN WURDEN.


>**Informationen :**
>
>Obwohl es keine rechtliche Verpflichtung im Rahmen der Lizenz ist, bitten wir jeden, der abgeleitete Werke, modifizierte Versionen oder Fork von Recalbox erstellen möchte, keinen Code zu verwenden, der den `Hauptzweig` noch nicht erreicht hat :
>
>> Wenn Sie an einer Fork arbeiten, bitten wir Sie aus Respekt vor unserer Arbeit, unsere laufenden Arbeiten nicht in andere Zweige als den Hauptzweig zu integrieren. Bitte warten Sie auf eine Zusammenführung auf dem Hauptzweig.  
>> Quelle: unsere [README-Datei](https://gitlab.com/recalbox/recalbox/blob/master/README.md)
{.is-info}

