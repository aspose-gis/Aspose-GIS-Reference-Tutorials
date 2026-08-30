---
date: 2026-08-18
description: Dezimalgrad in DMS mit Aspose.GIS for .NET umwandeln. Dieser Schritt‑für‑Schritt
  C#‑Leitfaden zeigt, wie man Latitude/Longitude, Dezimalgrad in DMS und mehr konvertiert.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Koordinaten umwandeln
og_description: Dezimalgrad‑zu‑DMS‑Konvertierung leicht gemacht mit Aspose.GIS for
  .NET. Lernen Sie, Latitude‑Longitude‑Werte in das DMS‑Format in Minuten zu transformieren.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Wie man Dezimalgrad in DMS mit Aspose.GIS for .NET konvertiert
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Wie man Dezimalgrad in DMS mit Aspose.GIS for .NET konvertiert
url: /de/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Dezimalgrad in DMS mit Aspose.GIS konvertiert

## Einleitung
In diesem Tutorial lernen Sie **wie man Dezimalgrad in DMS konvertiert** mit der leistungsstarken Aspose.GIS Bibliothek für .NET. Egal, ob Sie **c# lat long konvertieren** müssen, menschenlesbare Standort‑Strings für Berichte erzeugen oder einfach verschiedene Koordinatenformate erkunden möchten, führt Sie dieser Leitfaden Schritt für Schritt mit klaren Erklärungen und sofort ausführbaren C#‑Snippets.

## Schnelle Antworten
- **Was bedeutet „Koordinaten in DMS konvertieren“?** Es wandelt numerische Breiten‑/Längengradwerte in die traditionelle Grad‑Minute‑Sekunden‑Notation um.  
- **Welche Bibliothek übernimmt die Konvertierung?** Aspose.GIS für .NET stellt die `GeoConvert`‑Klasse mit integrierter Formatunterstützung bereit.  
- **Benötige ich eine Lizenz, um es auszuprobieren?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6+.  
- **Kann ich denselben Code für andere Formate verwenden?** Ja – ändern Sie einfach den `PointFormats`‑Enum‑Wert (z. B. `DecimalDegrees`, `GeoRef`).  

## Was ist die Koordinatenkonvertierung zu DMS?
Die Konvertierung von Koordinaten zu DMS schreibt dezimale Breiten‑ und Längengradwerte in ein Format wie `25°30'00"N 45°30'00"E` um. Der Vorgang teilt jeden Dezimalgrad in ganze Grad, Minuten (ein Sechzigstel eines Grades) und Sekunden (ein Sechzigstel einer Minute) und fügt anschließend das passende Hemisphären‑Kennzeichen (N, S, E, W) hinzu. Diese menschenlesbare Form ist für viele Altdatenbestände und für die Kommunikation präziser Standorte ohne dezimale Notation unverzichtbar.

## Warum Aspose.GIS für die Koordinatenkonvertierung verwenden?
Aspose.GIS unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann mehrseitige GIS‑Dateien verarbeiten, ohne den gesamten Datensatz in den Speicher zu laden. Die API liefert sub‑millimetergenaue Ergebnisse für Randfälle wie negative Werte und hemisphärische Kennzeichnungen und läuft konsistent auf Windows-, Linux‑ und macOS‑.NET‑Laufzeiten.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Grundkenntnisse in C#** – Vertrautheit mit Variablen, Methodenaufrufen und Konsolenausgabe.  
2. **Aspose.GIS installiert** – Laden Sie das neueste Paket von der [Aspose.GIS-Website](https://releases.aspose.com/gis/net/) herunter. Sie können auch die Hauptseite der Aspose‑Releases unter der [Aspose releases website](https://releases.aspose.com/) erkunden.  

## Namespaces importieren
Zuerst importieren Sie die für GIS‑Operationen erforderlichen Namespaces:
Der Platzhalter für das Importieren von Namespaces bleibt unverändert.

## Schritt‑für‑Schritt‑Anleitung

### Was ist die GeoConvert‑Klasse?
Die `GeoConvert`‑Klasse stellt statische Methoden zum Konvertieren zwischen Koordinatenformaten wie Dezimalgrad, DMS und GeoRef bereit. Sie enthält Überladungen, die rohe numerische Werte oder `Point`‑Objekte akzeptieren und formatierte Zeichenketten oder neue `Point`‑Instanzen zurückgeben. Durch die Behandlung von Randfällen wie negativen Koordinaten und Rundungen stellt die Klasse sicher, dass die Ausgabe den gängigen GIS‑Spezifikationen entspricht und die Integration in jede .NET‑Mapping‑Anwendung vereinfacht.

### Schritt 1: Starten Sie den Konvertierungsprozess
Wir geben eine freundliche Meldung aus, damit Sie wissen, dass die Demo begonnen hat.

```csharp
using System;
using Aspose.Gis;
```

### Schritt 2: In Dezimalgrad konvertieren
Obwohl das Endziel DMS ist, beginnen wir damit, die ursprüngliche Dezimaldarstellung zu zeigen. Dies demonstriert auch den **Dezimalgrad‑zu‑DMS**‑Pfad, dem Sie später folgen werden.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Schritt 3: In Grad‑Dezimal‑Minuten konvertieren
Dieses Format (`DD°MM.m'`) ist ein gängiger Zwischenschritt, wenn Sie **Breiten‑/Längengrad‑Grad‑Minuten konvertieren** müssen.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Schritt 4: In Grad‑Minuten‑Sekunden (DMS) konvertieren
Hier ist der Kern unseres Tutorials — **Koordinaten in DMS konvertieren**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Schritt 5: In GeoRef konvertieren
Der Vollständigkeit halber demonstrieren wir auch das `GeoRef`‑Format, das in Remote‑Sensing‑Arbeitsabläufen nützlich ist.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Häufige Probleme und Lösungen
- **Falsche Hemisphären‑Buchstaben** – Stellen Sie sicher, dass Sie für Nord/Ost positive Werte und für Süd/West negative Werte übergeben; die API fügt automatisch das korrekte Suffix hinzu.  
- **Unerwartete leere Ausgabe** – Prüfen Sie, ob die `Aspose.Gis`‑Assembly korrekt referenziert ist und das Projekt eine unterstützte .NET‑Version anvisiert.  
- **Lizenz nicht gefunden** – Platzieren Sie Ihre Lizenzdatei im Anwendungsverzeichnis oder setzen Sie sie programmgesteuert mit `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Häufig gestellte Fragen

**Q: Ist Aspose.GIS mit anderen Programmiersprachen kompatibel?**  
A: Aspose.GIS richtet sich hauptsächlich an .NET‑Entwickler, aber eine Java‑Version ist ebenfalls verfügbar.

**Q: Kann ich Aspose.GIS vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.GIS über die [Website](https://releases.aspose.com/) erhalten.

**Q: Wie kann ich Support für Aspose.GIS erhalten?**  
A: Sie können Unterstützung im Aspose.GIS‑Community‑Forum [hier](https://forum.aspose.com/c/gis/33) erhalten.

**Q: Gibt es temporäre Lizenzen für Aspose.GIS?**  
A: Ja, temporäre Lizenzen können von der [temporären Lizenzseite](https://purchase.aspose.com/temporary-license/) bezogen werden.

**Q: Wo kann ich Aspose.GIS kaufen?**  
A: Sie können Aspose.GIS über die [Kaufseite](https://purchase.aspose.com/buy) erwerben.

## Fazit
Indem Sie diese Schritte befolgt haben, wissen Sie nun, wie Sie **Dezimalgrad in DMS konvertieren** und andere gängige GIS‑Formate mit Aspose.GIS für .NET verwenden. Diese Fähigkeit ermöglicht es Ihnen, menschenlesbare Standort‑Strings nahtlos in Mapping‑Anwendungen, Berichte oder jeden räumlichen Daten‑Workflow zu integrieren. Experimentieren Sie gern mit verschiedenen Breiten‑/Längengradwerten und erkunden Sie die weiteren Formate, die die `GeoConvert`‑Klasse bietet.

---

**Zuletzt aktualisiert:** 2026-08-18  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Verwandte Tutorials

- [Wie man Punktgeometrie erstellt und Geometrietyp abruft mit Aspose.GIS für .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Wie man GeoJSON konvertiert – Aspose.GIS für .NET](/gis/net/geo-data-conversion/)
- [MultiPoint-Geometrie in .NET mit Aspose.GIS erstellen](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}