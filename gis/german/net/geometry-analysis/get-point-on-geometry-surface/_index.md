---
date: 2025-12-09
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET prüfen, ob ein Punkt innerhalb
  eines Polygons liegt. Schritt‑für‑Schritt‑Anleitung zum Ermitteln eines Punktes
  auf der Oberfläche, zum Erstellen eines Polygons in C# und zum Abrufen eines Punktes
  im Polygon.
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: Punkt im Polygon prüfen und Punkt auf der Oberfläche ermitteln
url: /de/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Punkt innerhalb eines Polygons prüfen und Punkt auf Oberfläche erhalten

## Einleitung
In diesem Tutorial lernen Sie **wie man prüft, ob ein Punkt innerhalb eines Polygons liegt** mit Aspose.GIS für .NET und sehen außerdem, wie man **einen Punkt auf der Oberfläche** einer Geometrie erhält. Wir gehen Schritt für Schritt durch das Erstellen eines Polygons in C#, das Abrufen eines Punktes, der auf der Oberfläche des Polygons liegt, und die Überprüfung, dass der Punkt tatsächlich innerhalb des Polygons liegt. Am Ende haben Sie einen einsatzbereiten Code‑Snippet, den Sie in jede .NET‑Geodaten‑Anwendung einbinden können.

## Schnelle Antworten
- **Was bedeutet „Punkt innerhalb eines Polygons prüfen“?** Es überprüft, ob ein gegebener Koordinatenwert innerhalb der Grenzen einer Polygongeometrie liegt.  
- **Welche Methode liefert einen Punkt im Inneren eines Polygons?** `GetPointOnSurface()` liefert einen Punkt, der garantiert innerhalb des Polygons liegt.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework, .NET Core und .NET Standard sind alle kompatibel.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten zum Kopieren, Kompilieren und Ausführen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Umgebung einrichten
1. Aspose.GIS für .NET installieren: Laden Sie die Aspose.GIS‑Bibliothek für .NET von [hier](https://releases.aspose.com/gis/net/) herunter und installieren Sie sie.  
2. Entwicklungsumgebung einrichten: Stellen Sie sicher, dass Sie eine funktionierende Entwicklungsumgebung für .NET‑Programmierung haben. Falls nicht, können Sie Visual Studio oder eine andere .NET‑Entwicklungsumgebung Ihrer Wahl einrichten.  
3. Grundkenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut, falls Sie noch nicht damit vertraut sind.  
4. Zugriff auf die Dokumentation: Halten Sie die [Dokumentation](https://reference.aspose.com/gis/net/) griffbereit für Nachschlagen während des gesamten Tutorials.

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

Jetzt, da wir unsere Umgebung eingerichtet und die benötigten Namespaces importiert haben, zerlegen wir das Beispiel in mehrere Schritte, um es besser zu verstehen.

## Wie man ein Polygon in C# erstellt  
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

## Wie man einen Punkt auf der Oberfläche erhält  
Als Nächstes rufen wir mit der Methode `GetPointOnSurface()` einen Punkt auf der Oberfläche des Polygons ab. Dies ist der Schritt **Punkt auf Oberfläche erhalten**.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## Wie man prüft, ob ein Punkt innerhalb eines Polygons liegt  
Wir können überprüfen, ob der abgerufene Punkt innerhalb des Polygons liegt, indem wir die Methode `SpatiallyContains()` verwenden. Dies demonstriert das **Abrufen eines Punktes auf dem Polygon** und anschließend die Überprüfung.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Häufige Probleme und Lösungen
- **Leeres Polygon** – Stellen Sie sicher, dass der äußere Ring mindestens drei unterschiedliche Eckpunkte hat; andernfalls kann `GetPointOnSurface()` einen undefinierten Punkt zurückgeben.  
- **Uhrzeigersinn vs. Gegen‑Uhrzeigersinn** – Die Orientierung des Rings beeinflusst die Containment‑Prüfung nicht, aber ein konsistenter Windungsrichtung hilft bei anderen räumlichen Operationen.  
- **Koordinatensystem** – Das Beispiel verwendet ein einfaches kartesisches Koordinatensystem; bei der Arbeit mit realen Koordinaten stellen Sie sicher, dass das CRS (Coordinate Reference System) korrekt definiert ist.

## Fazit
In diesem Tutorial haben wir gelernt, wie man mit Aspose.GIS für .NET **prüft, ob ein Punkt innerhalb eines Polygons liegt**, einen **Punkt auf der Oberfläche** erhält und dessen Zugehörigkeit überprüft. Mit Aspose.GIS wird die Verarbeitung von Geodaten effizient und unkompliziert, sodass Entwickler robuste Geodaten‑Anwendungen erstellen können.

## FAQ
### Ist Aspose.GIS mit anderen .NET‑Frameworks kompatibel?
Ja, Aspose.GIS unterstützt verschiedene .NET‑Frameworks, einschließlich .NET Framework, .NET Core und .NET Standard.

### Kann ich Aspose.GIS vor dem Kauf testen?
Ja, Sie können eine kostenlose Testversion von Aspose.GIS von [hier](https://releases.aspose.com/) herunterladen.

### Wie kann ich Support für Aspose.GIS erhalten?
Sie können das Aspose.GIS‑Forum [hier](https://forum.aspose.com/c/gis/33) besuchen, um Unterstützung zu erhalten und sich mit anderen Benutzern und Entwicklern auszutauschen.

### Bietet Aspose.GIS temporäre Lizenzen an?
Ja, Sie können temporäre Lizenzen für Aspose.GIS von [hier](https://purchase.aspose.com/temporary-license/) erhalten.

### Wo kann ich Aspose.GIS kaufen?
Sie können Aspose.GIS über die Kaufseite [hier](https://purchase.aspose.com/buy) erwerben.

**Zusätzliche Fragen & Antworten**

**Q:** Was ist der beste Weg, große Polygon‑Datensätze zu verarbeiten?  
**A:** Laden Sie Geometrien lazy und verwenden Sie eine einzelne `GeometryFactory`‑Instanz, um den Speicherverbrauch zu reduzieren.

**Q:** Kann ich mehrere Punkte auf der Oberfläche abrufen?  
**A:** `GetPointOnSurface()` liefert einen einzelnen Innenpunkt. Um mehrere Innenpunkte zu erzeugen, können Sie einen Zufallspunkt‑Generator innerhalb der Begrenzungsbox des Polygons verwenden und jeden mit `SpatiallyContains()` testen.

**Q:** Ist es möglich, das Polygon nach der Erstellung in eine Shapefile zu exportieren?  
**A:** Ja, Aspose.GIS stellt die Klassen `FeatureSet` und `ShapefileWriter` bereit, um Geometrien im Shapefile‑Format zu schreiben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---