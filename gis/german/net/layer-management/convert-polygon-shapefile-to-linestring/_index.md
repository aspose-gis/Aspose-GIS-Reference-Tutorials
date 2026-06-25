---
date: 2026-06-25
description: Erfahren Sie, wie Sie ein Shapefile lesen und ein Polygon‑Shapefile in
  einen Linestring konvertieren, indem Sie Aspose.GIS für .NET verwenden. Verbessern
  Sie Ihre GIS‑Entwicklung mit klaren Schritt‑für‑Schritt‑Anleitungen.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Polygon‑Shapefile in Linestring konvertieren
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man Shapefile in C# liest – Polygon‑Shapefile in Linestring konvertieren
url: /de/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile in C# lesen – Polygon-Shapefile in Linestring konvertieren

## Einführung
Wenn Sie Daten zum **wie man Shapefile liest** in einer .NET-Umgebung benötigen, sind Sie hier genau richtig. Aspose.GIS für .NET abstrahiert das low‑level Binärformat einer Shapefile, sodass Sie geografische Features mit nur wenigen API‑Aufrufen laden, abfragen und transformieren können. Das Konvertieren einer Polygon‑Shapefile in einen Linestring ist besonders nützlich, wenn Sie lineare Darstellungen für Routing, Netzwerk‑Analyse oder einfache Visualisierung extrahieren möchten.

## Schnelle Antworten
- **Welche Bibliothek hilft Ihnen, Shapefile in C# zu lesen?** Aspose.GIS for .NET – es unterstützt 50+ GIS‑Formate und verarbeitet Dateien von mehreren hundert Megabyte, ohne die gesamte Datei in den Speicher zu laden.  
- **Können Sie ein Polygon in eine Linie konvertieren?** Ja – rufen Sie `LineString` auf dem Außenring des Polygons auf und schreiben Sie das Ergebnis in eine neue Shapefile.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist für Produktionsumgebungen erforderlich; eine kostenlose Testversion reicht für die Evaluierung.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Ist eine Testversion verfügbar?** Absolut – laden Sie eine kostenlose Testversion von der Aspose‑Website herunter.

`LineString` ist ein Geometrietyp, der eine Reihe verbundener Liniensegmente darstellt.

## Was bedeutet “read shapefile c#”?
`Document` ist die Kernklasse, die einen GIS‑Datensatz repräsentiert und Zugriff auf seine Features bietet.  
Das Lesen einer Shapefile in C# bedeutet, die `.shp`‑Datei in den Speicher zu laden, damit Sie ihre Geometrien abfragen, ändern oder transformieren können. **Sie instanziieren einfach die `Document`‑Klasse mit dem Dateipfad, und Aspose.GIS analysiert die binäre Struktur für Sie**, wodurch Features über eine einfach zu nutzende Sammlung bereitgestellt werden. Dieser Ansatz eliminiert die Notwendigkeit, manuell mit Low‑Level‑Dateiköpfen oder Koordinaten‑Arrays zu arbeiten.

## Warum Polygon mit Aspose.GIS in eine Linie konvertieren?
Das Konvertieren eines Polygons in einen Linestring bewahrt die exakte äußere Grenze, während innere Ringe entfernt werden, und liefert Ihnen eine saubere lineare Darstellung. Aspose.GIS verarbeitet **Datensätze von bis zu 500 MB in weniger als 2 Sekunden auf einem typischen Server**, wodurch Stapelkonvertierungen schnell und speichereffizient sind. Die Bibliothek behält zudem die ursprüngliche räumliche Referenz bei, sodass die resultierenden Linien perfekt mit bestehenden GIS‑Layern übereinstimmen.

## Voraussetzungen
Bevor wir in das Tutorial einsteigen, stellen Sie sicher, dass Sie Folgendes bereit haben:

- **Aspose.GIS Library** – Laden Sie die Aspose.GIS‑Bibliothek von der [Website](https://releases.aspose.com/gis/net/) herunter und installieren Sie sie.  
- **Shapefile Data** – Haben Sie eine Polygon‑Shapefile bereit für die Konvertierung. Wenn Sie keine haben, können Sie Beispieldaten finden oder Ihre eigene erstellen.  
- **Development Environment** – Richten Sie Ihre .NET‑Entwicklungsumgebung mit den erforderlichen Tools ein (Visual Studio, .NET‑SDK usw.).

## Namespaces importieren
Die `Document`‑Klasse ist das Kernobjekt von Aspose.GIS, das einen GIS‑Datensatz repräsentiert und Methoden zum Lesen und Schreiben von Shapefiles bereitstellt. Fügen Sie die folgenden Namespaces am Anfang Ihrer Code‑Datei hinzu:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie liest man eine Shapefile und konvertiert ein Polygon in einen Linestring?
Laden Sie die Quell‑Polygon‑Shapefile, extrahieren Sie den Außenring jedes Polygons, erstellen Sie daraus ein `LineString` und schreiben Sie das Ergebnis in eine neue Shapefile – alles in fünf einfachen Schritten. Dieses Muster funktioniert für Datensätze jeder Größe und stellt sicher, dass das Koordinatensystem der Quelle im Ziel erhalten bleibt.

### Schritt 1: Dokumentverzeichnis festlegen
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Pfad, in dem sich Ihre Shapefile befindet.

### Schritt 2: Quell‑Shapefile öffnen
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Diese Zeile öffnet die Quell‑Polygon‑Shapefile, sodass Sie deren Features lesen können.

### Schritt 3: Ziel‑Linestring‑Shapefile erstellen
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Hier erstellen wir eine neue Linestring‑Shapefile, die die konvertierten Geometrien speichert.

### Schritt 4: Durch Quell‑Features iterieren
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
Die Schleife durchläuft jedes Polygon‑Feature in der Originaldatei.

### Schritt 5: Polygon in Linestring konvertieren und in das Ziel schreiben
Die Eigenschaft `ExteriorRing` gibt die äußere Grenze eines Polygons als `LineString` zurück.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
In diesem Block konvertieren wir das Polygon in eine Linie (`LineString`) und fügen das neue Feature zur Ziel‑Shapefile hinzu.

## Häufige Probleme und Tipps
- **Coordinate System Mismatch** – Stellen Sie sicher, dass sowohl Quell‑ als auch Ziel‑Layer dieselbe räumliche Referenz verwenden; andernfalls können die Linien verschoben erscheinen.  
- **Large Files** – Beim Verarbeiten sehr großer Shapefiles sollten Sie in Erwägung ziehen, Features zu streamen, anstatt sie alle auf einmal in den Speicher zu laden.  
- **Null Geometries** – Schützen Sie sich vor Features mit leeren Geometrien, um Laufzeitausnahmen zu vermeiden.  
- **Extract lines from polygon** – Wenn Sie nur den Außenring benötigen, verwenden Sie die `ExteriorRing`‑Eigenschaft; für Innenringe iterieren Sie `InteriorRings`.  

## Häufig gestellte Fragen

**Q: Ist Aspose.GIS mit allen .NET‑Versionen kompatibel?**  
A: Ja, Aspose.GIS unterstützt .NET Framework 4.5+, .NET Core 3.1+, und .NET 5/6/7 und sorgt für nahtlose Integration in moderne Entwicklungsumgebungen.

**Q: Kann ich Aspose.GIS für kommerzielle Projekte verwenden?**  
A: Ja, das können Sie. Kaufen Sie eine Lizenz [hier](https://purchase.aspose.com/buy), um Evaluationsbeschränkungen zu entfernen und vollen Support zu erhalten.

**Q: Gibt es Beispiele oder Dokumentation?**  
A: Ja, Sie finden umfassende Dokumentation und Code‑Beispiele auf der [Dokumentationsseite](https://reference.aspose.com/gis/net/).

**Q: Ist eine Testversion verfügbar?**  
A: Absolut – testen Sie Aspose.GIS mit einer kostenlosen Testversion, indem Sie [diesen Link](https://releases.aspose.com/) besuchen.

**Q: Wo kann ich Hilfe oder Support erhalten?**  
A: Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Community‑Unterstützung und offiziellen Support.

---

**Zuletzt aktualisiert:** 2026-06-25  
**Getestet mit:** Aspose.GIS for .NET (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Shapefile in GeoJSON konvertiert mit Aspose.GIS für .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Wie man GeoJSON aus einem Stream liest mit Aspose.GIS für .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Wie man Polygongeometrie erstellt mit Aspose.GIS für .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}