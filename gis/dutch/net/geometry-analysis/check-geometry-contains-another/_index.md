---
title: Controleer of geometrie een andere bevat
linktitle: Controleer of geometrie een andere bevat
second_title: Aspose.GIS .NET-API
description: Ontdek Aspose.GIS voor .NET, een robuuste bibliotheek voor naadloze georuimtelijke gegevensintegratie in uw .NET-toepassingen.
type: docs
weight: 14
url: /nl/net/geometry-analysis/check-geometry-contains-another/
---
## Invoering
Aspose.GIS voor .NET is een krachtige bibliotheek waarmee ontwikkelaars naadloos met georuimtelijke gegevens kunnen werken binnen hun .NET-toepassingen. Of u nu een kaarttoepassing bouwt, geospatiale analyses uitvoert of locatiegebaseerde functies in uw software integreert, Aspose.GIS vereenvoudigt het proces door intuïtieve API's en robuuste functionaliteit te bieden.
## Vereisten
Voordat u Aspose.GIS voor .NET gaat gebruiken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. .NET-ontwikkelomgeving instellen
Zorg ervoor dat er een werkende .NET-ontwikkelomgeving op uw computer is geïnstalleerd. Dit omvat ook het correct installeren en configureren van de .NET SDK.
### 2. Aspose.GIS-installatie
 Installeer Aspose.GIS voor .NET door de bibliotheek te downloaden vanaf de releasepagina[hier](https://releases.aspose.com/gis/net/) . Volg de installatie-instructies in de documentatie[hier](https://reference.aspose.com/gis/net/)om Aspose.GIS in uw project te integreren.
### 3. Basiskennis van C#
Maak uzelf vertrouwd met de programmeertaal C#, aangezien Aspose.GIS voor .NET voornamelijk met C# wordt gebruikt.

## Naamruimten importeren
Importeer in uw C#-project de benodigde naamruimten om de Aspose.GIS-functionaliteiten te gebruiken:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Definieer geometrieobjecten
Definieer eerst de geometrieobjecten met behulp van Aspose.GIS-klassen:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## Stap 2: Controleer de ruimtelijke insluiting
Controleer vervolgens of de ene geometrie een andere bevat:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // Vals
```
## Stap 3: Definieer een andere geometrie
Definieer een ander geometrieobject:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Stap 4: Controleer de ruimtelijke insluiting opnieuw
Controleer of de nieuw gedefinieerde geometrie zich in de eerste geometrie bevindt:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // WAAR
```
## Stap 5: Gelijkwaardige functionaliteit
 Begrijp dat`a.SpatiallyContains(b)` is gelijk aan`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // WAAR
```

## Conclusie
Concluderend biedt Aspose.GIS voor .NET krachtige tools voor het verwerken van georuimtelijke gegevens in .NET-toepassingen. Door deze handleiding te volgen en het gegeven voorbeeld te gebruiken, kunt u efficiënt ruimtelijke controles uitvoeren en andere geospatiale functionaliteiten binnen uw projecten benutten.
## Veelgestelde vragen
### Vraag 1: Is Aspose.GIS compatibel met .NET Core?
A: Ja, Aspose.GIS ondersteunt .NET Core volledig, waardoor u georuimtelijke toepassingen op verschillende platforms kunt ontwikkelen.
### Vraag 2: Kan ik geospatiale analyses uitvoeren met Aspose.GIS?
A: Absoluut, Aspose.GIS biedt verschillende functionaliteiten voor georuimtelijke analyse, waaronder ruimtelijke zoekopdrachten, afstandsberekeningen en geometriemanipulaties.
### V3: Hoe vaak worden er updates uitgebracht voor Aspose.GIS?
A: Aspose.GIS brengt regelmatig updates uit om de prestaties te verbeteren, nieuwe functies toe te voegen en eventuele gerapporteerde problemen op te lossen. Je kunt op de hoogte blijven door de releasepagina te bezoeken.
### V4: Is er een communityforum voor Aspose.GIS-gebruikers?
A: Ja, u kunt lid worden van het Aspose.GIS-communityforum[hier](https://forum.aspose.com/c/gis/33) om in contact te komen met andere gebruikers, vragen te stellen en uw ervaringen te delen.
### V5: Kan ik Aspose.GIS uitproberen voordat ik een aankoop doe?
 A: Zeker, u kunt Aspose.GIS verkennen door de gratis proefversie te downloaden van[hier](https://releases.aspose.com/).