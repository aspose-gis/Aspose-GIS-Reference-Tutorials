---
date: 2026-08-24
description: Erfahren Sie, wie Sie gekrümmte Liniengeometrie erstellen und Kurven
  mit Aspose.GIS für .NET hinzufügen, um eine präzise Verarbeitung geospatialer Daten
  zu ermöglichen.
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: Wie man Kurven hinzufügt – Compound Curve Geometry
og_description: Erfahren Sie, wie Sie gekrümmte Liniengeometrie mit Aspose.GIS für
  .NET erstellen. Dieses Tutorial zeigt Schritt für Schritt, wie man Kurven hinzufügt
  und in wenigen Minuten Compound Curves erstellt.
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: Wie man gekrümmte Liniengeometrie mit Aspose.GIS erstellt
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: Wie man gekrümmte Liniengeometrie mit Aspose.GIS erstellt
url: /de/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man gekrümmte Liniengeometrie mit Aspose.GIS erstellt

## Einführung
In diesem Leitfaden entdecken Sie **wie man gekrümmte Liniengeometrie** mit Aspose.GIS für .NET erstellt. Egal, ob Sie interaktive Karten erstellen, räumliche Analysen durchführen oder GIS‑Datensätze generieren, das Beherrschen der Möglichkeit, Kurven hinzuzufügen, ermöglicht es Ihnen, reale Merkmale – wie kurvenreiche Straßen oder mäandernde Flüsse – mit hoher Präzision zu modellieren. Das Tutorial führt Sie durch jeden Schritt, von der Einrichtung des Projekts bis zum Export einer wiederverwendbaren zusammengesetzten Kurvengeometrie.

## Schnelle Antworten
- **Was ist das Hauptziel?** Erstellen Sie eine zusammengesetzte Kurvengeometrie, die gerade Linien und Kreisbögen kombiniert.  
- **Welche Bibliothek wird verwendet?** Aspose.GIS for .NET.  
- **Voraussetzungen?** Visual Studio, installierte Aspose.GIS und ein C#‑Projekt, das .NET 6 oder höher targetiert.  
- **Typische Implementierungszeit?** Etwa 10‑15 Minuten für ein funktionierendes Beispiel.  
- **Unterstütztes Ausgabeformat?** Shapefile (der gleiche Code schreibt auch GeoJSON, KML und weitere Formate).

## Was ist ein zusammengesetzter Kurve?
Eine zusammengesetzte Kurve ist eine einzelne Geometrie, die aus mehreren verbundenen Kurvenkomponenten besteht – geraden `LineString`s und Kreisbögen – die zu einer komplexeren Form zusammengefügt werden. Sie ist ideal, wenn eine einzelne einfache Linie einen Pfad nicht genau darstellen kann, beispielsweise eine Autobahn mit sanften Kurven oder ein Fluss, der einem natürlichen Bogen folgt.

## Warum Aspose.GIS zum Hinzufügen von Kurven verwenden?
Aspose.GIS bietet eine **umfangreiche Geometrie‑API**, die nativ LineStrings, CircularStrings und Compound Curves unterstützt und damit die Notwendigkeit externer GIS‑Bibliotheken eliminiert. Die Bibliothek ist **plattformübergreifend**, funktioniert mit .NET Framework 4.6+, .NET Core 2.0+, und .NET 5/6/7+. Sie **verarbeitet bis zu 500‑seitige Vektordatensätze, ohne die gesamte Datei in den Speicher zu laden**, und liefert schnelle, speichereffiziente Operationen. Der Export ist unkompliziert: Sie können direkt in Shapefile, GeoJSON, KML, GML und über 30 weitere Formate schreiben.

## Warum das wichtig ist
Das Hinzufügen von Kurven ermöglicht es Ihnen, reale Merkmale genauer zu modellieren, was die visuelle Qualität von Kartenrenderings verbessert und die Präzision bei räumlichen Analysen wie Nähe‑Suchen oder Netzwerk‑Routing erhöht. Das Beherrschen von **wie man gekrümmte Liniengeometrie erstellt** erhöht daher die Treue jeder GIS‑basierten .NET‑Lösung.

## Häufige Anwendungsfälle
- **Verkehrsnetze:** Modellieren Sie Autobahnen, Eisenbahnen oder Radwege mit sanften Kurven.  
- **Hydrologie:** Stellen Sie Flussverläufe dar, die natürlichen Bögen folgen.  
- **Stadtplanung:** Zeichnen Sie Grundstücksgrenzen, die gekrümmte Abschnitte enthalten.  
- **Benutzerdefinierte Symbole:** Erstellen Sie dekorative oder schematische Formen für Kartenlegenden.

## Voraussetzungen
- Visual Studio (jede aktuelle Ausgabe).  
- Aspose.GIS für .NET, heruntergeladen von der [Download‑Seite](https://releases.aspose.com/gis/net/).  
- Ein C#‑Projekt, das .NET 6 (oder eine unterstützte Version) targetiert.

## Namespaces importieren
Die `using`‑Direktiven bringen die erforderlichen Aspose.GIS‑Typen in den Gültigkeitsbereich.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt‑für‑Schritt‑Anleitung zum Erstellen einer zusammengesetzten Kurvengeometrie

### Schritt 1: Ausgabepfad festlegen
Zuerst geben Sie an, wo die resultierende Shapefile gespeichert werden soll. Ersetzen Sie den Platzhalter durch einen gültigen Ordner auf Ihrem Rechner.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Schritt 2: Vektorlayer erstellen
`VectorLayer` stellt einen räumlichen Layer dar, der Features und deren Geometrien innerhalb eines GIS‑Datensatzes enthält. Der `using`‑Block sorgt dafür, dass die Datei nach dem Schreiben ordnungsgemäß geschlossen wird.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Schritt 3: Das Compound‑Curve‑Feature konstruieren
Die Klasse `CompoundCurve` ist Aspose.GIS‑oberstes Objekt für eine Geometrie, die aus mehreren verbundenen Kurvenabschnitten besteht. Hier erzeugen wir eine leere Compound‑Curve, die später einzelne Komponenten erhalten wird.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Schritt 4: Komponenten‑Kurven definieren
Wir bereiten fünf Stücke vor – zwei gerade `LineString`s, zwei `CircularString`‑Bögen und einen abschließenden `LineString`. `LineString` steht für eine einfache gerade Linie, die durch eine geordnete Liste von Punkten definiert ist. `CircularString` ist Aspose.GIS‑Darstellung eines Kreisbogens, definiert durch drei Punkte (Start, Mitte, Ende), die auf demselben Kreis liegen.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Schritt 5: Komponenten‑Kurven zur Compound‑Curve hinzufügen
Jede Komponente wird in Reihenfolge angehängt, wobei Kontinuität und Orientierung erhalten bleiben. Die Methode `Add` prüft automatisch, dass der Endpunkt eines Segments mit dem Startpunkt des nächsten übereinstimmt.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Schritt 6: Geometrie dem Feature zuweisen
Jetzt wird die zusammengefügte `CompoundCurve` zur Geometrie des Features, das wir im Layer speichern werden.

```csharp
feature.Geometry = compoundCurve;
```

### Schritt 7: Das Feature dem Layer hinzufügen
Abschließend schreiben wir das Feature in die Shapefile. Wenn der `using`‑Block endet, wird die Datei geschlossen und ist bereit für die Verwendung in jeder GIS‑Anwendung.

```csharp
layer.Add(feature);
```

## Häufige Probleme & Tipps
- **Koordinatenreihenfolge:** Aspose.GIS erwartet Koordinaten in `X Y`‑Reihenfolge (Länge, Breite). Das Vertauschen der Reihenfolge kehrt die Geometrie um.  
- **CircularString‑Syntax:** Der Mittelpunkt muss auf dem gewünschten Bogen liegen; andernfalls kollabiert die Kurve zu einer geraden Linie.  
- **Datei‑Überschreiben:** `VectorLayer.Create` überschreibt eine vorhandene Shapefile ohne Warnung – verwenden Sie während der Entwicklung einen eindeutigen Dateinamen.  
- **Leistung:** Bei großen Datensätzen sollten Sie Features stapelweise hinzufügen, anstatt sie einzeln im `using`‑Block einzufügen.  
- **Pro‑Tipp:** Verwenden Sie dieselbe `CompoundCurve`‑Instanz wieder, wenn Sie viele ähnliche Features erstellen; rufen Sie `compoundCurve.Clear()` auf, bevor Sie sie neu befüllen, um Speicherzuweisungen zu reduzieren.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.GIS für .NET mit anderen .NET‑Frameworks verwenden?**  
A: Ja, Aspose.GIS funktioniert mit .NET Framework, .NET Core und .NET Standard und unterstützt Versionen von 4.6 bis .NET 7.

**Q: Unterstützt Aspose.GIS das Lesen und Schreiben verschiedener geospatialer Dateiformate?**  
A: Absolut. Es liest und schreibt Shapefile, GeoJSON, KML, GML und mehr als 30 weitere Formate.

**Q: Ist Aspose.GIS für Desktop‑ und Web‑Anwendungen geeignet?**  
A: Ja, die Bibliothek kann in Desktop-, Web‑ und Cloud‑Diensten verwendet werden, ohne plattformspezifische Abhängigkeiten.

**Q: Kann ich räumliche Analysen mit Aspose.GIS für .NET durchführen?**  
A: Ja, Sie können Entfernungen berechnen, geometrische Operationen ausführen und räumliche Abfragen direkt auf den Geometrien durchführen.

**Q: Wo kann ich Community‑Hilfe für Aspose.GIS erhalten?**  
A: Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33), um Fragen zu stellen und Ideen mit anderen Entwicklern zu teilen.

---

**Zuletzt aktualisiert:** 2026-08-24  
**Getestet mit:** Aspose.GIS for .NET (latest stable release)  
**Autor:** Aspose

## Verwandte Tutorials

- [Vektorlayer & Circular String in Aspose.GIS für .NET erstellen](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Vektorlayer und Kurvenpolygon mit Aspose.GIS erstellen](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [WKT in Geometrie konvertieren: MultiCurve mit Aspose.GIS .NET](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}