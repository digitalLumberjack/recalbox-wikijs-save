---
title: Anzeige von Systemen
description: Bedienung und Änderungen an der Systemsanzeige. (Recalbox v6.1 und höher)
---

# Anzeige von Systemen

## Wie das Display funktioniert

Die Anzeige der Systeme im Recalbox-Menü wird über die Datei _« es\_systems.cfg »_ verwaltet. Diese Datei befindet sich im Ordner :


>./recalbox/**share\_init**/system/.emulationstation/es\_systems.cfg
{.is-info}

Es enthält die Namen der verschiedenen Systeme, die von Ihrer Version von Recalbox unterstützt werden. Es ist wie folgt aufgebaut :

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Panasonic 3DO</fullname>
    <name>3do</name>
    <path>/recalbox/share/roms/3do</path>
    <extension>.iso .ISO .cue .CUE .chd .CHD</extension>
    <command>python /usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc %CONTROLLERSCONFIG% -system %SYSTEM% -rom %ROM% -emulator %EMULATOR% -core %CORE% -ratio %RATIO% %NETPLAY%</command>
    <platform>3do</platform>
    <theme>3do</theme>
    <emulators>
      <emulator name="libretro">
        <cores>
          <core>4do</core>
        </cores>
      </emulator>
    </emulators>
  </system>
  <system>
      [. . .]
  </system>
  [. . .]
</systemList>
```

Die Systeme werden in der Reihenfolge angezeigt, in der sie in dieser Datei aufgeführt sind. Es enthält auch die Konfiguration dieser Systeme.

## Ändern der Anzeigereihenfolge


>**WICHTIG** : Ändern Sie **NICHT** die ursprüngliche Datei _« es\_systems.cfg »_ \(die sich im Verzeichnis _«_ share\_init _»_ befindet\). Im Falle eines Problems mit den später vorgenommenen Änderungen bleibt es die einzige Ursprung, warum Recalbox korrekt funktioniert.
{.is-danger}

Die Reihenfolge der Anzeige darf nur aus der Datei _« es\_systems.cfg »_ geändert werden, die sich im folgenden Verzeichnis befindet :


>./recalbox/**share**/system/.emulationstation/es\_systems.cfg
{.is-info}

**Ursprünglich existiert diese Datei nicht.** Es ist notwendig, entweder die Originaldatei zu kopieren oder eine neue Datei zu erstellen. Nach der Erstellung der neuen Datei ist es möglich, die Systeme in die gewünschte Reihenfolge zu bringen. Die Konfiguration der verschiedenen Systeme wird immer aus der ursprünglichen _« es\_systems.cfg »_ übernommen, aber die Reihenfolge der Systeme entspricht der in der neuen Datei definierten.

Wenn in der neuen Datei ein System fehlt oder falsch ausgefüllt ist, wird der Originaldatei Priorität eingeräumt. Für die neue Datei gibt es nur 2 Unterscheidungsmerkmale, die obligatorisch sind : _**« fullname »**_ und _**« platform »**_, alle anderen sind optional. Die Datei muss mindestens wie folgt aufgebaut sein :

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Nintendo Entertainment System</fullname>
    <platform>nes</platform>
  </system>
  <system>
    <fullname>Family Computer Disk System</fullname>
    <platform>fds</platform>
  </system>
  <system>
    <fullname>Super Nintendo Entertainment System</fullname>
    <platform>snes</platform>
  </system>
  <system>
    <fullname>Satellaview</fullname>
    <platform>satellaview</platform>
  </system> 
    [. . .]
  </system>
  [. . .]
</systemList>
```

## Hinzufügen eines **«** Benutzerdefiniert **»** - Systems


>**WICHTIG** : Ändern Sie **NICHT** die ursprüngliche Datei _« es\_systems.cfg »_ \(die sich im Verzeichnis _«_ share\_init _»_ befindet\). Im Falle eines Problems mit den später vorgenommenen Änderungen bleibt es die einzige Ursprung, warum Recalbox korrekt funktioniert.
>
>Diese Operation erlaubt es Ihnen nicht, einen neuen Emulator zur Recalbox hinzuzufügen, sondern einen neuen Systemeintrag im allgemeinen Auswahlmenü.
>
>Es ist möglich, die Änderung der Reihenfolge der Systeme mit der Hinzufügung eines oder mehrerer benutzerdefiniert-Systeme zu kombinieren.
{.is-danger}

Was die Änderung der Reihenfolge der Systeme betrifft, so darf das Hinzufügen eines _«_ benutzerdefinierten _»_ Systems nur aus der Datei _« es\_systems.cfg »_ erfolgen, die sich im folgenden Verzeichnis befindet :


>./recalbox/**share**/system/.emulationstation/es\_systems.cfg
{.is-info}

**Ursprünglich existiert diese Datei nicht.** Kopieren Sie entweder die Originaldatei oder erstellen Sie eine neue Datei. Nachdem die neue Datei erstellt wurde, ist es nun möglich, ein neues System hinzuzufügen.

Wenn in der neuen Datei ein System falsch ausgefüllt ist, wird der Originaldatei Priorität eingeräumt. Für die neue Datei sind alle Unterscheidungsmerkmale obligatorisch. Um also ein neues System zu erstellen, ist der einfachste Weg, von einem bestehenden System aus zu beginnen \(entsprechend den roms, die Sie einbinden möchten\) und nur das Wesentliche zu ändern :  
- _**« fullname »**_ : Ermöglicht es Ihnen, den Namen des neuen Systems anzugeben.  
_****- **« path »**_ : Ermöglicht es Ihnen, das Verzeichnis anzugeben, das die roms des neuen Systems enthält.  
_****- **« theme »**_ : Ermöglicht es Ihnen, das zu verwendende Design festzulegen. Es ist notwendig, dieses neue Design vorher zu erstellen \(Logo, Hintergrund,...\).  
_****_**Alle anderen Unterscheidungsmerkmale dürfen nicht verändert werden.**

Hier ist ein Beispiel für eine Hinzufügung für ein SNES-basiertes System, das nur übersetzte roms enthält :

```markup
<?xml version="1.0"?>
<systemList>
  <system>
    <fullname>Super Nintendo Fan Trad</fullname>
    <name>snes</name>
    <path>/recalbox/share/roms/snestrad</path>
    <extension>.smc .sfc .SMC .SFC .mgd .MGD .zip .ZIP .7z .7Z</extension>
    <command>python /usr/lib/python2.7/site-packages/configgen/emulatorlauncher.pyc %CONTROLLERSCONFIG% -system %SYSTEM% -rom %ROM% -emulator %EMULATOR% -core %CORE% -ratio %RATIO% %NETPLAY%</command>
    <platform>snes</platform>
    <theme>snestrad</theme>
    <emulators>
      <emulator name="libretro">
        <cores>
          <core>snes9x2005</core>
          <core>snes9x2010</core>
          <core>snes9x2002</core>
        </cores>
      </emulator>
    </emulators>
  </system>
</systemList>
```

