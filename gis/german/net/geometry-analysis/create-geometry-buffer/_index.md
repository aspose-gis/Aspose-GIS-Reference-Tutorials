---
date: 2026-06-05
description: Erfahren Sie, wie Sie Geometrie mit Aspose.GIS für .NET puffern und räumliche
  Analyse‑Puffer durchführen, einschließlich Installation, Namespace‑Importen und
  Überprüfungen der Enthaltenheit.
keywords:
- spatial analysis buffer
- how to buffer geometry
- Aspose.GIS buffering tutorial
- .NET spatial analysis
- geometry buffer example
linktitle: Wie man einen Puffer mit Aspose.GIS für .NET erstellt
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to buffer geometry with Aspose.GIS for .NET and perform spatial
    analysis buffers, including installation, namespace imports, and containment checks.
  headline: How to Buffer Geometry Using Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to buffer geometry with Aspose.GIS for .NET and perform spatial
    analysis buffers, including installation, namespace imports, and containment checks.
  name: How to Buffer Geometry Using Aspose.GIS for .NET
  steps:
  - name: Create a Geometry Buffer
    text: A `LineString` is an ordered collection of points forming a continuous line.
      First, we define a simple `LineString` geometry that will serve as the source
      for our buffer. In this snippet we create a `LineString` and add two points,
      forming a diagonal line from (0,0) to (3,3).
  - name: Generate Buffer for LineString
    text: 'The `GetBuffer` method creates a polygon representing all points within
      the specified distance from the source geometry. Next, we generate a buffer
      around the line with a **positive distance** of 1 unit. The `GetBuffer` method
      returns a polygon that includes every point located within 1 unit of the '
  - name: Check Spatial Containment
    text: The `SpatiallyContains` predicate returns true if the target geometry lies
      completely inside the source geometry. Now we demonstrate **how to check containment**
      by testing whether specific points fall inside the buffer. The `SpatiallyContains`
      predicate returns `true` if the point lies inside the b
  - name: Define a Polygon Geometry
    text: A `Polygon` represents a closed planar surface defined by a sequence of
      linear rings. We’ll also create a `Polygon` geometry to illustrate buffering
      with a **negative distance**, which shrinks the shape. The polygon represents
      a square with vertices at (0,0), (0,3), (3,3), and (3,0).
  - name: Generate Buffer for Polygon
    text: Applying a negative distance of –1 unit contracts the polygon inward. The
      resulting `polygonBuffer` is a smaller square, useful for creating interior
      zones.
  - name: Access Buffer Exterior Ring Points
    text: Finally, we retrieve and display the coordinates of the buffer’s exterior
      ring. This loop prints each vertex of the contracted polygon, confirming the
      buffer geometry.
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework, .NET Core, .NET 5, and .NET 6.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. The library supports buffering, intersecting, distance calculations,
      and more.
    question: Can I perform spatial analysis using Aspose.GIS for .NET?
  - answer: The API is optimized for large datasets and can handle **hundreds of thousands
      of geometries** without exhausting memory, provided you process them in reasonable
      batches.
    question: Are there limits on dataset size?
  - answer: Yes, it handles a wide range of coordinate systems and allows on‑the‑fly
      transformations.
    question: Does Aspose.GIS support different spatial reference systems?
  - answer: Visit the Aspose.GIS community forum at [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33)
      for assistance.
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man Geometrie mit Aspose.GIS für .NET puffert
url: /de/net/geometry-analysis/create-geometry-buffer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Geometrien mit Aspose.GIS für .NET puffert

## Einführung
Wenn Sie mit Geodaten in einer .NET‑Umgebung arbeiten, ist **das Wissen, wie man Geometrien puffert** entscheidend für Proximitätsanalysen, Zonierung und Feature‑Generalisierung. In diesem Tutorial führen wir Sie durch den gesamten Prozess mit Aspose.GIS für .NET – von der Installation über das Importieren der erforderlichen Namespaces, das Erzeugen von Puffern für Linien‑ und Polygongeometrien bis hin zur Prüfung räumlicher Einschließungen. Am Ende können Sie **räumliche Analyse‑Puffer** sicher in Ihren eigenen Anwendungen einsetzen.

## Schnellantworten
- **Was ist ein Geometrie‑Puffer?** Ein Polygon, das alle Punkte innerhalb einer angegebenen Entfernung von einer Quellgeometrie umschließt.  
- **Warum Aspose.GIS für das Puffer‑Erstellen verwenden?** Es bietet eine einfache, hoch‑leistungsfähige API, die auf .NET Framework, .NET Core und .NET 5/6+ funktioniert.  
- **Wie installiert man Aspose.GIS?** Laden Sie die Bibliothek von der offiziellen Website herunter und fügen Sie sie als Referenz in Visual Studio hinzu.  
- **Wie prüft man die Einschließung?** Verwenden Sie die Methode `SpatiallyContains`, um zu testen, ob ein Punkt innerhalb des erzeugten Puffers liegt.  
- **Kann ich über das Puffer‑Erstellen hinaus räumliche Analysen durchführen?** Ja – Operationen wie Schnitt, Vereinigung und Distanzberechnungen werden ebenfalls unterstützt.

## Was ist ein Geometrie‑Puffer?
Ein Geometrie‑Puffer erzeugt eine Zone um ein Feature (Punkt, Linie oder Polygon) in einer benutzerdefinierten Entfernung. Diese Zone ist nützlich, um nahegelegene Features zu identifizieren, Wirkungsbereiche zu erstellen oder komplexe Formen zu vereinfachen. Puffer werden häufig in Proximity‑Abfragen, Umwelt‑Impact‑Assessments und Netzwerk‑Analysen eingesetzt und bieten eine klare visuelle Darstellung des Bereichs, der innerhalb der angegebenen Entfernung zur ursprünglichen Geometrie liegt.

## Wie man Geometrien mit Aspose.GIS puffert
Laden Sie Ihre Quellgeometrie, rufen Sie `GetBuffer` mit der gewünschten Entfernung auf, und Sie erhalten sofort ein Polygon, das die Pufferzone darstellt. Dieses Zwei‑Schritt‑Muster funktioniert für Punkte, Linien und Polygone, und die API kümmert sich automatisch um Nuancen des Koordinatensystems, sodass Sie keine eigene Mathematik schreiben müssen.

### Warum Aspose.GIS für räumliche Analyse‑Puffer verwenden?
- **Plattformübergreifende Unterstützung:** Läuft auf Windows, Linux und macOS.  
- **Keine externen Abhängigkeiten:** Keine nativen GIS‑Bibliotheken nötig.  
- **Umfangreiche API:** Enthält Pufferung, räumliche Prädikate und Koordinatensystem‑Transformationen.  
- **Leistungsoptimiert:** Verarbeitet Datensätze mit bis zu **500 000 Features** in weniger als **2 Sekunden** auf einem typischen 8‑Kern‑Server und ist damit ideal für anspruchsvolle räumliche Analyse‑Puffer.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Visual Studio 2019 oder neuer** (oder jede kompatible .NET‑IDE).  
- **.NET 6 SDK** (oder .NET Core 3.1+).  
- **Aspose.GIS für .NET‑Bibliothek** – siehe die Installationsschritte unten.  

### Wie man Aspose.GIS für .NET installiert
1. Laden Sie die Aspose.GIS für .NET‑Bibliothek von dem [Download‑Link](https://releases.aspose.com/gis/net/) herunter.  
2. In Visual Studio klicken Sie mit der rechten Maustaste auf Ihr Projekt → **Add** → **Reference…** → navigieren Sie zur heruntergeladenen DLL und fügen Sie sie hinzu.  
3. Erwerben Sie eine Lizenz von [Aspose](https://purchase.aspose.com/buy) oder nutzen Sie eine [temporäre Lizenz](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke.

## Importieren von Namespaces
Der `Aspose.Gis`‑Namespace enthält alle Kernklassen, die Sie für die Erstellung von Geometrien, das Puffer‑Erstellen und räumliche Prädikate benötigen.

Die Klasse `GeometryFactory` ist der Einstiegspunkt zum Erzeugen von Geometrieobjekten wie `LineString` und `Polygon`. Das Importieren dieser Namespaces macht die API in Ihrer gesamten Datei verfügbar.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nun zerlegen wir den Puffer‑Erstellungsprozess Schritt für Schritt.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Einen Geometrie‑Puffer erstellen
Ein `LineString` ist eine geordnete Sammlung von Punkten, die eine durchgehende Linie bilden.  
Zuerst definieren wir eine einfache `LineString`‑Geometrie, die als Quelle für unseren Puffer dient.

```csharp
// Define a LineString geometry
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```

In diesem Snippet erstellen wir einen `LineString` und fügen zwei Punkte hinzu, die eine diagonale Linie von (0,0) nach (3,3) bilden.

### Schritt 2: Puffer für LineString erzeugen
Die Methode `GetBuffer` erzeugt ein Polygon, das alle Punkte innerhalb der angegebenen Entfernung von der Quellgeometrie darstellt.  
Als Nächstes erzeugen wir einen Puffer um die Linie mit einer **positiven Entfernung** von 1 Einheit.

```csharp
// Generate a buffer for the LineString with a positive distance
var lineBuffer = line.GetBuffer(distance: 1);
```

Die Methode `GetBuffer` gibt ein Polygon zurück, das jeden Punkt innerhalb von 1 Einheit der ursprünglichen Linie enthält.

### Schritt 3: Räumliche Einschließung prüfen
Das Prädikat `SpatiallyContains` liefert **true**, wenn die Zielgeometrie vollständig innerhalb der Quellgeometrie liegt.  
Jetzt zeigen wir **wie man die Einschließung prüft**, indem wir testen, ob bestimmte Punkte innerhalb des Puffers liegen.

```csharp
// Check spatial containment of points within the buffer
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     // True
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); // True
```

Das Prädikat `SpatiallyContains` gibt `true` zurück, wenn der Punkt innerhalb des Puffer‑Polygons liegt.

### Schritt 4: Ein Polygon definieren
Ein `Polygon` stellt eine geschlossene planare Fläche dar, die durch eine Sequenz linearer Ringe definiert ist.  
Wir erstellen außerdem eine `Polygon`‑Geometrie, um das Puffer‑Erstellen mit einer **negativen Entfernung** zu demonstrieren, die die Form verkleinert.

```csharp
// Define a Polygon geometry
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```

Das Polygon stellt ein Quadrat mit den Eckpunkten (0,0), (0,3), (3,3) und (3,0) dar.

### Schritt 5: Puffer für Polygon erzeugen
Durch Anwendung einer negativen Entfernung von –1 Einheit wird das Polygon nach innen verkleinert.

```csharp
// Generate a buffer for the Polygon with a negative distance
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```

Der resultierende `polygonBuffer` ist ein kleineres Quadrat, nützlich für die Erstellung von Innenzonen.

### Schritt 6: Punkte des äußeren Rings des Puffers auslesen
Abschließend rufen wir die Koordinaten des äußeren Rings des Puffers ab und geben sie aus.

```csharp
// Access points of the exterior ring of the buffer Polygon
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```

Diese Schleife gibt jeden Scheitelpunkt des verkleinerten Polygons aus und bestätigt die Puffergeometrie.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Puffer gibt `null` zurück** | Stellen Sie sicher, dass der Distanzwert für das Koordinatensystem der Geometrie geeignet ist. |
| **`SpatiallyContains` liefert immer `false`** | Vergewissern Sie sich, dass beide Geometrien dasselbe räumliche Referenzsystem (CRS) verwenden. |
| **Leistungsverlust bei großen Datensätzen** | Verarbeiten Sie Geometrien in Batches und verwenden Sie dieselbe `GeometryFactory`‑Instanz wieder. |

## Häufig gestellte Fragen

**F: Ist Aspose.GIS für .NET mit anderen .NET‑Frameworks kompatibel?**  
A: Ja, es funktioniert mit .NET Framework, .NET Core, .NET 5 und .NET 6.

**F: Kann ich mit Aspose.GIS räumliche Analysen durchführen?**  
A: Absolut. Die Bibliothek unterstützt Pufferung, Schnittmengen, Distanzberechnungen und mehr.

**F: Gibt es Grenzen für die Datensatzgröße?**  
A: Die API ist für große Datensätze optimiert und kann **Hunderttausende von Geometrien** verarbeiten, ohne den Speicher zu erschöpfen, vorausgesetzt, Sie verarbeiten sie in sinnvollen Batches.

**F: Unterstützt Aspose.GIS verschiedene räumliche Referenzsysteme?**  
A: Ja, es verarbeitet eine breite Palette von Koordinatensystemen und ermöglicht Transformationen „on‑the‑fly“.

**F: Wo finde ich technischen Support?**  
A: Besuchen Sie das Aspose.GIS‑Community‑Forum unter [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33) für Unterstützung.

---

**Zuletzt aktualisiert:** 2026-06-05  
**Getestet mit:** Aspose.GIS für .NET (neueste Version)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Polygon‑Geometrie mit Aspose.GIS für .NET erstellt](/gis/net/geometry-creation/create-polygon-geometry/)
- [Wie man räumliche Überlappungsanalysen von Geometrien mit Aspose.GIS für .NET durchführt](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Wie man den Schwerpunkt einer Geometrie mit Aspose.GIS für .NET ermittelt](/gis/net/geometry-analysis/get-geometry-centroid/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}