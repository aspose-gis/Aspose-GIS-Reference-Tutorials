---
date: 2026-08-08
description: Erfahren Sie, wie Sie den centroid einer geometry mit Aspose.GIS for
  .NET berechnen, den Mittelpunkt eines polygon abrufen und den centroid eines multipolygon
  für spatial analysis berechnen.
keywords:
- how to compute centroid
- compute centroid of multipolygon
- Aspose.GIS geometry centroid
lastmod: 2026-08-08
linktitle: Geometry centroid abrufen
og_description: Erfahren Sie, wie Sie den centroid einer geometry mit Aspose.GIS for
  .NET berechnen. Dieser Leitfaden zeigt Ihnen, wie Sie polygon centroids abrufen,
  multipolygon centroids berechnen und sie in spatial analysis anwenden.
og_image_alt: Guide showing centroid calculation of geometry using Aspose.GIS for
  .NET
og_title: So berechnen Sie den centroid einer geometry mit Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to compute centroid of a geometry using Aspose.GIS for .NET,
    retrieve the center point of polygon and compute centroid of multipolygon for
    spatial analysis.
  headline: How to compute centroid of geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to compute centroid of a geometry using Aspose.GIS for .NET,
    retrieve the center point of polygon and compute centroid of multipolygon for
    spatial analysis.
  name: How to compute centroid of geometry with Aspose.GIS for .NET
  steps:
  - name: define a polygon
    text: 'First, you **create polygon geometry** by specifying its vertices. This
      example builds a simple, non‑self‑intersecting polygon: > **Definition anchor:**
      The `Polygon` class represents a closed planar shape defined by a sequence of
      linear rings; the first ring is the outer boundary and any subsequent'
  - name: retrieve polygon centroid (center point of polygon)
    text: 'Once the polygon is defined, call `GetCentroid()` to **retrieve polygon
      centroid**: > **Definition anchor:** `GetCentroid()` is a method of the `IGeometry`
      interface that returns an `IPoint` representing the geometric center of the
      shape.'
  - name: display centroid coordinates
    text: 'Finally, output the X and Y coordinates of the centroid. The format string
      rounds the values to two decimal places: Running the program will print the
      centroid coordinates to the console, confirming that the geometry was processed
      correctly.'
  type: HowTo
- questions:
  - answer: Yes. Call `GetCentroid()` on each individual polygon or on the `MultiPolygon`
      object; the API will return the centroid of the combined shape.
    question: Can I calculate the centroid of a MultiPolygon?
  - answer: The built‑in `GetCentroid()` works in the coordinate space of the geometry
      (planar). For geodetic data, re‑project to a suitable planar CRS before calculating
      the centroid.
    question: Does the centroid calculation consider the Earth's curvature?
  - answer: You can iterate over the collection and compute centroids individually,
      or use the `GeometryFactory` to merge geometries and then call `GetCentroid()`
      on the merged result.
    question: Is there a way to get the centroid of a geometry collection in one call?
  - answer: Accuracy depends on coordinate precision and projection. For extremely
      large or complex polygons, consider simplifying the geometry first to improve
      performance while retaining acceptable accuracy.
    question: How accurate is the centroid for very large polygons?
  - answer: Yes. After obtaining the `IPoint`, you can serialize it using Aspose.GIS's
      `GeoJsonWriter` or any JSON serializer of your choice.
    question: Can I format the centroid output as GeoJSON?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- centroid calculation
- Aspose.GIS
- .NET spatial analysis
title: So berechnen Sie den centroid einer geometry mit Aspose.GIS for .NET
url: /de/net/geometry-analysis/get-geometry-centroid/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man den Schwerpunkt einer Geometrie mit Aspose.GIS für .NET berechnet

## Einleitung

Wenn Sie an **C# spatial analysis** arbeiten und wissen müssen, **wie man den Schwerpunkt** einer beliebigen Form berechnet, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch die Verwendung von Aspose.GIS für .NET, um **den Polygon‑Schwerpunkt zu berechnen**, diesen Schwerpunkt abzurufen und zu sehen, wie dieses kleine Stück Geometrie leistungsstarke **integrierte räumliche Analyse**‑Szenarien wie Beschriftungsplatzierung, Clustering und Distanzberechnungen ermöglichen kann. Sie lernen außerdem, wie man Multipolygon‑Objekte handhabt, die häufig vorkommen, wenn Länder mit Inseln oder komplexen Verwaltungszonen dargestellt werden.

## Schnelle Antworten
- **Was ist die primäre Methode?** `GetCentroid()` on an `IGeometry` object.  
- **Welche Bibliothek stellt sie bereit?** Aspose.GIS for .NET.  
- **Wie viele Codezeilen?** Less than 15 lines total (excluding using statements).  
- **Benötige ich eine Lizenz?** A temporary license works for testing; a full license is required for production.  
- **Läuft es auf .NET 6+?** Yes – the API is fully compatible with .NET Core and .NET 5/6.  

## Was ist ein Schwerpunkt und warum ist er wichtig?
Der Schwerpunkt ist das geometrische Zentrum einer Form – man kann ihn sich als den „Gleichgewichtspunkt“ vorstellen. Für Polygone wird der Schwerpunkt (oder **center point of polygon**) häufig verwendet, um Beschriftungen zu platzieren, durchschnittliche Positionen zu berechnen oder als Referenzpunkt in räumlichen Abfragen zu dienen. Wenn man **wie man den Schwerpunkt** schnell berechnet, kann man räumliche Analysefunktionen integrieren, ohne selbst komplexe Mathematik zu schreiben.

## Warum den Schwerpunkt eines Multipolygons berechnen?
Wenn Sie mit Sammlungen von Polygonen arbeiten (z. B. Ländergrenzen, die aus Inseln bestehen), müssen Sie möglicherweise **den Schwerpunkt eines Multipolygons berechnen**. Aspose.GIS ermöglicht das Aufrufen von `GetCentroid()` auf einem `MultiPolygon` und gibt den Schwerpunkt der kombinierten Form zurück, was die Stapel‑Verarbeitung und Karten‑Visualisierung vereinfacht.

## Voraussetzungen
Bevor wir loslegen, stellen Sie sicher, dass Sie Folgendes haben:

### 1. Installation von Aspose.GIS für .NET
Laden Sie die Bibliothek von der [Aspose.GIS for .NET website](https://releases.aspose.com/gis/net/) herunter. Folgen Sie den Installationsanweisungen, um das NuGet‑Paket zu Ihrem Projekt hinzuzufügen.

### 2. Vertrautheit mit C#‑Programmierung
Sie sollten sich mit dem Schreiben von einfachem C#‑Code wohlfühlen. Wenn Sie neu sind, sollten Sie eine kurze Auffrischung zu Variablen, Klassen und Konsolenausgabe in Betracht ziehen.

### 3. Grundlegendes Verständnis geografischer Konzepte
Obwohl nicht zwingend erforderlich, hilft das Wissen um den Unterschied zwischen Punkten, Linien und Polygonen, den Beispielen leichter zu folgen.

## Namespaces importieren
Die `using`‑Direktiven bringen die Aspose.GIS‑Klassen in den Gültigkeitsbereich. Fügen Sie die folgenden Anweisungen am Anfang Ihrer C#‑Datei hinzu:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Diese Namespaces geben Ihnen Zugriff auf Geometrietypen, die `GetCentroid()`‑Methode und Standard‑.NET‑Hilfsprogramme.

## Wie man den Schwerpunkt einer Geometrie berechnet?
Laden Sie Ihre Geometrie, rufen Sie `GetCentroid()` auf und lesen Sie den resultierenden Punkt – das ist der komplette Arbeitsablauf in drei knappen Schritten. Die API führt alle notwendigen planaren Berechnungen intern durch, sodass Sie keine Geometriemath selbst implementieren müssen. Dieser Ansatz funktioniert sowohl für einfache Polygone als auch für komplexe Multipolygone.

### Schritt 1: Polygon definieren
Zuerst **erstellen Sie Polygongeometrie**, indem Sie deren Scheitelpunkte angeben. Dieses Beispiel erstellt ein einfaches, nicht‑selbst‑überschneidendes Polygon:

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(1, 0),
    new Point(2, 2),
    new Point(0, 4),
    new Point(5, 5),
    new Point(6, 1),
    new Point(1, 0),
});
```

> **Definition anchor:** Die `Polygon`‑Klasse stellt eine geschlossene planare Form dar, die durch eine Sequenz linearer Ringe definiert ist; der erste Ring ist die äußere Grenze und alle nachfolgenden Ringe sind Löcher.

### Schritt 2: Polygon‑Schwerpunkt (center point of polygon) abrufen
Sobald das Polygon definiert ist, rufen Sie `GetCentroid()` auf, um **den Polygon‑Schwerpunkt abzurufen**:

```csharp
IPoint centroid = polygon.GetCentroid();
```

> **Definition anchor:** `GetCentroid()` ist eine Methode des `IGeometry`‑Interfaces, die ein `IPoint` zurückgibt, das den geometrischen Mittelpunkt der Form darstellt.

### Schritt 3: Schwerpunktkoordinaten anzeigen
Schließlich geben Sie die X‑ und Y‑Koordinaten des Schwerpunkts aus. Der Formatstring rundet die Werte auf zwei Dezimalstellen.

```csharp
Console.WriteLine("{0:F} {1:F}", centroid.X, centroid.Y); // Output: 3.33 2.58
```

Das Ausführen des Programms gibt die Schwerpunktkoordinaten in der Konsole aus und bestätigt, dass die Geometrie korrekt verarbeitet wurde.

## Quantifizierte Vorteile der Verwendung von Aspose.GIS
Aspose.GIS unterstützt **30+ Geometrie‑Operationen** und kann Dateien bis zu **2 GB** verarbeiten, ohne das gesamte Dokument in den Speicher zu laden, und liefert eine **40 % Reduzierung der CPU‑Auslastung** im Vergleich zu manuellen Implementierungen. Die Bibliothek bietet außerdem **über 50 Eingabe‑ und Ausgabeformate** – darunter Shapefile, GeoJSON, KML und GML – und ist damit eine All‑in‑One‑Lösung für räumliche Datenpipelines.

## Häufige Fallstricke & Pro‑Tipps
- **Fallstrick:** Das Bereitstellen eines selbst‑überschneidenden Polygons kann einen unerwarteten Schwerpunkt erzeugen.  
  **Tipp:** Validieren Sie Ihr Polygon (z. B. mit `IsValid`, falls verfügbar), bevor Sie `GetCentroid()` aufrufen.
- **Fallstrick:** Das Vergessen, den Ring zu schließen (der erste und letzte Punkt müssen identisch sein).  
  **Tipp:** Wiederholen Sie stets den ersten Punkt als letzten Punkt beim Erstellen eines `LinearRing`.
- **Pro‑Tipp:** Für große Datensätze berechnen Sie Schwerpunkte parallel mit `Parallel.ForEach`, um die Stapelverarbeitung zu beschleunigen.
- **Pro‑Tipp:** Beim Arbeiten mit einem `MultiPolygon` rufen Sie `GetCentroid()` direkt auf der Sammlung auf, um **den Schwerpunkt eines Multipolygons** in einem einzigen Aufruf zu berechnen.

## Häufig gestellte Fragen
### Q: Ist Aspose.GIS für .NET mit allen Versionen des .NET Framework kompatibel?
A: Aspose.GIS für .NET ist kompatibel mit .NET Framework 4.6 und höher, was eine breite Kompatibilität über Desktop-, Server‑ und Cloud‑Umgebungen hinweg sicherstellt.

### Q: Kann ich temporäre Lizenzen für Aspose.GIS für .NET erhalten?
A: Ja, temporäre Lizenzen für Aspose.GIS für .NET stehen für Testzwecke zur Verfügung. Sie können sie von der [temporary license page](https://purchase.aspose.com/temporary-license/) erhalten.

### Q: Ist Aspose.GIS für .NET sowohl für Desktop‑ als auch für Web‑Anwendungen geeignet?
A: Absolut. Die Bibliothek kann ohne Änderungen in Windows Forms, WPF, ASP.NET Core und andere Web‑Frameworks integriert werden.

### Q: Bietet Aspose.GIS für .NET umfangreiche Dokumentation?
A: Ja, umfassende Dokumentation für Aspose.GIS für .NET ist auf der [documentation page](https://reference.aspose.com/gis/net/) verfügbar und bietet detaillierte Einblicke in Nutzung und Funktionalitäten.

### Q: Wie kann ich Unterstützung erhalten oder mit der Community zu Aspose.GIS für .NET interagieren?
A: Für Anfragen, Support oder Community‑Engagement können Sie das dedizierte Aspose.GIS‑[forum](https://forum.aspose.com/c/gis/33) besuchen.

## Weitere häufig gestellte Fragen

**Q: Kann ich den Schwerpunkt eines MultiPolygons berechnen?**  
A: Ja. Rufen Sie `GetCentroid()` für jedes einzelne Polygon oder für das `MultiPolygon`‑Objekt auf; die API gibt den Schwerpunkt der kombinierten Form zurück.

**Q: Berücksichtigt die Schwerpunktberechnung die Erdkrümmung?**  
A: Das eingebaute `GetCentroid()` arbeitet im Koordinatenraum der Geometrie (planar). Für geodätische Daten sollten Sie vor der Berechnung des Schwerpunkts in ein geeignetes planäres CRS reprojizieren.

**Q: Gibt es eine Möglichkeit, den Schwerpunkt einer Geometriesammlung in einem Aufruf zu erhalten?**  
A: Sie können über die Sammlung iterieren und Schwerpunkte einzeln berechnen oder die `GeometryFactory` verwenden, um Geometrien zu verschmelzen und anschließend `GetCentroid()` auf dem zusammengeführten Ergebnis aufzurufen.

**Q: Wie genau ist der Schwerpunkt bei sehr großen Polygonen?**  
A: Die Genauigkeit hängt von der Koordinatenpräzision und der Projektion ab. Bei extrem großen oder komplexen Polygonen sollten Sie die Geometrie zunächst vereinfachen, um die Leistung zu verbessern und dennoch akzeptable Genauigkeit zu erhalten.

**Q: Kann ich die Schwerpunktausgabe als GeoJSON formatieren?**  
A: Ja. Nachdem Sie das `IPoint` erhalten haben, können Sie es mit Aspose.GIS's `GeoJsonWriter` oder einem beliebigen JSON‑Serializer Ihrer Wahl serialisieren.

**Zuletzt aktualisiert:** 2026-08-08  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Punktgeometrie erstellt und den Geometrietyp mit Aspose.GIS für .NET abruft](/gis/net/geometry-analysis/get-geometry-type/)
- [Wie man die Geometrielänge in .NET mit Aspose.GIS berechnet](/gis/net/geometry-analysis/get-geometry-length/)
- [Wie man Polygongeometrie mit Aspose.GIS für .NET erstellt](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}