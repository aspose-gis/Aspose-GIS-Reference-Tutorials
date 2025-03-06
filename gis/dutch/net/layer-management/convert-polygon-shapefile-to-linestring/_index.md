---
title: Converteer polygoon-vormbestand naar lijntekenreeks
linktitle: Converteer polygoon-vormbestand naar lijntekenreeks
second_title: Aspose.GIS .NET-API
description: Ontdek de kracht van Aspose.GIS voor .NET en converteer Polygon Shape-bestanden moeiteloos naar Linestrings. Geef vandaag nog uw GIS-ontwikkeling een boost!
weight: 18
url: /nl/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converteer polygoon-vormbestand naar lijntekenreeks

## Invoering
Als u werkt met geografische informatiesystemen (GIS) in .NET, is Aspose.GIS een krachtige bibliotheek die uw taken kan vereenvoudigen. In deze tutorial begeleiden we u bij het converteren van een Polygon Shapefile naar een Linestring met behulp van Aspose.GIS. Dit kan met name handig zijn wanneer u lineaire kenmerken uit polygonale gegevens moet extraheren voor verschillende toepassingen, zoals routeplanning of netwerkanalyse.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je over het volgende beschikt:
-  Aspose.GIS-bibliotheek: Download en installeer de Aspose.GIS-bibliotheek van de[website](https://releases.aspose.com/gis/net/).
- Shapefile-gegevens: Zorg ervoor dat een Polygon Shapefile gereed is voor conversie. Als u er geen heeft, kunt u voorbeeldgegevens vinden of uw eigen gegevens maken.
- Ontwikkelomgeving: Richt uw .NET-ontwikkelomgeving in met de benodigde tools.
## Naamruimten importeren
In uw C#-code moet u de Aspose.GIS-naamruimten importeren om toegang te krijgen tot de vereiste klassen en methoden. Voeg de volgende naamruimten toe aan het begin van uw codebestand:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Stap 1: Stel de documentmap in
```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
```
Vervang "Uw documentenmap" door het pad naar de map waar uw Shapefile zich bevindt.
## Stap 2: Open het bron-shapebestand
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // De rest van de code komt hier terecht
}
```
Met deze stap wordt het bronpolygoonvormbestand geopend om te lezen.
## Stap 3: Maak het Shapefile voor de doellijnstring
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // De rest van de code komt hier terecht
}
```
Hier maken we een nieuw Linestring Shapefile voor het schrijven van de geconverteerde gegevens.
## Stap 4: Herhaal de bronfuncties
```csharp
foreach (Feature sourceFeature in source)
{
    // De rest van de code komt hier terecht
}
```
Deze lus doorloopt elk object in het bronpolygoonvormbestand.
## Stap 5: Converteer polygoon naar lijnstring en schrijf naar bestemming
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
In deze stap wordt elk Polygoon-object geconverteerd naar een Linestring, en het resulterende Linestring-object wordt naar het doel-Shapefile geschreven.
## Conclusie
Door deze stappen te volgen, kunt u eenvoudig een Polygon Shapefile naar een Linestring converteren met behulp van Aspose.GIS voor .NET. Dit proces opent nieuwe mogelijkheden voor data-analyse en visualisatie in GIS-toepassingen.

## Veelgestelde vragen
### Is Aspose.GIS compatibel met alle versies van .NET?
Ja, Aspose.GIS ondersteunt verschillende versies van .NET, waardoor compatibiliteit met uw ontwikkelomgeving wordt gegarandeerd.
### Kan ik Aspose.GIS gebruiken voor commerciële projecten?
 Ja, dat kan. Als u Aspose.GIS in commerciële projecten wilt gebruiken, kunt u overwegen een licentie aan te schaffen[hier](https://purchase.aspose.com/buy).
### Zijn er voorbeelden of documentatie beschikbaar?
 Ja, u kunt uitgebreide documentatie en voorbeelden vinden op de website[documentatiepagina](https://reference.aspose.com/gis/net/).
### Is er een proefversie beschikbaar?
 Ja, u kunt Aspose.GIS gratis uitproberen door te bezoeken[deze link](https://releases.aspose.com/).
### Waar kan ik hulp of ondersteuning zoeken?
 Bezoek de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) voor hulp of ondersteuningsgerelateerde vragen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
