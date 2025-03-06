---
title: Bemästra geometriöverlägg med Aspose.GIS för .NET
linktitle: Hitta geometriöverlägg
second_title: Aspose.GIS .NET API
description: Lär dig hur du utför geometriska överlagringsoperationer med Aspose.GIS för .NET. Mästarkorsning, förening, skillnad och symmetriska skillnadsoperationer.
weight: 16
url: /sv/net/geometry-analysis/find-geometry-overlays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra geometriöverlägg med Aspose.GIS för .NET

## Introduktion
Inom området för geografiska informationssystem (GIS) är överlagringsoperationer grundläggande för rumslig analys. De möjliggör jämförelse och kombination av olika rumsliga datamängder för att få värdefulla insikter. Aspose.GIS för .NET tillhandahåller robusta funktioner för att utföra geometriska överlagringar effektivt. I den här handledningen kommer vi att fördjupa oss i olika överlagringsoperationer som Intersection, Union, Difference och Symmetric Difference med Aspose.GIS för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
### 1. .NET utvecklingsmiljö
Se till att du har en .NET-utvecklingsmiljö inställd på din dator. Du kan ladda ner och installera .NET SDK från .NET-webbplatsen.
### 2. Aspose.GIS för .NET Library
 Ladda ner och installera Aspose.GIS för .NET-biblioteket från[hemsida](https://releases.aspose.com/gis/net/).
## Importera namnområden
Innan du kan börja använda Aspose.GIS för .NET måste du importera de nödvändiga namnrymden till ditt projekt.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 1: Skapa polygonobjekt
Först kommer vi att definiera två polygonobjekt som representerar rumsliga områden.
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
## Steg 2: Utför korsningsoperation
Låt oss sedan hitta skärningspunkten mellan de två polygonerna.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```
## Steg 3: Skriv ut skärningspunkter
Vi skriver ut punkterna för skärningspolygonen.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Steg 4: Utför Union Operation
Låt oss nu hitta föreningen av de två polygonerna.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```
## Steg 5: Skriv ut Union Points
Skriv ut punkterna för unionspolygonen.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Steg 6: Utför skillnadsoperation
Låt oss sedan hitta skillnaden mellan de två polygonerna.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```
## Steg 7: Skriv ut skillnadspunkter
Skriv ut punkterna för differenspolygonen.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Steg 8: Utför symmetrisk skillnadsoperation
Låt oss slutligen hitta den symmetriska skillnaden mellan de två polygonerna.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // Multipolygon
```
## Steg 9: Skriv ut symmetriska skillnadspolygoner
Skriv ut punkterna för varje polygon i den symmetriska skillnaden.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Slutsats
Att bemästra geometriöverlagringar är avgörande i rumslig analys och Aspose.GIS för .NET tillhandahåller en omfattande uppsättning verktyg för att utföra dessa operationer effektivt. Genom att följa denna handledning har du lärt dig hur du använder Aspose.GIS för .NET för att utföra skärnings-, förenings-, skillnads- och symmetriska skillnadsoperationer på geometriska former.
## FAQ's
### F: Kan jag använda Aspose.GIS för .NET i mina kommersiella projekt?
Ja, Aspose.GIS för .NET kan användas i både kommersiella och icke-kommersiella projekt.
### F: Finns det en testversion tillgänglig för Aspose.GIS för .NET?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### F: Hur kan jag få support för Aspose.GIS för .NET?
 Du kan få stöd från Aspose.GIS community forum[här](https://forum.aspose.com/c/gis/33).
### F: Finns det några tillfälliga licenser tillgängliga för Aspose.GIS för .NET?
 Ja, tillfälliga licenser är tillgängliga för test- och utvärderingssyften. Du kan få dem från[här](https://purchase.aspose.com/temporary-license/).
### F: Kan jag köpa Aspose.GIS för .NET direkt?
 Ja, du kan köpa Aspose.GIS för .NET från webbplatsen[här](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
