---
date: 2025-12-11
description: Erfahren Sie, wie Sie Koordinaten mit Aspose.GIS für .NET in DMS konvertieren.
  Enthält C#‑Beispiele, c# convert latitude longitude und eine Schritt‑für‑Schritt‑Anleitung.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Koordinaten in DMS umwandeln mit Aspose.GIS für .NET
url: /de/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Koordinaten in DMS umwandeln mit Aspose.GIS

## Einleitung
In diesem Tutorial erfahren Sie, wie Sie **Koordinaten in DMS** (Grad, Minuten, Sekunden) mit der leistungsstarken Aspose.GIS‑Bibliothek für .NET konvertieren. Egal, ob Sie c# latitude longitude für Mapping‑Anwendungen umwandeln, menschenlesbare Standort‑Strings erzeugen oder einfach verschiedene Koordinatenformate erkunden möchten – dieser Leitfaden führt Sie Schritt für Schritt mit klaren Erklärungen und sofort ausführbarem C#‑Code.

## Schnelle Antworten
- **Was bedeutet „Koordinaten in DMS umwandeln“?** Es wandelt numerische Breiten‑/Längengradwerte in die traditionelle Grad‑Minute‑Sekunden‑Notation um.  
- **Welche Bibliothek übernimmt die Umwandlung?** Aspose.GIS für .NET stellt die `GeoConvert`‑Klasse mit integrierter Formatunterstützung bereit.  
- **Benötige ich eine Lizenz, um es auszuprobieren?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, und .NET 5/6+.  
- **Kann ich denselben Code für andere Formate verwenden?** Ja – ändern Sie einfach den `PointFormats`‑Enum‑Wert (z. B. `DecimalDegrees`, `GeoRef`).  

## Was ist die Koordinatenumwandlung in DMS?
Die Umwandlung von Koordinaten in DMS schreibt Dezimal‑Breiten‑ und Längengradwerte in ein Format wie `25°30'00"N 45°30'00"E` um. Diese Darstellung wird in der Kartografie, Navigation und beim GIS‑Datenaustausch häufig verwendet.

## Warum Aspose.GIS für die Koordinatenumwandlung verwenden?
- **All‑in‑One‑API** – Keine externen Bibliotheken oder komplexe Mathematik; Aspose.GIS übernimmt das Parsen und Formatieren intern.  
- **Hohe Genauigkeit** – Präzise Handhabung von Randfällen wie negativen Werten und hemisphärischen Bezeichnern.  
- **Plattformübergreifend** – Funktioniert gleich auf Windows-, Linux- und macOS‑.NET‑Laufzeiten.  
- **Erweiterbar** – Einfaches Umschalten zwischen DMS, Dezimalgrad, Grad‑Dezimal‑Minuten und GeoRef‑Formaten.  

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie:

1. **Grundkenntnisse in C#** – Vertrautheit mit Variablen, Methodenaufrufen und Konsolenausgabe.  
2. **Aspose.GIS installiert** – Laden Sie das neueste Paket von der [Aspose.GIS‑Website](https://releases.aspose.com/gis/net/) herunter.  

## Namespaces importieren
Importieren Sie zunächst die für GIS‑Operationen erforderlichen Namespaces:

```csharp
using System;
using Aspose.Gis;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Starten des Umwandlungsprozesses
Wir geben eine freundliche Meldung aus, damit Sie wissen, dass das Demo begonnen hat.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Schritt 2: In Dezimalgrad umwandeln  
Obwohl das Endziel DMS ist, zeigen wir zunächst die ursprüngliche Dezimaldarstellung.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Schritt 3: In Grad‑Dezimal‑Minuten umwandeln  
Dieses Format (`DD°MM.m'`) ist ein gängiger Zwischenschritt, wenn Sie *convert lat long degree minutes* benötigen.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Schritt 4: In Grad‑Minute‑Sekunden (DMS) umwandeln  
Hier ist der Kern unseres Tutorials – **Koordinaten in DMS umwandeln**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Schritt 5: In GeoRef umwandeln  
Zur Vollständigkeit demonstrieren wir auch das `GeoRef`‑Format, das in Remote‑Sensing‑Workflows nützlich ist.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Häufige Probleme und Lösungen
- **Falsche Hemisphären‑Buchstaben** – Stellen Sie sicher, dass Sie positive Werte für Nord/Ost und negative für Süd/West übergeben; die API fügt automatisch das korrekte Suffix hinzu.  
- **Unerwartete leere Ausgabe** – Prüfen Sie, ob die `Aspose.Gis`‑Assembly korrekt referenziert ist und das Projekt ein unterstütztes .NET‑Target verwendet.  
- **Lizenz nicht gefunden** – Platzieren Sie Ihre Lizenzdatei im Anwendungsverzeichnis oder setzen Sie sie programmgesteuert mit `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Häufig gestellte Fragen

**Q: Ist Aspose.GIS mit anderen Programmiersprachen kompatibel?**  
A: Aspose.GIS richtet sich primär an .NET‑Entwickler, es gibt jedoch auch eine Java‑Version.

**Q: Kann ich Aspose.GIS vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.GIS über die [Website](https://releases.aspose.com/) erhalten.

**Q: Wie bekomme ich Support für Aspose.GIS?**  
A: Unterstützung finden Sie im Aspose.GIS‑Community‑Forum [hier](https://forum.aspose.com/c/gis/33).

**Q: Gibt es temporäre Lizenzen für Aspose.GIS?**  
A: Ja, temporäre Lizenzen können Sie auf der [temporären Lizenz‑Seite](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Wo kann ich Aspose.GIS kaufen?**  
A: Sie können Aspose.GIS auf der [Kauf‑Seite](https://purchase.aspose.com/buy) erwerben.

## Fazit
Durch Befolgen dieser Schritte wissen Sie jetzt, wie Sie **Koordinaten in DMS** und andere gängige GIS‑Formate mit Aspose.GIS für .NET umwandeln. Diese Fähigkeit ermöglicht es Ihnen, menschenlesbare Standort‑Strings nahtlos in Mapping‑Anwendungen, Berichte oder jede räumliche Daten‑Workflow‑Kette zu integrieren. Experimentieren Sie gern mit verschiedenen Breiten‑/Längengradwerten und erkunden Sie die weiteren Formate, die die `GeoConvert`‑Klasse bietet.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}