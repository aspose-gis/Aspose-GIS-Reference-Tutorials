---
date: 2026-01-31
description: Erfahren Sie, wie Sie den Abstand zwischen Geometrien mit Aspose.GIS
  für .NET berechnen. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie Sie Aspose.GIS
  verwenden, den Abstand zu einer Geometrie ermitteln und Abstandsberechnungen in
  Ihre Anwendungen integrieren.
linktitle: How to Calculate Distance Between Geometries
second_title: Aspose.GIS .NET API
title: Wie man den Abstand zwischen Geometrien mit Aspose.GIS berechnet
url: /de/net/geometry-analysis/calculate-distance-between-geometries/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man den Abstand zwischen Geometrien mit Aspose.GIS berechnet

## Einführung
Falls Sie jemals wissen mussten, **wie man den Abstand berechnet** zwischen zwei räumlichen Objekten – sei es ein Straßennetz, Lieferzonen oder Umweltelemente – ist dieser Leitfaden genau das Richtige für Sie. In .NET macht Aspose.GIS Abstandsberechnungen einfach, genau und performant. Wir gehen ein praxisnahes Beispiel durch, das **wie man Aspose.GIS verwendet**, einfache Geometrien erstellt und die **GetDistanceTo**‑Methode aufruft, um den Abstand zwischen ihnen zu erhalten.

## Schnelle Antworten
- **Was bedeutet „Abstand berechnen“ in GIS?** Es gibt den kürzesten (euklidischen) Abstand zwischen zwei Geometrien zurück.  
- **Welche Aspose.GIS‑Klasse liefert die Berechnung?** `Geometry.GetDistanceTo(Geometry other)`.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine Lizenz erforderlich.  
- **Kann ich den Abstand für 3‑D‑Geometrien berechnen?** Ja, Aspose.GIS unterstützt 2‑D‑ und 3‑D‑Berechnungen.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Wie man den Abstand zwischen Geometrien berechnet
In diesem Tutorial konzentrieren wir uns auf die Messung des **Abstands zwischen Punkt‑Polygon**‑Geometrien – eine gängige Aufgabe, wenn Sie wissen müssen, wie weit ein Feature (wie ein Sensor oder ein Kundenstandort) von einem definierten Gebiet entfernt ist. Obwohl das Beispiel ein `Polygon` und einen `LineString` verwendet, funktioniert die gleiche `GetDistanceTo`‑Methode perfekt für ein `Point`‑zu‑`Polygon`‑Szenario.

## Was ist Abstandsberechnung in der Geodaten‑Programmierung?
Die Abstandsberechnung misst die kürzeste Linie, die zwei Geometrien verbindet. Sie ist eine Kernoperation für Aufgaben wie Proximitätsanalyse, Routing, Clustering und räumliche Indizierung.

## Warum Aspose.GIS zur Abstandsberechnung verwenden?
- **Hohe Präzision** – Verwendet Double‑Precision‑Arithmetik.  
- **Null‑Abhängigkeit** – Keine nativen GIS‑Bibliotheken erforderlich.  
- **Plattformübergreifend** – Funktioniert auf Windows, Linux und macOS mit .NET Core/5+.  
- **Umfangreiches Geometriemodell** – Unterstützt Punkte, Linien, Polygone und Multi‑Geometrien sofort.

## Voraussetzungen
- **Aspose.GIS für .NET** installiert (Download von der [Aspose.GIS für .NET Releases‑Seite](https://releases.aspose.com/gis/net/)).  
- Grundkenntnisse in C# und .NET‑Projektstruktur.  
- Eine Entwicklungsumgebung wie Visual Studio 2022 oder VS Code.

## Namespaces importieren
Bevor Sie Aspose.GIS verwenden können, fügen Sie die erforderlichen Namespaces zu Ihrer C#‑Datei hinzu:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Schritt 1: Ein Polygon‑Geometry erstellen
```csharp
var polygon = new Polygon();
```
Wir beginnen mit einem leeren Polygon, das später ein rechteckiges Gebiet darstellen wird.

### Schritt 2: Den äußeren Ring des Polygons definieren
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
Der äußere Ring ist eine geschlossene Punktschleife, wir ein 1 × LineString‑Geometry erstellen
```csharp
var line = new LineString();
```
Ein `LineString` ist eine Reihe verbundener Liniensegmente. Wir verwenden ihn, um eine Straße oder einen Pfad darzustellen.

### Schritt 4: Punkte zum LineString hinzufügen
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
Diese beiden Punkte verleihen der Linie eine schräge Form, die das Polygon nicht schneidet, was die Abstandsberechnung interessant macht.

### Schritt 5: Den Abstand berechnen
```csharp
double distance = polygon.GetDistanceTo(line);
```
Hier **erhalten wir den Abstand zur Geometrie**, indem wir Aspose.GIS berechnet den### Schritt 6: Das Ergebnis ausgeben
```csharp
Console.WriteLine(distance.ToString("F")); // 0.63
```
Das Ergebnis wird mit zwei Dezimalstellen (`0.63`) ausgegeben. Dieser Wert stellt den minimalen euklidischen Abstand zwischen dem Quadrat und der Linie dar.

## Gemeinsame Anwendungsfälle
 Depot zu einer Lieferstrecke.  
- **Umweltüberwachungstoffplume von einem Schutzgebiet entfernt ist.  
- **Stadtplanung:** Bestimmen Sie den & Tipps
- **Koordinatensystem ist wichtig:** Stellen Sie sicher, dass beide Geometrien dasselbe CRS (Coordinate Reference System) verwenden, bevor Sie den Abstand berechnen.  
- **Leistung:** Bei großen Datensätzen sollten Sie räumliche Indizierung (R‑Tree) in Betracht ziehen, um O(N²)-Vergleiche zu vermeiden.  
- **Genauigkeit:** Wenn Sie geodätische (Großkreis‑)Entfernungen benötigen, transformieren Sie die Koordinaten zuerst in eine geeignete Projektion.

## FAQ

### Ist Aspose.GIS für .NET mit allen .NET‑Frameworks kompatibel?
Ja, Asp und höher.

### Kann ich Aspose.GIS für .NET verwenden, um komplexe räumliche Analysen durchzuführen?
Absolut! Aspose.GIS für .NET bietet eine breite Palette von Funktionalitäten für fortgeschrittene räumliche Analyseaufgaben.

### Unterstützt Aspose.G auch 3D‑Geometrien?
Ja, Sie können sowohl mit 2D Aspose.GIS für .NET arbeitenBibliotheken integrieren?
Aspose.GIS für .NET bietet Interoperabilität mit anderen GIS‑Bibliotheken, sodass Sie zusätzliche Funktionalitäten nutzen können.

### Steht technischer Support für Aspose.GIS‑Benutzer zur Verfügung?
Ja, Benutzer von Aspose.GIS für .NET[Foren](https://forum.aspose.com/c/gis/33) technischen Support erhalten.

## Frequently Asked Questions

**Q: Wie genau ist der von `GetDistanceTo` zurückgegebene Abstand?**  
A: Simple Features Specification, wodurch für typische planare Koordinaten eine Unter‑Meter‑Genauigkeit erreicht wird.

**Q:Polygon` berechnen?**  
A: Ja – rufen Sie einfach `point.GetDistanceTo(polygon)` (oder umgekehrt) auf, und Aspose.GIS gibt den kürzesten Abstand vom Punkt zur Polygonkante zurück.

**Q: Unterstützt die API Batch‑Abstandsberechnungen?**  
A: Zwar gibt es keine einzelne Batch‑Methode, Sie können jedoch über Sammlungen von Geometrien iterieren und denselben `GetDistanceTo`‑Aufruf effizient wiederverwenden.

**Q: Was passiert, wenn die Geometrien sich schneiden?**  
A: Die Methode gibt `0.0` zurück, weil der kürzeste Abstand zwischen sich schneidenden Geometrien null ist.

**Q: Gibt es eine Möglichkeit, die nächstgelegenen Punkte jeder Geometrie zu erhalten?**  
A: Ja – verwenden Sie `Geometry.GetNearestPoints(Geometry other)`, das ein Tupel mit den nächstgelegenen Punkten beider Geometrien zurückgibt.

## Fazit
Die Berechnung des Abstands zwischen Geometrien ist eine grundlegende Operation in jeder GIS‑fähigen .NET‑Anwendung. Durch die oben beschriebenen Schritte wissen Sie jetzt, **wie man den Abstand berechnet** mit Aspose.GIS, **wie man Aspose** verwendet, um Geometrien zu erstellen und zu manipulieren, und **wie man den Abstand zur Geometrie** mit einem einzigen Methodenaufruf abruft. Experimentieren Sie mit verschiedenen Formen, Koordinatensystemen und größeren Datensätzen, um zu sehen, wie diese Fähigkeit Ihr nächstes räumliches Analyseprojekt unterstützen kann.

---

**Zuletzt aktualisiert:** 2026-01-31  
**Getestet mit:** Aspose.G  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}