---
title: Übersetzung im Spiel \(Retroarch AI\)
description: Übersetze deine Spiele live !
---

# Übersetzung im Spiel \(Retroarch AI\)

## Retroarch Ai, was ist das?

Willkommen in der Zukunft !

RetroArch bietet seit einiger Zeit einen Übersetzungsservice namens "OCR" auf English \(Optische Zeichenerkennung\) und **Sprachsynthese** an, mit dem Sie Ihre ausländischen Spiele fast sofort übersetzen können !


>Diese Funktion erfordert eine Internetverbindung !
{.is-danger}

![Vorher](/migration-images/fortgeschrittener-benutzer/ocr1.png)

![Nachher](/migration-images/fortgeschrittener-benutzer/ocr2.png)

## Konfiguration :

Wie Sie wissen, wird alles getan, um die Konfiguration dieser Art von Dienst so einfach wie möglich zu gestalten.


>Dieser Dienst erfordert die Registrierung an eine Programmierschnittstelle \(API\).
>
>Recalbox verwendet standardmäßig [Ztranslate.net](https://ztranslate.net/), aber andere Programmierschnittstelles können konfiguriert werden !
{.is-warning}

* Sobald Sie sich registriert und mit der Website verbunden haben, gehen Sie zum Abschnitt Einstellungen \(settings\), um Ihren `API KEY` abzurufen.
* Öffnen Sie Ihre Datei `recalbox.conf`
  * Suche nach der Zeile `;global.translate.apikey=YOUR_API_KEY_HERE`
  * Löschen Sie das `;` am Anfang der Zeile und fügen Sie Ihre `API KEY` anstelle von `YOUR_API_KEY_HERE`ein.


>Recalbox erkennt dann automatisch die Sprache Ihres Spiels und übersetzt sie in die Sprache, die Sie im Hauptmenü eingerichtet haben.
{.is-success}

## Lass uns gehen !

Verwöhnen Sie sich selbst und vergessen Sie die Frustration, ein 100% japanisches Spiel zu beginnen. 😆

* Um die Übersetzung zu aktivieren, ist es einfach :`HOTKEY + ABWÄRTS-LINKS JOYSTICK` , das Spiel wird angehalten und zeigt Ihnen ein Bild mit dem alternativ Text.
* Appuyez à nouveau sur la combinaison de touches "AI-Service" pour reprendre le jeu.

Standardmäßig verwendet Recalbox den Bildmodus anstelle der Sprachsynthese. Um es nutzen zu können, ist eine einfache Konfigurationsüberlastung erforderlich !

