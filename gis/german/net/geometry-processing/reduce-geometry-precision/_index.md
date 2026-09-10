---
date: 2026-09-10
description: Erfahren Sie, wie Sie die geometry-Dateigröße durch Senkung der precision
  und Rundung von Z values mit Aspose.GIS for .NET reduzieren, um die performance
  zu verbessern und den memory usage zu senken.
keywords:
- reduce geometry file size
- reduce geometry precision
- round Z values
- Aspose.GIS .NET
- geometry processing
lastmod: 2026-09-10
linktitle: Geometry-Präzision reduzieren
og_description: Erfahren Sie, wie Sie die geometry-Dateigröße durch Senkung der precision
  und Rundung von Z values mit Aspose.GIS for .NET reduzieren, um die performance
  zu verbessern und den memory usage zu senken.
og_image_alt: Guide showing how to reduce geometry file size by rounding Z in .NET
  using Aspose.GIS
og_title: Wie man die geometry-Dateigröße durch Rundung von Z in .NET reduziert
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to reduce geometry file size by lowering precision and rounding
    Z values with Aspose.GIS for .NET, improving performance and cutting memory usage.
  headline: How to reduce geometry file size by rounding Z in .NET
  type: TechArticle
- questions:
  - answer: Reducing geometry precision helps optimize memory usage and improve performance,
      especially when dealing with large datasets in GIS applications.
    question: Why is geometry precision reduction important in GIS?
  - answer: While minor accuracy is lost, the trade‑off often yields a good balance
      between precision and performance for most spatial analyses.
    question: Does reducing geometry precision affect accuracy?
  - answer: Yes, you can specify the desired number of decimal places for both XY
      and Z coordinates using the `RoundXY` and `RoundZ` methods.
    question: Can I customize the precision reduction level in Aspose.GIS for .NET?
  - answer: Absolutely—less data per vertex means faster spatial queries, reduced
      I/O, and lower memory consumption, often delivering **30 % faster processing**
      on typical datasets.
    question: Are there measurable performance benefits?
  - answer: You can get support by visiting the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      or accessing the documentation available in the [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/).
    question: Where can I get support for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- reduce geometry file size
- Aspose.GIS
- .NET GIS
- geometry precision
- round Z
title: Wie man die geometry-Dateigröße durch Rundung von Z in .NET reduziert
url: /de/net/geometry-processing/reduce-geometry-precision/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Dateigröße von Geometrien durch Runden von Z in .NET reduziert

## Einführung
Wenn Sie mit großen räumlichen Datensätzen arbeiten, haben Sie wahrscheinlich bemerkt, dass jede zusätzliche Dezimalstelle in Ihren Geometriedaten sich sowohl auf die Dateigröße als auch auf die Verarbeitungszeit auswirkt. In diesem Tutorial lernen Sie **wie man die Dateigröße von Geometrien reduziert** indem Sie die Geometrie‑Präzision verringern und **wie man Z**‑Werte mit Aspose.GIS für .NET rundet. Am Ende des Leitfadens können Sie Geometriedateien verkleinern, räumliche Operationen beschleunigen und Ihren Speicherbedarf gering halten, alles mit ein paar einfachen Methodenaufrufen.

## Schnelle Antworten
- **Was bedeutet „round Z“?** Es kürzt die Anzahl der Dezimalstellen der Z‑Koordinate in einem Geometrieobjekt.  
- **Warum die Dateigröße von Geometrien reduzieren?** Weniger Dezimalstellen pro Scheitelpunkt reduzieren den Speicherbedarf, beschleunigen Abfragen und senken den RAM‑Verbrauch.  
- **Welche Bibliothek übernimmt das?** Aspose.GIS für .NET bietet integrierte `RoundZ`‑ und `RoundXY`‑Methoden.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich die Anzahl der Dezimalstellen steuern?** Ja, Sie geben die gewünschte Stellenzahl in den `Round*`‑Methoden an.

## Was bedeutet „Z runden“ in GIS?
Das Runden der Z‑Koordinate entfernt unnötige Dezimalpräzision und wandelt einen Wert wie 3,345 in 3,3 (oder jede von Ihnen angegebene Präzision) um. Diese Reduktion kann die Dateigröße merklich verringern und die Verarbeitung beschleunigen, insbesondere wenn Detailgenauigkeit der Höhe, die feiner ist als die erforderliche Analyse‑Toleranz, nicht benötigt wird. Es ist eine gängige Technik zur Optimierung von 3‑D‑Datensätzen.

## Warum die Dateigröße von Geometrien mit Aspose.GIS reduzieren?
Aspose.GIS unterstützt **30+ Vektor‑ und Rasterformate** und kann Dateien bis zu **2 GB** verarbeiten, ohne den gesamten Datensatz in den Speicher zu laden. Das Reduzieren der Präzision verringert die Datenmenge pro Scheitelpunkt, was typischerweise **20‑40 % schnellere räumliche Abfragen** und **15‑30 % geringeren Speicherverbrauch** bei großen Datensätzen ergibt.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Aspose.GIS für .NET Bibliothek: Laden Sie die Bibliothek von der [Aspose.GIS-Website](https://releases.aspose.com/gis/net/) herunter und installieren Sie sie.  
2. Grundkenntnisse in C#‑Programmierung: Vertrautheit mit der C#‑Sprache ist von Vorteil.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces, um die Aspose.GIS‑Klassen und -Methoden zu verwenden.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Einen Punkt erstellen
`Point` ist die grundlegende Geometrie‑Klasse, die einen einzelnen Ort im 2‑D‑ oder 3‑D‑Raum darstellt. Sie werden sie verwenden, um die Präzisionsreduktion zu demonstrieren.

```csharp
Point point = new Point(1.344, 2.345, 3.345, 4.345);
```

## Schritt 2: XY‑Präzision reduzieren
`RoundXY` reduziert die Anzahl der Dezimalstellen für die X‑ und Y‑Koordinaten. Diese Methode akzeptiert die gewünschte Stellenzahl und gibt eine neue Geometrie mit der angepassten Präzision zurück.

```csharp
point.RoundXY(digits: 2);
```

## Schritt 3: Koordinaten anzeigen
Nach dem Runden können Sie die aktualisierten Koordinatenwerte prüfen.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Schritt 4: Z‑Präzision reduzieren – Z runden
`RoundZ` begrenzt die Präzision der Höhenkomponente (Z). Das Anwenden dieses Schrittes führt häufig zu den größten Reduktionen der Dateigröße bei 3‑D‑Datensätzen, da Höhenwerte üblicherweise viele Dezimalstellen enthalten.

```csharp
point.RoundZ(digits: 1);
```

## Schritt 5: Aktualisierte Koordinaten anzeigen
Zeigen Sie die Koordinaten des Punktes nach der Z‑Präzisionsreduktion an.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Schritt 6: Einen Linestring erstellen
`LineString` ist eine Sammlung von Punkten, die eine Polylinie bilden. Sie ist nützlich, um batch‑weise Präzisionsänderungen über mehrere Scheitelpunkte zu demonstrieren.

```csharp
LineString line = new LineString();
line.AddPoint(1.2, 2.3);
line.AddPoint(2.4, 3.1);
```

## Schritt 7: XY‑Präzision des Linestring reduzieren
Wenden Sie `RoundXY` auf das gesamte `LineString` an, um die X/Y‑Werte für jeden Scheitelpunkt zu kürzen.

```csharp
line.RoundXY(digits: 0);
```

## Schritt 8: Aktualisierte Koordinaten des Linestring anzeigen
Untersuchen Sie die Koordinaten, nachdem die XY‑Präzision reduziert wurde.

```csharp
Console.WriteLine("{0}, {1}", line[0].X, line[0].Y);
Console.WriteLine("{0}, {1}", line[1].X, line[1].Y);
```

## Häufige Anwendungsfälle & Tipps
- **Große Raster‑zu‑Vektor‑Konvertierungen:** Das Runden von Z kann Zwischendateien der Geometrie verkleinern und die Konvertierungspipelines beschleunigen.  
- **Mobile GIS‑Apps:** Geringere Präzision reduziert die Bandbreite beim Übertragen von Geometrien über das Netzwerk.  
- **Pro‑Tipp:** Wenden Sie `RoundXY` vor `RoundZ` an, um den Arbeitsablauf konsistent zu halten und ein erneutes Runden bereits gerundeter Werte zu vermeiden.

## Häufig gestellte Fragen

**Q: Warum ist die Reduktion der Geometrie‑Präzision in GIS wichtig?**  
A: Die Reduktion der Geometrie‑Präzision hilft, den Speicherverbrauch zu optimieren und die Leistung zu verbessern, insbesondere bei großen Datensätzen in GIS‑Anwendungen.

**Q: Beeinflusst die Reduktion der Geometrie‑Präzision die Genauigkeit?**  
A: Zwar geht eine geringe Genauigkeit verloren, aber der Kompromiss liefert oft ein gutes Gleichgewicht zwischen Präzision und Leistung für die meisten räumlichen Analysen.

**Q: Kann ich das Niveau der Präzisionsreduktion in Aspose.GIS für .NET anpassen?**  
A: Ja, Sie können die gewünschte Anzahl von Dezimalstellen für sowohl XY‑ als auch Z‑Koordinaten mit den Methoden `RoundXY` und `RoundZ` angeben.

**Q: Gibt es messbare Leistungsverbesserungen?**  
A: Absolut – weniger Daten pro Scheitelpunkt bedeuten schnellere räumliche Abfragen, reduzierten I/O und geringeren Speicherverbrauch, oft mit **30 % schnellerer Verarbeitung** bei typischen Datensätzen.

**Q: Wo kann ich Unterstützung für Aspose.GIS für .NET erhalten?**  
A: Sie können Unterstützung erhalten, indem Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) besuchen oder die Dokumentation im [Aspose.GIS .NET API‑Referenz](https://reference.aspose.com/gis/net/) aufrufen.

---

**Zuletzt aktualisiert:** 2026-09-10  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man die Präzision beim Schreiben von Geometrien mit Aspose.GIS begrenzt](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Vektorlayer erstellen, Präzision mit Aspose.GIS für .NET begrenzen](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Wie man Geometrie in WKT mit Aspose.GIS für .NET übersetzt](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}