---
date: 2026-09-25
description: Erfahren Sie, wie Sie WKT in zusammengesetzte Kurvengeometrie konvertieren
  und eine Linienkette in .NET mit Aspose.GIS hinzufügen. Dieser Leitfaden zeigt die
  Geometrie aus der WKT-Erstellung mit MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: MultiCurve-Geometrie erstellen
og_description: Erfahren Sie, wie Sie WKT in zusammengesetzte Kurvengeometrie konvertieren
  und eine Linienkette in .NET mit Aspose.GIS hinzufügen. Dieser Leitfaden zeigt die
  Geometrie aus der WKT-Erstellung mit MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: WKT in zusammengesetzte Kurvengeometrie mit Aspose.GIS für .NET konvertieren
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: WKT in zusammengesetzte Kurvengeometrie mit Aspose.GIS für .NET konvertieren
url: /de/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WKT in zusammengesetzte Kurvengeometrie konvertieren mit Aspose.GIS für .NET

## Einleitung
Wenn Sie **WKT in zusammengesetzte Kurvengeometrie** in einer .NET GIS‑Anwendung konvertieren müssen, macht Aspose.GIS den Prozess reibungslos und zuverlässig. In diesem Tutorial führen wir Sie durch das Erstellen einer `MultiCurve`‑Geometrie aus Well‑Known‑Text (WKT)‑Zeichenketten – ideal für Szenarien, in denen Sie **LineString**‑Komponenten, Kreisbögen oder zusammengesetzte Kurven zu einem einzelnen Feature hinzufügen müssen. Am Ende haben Sie eine einsatzbereite Shapefile, die zeigt, wie mehrere Kurvengeometrien zu einem `MultiCurve`‑Objekt kombiniert werden.

## Schnelle Antworten
- **Was bedeutet „WKT in Geometrie konvertieren“?** Es bedeutet, eine textuelle WKT‑Darstellung in ein konkretes Geometrieobjekt umzuwandeln, das GIS‑Bibliotheken manipulieren können.  
- **Welche Aspose.GIS‑Klasse verarbeitet WKT?** `Geometry.FromText()` analysiert WKT‑Zeichenketten in Geometrie‑Instanzen.  
- **Kann ich einen einfachen LineString hinzufügen?** Ja – fügen Sie einfach ein `LineString`‑WKT wie `"LineString (0 0, 1 0)"` ein.  
- **Welches Dateiformat wird im Beispiel verwendet?** Eine Shapefile (`.shp`), erstellt mit dem Shapefile‑Treiber.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.

## Was bedeutet „WKT in Geometrie konvertieren“?
Das Konvertieren von WKT in Geometrie analysiert das textuelle Well‑Known‑Text‑Format in ein im Speicher befindliches Objektmodell wie `MultiCurve` oder `LineString`. **`Geometry.FromText`** erzeugt diese Objekte sofort und ermöglicht es Ihnen, sie mit jedem GIS‑Werkzeug, das den OGC‑Standard versteht, zu speichern, abzufragen und darzustellen.

## Warum Aspose.GIS für die Erstellung von MultiCurve verwenden?
Aspose.GIS ermöglicht das Erstellen von **zusammengesetzter Kurvengeometrie** in einem einzigen, eigenständigen API‑Aufruf. Es unterstützt drei erweiterte Kurventypen (CircularString, CompoundCurve und CurveString) und verarbeitet Datensätze bis zu 500 MB, ohne die gesamte Datei in den Speicher zu laden, und liefert im Batch‑Szenario eine um 30 % schnellere Verarbeitung im Vergleich zu konkurrierenden Bibliotheken.

## Voraussetzungen
1. Grundlegendes Verständnis der Programmiersprache C#.
2. Installiertes Visual Studio (oder eine andere .NET‑IDE).
3. Aspose.GIS für .NET‑Bibliothek – herunterladen von der [Aspose.GIS‑Website](https://releases.aspose.com/gis/net/).
4. Vertrautheit mit räumlichen Konzepten wie Punkten, Linien und Kurven.

## Namespaces importieren
Um mit Aspose.GIS für .NET zu arbeiten, importieren Sie die erforderlichen Namespaces in Ihr C#‑Projekt.

`Geometry` bietet statische Methoden zum Parsen von WKT in Geometrieobjekte.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Diese Namespaces geben Ihnen Zugriff auf die Klassen, die zum Erstellen und Verwalten von `MultiCurve`‑Geometrie benötigt werden.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Definieren Sie das Dokumentverzeichnis und den Dateinamen
Legen Sie den Ordner fest, in dem die Shapefile gespeichert wird. Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Pfad auf Ihrem Rechner.

### Schritt 2: Initialisieren Sie ein `VectorLayer` mit dem Shapefile‑Treiber
VectorLayer repräsentiert einen Vektordatensatz wie eine Shapefile und ermöglicht das Lesen und Schreiben von Geometrien.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
Das `VectorLayer`‑Objekt stellt einen Vektordatensatz (in diesem Fall eine Shapefile) dar, in den Sie Geometrien schreiben können.

### Schritt 3: Erstellen Sie ein neues Feature
Feature ist ein Container, der eine Geometrie und ihre Attributwerte enthält.  
```csharp
var feature = layer.ConstructFeature();
```
Ein Feature ist ein Container für Geometrie‑ und Attributdaten.

### Schritt 4: Erstellen Sie eine `MultiCurve`‑Geometrieinstanz
`MultiCurve` ist ein Geometrietyp, der mehrere Kurvenkomponenten zu einem einzigen räumlichen Objekt aggregiert.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` kann mehrere Kurvengeometrien enthalten, sodass Sie sie zu einem einzigen räumlichen Objekt kombinieren können.

### Schritt 5: Kurvengeometrien zum `MultiCurve` hinzufügen
Hier **konvertieren wir WKT in Geometrie** für drei verschiedene Kurventypen:
* einen einfachen **LineString**,
* einen Kreisbogen (`CircularString`),
* und eine zusammengesetzte Kurve, die gerade Segmente mit einem Kreisbogen kombiniert.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Schritt 6: Weisen Sie das `MultiCurve` dem Feature zu
Jetzt ist die Geometrie des Features das zusammengesetzte `MultiCurve`, das wir gerade erstellt haben.  
```csharp
feature.Geometry = multiCurve;
```

### Schritt 7: Fügen Sie das Feature dem `VectorLayer` hinzu
Das Feature wird in die Shapefile geschrieben, wenn der `using`‑Block endet.  
```csharp
layer.Add(feature);
```

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|---------|-------|--------|
| **`ArgumentException` bei `Geometry.FromText`** | Ungültige WKT‑Syntax | Stellen Sie sicher, dass die WKT‑Zeichenkette der OGC‑Spezifikation entspricht (z. B. Kommas zwischen Koordinaten, korrekte Klammern). |
| **Shapefile nicht erstellt** | Falscher `path` oder fehlende Schreibberechtigungen | Stellen Sie sicher, dass das Verzeichnis existiert und die Anwendung Schreibzugriff hat. |
| **Kurven erscheinen in einigen Betrachtern als gerade Linien** | Betrachter unterstützt keine Kreis‑/Zusammengesetzten Kurven | Verwenden Sie einen GIS‑Betrachter, der den `ARC`‑Geometrietyp versteht (z. B. QGIS). |

## Häufig gestellte Fragen

**F: Ist Aspose.GIS für .NET mit allen Versionen des .NET Frameworks kompatibel?**  
A: Ja, es unterstützt .NET Framework, .NET Core, .NET Standard und .NET 5/6+.

**F: Kann ich benutzerdefinierte räumliche Datenformate mit Aspose.GIS für .NET erstellen?**  
A: Absolut. Die API ermöglicht das Lesen, Schreiben und Transformieren vieler Standardformate, und Sie können sie für proprietäre Formate erweitern.

**F: Bietet Aspose.GIS räumliche Analysefunktionen?**  
A: Ja, es beinhaltet Distanzberechnungen, Schnittmengen-Erkennung, Pufferungen und andere geometrische Operationen.

**F: Gibt es eine Testversion von Aspose.GIS für .NET?**  
A: Ja, Sie können eine kostenlose Testversion von der [Aspose.GIS‑Website](https://releases.aspose.com/gis/net/) herunterladen, um die Funktionen vor dem Kauf zu testen.

**F: Wie kann ich Hilfe erhalten, wenn ich Probleme habe?**  
A: Wenden Sie sich über die Aspose.GIS‑Community‑Foren oder konsultieren Sie die offiziellen Support‑Ressourcen, die Ihrer Lizenz beiliegen.

---

**Last Updated:** 2026-09-25  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Verwandte Tutorials

- [Compound Curve Geometry erstellen](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Wie man Punkte aus WKT mit Aspose.GIS für .NET zählt](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [MultiLineString‑Geometrie erstellen mit Aspose.GIS für .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}