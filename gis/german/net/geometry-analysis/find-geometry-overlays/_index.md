---
title: Beherrschen von Geometrieüberlagerungen mit Aspose.GIS für .NET
linktitle: Finden Sie Geometrie-Overlays
second_title: Aspose.GIS .NET-API
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET geometrische Überlagerungsvorgänge durchführen. Meistern Sie Schnitt-, Vereinigungs-, Differenz- und symmetrische Differenzoperationen.
type: docs
weight: 16
url: /de/net/geometry-analysis/find-geometry-overlays/
---
## Einführung
Im Bereich der geografischen Informationssysteme (GIS) sind Overlay-Operationen von grundlegender Bedeutung für die räumliche Analyse. Sie ermöglichen den Vergleich und die Kombination verschiedener Geodatensätze, um wertvolle Erkenntnisse abzuleiten. Aspose.GIS für .NET bietet robuste Funktionen für die effiziente Durchführung geometrischer Überlagerungen. In diesem Tutorial befassen wir uns mit verschiedenen Überlagerungsoperationen wie Schnittmenge, Vereinigung, Differenz und symmetrischer Differenz mithilfe von Aspose.GIS für .NET.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. .NET-Entwicklungsumgebung
Stellen Sie sicher, dass auf Ihrem Computer eine .NET-Entwicklungsumgebung eingerichtet ist. Sie können das .NET SDK von der .NET-Website herunterladen und installieren.
### 2. Aspose.GIS für .NET-Bibliothek
 Laden Sie die Aspose.GIS für .NET-Bibliothek von herunter und installieren Sie sie[Webseite](https://releases.aspose.com/gis/net/).
## Namespaces importieren
Bevor Sie Aspose.GIS für .NET verwenden können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Polygonobjekte erstellen
Zuerst definieren wir zwei Polygonobjekte, die räumliche Regionen darstellen.
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
## Schritt 2: Kreuzungsvorgang durchführen
Als nächstes suchen wir den Schnittpunkt der beiden Polygone.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```
## Schritt 3: Schnittpunkte drucken
Wir drucken die Punkte des Schnittpolygons.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Schritt 4: Führen Sie die Union-Operation durch
Lassen Sie uns nun die Vereinigung der beiden Polygone finden.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```
## Schritt 5: Union Points drucken
Drucken Sie die Punkte des Vereinigungspolygons.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Schritt 6: Differenzoperation durchführen
Als nächstes wollen wir den Unterschied zwischen den beiden Polygonen ermitteln.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```
## Schritt 7: Differenzpunkte drucken
Drucken Sie die Punkte des Differenzpolygons.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Schritt 8: Führen Sie eine symmetrische Differenzoperation durch
Lassen Sie uns abschließend den symmetrischen Unterschied zwischen den beiden Polygonen ermitteln.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```
## Schritt 9: Symmetrische Differenzpolygone drucken
Drucken Sie die Punkte jedes Polygons in der symmetrischen Differenz aus.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Abschluss
Die Beherrschung von Geometrieüberlagerungen ist bei der räumlichen Analyse von entscheidender Bedeutung und Aspose.GIS für .NET bietet einen umfassenden Satz an Werkzeugen, um diese Vorgänge effizient durchzuführen. Durch die Befolgung dieses Tutorials haben Sie gelernt, wie Sie Aspose.GIS für .NET verwenden, um Schnitt-, Vereinigungs-, Differenz- und symmetrische Differenzoperationen für geometrische Formen durchzuführen.
## FAQs
### F: Kann ich Aspose.GIS für .NET in meinen kommerziellen Projekten verwenden?
Ja, Aspose.GIS für .NET kann sowohl in kommerziellen als auch nichtkommerziellen Projekten verwendet werden.
### F: Gibt es eine Testversion für Aspose.GIS für .NET?
 Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
### F: Wie erhalte ich Unterstützung für Aspose.GIS für .NET?
 Unterstützung erhalten Sie im Aspose.GIS-Community-Forum[Hier](https://forum.aspose.com/c/gis/33).
### F: Gibt es temporäre Lizenzen für Aspose.GIS für .NET?
 Ja, temporäre Lizenzen sind für Test- und Evaluierungszwecke verfügbar. Sie können sie bei beziehen[Hier](https://purchase.aspose.com/temporary-license/).
### F: Kann ich Aspose.GIS für .NET direkt kaufen?
 Ja, Sie können Aspose.GIS für .NET auf der Website erwerben[Hier](https://purchase.aspose.com/buy).