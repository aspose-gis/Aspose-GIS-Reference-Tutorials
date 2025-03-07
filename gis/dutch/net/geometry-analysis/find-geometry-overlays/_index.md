---
title: Beheersing van geometrie-overlays met Aspose.GIS voor .NET
linktitle: Vind geometrie-overlays
second_title: Aspose.GIS .NET-API
description: Leer hoe u geometrische overlay-bewerkingen uitvoert met Aspose.GIS voor .NET. Master-bewerkingen op het gebied van snijpunten, samenvoegingen, verschillen en symmetrische verschillen.
weight: 16
url: /nl/net/geometry-analysis/find-geometry-overlays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheersing van geometrie-overlays met Aspose.GIS voor .NET

## Invoering
Op het gebied van geografische informatiesystemen (GIS) zijn overlay-operaties van fundamenteel belang voor ruimtelijke analyse. Ze maken de vergelijking en combinatie van verschillende ruimtelijke datasets mogelijk om waardevolle inzichten te verkrijgen. Aspose.GIS voor .NET biedt robuuste functionaliteiten voor het efficiënt uitvoeren van geometrische overlays. In deze zelfstudie gaan we dieper in op verschillende overlay-bewerkingen, zoals Intersection, Union, Difference en Symmetric Difference met behulp van Aspose.GIS voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. .NET-ontwikkelomgeving
Zorg ervoor dat er een .NET-ontwikkelomgeving op uw computer is geïnstalleerd. U kunt de .NET SDK downloaden en installeren vanaf de .NET-website.
### 2. Aspose.GIS voor .NET-bibliotheek
 Download en installeer Aspose.GIS voor .NET-bibliotheek vanuit de[website](https://releases.aspose.com/gis/net/).
## Naamruimten importeren
Voordat u Aspose.GIS voor .NET kunt gaan gebruiken, moet u de benodigde naamruimten in uw project importeren.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: maak polygoonobjecten
Eerst definiëren we twee polygoonobjecten die ruimtelijke gebieden vertegenwoordigen.
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
## Stap 2: Voer kruispuntbewerking uit
Laten we vervolgens het snijpunt van de twee polygonen vinden.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Veelhoek
```
## Stap 3: Druk kruispunten af
We printen de punten van de snijpolygoon.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Stap 4: Voer Union-operatie uit
Laten we nu de vereniging van de twee polygonen vinden.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Veelhoek
```
## Stap 5: Union-punten afdrukken
Druk de punten van de verenigingspolygoon af.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Stap 6: Voer de verschilbewerking uit
Laten we vervolgens het verschil tussen de twee polygonen vinden.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Veelhoek
```
## Stap 7: Verschilpunten afdrukken
Druk de punten van de verschilpolygoon af.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Stap 8: Voer een symmetrische verschilbewerking uit
Laten we ten slotte het symmetrische verschil tussen de twee polygonen vinden.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // Multipolygoon
```
## Stap 9: Druk symmetrische verschilpolygonen af
Druk de punten van elke veelhoek in het symmetrische verschil af.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Conclusie
Het beheersen van geometrie-overlays is cruciaal bij ruimtelijke analyse en Aspose.GIS voor .NET biedt een uitgebreide set tools om deze bewerkingen efficiënt uit te voeren. Door deze tutorial te volgen, hebt u geleerd hoe u Aspose.GIS voor .NET kunt gebruiken om bewerkingen op het gebied van snijpunten, samenvoegingen, verschillen en symmetrische verschillen uit te voeren op geometrische vormen.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.GIS voor .NET gebruiken in mijn commerciële projecten?
Ja, Aspose.GIS voor .NET kan worden gebruikt in zowel commerciële als niet-commerciële projecten.
### Vraag: Is er een proefversie beschikbaar voor Aspose.GIS voor .NET?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik ondersteuning krijgen voor Aspose.GIS voor .NET?
 U kunt ondersteuning krijgen van het Aspose.GIS-communityforum[hier](https://forum.aspose.com/c/gis/33).
### Vraag: Zijn er tijdelijke licenties beschikbaar voor Aspose.GIS voor .NET?
 Ja, er zijn tijdelijke licenties beschikbaar voor test- en evaluatiedoeleinden. U kunt ze verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Kan ik Aspose.GIS voor .NET rechtstreeks kopen?
 Ja, u kunt Aspose.GIS voor .NET aanschaffen via de website[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
