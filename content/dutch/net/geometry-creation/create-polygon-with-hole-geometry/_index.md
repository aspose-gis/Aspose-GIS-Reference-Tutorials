---
title: Maak een polygoon met gatengeometrie met behulp van Aspose.GIS
linktitle: Maak veelhoeken met gatengeometrie
second_title: Aspose.GIS .NET-API
description: Leer hoe u een polygoon met gatgeometrie kunt maken met Aspose.GIS voor .NET. Stapsgewijze zelfstudie met codevoorbeelden.
type: docs
weight: 13
url: /nl/net/geometry-creation/create-polygon-with-hole-geometry/
---
## Invoering
In deze zelfstudie doorlopen we het proces van het maken van een polygoon met een gatgeometrie met behulp van Aspose.GIS voor .NET. Aspose.GIS is een krachtige bibliotheek waarmee ontwikkelaars met georuimtelijke gegevens in hun .NET-applicaties kunnen werken. 
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Aspose.GIS voor .NET Library: u kunt het downloaden van[hier](https://releases.aspose.com/gis/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u een ontwikkelomgeving hebt waarin Visual Studio of een andere .NET IDE is geïnstalleerd.
## Naamruimten importeren
Ten eerste moet u de benodigde naamruimten importeren om met Aspose.GIS-functionaliteiten te kunnen werken. Hier leest u hoe u het moet doen:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu verder gaan met het maken van een polygoon met een gatgeometrie met behulp van Aspose.GIS voor .NET.
## Stap 1: Maak een polygoonobject
```csharp
Polygon polygon = new Polygon();
```
## Stap 2: Definieer de buitenring
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Stap 3: Definieer de binnenring (gat)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Stap 4: Wijs buitenring toe en voeg binnenring toe aan polygoon
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je een polygoon met een gatengeometrie kunt maken met behulp van Aspose.GIS voor .NET. Deze kennis zal nuttig zijn voor verschillende geospatiale toepassingen waarbij dergelijke geometrieën essentieel zijn.
## Veelgestelde vragen
### 1. Wat is Aspose.GIS?
Aspose.GIS is een .NET-bibliotheek waarmee ontwikkelaars met georuimtelijke gegevens kunnen werken, waardoor ze verschillende georuimtelijke bestandsindelingen kunnen maken, lezen en manipuleren.
### 2. Kan ik Aspose.GIS gebruiken voor commerciële projecten?
 Ja, u kunt Aspose.GIS gebruiken voor zowel persoonlijke als commerciële projecten door een licentie aan te schaffen. Bezoek[hier](https://purchase.aspose.com/buy) voor meer details.
### 3. Is er een gratis proefversie beschikbaar voor Aspose.GIS?
 Ja, u kunt profiteren van een gratis proefversie van Aspose.GIS vanaf[hier](https://releases.aspose.com/).
### 4. Waar kan ik ondersteuning vinden voor Aspose.GIS?
 Ondersteuning voor Aspose.GIS vindt u op de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33).
### 5. Hoe kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
 U kunt een tijdelijke licentie voor Aspose.GIS verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).