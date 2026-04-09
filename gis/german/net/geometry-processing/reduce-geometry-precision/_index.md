---
date: 2026-04-09
description: Erfahren Sie, wie Sie die Geometriepräzision reduzieren und Z‑Werte mit
  Aspose.GIS für .NET runden, um die GIS‑Leistung zu steigern und Speicher zu sparen.
keywords:
- how to reduce geometry
- how to round z
- geometry precision .NET
linktitle: Geometriepräzision reduzieren
second_title: Aspose.GIS .NET API
title: Wie man die Geometriepräzision reduziert und Z in .NET rundet
url: /de/net/geometry-processing/reduce-geometry-precision/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Geometriepräzision reduziert und Z in .NET rundet

## Einleitung
Wenn Sie mit großen räumlichen Datensätzen arbeiten, haben Sie wahrscheinlich bemerkt, dass jede zusätzliche Dezimalstelle in Ihren Geometriedaten sich summiert – sowohl in der Dateigröße als auch in der Verarbeitungszeit. In diesem Tutorial lernen Sie **wie man die Geometriepräzision reduziert** und **wie man Z rundet** mit Aspose.GIS für .NET. Am Ende des Leitfadens können Sie Geometriedateien verkleinern, räumliche Operationen beschleunigen und Ihren Speicherverbrauch niedrig halten, alles mit ein paar einfachen Methodenaufrufen.

## Schnelle Antworten
- **Was bedeutet „how to round Z“?** Es reduziert die Anzahl der Dezimalstellen der Z‑Koordinate in einem Geometrieobjekt.  
- **Warum die Geometriepräzision reduzieren?** Es verringert die Menge der pro Scheitelpunkt gespeicherten Daten, was räumliche Abfragen beschleunigt und den Speicherverbrauch reduziert.  
- **Welche Bibliothek übernimmt das?** Aspose.GIS für .NET bietet integrierte `RoundZ`‑ und `RoundXY`‑Methoden.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert zum Testen; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich die Anzahl der Dezimalstellen steuern?** Ja, Sie geben die gewünschte Stellenzahl in den `Round*`‑Methoden an.

## Wie man die Geometriepräzision in .NET reduziert
Das Reduzieren der Geometriepräzision ist so einfach wie das Aufrufen von `RoundXY` auf einem beliebigen Geometrieobjekt. Die Methode akzeptiert die Anzahl der Dezimalstellen, die Sie für die X‑ und Y‑Koordinaten beibehalten möchten. Dieser Vorgang ist besonders nützlich, wenn die genaue Sub‑Meter‑Genauigkeit für Ihre Analyse nicht erforderlich ist.

## Wie man Z‑Werte in .NET rundet
Wenn Ihre Daten eine Z‑Komponente (Höhe) enthalten, können Sie `RoundZ` aufrufen, um deren Präzision zu begrenzen. Dies ist der **how to round z**‑Schritt, der häufig die größten Dateigrößenreduktionen für 3‑D‑Datensätze liefert, da Höhenwerte tendenziell viele Dezimalstellen besitzen.

## Was bedeutet „how to round Z“ in GIS?
Das Runden der Z‑Koordinate reduziert überschüssige Dezimalpräzision und wandelt einen Wert wie 3,345 in 3,3 (oder jede von Ihnen definierte Präzision) um. Dieser einfache Vorgang kann Dateigrößen dramatisch verkleinern und Berechnungen beschleunigen, insbesondere wenn die dritte Dimension für Ihre Analyse nicht entscheidend ist.

## Warum die Geometriepräzision mit Aspose.GIS reduzieren?
- **Performance‑Steigerung:** Weniger zu verarbeitende Daten bedeuten schnellere räumliche Abfragen und Transformationen.  
- **Speichereinsparungen:** Kleinere Scheitelpunktdarstellungen geben RAM frei, sodass größere Datensätze im Speicher bleiben können.  
- **Flexibilität:** Sie bestimmen das Präzisionsniveau, das Genauigkeit und Geschwindigkeit ausbalanciert.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Aspose.GIS für .NET Bibliothek: Laden Sie die Bibliothek von der [Aspose.GIS-Website](https://releases.aspose.com/gis/net/) herunter und installieren Sie sie.  
2. Grundkenntnisse in C#‑Programmierung: Vertrautheit mit der Programmiersprache C# ist vorteilhaft.

## Namespaces importieren
Zuerst importieren Sie die erforderlichen Namespaces, um die Aspose.GIS‑Klassen und -Methoden zu verwenden.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Einen Punkt erstellen
Lassen Sie uns beginnen, indem wir einen Punkt mit spezifischen Koordinaten erstellen.

```csharp
Point point = new Point(1.344, 2.345, 3.345, 4.345);
```

## Schritt 2: XY‑Präzision reduzieren
Jetzt reduzieren wir die Präzision der X‑ und Y‑Koordinaten des Punktes auf zwei Dezimalstellen.

```csharp
point.RoundXY(digits: 2);
```

## Schritt 3: Koordinaten anzeigen
Zeigen Sie die aktualisierten Koordinaten des Punktes an.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Schritt 4: Z‑Präzision reduzieren – **how to round z**
Als Nächstes reduzieren wir die Präzision der Z‑Koordinate des Punktes auf eine Dezimalstelle. Dies ist der Kern von **how to round z**.

```csharp
point.RoundZ(digits: 1);
```

## Schritt 5: Aktualisierte Koordinaten anzeigen
Zeigen Sie die aktualisierten Koordinaten des Punktes nach der Reduzierung der Z‑Präzision an.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Schritt 6: Einen LineString erstellen
Jetzt erstellen wir einen `LineString` und fügen ihm Punkte hinzu.

```csharp
LineString line = new LineString();
line.AddPoint(1.2, 2.3);
line.AddPoint(2.4, 3.1);
```

## Schritt 7: XY‑Präzision des LineString reduzieren
Reduzieren Sie die Präzision der X‑ und Y‑Koordinaten des `LineString` auf null Dezimalstellen.

```csharp
line.RoundXY(digits: 0);
```

## Schritt 8: Aktualisierte Koordinaten des LineString anzeigen
Zeigen Sie die aktualisierten Koordinaten des `LineString` nach der Reduzierung der XY‑Präzision an.

```csharp
Console.WriteLine("{0}, {1}", line[0].X, line[0].Y);
Console.WriteLine("{0}, {1}", line[1].X, line[1].Y);
```

## Gemeinsame Anwendungsfälle & Tipps
- **Große Raster‑Vector‑Konvertierungen:** Das Runden von Z kann Zwischendateien der Geometrie verkleinern.  
- **Mobile GIS‑Apps:** Geringere Präzision reduziert die Bandbreite beim Übertragen von Geometrie über das Netzwerk.  
- **Pro‑Tipp:** Wenden Sie `RoundXY` vor `RoundZ` an, um den Workflow konsistent zu halten.

## Häufig gestellte Fragen

**Q: Warum ist die Reduzierung der Geometriepräzision in GIS wichtig?**  
A: Die Reduzierung der Geometriepräzision hilft, den Speicherverbrauch zu optimieren und die Leistung zu verbessern, insbesondere bei großen Datensätzen in GIS‑Anwendungen.

**Q: Beeinflusst die Reduzierung der Geometriepräzision die Genauigkeit?**  
A: Während ein geringfügiger Genauigkeitsverlust entsteht, liefert der Kompromiss oft ein gutes Gleichgewicht zwischen Präzision und Leistung für die meisten räumlichen Analysen.

**Q: Kann ich das Niveau der Präzisionsreduktion in Aspose.GIS für .NET anpassen?**  
A: Ja, Sie können die gewünschte Anzahl von Dezimalstellen für sowohl XY‑ als auch Z‑Koordinaten mit den `RoundXY`‑ und `RoundZ`‑Methoden angeben.

**Q: Gibt es messbare Leistungsvorteile?**  
A: Absolut – weniger Daten pro Scheitelpunkt bedeuten schnellere räumliche Abfragen, reduzierten I/O und geringeren Speicherverbrauch.

**Q: Wo kann ich Unterstützung für Aspose.GIS für .NET erhalten?**  
A: Sie erhalten Unterstützung, indem Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) besuchen oder die Dokumentation [hier](https://reference.aspose.com/gis/net/) aufrufen.

---

**Zuletzt aktualisiert:** 2026-04-09  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}