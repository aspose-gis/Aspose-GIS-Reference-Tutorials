---
title: Creëer MultiPolygon-geometrie met Aspose.GIS
linktitle: Creëer MultiPolygon-geometrie
second_title: Aspose.GIS .NET-API
description: Leer hoe u MultiPolygon-geometrie kunt maken met Aspose.GIS voor .NET. Stap-voor-stap handleiding voor beginners. Gratis proefversie beschikbaar.
weight: 16
url: /nl/net/geometry-creation/create-multipolygon-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creëer MultiPolygon-geometrie met Aspose.GIS

## Invoering
In de wereld van de ontwikkeling van geografische informatiesystemen (GIS) onderscheidt Aspose.GIS voor .NET zich als een krachtig hulpmiddel voor het creëren, bewerken en analyseren van georuimtelijke gegevens. Of u nu een doorgewinterde ontwikkelaar bent of net begint, het beheersen van Aspose.GIS kan een wereld aan mogelijkheden voor uw projecten openen.
## Vereisten
Voordat u Aspose.GIS voor .NET gaat gebruiken, zijn er een aantal vereisten waaraan u moet voldoen:
### Aspose.GIS voor .NET installeren
1.  Download Aspose.GIS: Ga naar de[downloadpagina](https://releases.aspose.com/gis/net/)en selecteer de juiste versie voor uw ontwikkelomgeving.
2. Aspose.GIS installeren: Volg de installatie-instructies in de documentatie om Aspose.GIS voor .NET op uw machine te installeren.

## Naamruimten importeren
Om met Aspose.GIS in uw .NET-project te gaan werken, moet u de benodigde naamruimten importeren:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Maak lineaire ringen
Eerst moeten we LinearRings voor elke polygoon maken. Elke LinearRing vertegenwoordigt een gesloten lijnreeks die de grens van een veelhoek vormt.
```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```
## Stap 2: Maak polygonen
Vervolgens maken we Polygon-objecten met behulp van de LinearRings die we hebben gedefinieerd.
```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```
## Stap 3: Maak MultiPolygon
Laten we nu deze polygonen combineren tot een MultiPolygon-geometrie.
```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```
Gefeliciteerd! U hebt met succes een MultiPolygon-geometrie gemaakt met Aspose.GIS voor .NET.

## Conclusie
Het beheersen van Aspose.GIS voor .NET opent een wereld aan mogelijkheden voor ontwikkelaars die met georuimtelijke gegevens werken. Door deze stapsgewijze handleiding te volgen, heeft u geleerd hoe u een MultiPolygon-geometrie kunt maken, waarmee u de basis legt voor complexere GIS-toepassingen.
## Veelgestelde vragen
### Is Aspose.GIS voor .NET geschikt voor beginners?
Absoluut! Aspose.GIS biedt uitgebreide documentatie en tutorials om ontwikkelaars van alle vaardigheidsniveaus op weg te helpen.
### Kan ik Aspose.GIS uitproberen voordat ik een aankoop doe?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/) om de functies ervan te verkennen voordat u een aankoop doet.
### Waar kan ik ondersteuning vinden voor Aspose.GIS?
 U kunt het Aspose.GIS-forum bezoeken[hier](https://forum.aspose.com/c/gis/33) om vragen te stellen en hulp te krijgen van de gemeenschap.
### Is er een tijdelijke licentie beschikbaar voor Aspose.GIS?
 Ja, u kunt een tijdelijke licentie verkrijgen via[hier](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.
### Kan ik Aspose.GIS rechtstreeks aanschaffen?
 Ja, u kunt Aspose.GIS kopen via de website[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
