---
title: Überprüfen Sie Geometrien auf Gleichheit
linktitle: Überprüfen Sie Geometrien auf Gleichheit
second_title: Aspose.GIS .NET-API
description: Erfahren Sie in diesem umfassenden Tutorial, wie Sie mit Aspose.GIS für .NET Geometrien in Ihren .NET-Anwendungen auf Gleichheit prüfen.
type: docs
weight: 10
url: /de/net/geometry-analysis/check-geometries-for-equality/
---
## Einführung
Aspose.GIS für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, effizient mit Geodaten in ihren .NET-Anwendungen zu arbeiten. Ganz gleich, ob Sie Kartierungsanwendungen oder räumliche Analysetools erstellen oder Geodatenfunktionen in bestehende Software integrieren, Aspose.GIS bietet die Tools, die Sie für die Erledigung Ihrer Aufgabe benötigen.
## Voraussetzungen
Bevor Sie mit der Verwendung von Aspose.GIS für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### .NET Framework installiert
Stellen Sie sicher, dass das .NET Framework auf Ihrem System installiert ist. Sie können es von der Microsoft-Website herunterladen.
### Aspose.GIS für .NET-Bibliothek
 Laden Sie die Aspose.GIS für .NET-Bibliothek von herunter und installieren Sie sie[Download-Seite](https://releases.aspose.com/gis/net/). Befolgen Sie die Installationsanweisungen in der Dokumentation.
### Entwicklungsumgebung
Richten Sie Ihre bevorzugte Entwicklungsumgebung, z. B. Visual Studio, für die .NET-Entwicklung ein.

## Namespaces importieren
Importieren Sie in Ihrer .NET-Anwendung die erforderlichen Namespaces, um die Aspose.GIS-Funktionalität zu nutzen:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Geometrien definieren
Definieren Sie zunächst die Geometrien, die Sie vergleichen möchten. In diesem Beispiel haben wir zwei Geometrien:`geometry1` Und`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Schritt 2: Überprüfen Sie die Geometrien auf Gleichheit
 Überprüfen Sie nun, ob die Geometrien räumlich gleich sind`SpatiallyEquals` von Aspose.GIS bereitgestellte Methode.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // WAHR
```
 Dies wird gedruckt`True` zur Konsole seitdem`geometry1` Und`geometry2` sind räumlich gleich.
## Schritt 3: Geometrie ändern
 Als nächstes ändern wir es`geometry2` durch Hinzufügen eines neuen Punktes.
```csharp
geometry2.AddPoint(3, 3);
```
## Schritt 4: Überprüfen Sie die Gleichheit erneut
Überprüfen Sie nun noch einmal die Gleichheit der Geometrien nach der Änderung.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // FALSCH
```
 Diesmal wird die Ausgabe sein`False` da die Geometrien durch die vorgenommene Modifikation nicht mehr räumlich gleich sind`geometry2`.

## Abschluss
Zusammenfassend stellt Aspose.GIS für .NET leistungsstarke Tools für die Arbeit mit Geodaten in .NET-Anwendungen bereit. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie Geometrien mit Aspose.GIS-Methoden ganz einfach auf Gleichheit prüfen.
## FAQs
### Kann ich Aspose.GIS für .NET mit anderen .NET-Frameworks verwenden?
Ja, Aspose.GIS für .NET ist mit verschiedenen .NET-Frameworks kompatibel, einschließlich .NET Core und .NET Standard.
### Gibt es eine kostenlose Testversion für Aspose.GIS für .NET?
 Ja, Sie können eine kostenlose Testversion herunterladen[Veröffentlichungsseite](https://releases.aspose.com/).
### Wo finde ich Dokumentation für Aspose.GIS für .NET?
 Eine ausführliche Dokumentation finden Sie auf der[Aspose.GIS-Dokumentationsseite](https://reference.aspose.com/gis/net/).
### Wie erhalte ich Unterstützung für Aspose.GIS für .NET?
 Unterstützung erhalten Sie im Aspose.GIS-Community-Forum[Hier](https://forum.aspose.com/c/gis/33).
### Kann ich eine temporäre Lizenz für Aspose.GIS für .NET erwerben?
 Ja, Sie können eine temporäre Lizenz bei erwerben[Kaufseite](https://purchase.aspose.com/temporary-license/).