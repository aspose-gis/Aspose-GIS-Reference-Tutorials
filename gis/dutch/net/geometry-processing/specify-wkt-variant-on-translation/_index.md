---
title: Specificeer WKT-variant op vertaling met Aspose.GIS
linktitle: Geef WKT-variant op vertaling op
second_title: Aspose.GIS .NET-API
description: Leer hoe u WKT-varianten kunt specificeren in Aspose.GIS voor .NET om het formaat en de precisie van de ruimtelijke gegevensrepresentatie effectief te beheren.
type: docs
weight: 19
url: /nl/net/geometry-processing/specify-wkt-variant-on-translation/
---
## Invoering
Aspose.GIS voor .NET is een krachtige bibliotheek waarmee ontwikkelaars moeiteloos met GIS-gegevens (geografisch informatiesysteem) kunnen werken in hun .NET-toepassingen. Een van de essentiële kenmerken van Aspose.GIS is de mogelijkheid om tijdens de vertaling de variant Well-Known Text (WKT) te specificeren, waardoor gebruikers het formaat en de precisie van representaties van ruimtelijke gegevens kunnen bepalen. In deze tutorial onderzoeken we stap voor stap hoe u WKT-varianten kunt specificeren met behulp van Aspose.GIS voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Aspose.GIS voor .NET: Download en installeer Aspose.GIS voor .NET vanaf de[downloadpagina](https://releases.aspose.com/gis/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u een .NET-ontwikkelomgeving hebt ingesteld.
3. Basiskennis: Bekendheid met de programmeertaal C# en het .NET-framework.

## Naamruimten importeren
Voordat u de Aspose.GIS-functionaliteit in uw code gebruikt, importeert u de benodigde naamruimten:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Stap 1: Maak een puntobject
 Maak eerst een`Point` object met breedtegraad, lengtegraad en optionele meetwaarden (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Stap 2: Ruimtelijk referentiesysteem (SRS) instellen
Wijs een ruimtelijk referentiesysteem (SRS) toe aan het puntobject. In dit voorbeeld gebruiken we het ruimtelijke referentiesysteem WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Stap 3: Geef de WKT-variant op
 Geef nu de WKT-variant op voor vertaling. Aspose.GIS ondersteunt verschillende WKT-varianten, waaronder`Iso`, `SimpleFeatureAccessOutdated` , En`ExtendedPostGis`. Kies de juiste variant op basis van uw wensen:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // PUNT M (23,5732, 25,3421, 40,3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // PUNT (23,5732, 25,3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23,5732, 25,3421, 40,3)
```
## Stap 4: Beheer het numerieke formaat
U kunt het numerieke formaat van de coördinaten in de WKT-weergave bepalen. Aspose.GIS biedt opties om de decimale precisie te specificeren:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // PUNT M (23,5732 25,342099999999999 40,299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // PUNT M (23,5732 25,3421 40,3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // PUNT M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // PUNT M (23,573 25,342 40,3)
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u WKT-varianten kunt specificeren bij vertaling met behulp van Aspose.GIS voor .NET. Door de hierboven beschreven stappen te volgen, kunnen ontwikkelaars effectief het formaat en de precisie van de representatie van ruimtelijke gegevens in hun .NET-toepassingen beheren, waardoor de flexibiliteit en bruikbaarheid van geografische informatiesystemen worden vergroot.
## Veelgestelde vragen
### Is Aspose.GIS compatibel met alle versies van .NET?
Ja, Aspose.GIS ondersteunt .NET Framework 4.0 en hoger.
### Kan ik Aspose.GIS gebruiken voor commerciële projecten?
Ja, Aspose.GIS kan worden gebruikt voor zowel persoonlijke als commerciële projecten.
### Biedt Aspose.GIS ondersteuning voor andere ruimtelijke gegevensformaten?
Ja, Aspose.GIS ondersteunt een breed scala aan indelingen voor ruimtelijke gegevens, waaronder ESRI Shapefile, GeoJSON en KML.
### Is er een gratis proefversie beschikbaar voor Aspose.GIS?
 Ja, u kunt een gratis proefversie van Aspose.GIS downloaden van[hier](https://releases.aspose.com/).
### Waar kan ik hulp of ondersteuning krijgen voor Aspose.GIS?
 U kunt uw vragen posten of hulp zoeken bij de Aspose.GIS-gemeenschap op de[forum](https://forum.aspose.com/c/gis/33).