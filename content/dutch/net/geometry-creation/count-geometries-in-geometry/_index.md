---
title: Tel geometrieën in geometrie met Aspose.GIS
linktitle: Tel geometrieën in geometrie
second_title: Aspose.GIS .NET-API
description: Leer hoe u geometrieën in een geometrie kunt tellen met Aspose.GIS voor .NET. Stapsgewijze tutorial met codevoorbeelden voor ontwikkelaars.
type: docs
weight: 23
url: /nl/net/geometry-creation/count-geometries-in-geometry/
---
## Invoering
Aspose.GIS voor .NET is een krachtig hulpmiddel voor ontwikkelaars die georuimtelijke functionaliteit willen opnemen in hun .NET-toepassingen. Of u nu kaartsoftware, locatiegebaseerde services of tools voor ruimtelijke analyse bouwt, Aspose.GIS biedt een uitgebreide reeks functies om aan uw behoeften te voldoen. In deze zelfstudie onderzoeken we hoe u geometrieën binnen een geometrie kunt tellen met behulp van Aspose.GIS voor .NET.
## Vereisten
Voordat u in deze zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Visual Studio: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd.
2. Aspose.GIS voor .NET: Download en installeer Aspose.GIS voor .NET vanaf de[downloadpagina](https://releases.aspose.com/gis/net/).
3. Basiskennis van C#: maak uzelf vertrouwd met de basisprincipes van de programmeertaal C#.

## Naamruimten importeren
Voordat u begint met coderen, moet u de benodigde naamruimten importeren om toegang te krijgen tot de Aspose.GIS-functionaliteit.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 2: Maak puntgeometrie
```csharp
Point point = new Point(40.7128, -74.006);
```
 Hier creëren we een`Point` geometrie met breedtegraad 40,7128 en lengtegraad -74,006.
## Stap 3: Maak LineString-geometrie
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Met deze stap wordt een`LineString` geometrie en voegt er twee punten aan toe.
## Stap 4: Maak een geometriecollectie
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Wij maken dan een`GeometryCollection` en voeg de eerder gemaakte punt- en lijngeometrieën eraan toe.
## Stap 5: Tel geometrieën
```csharp
int geometriesCount = geometryCollection.Count;
```
 Deze stap telt het aantal geometrieën binnen de`GeometryCollection`.
## Stap 6: Geef de telling weer
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Ten slotte drukken we het aantal geometrieën af, wat in dit geval het geval is`2`.

## Conclusie
In deze tutorial hebben we geleerd hoe je geometrieën binnen een geometrie kunt tellen met behulp van Aspose.GIS voor .NET. Door deze stappen te volgen, kunt u eenvoudig geospatiale functionaliteit in uw .NET-applicaties integreren.
## Veelgestelde vragen
### Is Aspose.GIS voor .NET geschikt voor zowel desktop- als webapplicaties?
Ja, Aspose.GIS voor .NET kan naadloos worden gebruikt in zowel desktop- als webapplicaties.
### Kan ik ruimtelijke zoekopdrachten uitvoeren met Aspose.GIS voor .NET?
Absoluut, Aspose.GIS voor .NET biedt robuuste ondersteuning voor het uitvoeren van ruimtelijke zoekopdrachten op geometrieën.
### Ondersteunt Aspose.GIS voor .NET verschillende GIS-bestandsformaten?
Ja, Aspose.GIS voor .NET ondersteunt een breed scala aan GIS-bestandsindelingen, waaronder SHP, KML en GeoJSON.
### Is er een gratis proefversie beschikbaar voor Aspose.GIS voor .NET?
 Ja, u kunt een gratis proefversie downloaden van de[website](https://releases.aspose.com/).
### Waar kan ik ondersteuning vinden voor Aspose.GIS voor .NET?
 Ondersteuning vindt u op de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33).