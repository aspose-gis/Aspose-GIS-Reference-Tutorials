---
date: 2026-02-13
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET prüfen, ob ein Punkt innerhalb
  eines Polygons liegt, Polygongeometrie erstellen und einen Punkt auf der Oberfläche
  in C# erhalten. Schritt‑für‑Schritt‑Anleitung mit vollständigem Codebeispiel.
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: Punkt im Polygon prüfen und Punkt auf Oberfläche erhalten
url: /de/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Punkt innerhalb eines Polygons prüfen und Punkt auf Oberfläche erhalten

## Einführung
In diesem Tutorial lernen Sie **wie man prüft, ob ein Punkt innerhalb eines Polygons liegt** mit Aspose.GIS für .NET und sehen außerdem, **wie man einen Punkt auf der Oberfläche** einer Geometrie erhält. Wir gehen Schritt für Schritt durch das Erstellen einer Polygongeometrie in C#, das Abrufen eines Punktes, der auf der Oberfläche des Polygons liegt, und die Überprüfung, dass der Punkt tatsächlich innerhalb des Polygons liegt. Am Ende haben Sie ein einsatzbereites Snippet, das Sie in jede .NET-Geodatenanwendung einbinden können.

## Schnelle Antworten
- **Was bedeutet „Punkt innerhalb eines Polygons prüfen“?** Es überprüft, ob ein gegebener Koordinatenpunkt innerhalb der Grenzen einer Polygongeometrie liegt.  
- **Welche Methode gibt einen Punkt im Inneren eines Polygons zurück?** `GetPointOnSurface()` gibt einen Punkt zurück, der garantiert innerhalb des Polygons liegt.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Vollversion erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework, .NET Core und .NET Standard sind alle kompatibel.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten zum Kopieren, Kompilieren und Ausführen.

## Was ist „Punkt innerhalb eines Polygons prüfen“?
Das Prüfen, ob ein Punkt innerhalb eines Polygons liegt, ist eine grundlegende räumliche Operation. Sie beantwortet die Frage „Liegt diese Koordinate innerhalb des vom Polygon definierten Bereichs?“ Dies ist für Aufgaben wie Geofencing, Kartenanalysen und räumliche Validierung unerlässlich.

## Warum Aspose.GIS für diese Aufgabe verwenden?
Aspose.GIS bietet eine leistungsstarke, vollständig verwaltete API, die komplexe Geometrieoperationen ohne externe Abhängigkeiten verarbeitet. Sie unterstützt eine Vielzahl von Koordinatenreferenzsystemen, funktioniert auf allen wichtigen .NET‑Laufzeiten und bietet klare, kaskadierbare Methoden wie `SpatiallyContains()` und `GetPointOnSurface()`.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Umgebung einrichten
1. Installieren Sie Aspose.GIS für .NET: Laden Sie die Aspose.GIS für .NET‑Bibliothek von [hier](https://releases.aspose.com/gis/net/) herunter und installieren Sie sie.  
2. Richten Sie Ihre Entwicklungsumgebung ein: Stellen Sie sicher, dass Sie eine funktionierende Entwicklungsumgebung für .NET‑Programmierung haben. Falls nicht, können Sie Visual Studio oder eine andere .NET‑Entwicklungsumgebung Ihrer Wahl einrichten.  
3. Grundkenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut, falls Sie noch nicht damit vertraut sind.  
4. Zugriff auf die Dokumentation: Halten Sie die [Dokumentation](https://reference.aspose.com/gis/net/) für die gesamte Dauer des Tutorials griffbereit.

## Namespaces importieren
Bevor wir in die Implementierung eintauchen, beginnen wir mit dem Import der erforderlichen Namespaces:

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

### Schritt 2: Punkt auf Oberfläche erhalten
Als Nächstes rufen wir mit der Methode `GetPointOnSurface()` einen Punkt auf der Oberfläche des Polygons ab. Dies ist der **Punkt‑auf‑Oberfläche‑Schritt**.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

### Schritt 3: Punkt innerhalb des Polygons prüfen
Wir können überprüfen, ob der abgerufene Punkt innerhalb des Polygons liegt, indem wir die Methode `SpatiallyContains()` verwenden. Dies demonstriert das **Abrufen eines Punktes auf dem Polygon** und anschließend das Prüfen.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Häufige Probleme und Lösungen
- **Leeres Polygon** – Stellen Sie sicher, dass der äußere Ring mindestens drei verschiedene Eckpunkte hat; andernfalls kann `GetPointOnSurface()` einen undefinierten Punkt zurückgeben.  
- **Uhrzeigersinn vs. Gegen‑Uhrzeigersinn** – Die Orientierung des Rings beeinflusst die Enthaltenheitsprüfung nicht, aber eine konsistente Windungsrichtung hilft bei anderen räumlichen Operationen.  
- **Koordinatensystem** – Das Beispiel verwendet ein einfaches kartesisches Koordinatensystem; bei der Arbeit mit realen Koordinaten stellen Sie sicher, dass das CRS (Coordinate Reference System) korrekt definiert ist.

## Häufig gestellte Fragen

### FAQ
#### Ist Aspose.GIS mit anderen .NET‑Frameworks kompatibel?
Ja, Aspose.GIS unterstützt verschiedene .NET‑Frameworks, einschließlich .NET Framework, .NET Core und .NET Standard.

#### Kann ich Aspose.GIS vor dem Kauf testen?
Ja, Sie können eine kostenlose Testversion von Aspose.GIS von [hier](https://releases.aspose.com/) herunterladen.

#### Wie kann ich Support für Aspose.GIS erhalten?
Sie können das Aspose.GIS‑Forum [hier](https://forum.aspose.com/c/gis/33) besuchen, um Unterstützung zu erhalten und mit anderen Benutzern und Entwicklern zu interagieren.

#### Bietet Aspose.GIS temporäre Lizenzen an?
Ja, Sie können temporäre Lizenzen für Aspose.GIS von [hier](https://purchase.aspose.com/temporary-license/) erhalten.

#### Wo kann ich Aspose.GIS kaufen?
Sie können Aspose.GIS über die Kaufseite [hier](https://purchase.aspose.com/buy) erwerben.

### Zusätzliche Fragen & Antworten

**F:** Was ist der beste Weg, große Polygon‑Datensätze zu handhaben?  
**A:** Laden Sie Geometrien lazy (nach Bedarf) und verwenden Sie eine einzelne `GeometryFactory`‑Instanz wieder, um den Speicherverbrauch zu reduzieren.

**F:** Kann ich mehrere Punkte auf der Oberfläche abrufen?  
**A:** `GetPointOnSurface()` gibt einen einzelnen Innenpunkt zurück. Um mehrere Innenpunkte zu erzeugen, können Sie einen Zufallspunkt‑Generator innerhalb der Begrenzungsbox des Polygons verwenden und jeden mit `SpatiallyContains()` testen.

**F:** Ist es möglich, das Polygon nach der Erstellung in eine Shapefile zu exportieren?  
**A:** Ja, Aspose.GIS stellt die Klassen `FeatureSet` und `ShapefileWriter` bereit, um Geometrien im Shapefile‑Format zu schreiben.

## Fazit
In diesem Tutorial haben wir gelernt, wie man mit Aspose.GIS für .NET **prüft, ob ein Punkt innerhalb eines Polygons liegt**, einen **Punkt auf der Oberfläche** erhält und dessen Enthaltensein überprüft. Mit Aspose.GIS wird die Verarbeitung von Geodaten effizient und unkompliziert, sodass Entwickler robuste Geodatenanwendungen erstellen können.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}