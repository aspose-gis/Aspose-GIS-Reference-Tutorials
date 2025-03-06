---
title: Coördineer de conversie met Aspose.GIS
linktitle: Converteer coördinaten
second_title: Aspose.GIS .NET-API
description: Leer hoe u coördinaten converteert met Aspose.GIS voor .NET. Stapsgewijze handleiding, vereisten en veelgestelde vragen worden verstrekt.
weight: 25
url: /nl/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Coördineer de conversie met Aspose.GIS

## Invoering
In deze tutorial duiken we in de wereld van geografische informatiesystemen (GIS) met behulp van de krachtige Aspose.GIS-bibliotheek voor .NET. Aspose.GIS is een uitgebreide toolkit waarmee ontwikkelaars moeiteloos met ruimtelijke gegevens kunnen werken. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze tutorial begeleidt u bij het gebruik van Aspose.GIS om coördinaten effectief om te zetten.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Basiskennis van C#: Bekendheid met de programmeertaal C# is essentieel om de gegeven codevoorbeelden te begrijpen en te implementeren.
  
2.  Installatie van Aspose.GIS: Zorg ervoor dat u de Aspose.GIS-bibliotheek voor .NET hebt gedownload en geïnstalleerd. Je kunt het downloaden van de[Aspose.GIS-website](https://releases.aspose.com/gis/net/).

## Naamruimten importeren
Laten we, voordat we beginnen, de benodigde naamruimten importeren om toegang te krijgen tot de functionaliteiten van Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

Laten we het gegeven voorbeeld in meerdere stappen opsplitsen voor een duidelijk begrip:
## Stap 1: Start het conversieproces
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Op deze regel wordt eenvoudigweg een bericht weergegeven dat de start van het coördinatenconversieproces aangeeft.
## Stap 2: Converteren naar decimale graden
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Hier converteren we de coördinaten (25,5, 45,5) naar decimale graden-indeling met behulp van de`AsPointText` methode met de`PointFormats.DecimalDegrees` parameter. Het resultaat wordt vervolgens naar de console afgedrukt.
## Stap 3: Converteer naar graden decimale minuten
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Deze stap converteert de coördinaten naar het decimale minutenformaat in graden en drukt het resultaat af.
## Stap 4: Converteren naar graadminuten seconden
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Op dezelfde manier converteren we de coördinaten naar het graadminuten-secondenformaat en geven we de uitvoer weer.
## Stap 5: Converteren naar GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Ten slotte converteren we de coördinaten naar het GeoRef-formaat en printen we het resultaat.

## Conclusie
In deze zelfstudie hebben we het proces van het converteren van coördinaten met Aspose.GIS voor .NET onderzocht. Door de stapsgewijze handleiding te volgen en de Aspose.GIS-bibliotheek te gebruiken, kunt u ruimtelijke gegevens binnen uw .NET-toepassingen efficiënt manipuleren.
## Veelgestelde vragen
### Is Aspose.GIS compatibel met andere programmeertalen?
Aspose.GIS richt zich primair op .NET-ontwikkelaars, maar biedt interoperabiliteit met Java via Aspose.GIS voor Java.
### Kan ik Aspose.GIS uitproberen voordat ik een aankoop doe?
 Ja, u heeft toegang tot een gratis proefversie van Aspose.GIS via de[website](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.GIS?
 U kunt hulp zoeken op het Aspose.GIS-communityforum[hier](https://forum.aspose.com/c/gis/33).
### Zijn er tijdelijke licenties beschikbaar voor Aspose.GIS?
 Ja, tijdelijke licenties zijn verkrijgbaar bij de[tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/).
### Waar kan ik Aspose.GIS kopen?
 U kunt Aspose.GIS aanschaffen bij de[aankooppagina](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
