---
date: 2026-08-24
description: Erfahren Sie, wie Sie gekrümmte Linien schreiben und zusammengesetzte
  Kurvengeometrien in .NET mit Aspose.GIS erstellen, um eine präzise geospatiale Datenverarbeitung
  zu ermöglichen.
keywords:
- write curved lines
- how to add curves
- create compound curve
- curve geometry .net
lastmod: 2026-08-24
linktitle: Wie man Kurven hinzufügt – zusammengesetzte Kurvengeometrie
og_description: Schreiben Sie gekrümmte Linien mit Aspose.GIS in .NET, um genaue zusammengesetzte
  Kurvengeometrien zu erstellen. Dieser Leitfaden zeigt Schritt‑für‑Schritt‑Code,
  häufige Stolperfallen und bewährte Tipps für GIS‑Entwickler.
og_image_alt: Developer guide showing how to write curved lines using Aspose.GIS in
  a .NET project
og_title: Gekrümmte Linien mit Aspose.GIS in .NET für GIS-Daten schreiben
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to write curved lines and create compound curve geometries
    in .NET with Aspose.GIS, enabling precise geospatial data processing.
  headline: How to write curved lines using Aspose.GIS in .NET
  type: TechArticle
- description: Learn how to write curved lines and create compound curve geometries
    in .NET with Aspose.GIS, enabling precise geospatial data processing.
  name: How to write curved lines using Aspose.GIS in .NET
  steps:
  - name: define the output path
    text: Replace the placeholder path with a folder that exists on your machine.
  - name: create a vector layer
    text: A **vector layer** stores spatial features. **Definition anchor:** `VectorLayer`
      represents a container for features of a single geometry type and manages reading/writing
      of GIS files.
  - name: construct the compound curve feature
    text: Here we create a new `Feature` and an empty `CompoundCurve` that will hold
      the individual curve parts.
  - name: define component curves
    text: 'A `LineString` is a sequence of points connected by straight line segments.
      A `CircularString` defines a circular arc using three points: start, intermediate,
      and end. We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. **Definition anchor:** `Line'
  - name: add component curves to the compound curve
    text: Append each component in order so the geometry stays continuous and correctly
      oriented.
  - name: assign geometry to the feature
    text: The assembled `CompoundCurve` becomes the geometry of the feature we will
      store.
  - name: add the feature to the layer
    text: Write the feature into the Shapefile. When the `using` block ends, the file
      is closed and ready for any GIS application.
  type: HowTo
- questions:
  - answer: Yes, the library runs on .NET Framework, .NET Core, .NET Standard, and
      .NET 5/6+ without modification.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It handles Shapefile, GeoJSON, KML, GML, and more than 30
      additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the same API works in console apps, Windows services, ASP.NET Core
      web apps, and cloud‑based functions.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, perform geometric unions/intersections,
      and execute spatial queries directly on the geometry objects.
    question: Can I perform spatial analysis with Aspose.GIS?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions, share snippets, and learn from other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- write curved lines
- Aspose.GIS
- compound curve
- .NET GIS
- geospatial programming
title: Wie man gekrümmte Linien mit Aspose.GIS in .NET schreibt
url: /de/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man gekrümmte Linien mit Aspose.GIS in .NET erstellt

## Einleitung
Wenn Sie **gekrümmte Linien** für Karten, Routing oder jede räumliche Analyse benötigen, bietet Aspose.GIS eine saubere, vollständig verwaltete .NET‑API zum Erstellen dieser Geometrien. In diesem Tutorial lernen Sie, wie Sie Kurven hinzufügen, sie zu einer Compound‑Curve zusammenfügen und das Ergebnis als Shapefile (oder ein anderes unterstütztes Format) exportieren. Die Schritte sind schnell, der Code ist unkompliziert und das Ergebnis ist bereit für die Verwendung in jeder GIS‑Anwendung.

## Schnelle Antworten
- **Was ist das Hauptziel?** Gekrümmte Linien schreiben und sie zu einer einzigen Compound‑Curve‑Geometrie bündeln.  
- **Welche Bibliothek erledigt die Aufgabe?** Aspose.GIS für .NET, ein rein verwaltetes GIS‑Toolkit.  
- **Was wird vorher benötigt?** Visual Studio, das Aspose.GIS‑NuGet‑Paket und ein .NET 6‑Projekt (oder neuer).  
- **Wie lange dauert ein einfaches Beispiel?** Etwa 10‑15 Minuten von Anfang bis Ende.  
- **Welche Ausgabeformate werden unterstützt?** Shapefile sofort einsatzbereit; derselbe Code funktioniert für GeoJSON, KML, GML und weitere.

## Was ist eine Compound‑Curve?
Eine **Compound‑Curve** ist eine einzelne Geometrie, die mehrere Kurvenkomponenten – gerade Linienstrings und Kreisbögen – zu einem durchgehenden Pfad verbindet. Sie ermöglicht die Modellierung von Merkmalen wie gewundenen Straßen, Flusskurven oder jedem Feature, das nicht exakt mit einer einfachen Geraden dargestellt werden kann.

## Warum Aspose.GIS zum Schreiben gekrümmter Linien verwenden?
Ein `VectorLayer` stellt einen Container für räumliche Features eines einzelnen Geometrietyps dar und übernimmt die Datei‑I/O für GIS‑Formate.  
Ein `CompoundCurve` ist eine Geometrie, die mehrere Linien‑ und Bogenkomponenten zu einer durchgehenden Form kombiniert.  
Ein `Feature` enthält Geometrie‑ und Attributdaten, die in einem GIS‑Layer gespeichert werden können.  

Aspose.GIS bietet eine umfassende, vollständig verwaltete Geometrie‑API, die Entwicklern das Erstellen und Manipulieren von LineString, CircularString und CompoundCurve ohne externe Abhängigkeiten ermöglicht. Sie abstrahiert die Dateiformat‑Verarbeitung, unterstützt plattformübergreifende .NET‑Laufzeiten und sorgt für leistungsstarke Lese‑/Schreib‑Operationen für GIS‑Daten.

## Warum das wichtig ist
Wenn gekrümmte Geometrien exakt gespeichert werden, können Kartenrenderer sanfte Übergänge darstellen und räumliche Berechnungen wie Länge, Puffer oder Netzwerk‑Analyse zuverlässige Ergebnisse liefern. Das verbessert sowohl die visuelle Treue als auch die analytische Präzision für Anwendungen von Navigationssystemen bis hin zu Umweltmodellierung. Präzise Darstellungen gekrümmter Linien erhöhen die Kartenqualität und ermöglichen genaue räumliche Berechnungen wie Distanzmessung, Netzwerk‑Routing und Nähe‑Analyse. Das Beherrschen des Schreibens gekrümmter Linien steigert die Qualität jeder GIS‑basierten .NET‑Lösung.

## Häufige Anwendungsfälle
- **Verkehrsnetze:** Autobahnen, Eisenbahnen oder Radwege modellieren, die sanfte Kurven enthalten.  
- **Hydrologie:** Flussmäander erfassen, die natürlichen Bögen folgen.  
- **Stadtplanung:** Grundstücksgrenzen mit gekrümmten Abschnitten festlegen.  
- **Benutzerdefinierte Symbole:** Dekorative Formen für Kartenlegenden oder UI‑Overlays erstellen.

## Voraussetzungen
- **Visual Studio** (jede aktuelle Edition).  
- **Aspose.GIS für .NET** – Download von der [download page](https://releases.aspose.com/gis/net/).  
- Ein C#‑Projekt, das **.NET 6** (oder eine unterstützte Version) targetet.

## Namespaces importieren
Die folgenden Namespaces geben Ihnen Zugriff auf die Geometrie‑ und I/O‑Klassen, die Sie benötigen.

**Definition anchor:** `Aspose.Gis` stellt die Kern‑GIS‑Typen bereit; `Aspose.Gis.Geometries` enthält Geometrieklassen wie `LineString` und `CompoundCurve`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie man gekrümmte Linien mit Aspose.GIS schreibt?
Der Vorgang umfasst das Festlegen eines Ausgabeverzeichnisses, das Erstellen eines `VectorLayer`, das Aufbauen einer `CompoundCurve` durch Anhängen von `LineString`‑ und `CircularString`‑Teilen, das Zuweisen der Geometrie zu einem `Feature` und schließlich das Hinzufügen des Features zum Layer. Der `using`‑Block stellt sicher, dass Ressourcen freigegeben und das Shapefile korrekt geschrieben wird.

### Schritt 1: Ausgabepfad definieren
Ersetzen Sie den Platzhalterpfad durch einen Ordner, der auf Ihrem Rechner existiert.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Schritt 2: Einen Vektor‑Layer erstellen
Ein **Vektor‑Layer** speichert räumliche Features.  

**Definition anchor:** `VectorLayer` stellt einen Container für Features eines einzelnen Geometrietyps dar und verwaltet das Lesen/Schreiben von GIS‑Dateien.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Schritt 3: Das Compound‑Curve‑Feature konstruieren
Hier erstellen wir ein neues `Feature` und eine leere `CompoundCurve`, die die einzelnen Kurventeile aufnehmen wird.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Schritt 4: Komponenten‑Kurven definieren
Ein `LineString` ist eine Folge von Punkten, die durch gerade Liniensegmente verbunden sind.  
Ein `CircularString` definiert einen Kreisbogen mit drei Punkten: Start, Zwischennpunkt und Ende.  

Wir bereiten fünf Stücke vor – zwei gerade `LineString`s, zwei `CircularString`‑Bögen und einen abschließenden `LineString`.  

**Definition anchor:** `LineString` ist eine Punktfolge, die eine gerade Linien‑Polylinie bildet, während `CircularString` einen Kreisbogen mit drei Punkten (Start, Zwischennpunkt, Ende) definiert.  

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Schritt 5: Komponenten‑Kurven zur Compound‑Curve hinzufügen
Fügen Sie jede Komponente in der Reihenfolge hinzu, damit die Geometrie durchgehend und korrekt ausgerichtet bleibt.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Schritt 6: Geometrie dem Feature zuweisen
Die zusammengebaute `CompoundCurve` wird zur Geometrie des Features, das wir speichern werden.

```csharp
feature.Geometry = compoundCurve;
```

### Schritt 7: Das Feature zum Layer hinzufügen
Schreiben Sie das Feature in das Shapefile. Wenn der `using`‑Block endet, wird die Datei geschlossen und ist für jede GIS‑Anwendung bereit.

```csharp
layer.Add(feature);
```

## Häufige Probleme & Tipps
- **Koordinatenreihenfolge:** Aspose.GIS erwartet `X Y` (Längengrad, Breitengrad). Ein Vertauschen der Reihenfolge kehrt die Geometrie um.  
- **CircularString‑Syntax:** Der Mittelpunkt muss auf dem gewünschten Bogen liegen; sonst kollabiert die Kurve zu einer Geraden.  
- **Datei‑Überschreiben:** `VectorLayer.Create` überschreibt ein vorhandenes Shapefile ohne Warnung – verwenden Sie während der Entwicklung einen eindeutigen Dateinamen.  
- **Performance‑Tipp:** Bei großen Datensätzen sollten Features stapelweise hinzugefügt werden, anstatt sie einzeln im `using`‑Block einzufügen.  
- **Pro‑Tipp:** Verwenden Sie dieselbe `CompoundCurve`‑Instanz für mehrere ähnliche Features; leeren Sie deren Inhalt mit `compoundCurve.Clear()` bevor Sie sie neu befüllen.

## Häufig gestellte Fragen

**F:** Kann ich Aspose.GIS für .NET mit anderen .NET‑Frameworks verwenden?  
**A:** Ja, die Bibliothek läuft auf .NET Framework, .NET Core, .NET Standard und .NET 5/6+ ohne Änderungen.

**F:** Unterstützt Aspose.GIS das Lesen und Schreiben verschiedener geospatialer Dateiformate?  
**A:** Absolut. Es verarbeitet Shapefile, GeoJSON, KML, GML und mehr als 30 weitere Formate.

**F:** Ist Aspose.GIS sowohl für Desktop‑ als auch für Web‑Anwendungen geeignet?  
**A:** Ja, dieselbe API funktioniert in Konsolen‑Apps, Windows‑Diensten, ASP.NET Core‑Web‑Apps und cloud‑basierten Funktionen.

**F:** Kann ich mit Aspose.GIS räumliche Analysen durchführen?  
**A:** Ja, Sie können Entfernungen berechnen, geometrische Vereinigungen/Schnittmengen durchführen und räumliche Abfragen direkt auf den Geometrieobjekten ausführen.

**F:** Wo kann ich Community‑Hilfe für Aspose.GIS erhalten?  
**A:** Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33), um Fragen zu stellen, Code‑Snippets zu teilen und von anderen Entwicklern zu lernen.

---

**Zuletzt aktualisiert:** 2026-08-24  
**Getestet mit:** Aspose.GIS for .NET (latest stable release)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Kurven mit Aspose.GIS für .NET in Linien konvertiert](/gis/net/geometry-processing/linearize-geometry/)
- [Erfahren Sie, wie man LineString‑Geometrie mit Aspose.GIS für .NET erstellt](/gis/net/geometry-creation/create-linestring-geometry/)
- [MultiLineString‑Geometrie mit Aspose.GIS für .NET erstellen](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}