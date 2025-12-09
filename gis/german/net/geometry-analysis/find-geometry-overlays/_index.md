---
date: 2025-12-07
description: Erfahren Sie, wie Sie Overlay-Operationen in diesem Spatial‑Overlay‑Tutorial
  mit Aspose.GIS für .NET durchführen. Beherrschen Sie Schnittmenge, Vereinigung,
  Differenz und symmetrische Differenz.
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: So führen Sie Overlay‑Operationen mit Aspose.GIS für .NET durch.
url: /de/net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Overlay‑Operationen mit Aspose.GIS für .NET durchführt

## Einführung
Overlay‑Analyse ist eine Kerntechnik in jedem **spatial overlay tutorial** — sie ermöglicht das Kombinieren, Vergleichen und Extrahieren von Erkenntnissen aus mehreren geografischen Ebenen. In diesem Leitfaden lernen Sie **wie man Overlay**‑Operationen wie Intersection, Union, Difference und Symmetric Difference mit der leistungsstarken Aspose.GIS‑Bibliothek für .NET ausführt. Am Ende des Tutorials können Sie diese Methoden auf reale GIS‑Probleme wie Flächennutzungsplanung, Umweltverträglichkeitsstudien und Routenoptimierung anwenden.

## Schnellantworten
- **Was ist eine Overlay‑Operation?** Eine räumliche Methode, die zwei Geometrien kombiniert, um eine neue Geometrie zu erzeugen (Intersection, Union usw.).  
- **Welche Bibliothek verarbeitet Overlays in .NET?** Aspose.GIS für .NET.  
- **Wie lange dauert die Implementierung?** Ungefähr 10‑15 Minuten für das Basisbeispiel.  
- **Benötige ich eine Lizenz?** Eine Testversion ist kostenlos; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Läuft das auf .NET Core / .NET 6+?** Ja — Aspose.GIS unterstützt alle modernen .NET‑Laufzeiten.

## Was ist eine Overlay‑Operation?
Eine Overlay‑Operation nimmt zwei geometrische Formen und berechnet eine neue Form basierend auf ihrer räumlichen Beziehung.  
- **Intersection** liefert die Fläche, die beiden Formen gemeinsam ist.  
- **Union** fügt die Formen zu einer einzigen Geometrie zusammen.  
- **Difference** subtrahiert eine Form von der anderen.  
- **Symmetric Difference** liefert die Teile, die zu einer der beiden Formen gehören, aber nicht zu beiden.

## Warum Aspose.GIS für Overlays verwenden?
Aspose.GIS bietet eine saubere, vollständig verwaltete API, die die Low‑Level‑Mathematik abstrahiert und Ihnen ermöglicht, sich auf die Geschäftslogik zu konzentrieren. Sie funktioniert plattformübergreifend, verarbeitet große Datensätze effizient und lässt sich nahtlos in andere .NET‑Komponenten integrieren.

## Voraussetzungen
- Eine funktionierende .NET‑Entwicklungsumgebung (Visual Studio, VS Code oder die .NET‑CLI).  
- Aspose.GIS für .NET‑Bibliothek — laden Sie die neueste Version von der [offiziellen Seite](https://releases.aspose.com/gis/net/) herunter.  

### Namespaces importieren
Bevor Sie Aspose.GIS für .NET verwenden können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie man Overlay‑Operationen in .NET durchführt
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Durchführung zum Erstellen zweier Polygone und zur Anwendung jeder Overlay‑Methode.

### Schritt 1: Polygon‑Objekte erstellen
Zunächst definieren wir zwei einfache Quadrat‑Polygone, die sich teilweise überschneiden. Diese dienen als Testdaten.

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### Schritt 2: Intersection‑Operation ausführen
Die **Intersection** liefert uns die überlappende Fläche der beiden Polygone.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Schritt 3: Intersection‑Punkte ausgeben
Wir verwenden eine Hilfsmethode (`PrintRing`), um die Koordinaten des resultierenden Polygons anzuzeigen.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Schritt 4: Union‑Operation ausführen
Die **Union** fügt beide Polygone zu einer einzigen Form zusammen, die die gesamte von beiden Polygonen bedeckte Fläche umfasst.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Schritt 5: Union‑Punkte ausgeben
Geben Sie die Koordinaten der vereinheitlichten Geometrie aus.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Schritt 6: Difference‑Operation ausführen
**Difference** subtrahiert `polygon2` von `polygon1` und lässt nur den Teil von `polygon1` übrig, der nicht mit `polygon2` überlappt.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Schritt 7: Difference‑Punkte ausgeben
Zeigen Sie die verbleibenden Eckpunkte nach der Subtraktion an.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Schritt 8: Symmetric Difference‑Operation ausführen
Die **Symmetric Difference** liefert die Flächen, die zu einem der beiden Polygone gehören, aber nicht zu beiden. Das Ergebnis ist ein `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Schritt 9: Symmetric Difference‑Polygone ausgeben
Iterieren Sie über jedes Polygon im `MultiPolygon` und geben Sie dessen Punkte aus.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| `null`‑Ergebnis von `Intersection` | Polygone überschneiden sich tatsächlich nicht. | Koordinaten überprüfen oder vor dem Aufruf von `Intersection` `Intersects` prüfen. |
| Unerwartetes `MultiPolygon` von `SymDifference` | Die symmetrische Differenz kann disjunkte Komponenten erzeugen. | Zu `IMultiPolygon` casten und wie gezeigt iterieren. |
| Leistungsabfall bei großen Datensätzen | Jede Operation berechnet die Geometrie von Grund auf neu. | Zwischenergebnisse wiederverwenden oder Geometrien vor dem Overlay mit `Simplify()` vereinfachen. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.GIS für .NET in kommerziellen Projekten verwenden?**  
A: Ja, Aspose.GIS für .NET kann sowohl in kommerziellen als auch in nicht‑kommerziellen Projekten mit einer gültigen Lizenz verwendet werden.

**F: Gibt es eine Testversion von Aspose.GIS für .NET?**  
A: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) herunterladen.

**F: Wie erhalte ich Support für Aspose.GIS für .NET?**  
A: Support erhalten Sie im Aspose.GIS‑Community‑Forum [hier](https://forum.aspose.com/c/gis/33).

**F: Gibt es temporäre Lizenzen für Aspose.GIS für .NET?**  
A: Ja, temporäre Lizenzen stehen für Test‑ und Evaluierungszwecke zur Verfügung. Sie können sie [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**F: Kann ich Aspose.GIS für .NET direkt kaufen?**  
A: Ja, Sie können Aspose.GIS für .NET über die Website [hier](https://purchase.aspose.com/buy) erwerben.

---

**Zuletzt aktualisiert:** 2025-12-07  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}