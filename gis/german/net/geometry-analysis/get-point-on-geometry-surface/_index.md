---
date: 2026-08-13
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET prüfen, ob ein Punkt innerhalb
  eines Polygons liegt, Polygongeometrie erstellen und den Punkt auf der Oberfläche
  in C# erhalten. Schritt‑für‑Schritt‑Anleitung mit vollständigem Codebeispiel.
keywords:
- check point inside polygon
- how to test polygon
- Aspose.GIS geometry
- .NET spatial analysis
lastmod: 2026-08-13
linktitle: Punkt im Polygon prüfen und Punkt auf Oberfläche erhalten
og_description: Erfahren Sie, wie Sie mit Aspise.GIS für .NET prüfen, ob ein Punkt
  innerhalb eines Polygons liegt und den Punkt auf der Oberfläche erhalten. Detailliertes
  C#‑Beispiel und bewährte Methoden für räumliche Analysen.
og_image_alt: Screenshot of Aspose.GIS code checking point inside polygon in C#
og_title: Punkt im Polygon prüfen – Aspose.GIS .NET Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to check point inside polygon using Aspose.GIS for .NET,
    create polygon geometry, and get point on surface in C#. Step‑by‑step guide with
    full code example.
  headline: Check point inside polygon and get point on surface
  type: TechArticle
- description: Learn how to check point inside polygon using Aspose.GIS for .NET,
    create polygon geometry, and get point on surface in C#. Step‑by‑step guide with
    full code example.
  name: Check point inside polygon and get point on surface
  steps:
  - name: create polygon geometry in C#
    text: First, we need to **create a polygon** geometry. We define the exterior
      ring of the polygon by specifying its vertices.
  - name: get point on surface
    text: The `GetPointOnSurface()` method returns a single interior point guaranteed
      to lie inside the polygon’s area. Next, we retrieve a point on the surface of
      the polygon using this method. This is the **get point on surface** step.
  - name: check point inside polygon
    text: The `SpatiallyContains()` method evaluates whether a geometry completely
      contains another geometry, returning true or false. We can verify whether the
      retrieved point lies inside the polygon using this method. This demonstrates
      **retrieving point on polygon** and then checking it.
  type: HowTo
- questions:
  - answer: It verifies whether a given coordinate lies within the boundaries of a
      polygon geometry.
    question: What does “check point inside polygon” mean?
  - answer: '`GetPointOnSurface()` returns a point guaranteed to be inside the polygon.'
    question: Which method returns a point on a polygon’s interior?
  - answer: A free trial works for evaluation; a full license is required for production.
    question: Do I need a license to run the example?
  - answer: .NET Framework, .NET Core, and .NET Standard are all compatible.
    question: Which .NET versions are supported?
  - answer: About 5‑10 minutes to copy, compile, and run.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- check point inside polygon
- Aspose.GIS
- .NET geometry
- C# spatial operations
title: Punkt im Polygon prüfen und Punkt auf Oberfläche erhalten
url: /de/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Punkt innerhalb eines Polygons prüfen und Punkt auf Oberfläche erhalten

## Einführung
In diesem Tutorial lernen Sie **wie man prüft, ob ein Punkt innerhalb eines Polygons liegt** mit Aspose.GIS für .NET und sehen außerdem, wie man **einen Punkt auf der Oberfläche** einer Geometrie erhält. Wir gehen die Erstellung einer Polygongeometrie in C# durch, holen einen Punkt, der auf der Oberfläche des Polygons liegt, und überprüfen, dass der Punkt tatsächlich innerhalb des Polygons liegt. Am Ende haben Sie ein einsatzbereites Snippet, das Sie in jede .NET-Geodatenanwendung einbinden können.

## Schnelle Antworten
- **Was bedeutet “check point inside polygon”?** Es prüft, ob ein gegebener Koordinatenpunkt innerhalb der Grenzen einer Polygongeometrie liegt.  
- **Welche Methode liefert einen Punkt im Inneren eines Polygons?** `GetPointOnSurface()` gibt einen Punkt zurück, der garantiert innerhalb des Polygons liegt.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion funktioniert für die Evaluierung; für den Produktionseinsatz ist eine Volllizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework, .NET Core und .NET Standard sind alle kompatibel.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten zum Kopieren, Kompilieren und Ausführen.

## Was bedeutet “check point inside polygon”?
Das Prüfen, ob ein Punkt innerhalb eines Polygons liegt, bestimmt, ob ein bestimmter Koordinatenpunkt innerhalb des geschlossenen Bereichs liegt, der durch die Eckpunkte des Polygons definiert ist. Die Operation liefert true, wenn der Punkt vollständig eingeschlossen ist, und false, wenn er außerhalb oder auf der Grenze liegt. Dieser grundlegende räumliche Test ermöglicht Geofencing, standortbasierte Analysen und kartengesteuerte Validierungsszenarien.

## Warum Aspose.GIS für diese Aufgabe verwenden?
Aspose.GIS bietet eine vollständig verwaltete .NET‑API, die Polygonoperationen bis zu 200 MB im speichereffizienten Modus verarbeitet, über 50 Koordinatenreferenzsysteme unterstützt und auf .NET Framework, .NET Core und .NET Standard ohne native Abhängigkeiten läuft.  
`GetPointOnSurface()` gibt einen Punkt zurück, der garantiert im Inneren der Geometrie liegt.  
`SpatiallyContains()` bestimmt, ob eine Geometrie eine andere vollständig enthält.  
Die kettenfähigen Methoden der Bibliothek – wie `SpatiallyContains()` und `GetPointOnSurface()` – liefern deterministische Ergebnisse und eliminieren die Notwendigkeit externer GIS‑Engines.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Umgebung einrichten
1. Installieren Sie Aspose.GIS für .NET: Laden Sie die Aspose.GIS für .NET‑Bibliothek von der **Aspose.GIS for .NET download page**([here](https://releases.aspose.com/gis/net/)) herunter und installieren Sie sie.  
2. Richten Sie Ihre Entwicklungsumgebung ein: Verwenden Sie Visual Studio, Rider oder eine beliebige .NET‑kompatible IDE Ihrer Wahl.  
3. Grundkenntnisse in C#: Sie sollten mit Klassen, Methoden und einfachen Konsolen‑App‑Projekten vertraut sein.  
4. Zugriff auf die Dokumentation: Halten Sie die **Aspose.GIS documentation**([documentation](https://reference.aspose.com/gis/net/)) während des gesamten Tutorials griffbereit.

## Namensräume importieren
Bevor wir mit der Implementierung beginnen, importieren wir zunächst die erforderlichen Namensräume:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Polygongeometrie in C# erstellen
Zuerst müssen wir eine **Polygon**‑Geometrie **erstellen**. Wir definieren den äußeren Ring des Polygons, indem wir seine Eckpunkte angeben.

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

### Schritt 2: Punkt auf der Oberfläche erhalten
Die Methode `GetPointOnSurface()` gibt einen einzelnen inneren Punkt zurück, der garantiert innerhalb des Polygonbereichs liegt. Anschließend holen wir mit dieser Methode einen Punkt auf der Oberfläche des Polygons. Dies ist der **Punkt auf der Oberfläche erhalten**‑Schritt.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

### Schritt 3: Punkt innerhalb eines Polygons prüfen
Die Methode `SpatiallyContains()` prüft, ob eine Geometrie eine andere vollständig enthält und gibt true oder false zurück. Wir können damit überprüfen, ob der abgerufene Punkt innerhalb des Polygons liegt. Dies demonstriert das **Abrufen eines Punkts auf dem Polygon** und anschließend das Prüfen.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Wie man die Polygon‑Enthaltung in C# testet
Sie testen die Polygon‑Enthaltung, indem Sie die Polygongeometrie erstellen, `GetPointOnSurface()` aufrufen, um einen inneren Punkt zu erhalten, und anschließend `SpatiallyContains()` verwenden, um zu prüfen, ob der Punkt innerhalb liegt. Dieses zweistufige Muster funktioniert für jedes gültige Polygon und skaliert bei großen Datensätzen, wenn es mit Lazy Loading kombiniert wird.

## Häufige Probleme und Lösungen
- **Leeres Polygon** – Stellen Sie sicher, dass der äußere Ring mindestens drei verschiedene Eckpunkte hat; andernfalls kann `GetPointOnSurface()` einen undefinierten Punkt zurückgeben.  
- **Uhrzeigersinn vs. Gegenuhrzeigersinn** – Die Orientierung des Rings beeinflusst die Enthaltungsprüfung nicht, aber eine konsistente Windungsreihenfolge hilft bei anderen räumlichen Operationen.  
- **Koordinatensystem** – Das Beispiel verwendet ein einfaches kartesisches Koordinatensystem; bei der Arbeit mit realen Koordinaten stellen Sie sicher, dass das CRS (Coordinate Reference System) korrekt definiert ist.

## Häufig gestellte Fragen

### FAQ

#### Ist Aspose.GIS mit anderen .NET‑Frameworks kompatibel?
Ja, Aspose.GIS unterstützt verschiedene .NET‑Frameworks, einschließlich .NET Framework, .NET Core und .NET Standard.

#### Kann ich Aspose.GIS vor dem Kauf testen?
Ja, Sie können eine kostenlose Testversion von Aspose.GIS von der **Aspose.GIS free trial download page**([here](https://releases.aspose.com/)) herunterladen.

#### Wie kann ich Support für Aspose.GIS erhalten?
Sie können das **Aspose.GIS forum**([here](https://forum.aspose.com/c/gis/33)) besuchen, um Hilfe zu erhalten und mit anderen Benutzern und Entwicklern zu interagieren.

#### Bietet Aspose.GIS temporäre Lizenzen an?
Ja, Sie können temporäre Lizenzen für Aspose.GIS von der **temporary license page**([here](https://purchase.aspose.com/temporary-license/)) erhalten.

#### Wo kann ich Aspose.GIS kaufen?
Sie können Aspose.GIS über die **Aspose.GIS purchase page**([here](https://purchase.aspose.com/buy)) erwerben.

### Zusätzliche Fragen & Antworten

**Q:** Was ist der beste Weg, große Polygon‑Datensätze zu handhaben?  
**A:** Laden Sie Geometrien lazy und verwenden Sie eine einzelne `GeometryFactory`‑Instanz wieder, um den Speicherverbrauch zu reduzieren.

**Q:** Kann ich mehrere Punkte auf der Oberfläche erhalten?  
**A:** `GetPointOnSurface()` gibt einen einzelnen inneren Punkt zurück. Um mehrere innere Punkte zu erzeugen, können Sie einen Zufallspunktgenerator innerhalb der Begrenzungsbox des Polygons verwenden und jeden mit `SpatiallyContains()` testen.

**Q:** Ist es möglich, das Polygon nach der Erstellung in eine Shapefile zu exportieren?  
**A:** Ja, Aspose.GIS stellt die Klassen `FeatureSet` und `ShapefileWriter` zur Verfügung, um Geometrien im Shapefile‑Format zu schreiben.

## Fazit
In diesem Tutorial haben wir gelernt, wie man **Punkt innerhalb eines Polygons prüft** mit Aspose.GIS für .NET, einen **Punkt auf der Oberfläche** erhält und dessen Enthaltung überprüft. Mit Aspose.GIS wird die Verarbeitung geodaten effizient und unkompliziert, sodass Sie robuste geospatiale Anwendungen bauen können, die von einfachen Karten bis zu Unternehmens‑Spatial‑Analytics skalieren.

---

**Zuletzt aktualisiert:** 2026-08-13  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Polygongeometrie mit Aspose.GIS für .NET erstellt](/gis/net/geometry-creation/create-polygon-geometry/)
- [Punkt innerhalb eines Polygons C# – Geometrie enthält andere prüfen](/gis/net/geometry-analysis/check-geometry-contains-another/)
- [Wie man den Schwerpunkt einer Geometrie mit Aspose.GIS für .NET berechnet](/gis/net/geometry-analysis/get-geometry-centroid/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}