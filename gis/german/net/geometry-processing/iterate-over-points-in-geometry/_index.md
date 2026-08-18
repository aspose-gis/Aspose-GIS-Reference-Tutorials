---
date: 2026-06-10
description: Erfahren Sie, wie Sie Points hinzufügen und Koordinaten zu einem Shape
  hinzufügen, während Sie über Geometry iterieren, mit Aspose.GIS for .NET, dem leistungsstarken
  GIS toolkit für .NET-Entwickler.
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: Wie man Points hinzufügt und über Geometry in .NET iteriert
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Wie man Points hinzufügt und über Geometry in .NET iteriert
url: /de/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Punkte hinzufügt und über Geometrie in .NET iteriert

## Einleitung

Wenn Sie mit GIS-Daten in einer .NET-Umgebung arbeiten, ist eines der ersten Dinge, die Sie wissen müssen, **wie man Punkte** zu einer Geometrie hinzufügt und anschließend mit diesen Punkten arbeitet. Aspose.GIS für .NET bietet eine saubere, objektorientierte API, die diesen Prozess unkompliziert macht. In diesem Tutorial führen wir Sie durch das Erstellen eines `LineString`, das Hinzufügen von Punkten zu ihm und das Iterieren über diese Punkte, sodass Sie Koordinaten extrahieren oder weitere Analysen durchführen können. Sie sehen außerdem, wie man **Koordinaten zu Shape**‑Objekten **hinzufügen** kann.

## Schnelle Antworten
- **Was ist die primäre Klasse für Punktesammlungen?** `LineString`
- **Wie fügt man einen Punkt hinzu?** Verwenden Sie `AddPoint(longitude, latitude)`
- **Können Sie mit einer foreach‑Schleife iterieren?** Ja, `LineString` implementiert `IEnumerable<IPoint>`
- **Voraussetzungen?** .NET 6+ (oder .NET Core 3.1/Framework 4.6+) und Aspose.GIS für .NET Bibliothek
- **Typischer Anwendungsfall?** Routen erstellen, Tracks visualisieren oder Daten für räumliche Analysen vorverarbeiten  
- **IPoint** stellt eine einzelne Punktgeometrie mit X (Longitude) und Y (Latitude) Koordinaten dar.

## Was bedeutet „Punkte hinzufügen“ in GIS?

Punkte hinzufügen bedeutet, einzelne Koordinatenpaare (Longitude, Latitude) in einen geometrischen Container wie einen `LineString`, `Polygon` oder `MultiPoint` einzufügen. Jeder Punkt wird zu einem Scheitelpunkt, der die Form oder den Pfad definiert, den Sie modellieren, und ermöglicht räumliche Operationen und Visualisierungen. Diese Scheitelpunkte können später für Analysen abgerufen, in verschiedene GIS‑Formate exportiert oder in räumlichen Berechnungen wie Distanzmessungen oder Schnittmengentests verwendet werden.

## Warum Punkte mit Aspose.GIS hinzufügen?

Sie fügen Punkte mit Aspose.GIS hinzu, weil die Bibliothek **typen­sichere Geometrie‑Verarbeitung** garantiert, **30+ Vektor‑ und Rasterformate** unterstützt und **Datensätze mit mehreren hundert Seiten** verarbeiten kann, ohne die gesamte Datei in den Speicher zu laden. Die API bietet zudem integrierte Iteration, räumliche Operationen und Formatkonvertierung (Shapefile, GeoJSON, KML usw.) auf allen unterstützten Plattformen.

## Voraussetzungen

- Visual Studio 2022 (oder jede C#‑IDE)  
- Aspose.GIS für .NET NuGet‑Paket installiert  
- Grundlegendes Verständnis der C#‑Syntax  

## Namespaces importieren

Begin by importing the necessary namespaces to enable access to the Aspose.GIS functionalities in your .NET application:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie man Punkte zu einer Geometrie hinzufügt?

Sie fügen Punkte hinzu, indem Sie eine `LineString`‑Instanz erstellen, für jedes Koordinatenpaar die Methode `AddPoint` aufrufen und bei Bedarf über die Sammlung iterieren. Dieses Drei‑Schritte‑Muster deckt Erstellung, Befüllung und Durchlauf in einer prägnanten, lesbaren Weise ab. **LineString ist ein Geometrietyp, der eine geordnete Sammlung von Punkten darstellt, die eine Polylinie bilden.** Dieser Ansatz stellt sicher, dass die Geometrie gültig bleibt und bereit für weitere räumliche Operationen wie Längenberechnung oder Export ist.

### Schritt 1: Erstellen eines `LineString`-Objekts  

`LineString` ist der Geometrietyp von Aspose.GIS, der eine geordnete Sammlung von Punkten darstellt, die eine Polylinie bilden.

```csharp
LineString line = new LineString();
```

### Schritt 2: Punkte zum `LineString` hinzufügen  

Die Methode `AddPoint` fügt am Ende der Linie einen neuen Scheitelpunkt (Longitude, Latitude) ein. Rufen Sie sie wiederholt auf, um **Koordinaten zu Shape**‑Objekten **hinzuzufügen**.

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### Schritt 3: Über die Punkte iterieren  

`LineString` implementiert `IEnumerable<IPoint>`, sodass Sie mit einer `foreach`‑Anweisung durch jeden Punkt iterieren können. Das macht das Extrahieren von X (Longitude)‑ und Y (Latitude)‑Werten trivial.

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

Die Schleife gibt die X (Longitude)- und Y (Latitude)-Werte jedes Punktes in der Konsole aus, sodass Sie überprüfen können, ob die Punkte korrekt hinzugefügt wurden.

## Häufige Anwendungsfälle

- **Routenplanung** – Erstellen Sie einen Pfad aus GPS‑Logs und analysieren Sie anschließend die Entfernungen zwischen Wegpunkten.  
- **Datenvalidierung** – Iterieren Sie über Punkte, um sicherzustellen, dass sie innerhalb erwarteter Grenzen liegen (z. B. innerhalb der Grenzen eines Landes).  
- **Visualisierung** – Exportieren Sie den `LineString` nach GeoJSON oder Shapefile zur Verwendung in Kartierungswerkzeugen.

## Häufig gestellte Fragen

**F1: Kann Aspose.GIS für .NET andere geometrische Formen neben `LineString` verarbeiten?**  
A: Ja, Aspose.GIS unterstützt `Point`, `Polygon`, `MultiLineString`, `MultiPolygon` und viele weitere Geometrietypen.

**F2: Ist Aspose.GIS sowohl für kommerzielle als auch für private Projekte geeignet?**  
A: Absolut. Lizenzoptionen decken kommerzielle, private und Bildungs‑Anwendungsfälle ab.

**F3: Bietet Aspose.GIS für .NET umfassende Dokumentation für Anfänger?**  
A: Ja, das Produkt enthält umfangreiche Dokumente, API‑Referenzen und Dutzende von Code‑Beispielen, die Ihnen einen schnellen Einstieg ermöglichen.

**F4: Kann ich die Funktionalität von Aspose.GIS für .NET durch benutzerdefinierte Entwicklung erweitern?**  
A: Sie können Erweiterungsmethoden erstellen oder Aspose.GIS‑Klassen kapseln, um spezifische Workflows zu unterstützen, und erhalten so die volle Kontrolle über benutzerdefinierte geospatiale Lösungen.

**F5: Ist technischer Support für Aspose.GIS‑Nutzer verfügbar?**  
A: Dedizierter technischer Support wird über die Aspose‑Foren und das Ticketsystem bereitgestellt, sodass Sie schnelle Hilfe erhalten.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.GIS for .NET 24.5 (latest at time of writing)  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Punkte in Geometrie mit Aspose.GIS für .NET zählt](/gis/net/geometry-creation/count-points-in-geometry/)
- [Wie man einen Punkt zu LineString hinzufügt und Geometrie in ein editierbares Format konvertiert mit Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [MultiPoint‑Geometrie mit Aspose.GIS für .NET erstellen](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}