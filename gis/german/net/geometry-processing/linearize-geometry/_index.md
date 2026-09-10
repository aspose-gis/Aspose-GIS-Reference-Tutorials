---
date: 2026-09-10
description: Erfahren Sie, wie Sie Kurven in Linien (linearize geometry) mit Aspose.GIS
  for .NET konvertieren, um eine effiziente geospatial processing und analysis in
  Ihren .NET‑Apps zu ermöglichen.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Geometrie linearize
og_description: Konvertieren Sie Kurven in Linien (linearize geometry) mit Aspose.GIS
  for .NET. Erfahren Sie step‑by‑step, wie Sie simplify geometries für schnelleres
  rendering und breitere compatibility.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Kurven in Linien konvertieren mit Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Wie man Kurven in Linien mit Aspose.GIS for .NET konvertiert
url: /de/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kurven in Linien umwandeln (Geometrie linearieren) mit Aspose.GIS für .NET

## Einleitung
Wenn Sie **Kurven in Linien umwandeln** müssen für Kartierung, räumliche Analyse oder Datenaustausch‑Aufgaben, bietet Aspose.GIS für .NET eine saubere, programmatische Möglichkeit, dies zu tun. In diesem Tutorial führen wir Sie durch ein vollständiges, praxisnahes Beispiel, das zeigt, wie Sie eine komplexe Geometrie – die Kurven und zusammengesetzte Formen enthält – in eine einfache lineare Darstellung umwandeln, die mit jedem GIS‑System funktioniert.

## Schnelle Antworten
- **Was bedeutet “convert curves to lines”?** Es wandelt gekrümmte Geometrien in gerade Liniensegmente um.  
- **Warum Aspose.GIS wählen?** Die Bibliothek unterstützt über 30 GIS‑Formate und erledigt die Geometrie‑Konvertierung ohne externe Werkzeuge.  
- **Was benötige ich vorher?** .NET Framework oder .NET Core, Visual Studio (oder jede C#‑IDE) und das Aspose.GIS‑NuGet‑Paket.  
- **Wie lange läuft das Beispiel?** Weniger als fünf Minuten, sobald die Bibliothek installiert ist.  
- **Kann ich in andere Formate exportieren?** Absolut – tauschen Sie den KML‑Treiber gegen Shapefile, GeoJSON usw. aus.  
Sie können das vollständige Produktpaket von der [Aspose-Website](https://releases.aspose.com/) herunterladen.

## Was bedeutet convert curves to lines?
Das Umwandeln von Kurven in Linien (auch **linearizing geometry** genannt) ersetzt jedes gekrümmte Segment durch eine Reihe kurzer gerader Linienstücke und erzeugt eine *lineare Geometrie*. Dadurch wird das Rendern bis zu fünfmal schneller, der Speicherverbrauch wird reduziert und die Daten können von Legacy‑GIS‑Diensten verwendet werden, die nur lineare Features akzeptieren.

## Warum Kurven in Linien umwandeln?
Lineare Geometrien rendern und werden abgefragt bis zu **5× schneller** als ihre gekrümmten Gegenstücke, und **über 30 GIS‑Plattformen** akzeptieren nur lineare Features. Das Vereinfachen von Geometrien verkleinert zudem die Dateigröße für webbasierte Vorschauen und ermöglicht Algorithmen – wie Netzwerk‑Analyse oder Clustering –, die gerade Linien als Eingabe benötigen.

## Wie Geometrie linearisiert wird
Verwenden Sie die von Aspose.GIS bereitgestellte Methode `ToLinearGeometry()`. Sie tesselliert automatisch jedes Kurvensegment einer Geometrie in gerade Liniensegmente und behält dabei alle Z‑Werte bei, sodass Sie eine lineare Annäherung erhalten, ohne Höhendaten zu verlieren. Sie können außerdem eine Toleranz angeben, um die maximale Abweichung zwischen der ursprünglichen Kurve und den erzeugten Segmenten zu steuern, wodurch Sie Genauigkeit und Dateigröße ausbalancieren können. Die Methode funktioniert sowohl für 2‑D‑ als auch für 3‑D‑Geometrien.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.GIS for .NET** – laden Sie es von der [Aspose.GIS‑Website](https://releases.aspose.com/gis/net/) herunter.  
2. **.NET Framework** (oder .NET Core) auf Ihrem Entwicklungsrechner installiert.  
3. **Visual Studio** (oder jede C#‑kompatible IDE) zum Schreiben und Ausführen des Beispiels.

## Namespaces importieren
Um die Funktionalität von Aspose.GIS zu nutzen, importieren Sie die erforderlichen Namespaces.

### Kern‑Namespaces von Aspose.GIS
Der Namespace `Aspose.Gis` enthält die Kern‑Geometrieklassen, Treiber und Hilfsprogramme, die für alle GIS‑Operationen benötigt werden.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Treiber für das Zielformat
`Aspose.Gis.Drivers` stellt statische Fabriken für jedes unterstützte Dateiformat bereit; `Drivers.Kml` erzeugt einen KML‑Writer.  
```csharp
using Aspose.GIS.Kml;
```

## Schritt‑für‑Schritt‑Anleitung zum Umwandeln von Kurven in Linien
Im Folgenden finden Sie eine detaillierte Durchgang durch jede Codezeile, die erklärt, **wie man Kurven in Linien umwandelt** und warum jeder Schritt wichtig ist.

### Schritt 1: Ausgabepfad definieren
`Path.Combine` erstellt einen plattformunabhängigen Dateipfad und behandelt Windows‑Backslashes sowie Unix‑Forward‑Slashes automatisch.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Ersetzen Sie `"Your Document Directory"` durch den Ordner, in dem die KML‑Datei gespeichert werden soll.

### Schritt 2: Einen Layer für die Ausgabedatei erstellen
Ein *Layer* gruppiert geografische Features desselben Typs. Hier instanziieren wir einen neuen KML‑Layer, der die linearisierten Geometrien speichert.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Schritt 3: Ein neues Feature erstellen
Ein *Feature* repräsentiert ein einzelnes geografisches Objekt (Punkt, Linie, Polygon usw.). Wir werden unsere lineare Geometrie an dieses Feature anhängen.  
```csharp
var feature = layer.ConstructFeature();
```

### Schritt 4: Die ursprüngliche komplexe Geometrie definieren
`Geometry.FromWkt` parst einen Well‑Known‑Text (WKT)‑String in ein Geometrie‑Objekt. Das Beispiel‑WKT enthält einen `LineString`, einen `CompoundCurve` und einen `CircularString`, um die Kurvenverarbeitung zu demonstrieren.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Schritt 5: Kurven in Linien umwandeln
`ToLinearGeometry()` tesselliert jede Kurve in der Quellgeometrie in gerade Liniensegmente und gibt eine neue lineare Geometrie zurück, die alle Z‑Koordinaten beibehält.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Schritt 6: Die lineare Geometrie dem Feature zuweisen
Die `Geometry`‑Eigenschaft des Features enthält nun die vereinfachte, lineare Version der ursprünglichen Form.  
```csharp
feature.Geometry = linear;
```

### Schritt 7: Das Feature dem Layer hinzufügen
Durch das Hinzufügen des Features zum KML‑Layer wird es zum Schreiben vorgemerkt; wenn der `using`‑Block endet, schreibt der Layer die Daten in die Ausgabedatei.  
```csharp
layer.Add(feature);
```

## Häufige Fallstricke & Pro‑Tipps
- **Pfadtrennzeichen:** Verwenden Sie `Path.Combine`, um Probleme unter Windows vs. Linux zu vermeiden.  
- **Sehr große Geometrien:** Das Linearieren komplexer Formen kann tausende von Scheitelpunkten erzeugen; erwägen Sie, nach der Linearisation `Simplify()` aufzurufen, um die Punktzahl zu reduzieren.  
- **Treiberwahl:** Wenn Sie ein anderes Ausgabeformat benötigen, ersetzen Sie `Drivers.Kml` durch `Drivers.Shapefile`, `Drivers.GeoJson` usw. und passen Sie die Dateierweiterung entsprechend an.  
- **Z‑Werte erhalten:** `ToLinearGeometry()` behält 3‑D‑ (Z‑)Koordinaten bei, sodass Sie keine Höhendaten verlieren.

## Häufig gestellte Fragen (FAQ)

**Q:** Ist Aspose.GIS für .NET mit .NET Core kompatibel?  
**A:** Ja, Aspose.GIS funktioniert mit .NET Core und ermöglicht plattformübergreifende Anwendungen.

**Q:** Kann ich mit verschiedenen GIS‑Dateiformaten mit Aspose.GIS für .NET arbeiten?  
**A:** Absolut! Die Bibliothek unterstützt KML, Shapefile, GeoJSON und viele weitere Formate – über 30 insgesamt.

**Q:** Bietet Aspose.GIS räumliche Operationen und Analysen?  
**A:** Ja, es stellt eine breite Palette räumlicher Funktionen bereit, von Pufferungen bis zu räumlichen Joins.

**Q:** Gibt es eine kostenlose Testversion?  
**A:** Ja, Sie können eine kostenlose Testversion von der [Aspose.GIS‑Website](https://releases.aspose.com/gis/net/) herunterladen.

**Q:** Wo kann ich Hilfe erhalten, wenn ich auf Probleme stoße?  
**A:** Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Community‑ und Support‑Unterstützung.

### Weitere häufige Fragen

**Q:** Kann ich Geometrien, die 3D‑ (Z‑)Koordinaten enthalten, linearieren?  
**A:** Ja, `ToLinearGeometry()` funktioniert sowohl mit 2D‑ als auch mit 3D‑Geometrien; Z‑Werte werden beibehalten.

**Q:** Wie wirkt sich die Linearisation auf die Dateigröße aus?  
**A:** Das Umwandeln von Kurven in viele kurze Liniensegmente kann die Dateigröße erhöhen; führen Sie `Simplify()` nach der Linearisation aus, wenn die Größe ein Problem darstellt.

**Q:** Kann ich die Segmentlänge beim Umwandeln von Kurven in Linien steuern?  
**A:** Die Standardmethode verwendet eine interne Toleranz. Für benutzerdefinierte Segmentierung können Sie Kurven manuell tessellieren, bevor Sie `ToLinearGeometry()` aufrufen.

## Fazit
In diesem Tutorial haben wir **wie man Kurven in Linien umwandelt** (Geometrie linearisiert) mit Aspose.GIS für .NET behandelt, von der Einrichtung der Umgebung bis zum Schreiben des linearisierten Ergebnisses in eine KML‑Datei. Sie können diesen Workflow nun in Kartenanwendungen, Datenverarbeitungspipelines oder jedes GIS‑bezogene Projekt einbetten, das vereinfachte Geometrien erfordert.

---

**Zuletzt aktualisiert:** 2026-09-10  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man GeoJSON mit Toleranz erstellt – Aspose.GIS für .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Polygon in Linie umwandeln mit Aspose.GIS für .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Erfahren Sie, wie man LineString‑Geometrie erstellt – Aspose.GIS für .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}