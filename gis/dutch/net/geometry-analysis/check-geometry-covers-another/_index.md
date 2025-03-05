---
title: Controleer of geometrie een ander omvat
linktitle: Controleer of geometrie een ander omvat
second_title: Aspose.GIS .NET-API
description: Leer hoe u Aspose.GIS voor .NET kunt gebruiken om efficiënt met geografische gegevens te werken, ruimtelijke informatie te analyseren en kaartfuncties in uw .NET-toepassingen te integreren.
type: docs
weight: 15
url: /nl/net/geometry-analysis/check-geometry-covers-another/
---
## Invoering
Aspose.GIS voor .NET is een krachtige bibliotheek die ontwikkelaars tools biedt om efficiënt met geografische gegevens te werken binnen hun .NET-applicaties. Of u nu een kaarttoepassing bouwt, ruimtelijke gegevens analyseert of geografische kenmerken in uw software integreert, Aspose.GIS biedt een uitgebreide reeks functionaliteiten om uw ontwikkelingsproces te stroomlijnen.
## Vereisten
Voordat u Aspose.GIS voor .NET gaat gebruiken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. Installeer Visual Studio
Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd. Aspose.GIS voor .NET kan naadloos worden geïntegreerd met Visual Studio, waardoor een soepele ontwikkelingservaring wordt geboden.
### 2. Verkrijg Aspose.GIS voor .NET
 Download de Aspose.GIS voor .NET-bibliotheek van de[website](https://releases.aspose.com/gis/net/). U kunt de bibliotheek rechtstreeks downloaden of een pakketbeheerder zoals NuGet gebruiken om deze in uw project te installeren.
### 3. Bekendheid met .NET Framework
Basiskennis van het .NET-framework en de programmeertaal C# is essentieel om Aspose.GIS voor .NET effectief te kunnen gebruiken.
### 4. Toegang tot documentatie en ondersteuning
 Verwijs naar de[documentatie](https://reference.aspose.com/gis/net/) voor gedetailleerde informatie over Aspose.GIS API's en functionaliteiten. Als u problemen ondervindt of vragen heeft, kunt u gebruik maken van de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) Voor assistentie.
### 5. Optioneel: tijdelijke licentie
 Als u Aspose.GIS voor .NET verkent, kunt u een tijdelijke licentie verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/) om de kenmerken van de bibliotheek te evalueren.

## Naamruimten importeren
Voordat u Aspose.GIS voor .NET in uw project gebruikt, moet u de benodigde naamruimten importeren:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu het gegeven voorbeeld in meerdere stappen opsplitsen om te begrijpen hoe u kunt controleren of de ene geometrie de andere bedekt met behulp van Aspose.GIS voor .NET.
## Stap 1: Maak een LineString-object
```csharp
var line = new LineString();
```
 Hier instantiëren we een nieuwe`LineString` object, dat een reeks verbonden lijnsegmenten in een tweedimensionale ruimte vertegenwoordigt.
## Stap 2: Punten toevoegen aan LineString
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
 Wij voegen punten toe aan de`LineString` de ... gebruiken`AddPoint` methode. In dit voorbeeld voegen we twee punten toe: (0, 0) en (1, 1), die een lijnsegment vormen.
## Stap 3: Maak een puntobject
```csharp
var point = new Point(0, 0);
```
 Instantieer een`Point` object dat een enkel punt in een tweedimensionale ruimte vertegenwoordigt. Hier creëren we een punt op coördinaten (0, 0).
## Stap 4: Controleer of de lijn een punt bedekt
```csharp
Console.WriteLine(line.Covers(point));    // WAAR
```
 Gebruik de`Covers` methode om te controleren of de lijn het punt bedekt. In dit geval keert het terug`True` omdat het punt (0, 0) op de lijn ligt.
## Stap 5: Controleer of het punt door een lijn wordt bedekt
```csharp
Console.WriteLine(point.CoveredBy(line)); // WAAR
```
Gebruik op dezelfde manier de`CoveredBy` methode om te controleren of het punt door de lijn wordt bedekt. Omdat het punt (0, 0) op de lijn ligt, keert het terug`True`.

## Conclusie
Concluderend biedt Aspose.GIS voor .NET krachtige tools voor het werken met geografische gegevens in .NET-applicaties. Door de hierboven beschreven stappen te volgen, kunt u de functionaliteiten van Aspose.GIS efficiënt gebruiken om te controleren of de ene geometrie de andere bedekt, waardoor de ruimtelijke analysemogelijkheden van uw software worden verbeterd.
## Veelgestelde vragen
### Kan ik Aspose.GIS voor .NET gebruiken in mijn commerciële projecten?
Ja, u kunt Aspose.GIS voor .NET gebruiken in zowel commerciële als niet-commerciële projecten na het verkrijgen van de juiste licentie.
### Is Aspose.GIS voor .NET compatibel met .NET Core?
Ja, Aspose.GIS voor .NET is compatibel met zowel .NET Framework- als .NET Core-omgevingen.
### Ondersteunt Aspose.GIS voor .NET verschillende GIS-formaten?
Ja, Aspose.GIS voor .NET ondersteunt een breed scala aan GIS-formaten, waaronder Shapefile, GeoJSON, KML en meer.
### Kan ik bijdragen aan de ontwikkeling van Aspose.GIS voor .NET?
Aspose.GIS voor .NET is een eigen bibliotheek ontwikkeld door Aspose, dus bijdragen van externe ontwikkelaars worden niet geaccepteerd. U kunt echter wel feedback en suggesties geven om de bibliotheek te verbeteren.
### Hoe vaak worden er updates uitgebracht voor Aspose.GIS voor .NET?
 Er worden regelmatig updates voor Aspose.GIS voor .NET uitgebracht om nieuwe functies, verbeteringen en bugfixes te introduceren. Controleer de[website](https://releases.aspose.com/gis/net/) voor de nieuwste uitgaven.