---
date: 2026-02-13
description: Erfahren Sie, wie Sie Koordinaten mit Aspose.GIS für .NET in DMS umwandeln.
  Dieser Schritt‑für‑Schritt‑C#‑Leitfaden zeigt, wie man in C# Breitengrad und Längengrad,
  Dezimalgrad in DMS und mehr konvertiert.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Wie man Koordinaten mit Aspose.GIS für .NET in DMS umwandelt
url: /de/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Koordinaten in DMS mit Aspose.GIS konvertiert

## Einleitung
In diesem Tutorial lernen Sie **wie man Koordinaten konvertiert** in DMS (Grad, Minuten, Sekunden) mit der leistungsstarken Aspose.GIS Bibliothek für .NET. Egal, ob Sie **c# convert lat long** benötigen, menschenlesbare Standort‑Strings erzeugen oder einfach verschiedene Koordinatenformate erkunden möchten, führt Sie dieser Leitfaden Schritt für Schritt mit klaren Erklärungen und sofort ausführbarem C#‑Code.

## Schnelle Antworten
- **Was bedeutet “convert coordinates to DMS”?** Es wandelt numerische Breitengrad-/Längengrad‑Werte in die traditionelle Grad‑Minute‑Sekunden‑Notation um.  
- **Welche Bibliothek übernimmt die Konvertierung?** Aspose.GIS für .NET stellt die `GeoConvert`‑Klasse mit integrierter Formatunterstützung bereit.  
- **Benötige ich eine Lizenz, um es auszuprobieren?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6+.  
- **Kann ich denselben Code für andere Formate verwenden?** Ja – ändern Sie einfach den `PointFormats`‑Enum‑Wert (z. B. `DecimalDegrees`, `GeoRef`).  

## Wie man Koordinaten in DMS konvertiert
Bevor wir in den Code eintauchen, klären wir, warum DMS nach wie vor wertvoll ist. Kartografen, Piloten und viele GIS‑Datenanbieter setzen auf DMS, weil es benutzerfreundlich ist und zu traditionellen Karten passt. Aspose.GIS eliminiert die Notwendigkeit manueller Berechnungen, sodass Sie sich auf die Logik Ihrer Anwendung konzentrieren können.

## Was ist die Koordinatenkonvertierung zu DMS?
Die Konvertierung von Koordinaten zu DMS schreibt dezimale Breitengrad‑ und Längengradwerte in ein Format wie `25°30'00"N 45°30'00"E` um. Diese Darstellung wird in der Kartografie, Navigation und beim GIS‑Datenaustausch häufig verwendet.

## Warum Aspose.GIS für die Koordinatenkonvertierung verwenden?
- **All‑in‑one‑API** – Keine externen Bibliotheken oder komplexe Mathematik; Aspose.GIS übernimmt das Parsen und Formatieren intern.  
- **Hohe Genauigkeit** – Präzise Handhabung von Randfällen wie negativen Werten und hemisphärischen Bezeichnern.  
- **Plattformübergreifend** – Funktioniert identisch auf Windows-, Linux- und macOS‑.NET‑Runtimes.  
- **Erweiterbar** – Einfaches Umschalten zwischen DMS, Dezimalgrad, Grad‑Dezimal‑Minuten und GeoRef‑Formaten.  

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie Folgendes haben:

1. **Grundkenntnisse in C#** – Vertrautheit mit Variablen, Methodenaufrufen und Konsolenausgabe.  
2. **Aspose.GIS installiert** – Laden Sie das neueste Paket von der [Aspose.GIS‑Website](https://releases.aspose.com/gis/net/) herunter.  

## Namespaces importieren
Importieren Sie zunächst die für GIS‑Operationen erforderlichen Namespaces:

```csharp
using System;
using Aspose.Gis;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Starten des Konvertierungsprozesses
Wir geben eine freundliche Meldung aus, damit Sie wissen, dass die Demo begonnen hat.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Schritt 2: In Dezimalgrad konvertieren  
Obwohl das Endziel DMS ist, beginnen wir mit der Anzeige der ursprünglichen Dezimaldarstellung. Dies demonstriert auch den Pfad **decimal degrees to dms**, dem Sie später folgen werden.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Schritt 3: In Grad‑Dezimal‑Minuten konvertieren  
Dieses Format (`DD°MM.m'`) ist ein gängiger Zwischenschritt, wenn Sie *convert lat long degree minutes* benötigen.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Schritt 4: In Grad‑Minuten‑Sekunden (DMS) konvertieren  
Hier ist der Kern unseres Tutorials – **convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Schritt 5: In GeoRef konvertieren  
Der Vollständigkeit halber zeigen wir auch das `GeoRef`‑Format, das in Remote‑Sensing‑Workflows nützlich ist.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Häufige Probleme und Lösungen
- **Falsche Hemisphären‑Buchstaben** – Stellen Sie sicher, dass Sie positive Werte für Nord/Ost und negative für Süd/West übergeben; die API fügt automatisch das korrekte Suffix hinzu.  
- **Unerwartete leere Ausgabe** – Überprüfen Sie, ob die `Aspose.Gis`‑Assembly korrekt referenziert ist und das Projekt eine unterstützte .NET‑Version targetiert.  
- **Lizenz nicht gefunden** – Legen Sie Ihre Lizenzdatei im Anwendungsverzeichnis ab oder setzen Sie sie programmgesteuert mit `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Häufig gestellte Fragen

**F: Ist Aspose.GIS mit anderen Programmiersprachen kompatibel?**  
A: Aspose.GIS richtet sich hauptsächlich an .NET‑Entwickler, aber eine Java‑Version ist ebenfalls verfügbar.

**F: Kann ich Aspose.GIS vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.GIS über die [Website](https://releases.aspose.com/) erhalten.

**F: Wie kann ich Support für Aspose.GIS erhalten?**  
A: Sie können Hilfe im Aspose.GIS‑Community‑Forum [hier](https://forum.aspose.com/c/gis/33) erhalten.

**F: Gibt es temporäre Lizenzen für Aspose.GIS?**  
A: Ja, temporäre Lizenzen können über die [temporäre Lizenz‑Seite](https://purchase.aspose.com/temporary-license/) bezogen werden.

**F: Wo kann ich Aspose.GIS kaufen?**  
A: Sie können Aspose.GIS über die [Kaufseite](https://purchase.aspose.com/buy) erwerben.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie nun, wie Sie **convert coordinates to DMS** und andere gängige GIS‑Formate mit Aspose.GIS für .NET **konvertieren**. Diese Fähigkeit ermöglicht es Ihnen, menschenlesbare Standort‑Strings nahtlos in Kartenanwendungen, Berichte oder jeden räumlichen Daten‑Workflow zu integrieren. Experimentieren Sie gern mit verschiedenen Breitengrad‑/Längengrad‑Werten und erkunden Sie die anderen von der `GeoConvert`‑Klasse angebotenen Formate.

---

**Zuletzt aktualisiert:** 2026-02-13  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}