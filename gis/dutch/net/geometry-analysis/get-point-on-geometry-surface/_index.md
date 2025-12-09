---
date: 2025-12-09
description: Leer hoe u controleert of een punt binnen een polygoon ligt met Aspose.GIS
  voor .NET. Stapsgewijze handleiding om een punt op een oppervlak te krijgen, een
  polygoon te maken in C# en een punt op een polygoon op te halen.
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: Controleer punt binnen polygoon en verkrijg punt op oppervlak
url: /nl/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Punt binnen polygoon controleren en punt op oppervlak verkrijgen

## Inleiding
In deze tutorial leer je **hoe je een punt binnen een polygoon kunt controleren** met Aspose.GIS voor .NET en zie je ook hoe je **een punt op het oppervlak** van een geometrie kunt verkrijgen. We lopen door het maken van een polygoon in C#, het ophalen van een punt dat op het oppervlak van de polygoon ligt, en het verifiëren dat het punt daadwerkelijk binnen de polygoon ligt. Aan het einde heb je een kant‑klaar fragment dat je in elke .NET geospatiale applicatie kunt gebruiken.

## Snelle antwoorden
- **Wat betekent “check point inside polygon”?** Het controleert of een gegeven coördinaat binnen de grenzen van een polygoongeometrie ligt.  
- **Welke methode retourneert een punt in het binnenste van een polygoon?** `GetPointOnSurface()` retourneert een punt dat gegarandeerd binnen de polygoon ligt.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework, .NET Core en .NET Standard zijn allemaal compatibel.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten om te kopiëren, compileren en uit te voeren.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

### Omgevingsinstelling
1. Installeer Aspose.GIS voor .NET: Download en installeer de Aspose.GIS voor .NET‑bibliotheek van [hier](https://releases.aspose.com/gis/net/).  
2. Stel je ontwikkelomgeving in: Zorg voor een werkende ontwikkelomgeving voor .NET‑programmering. Zo niet, kun je Visual Studio of een andere .NET‑ontwikkelomgeving naar keuze installeren.  
3. Basiskennis van C#: Maak jezelf vertrouwd met de basis van de programmeertaal C# als je dat nog niet bent.  
4. Toegang tot documentatie: Houd de [documentatie](https://reference.aspose.com/gis/net/) bij de hand voor naslag gedurende de tutorial.

## Namespaces importeren
Voordat we ingaan op de implementatie, laten we eerst de benodigde namespaces importeren:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nu we onze omgeving hebben opgezet en de vereiste namespaces hebben geïmporteerd, laten we het voorbeeld in meerdere stappen opsplitsen om het beter te begrijpen.

## Hoe een polygoon maken in C#  
Eerst moeten we een **polygoon** geometrie **creëren**. We definiëren de buitenring van de polygoon door de hoekpunten op te geven.

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

## Hoe een punt op het oppervlak verkrijgen  
Vervolgens halen we een punt op het oppervlak van de polygoon op met de `GetPointOnSurface()`‑methode. Dit is de **get point on surface** stap.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## Hoe een punt binnen een polygoon controleren  
We kunnen verifiëren of het opgehaalde punt binnen de polygoon ligt met behulp van de `SpatiallyContains()`‑methode. Dit toont **het ophalen van een punt op de polygoon** en vervolgens het controleren ervan.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Veelvoorkomende problemen en oplossingen
- **Lege polygoon** – Zorg ervoor dat de buitenring minstens drie verschillende hoekpunten heeft; anders kan `GetPointOnSurface()` een ongedefinieerd punt retourneren.  
- **Klokwijs vs. tegen de klok in** – De oriëntatie van de ring beïnvloedt de containment‑check niet, maar een consistente winding‑order helpt bij andere ruimtelijke bewerkingen.  
- **Coördinatensysteem** – Het voorbeeld gebruikt een eenvoudig Cartesiaans vlak; bij werken met echte coördinaten moet je ervoor zorgen dat het CRS (coordinate reference system) correct is gedefinieerd.

## Conclusie
In deze tutorial hebben we geleerd hoe je **een punt binnen een polygoon kunt controleren** met Aspose.GIS voor .NET, een **punt op het oppervlak** kunt verkrijgen, en de containment kunt verifiëren. Met Aspose.GIS wordt het verwerken van geospatiale data efficiënt en eenvoudig, waardoor ontwikkelaars robuuste geospatiale applicaties kunnen bouwen.

## Veelgestelde vragen
### Is Aspose.GIS compatibel met andere .NET‑frameworks?
Ja, Aspose.GIS ondersteunt verschillende .NET‑frameworks, waaronder .NET Framework, .NET Core en .NET Standard.

### Kan ik Aspose.GIS uitproberen voordat ik het koop?
Ja, je kunt een gratis proefversie van Aspose.GIS downloaden van [hier](https://releases.aspose.com/).

### Hoe kan ik ondersteuning krijgen voor Aspose.GIS?
Je kunt het Aspose.GIS‑forum bezoeken [hier](https://forum.aspose.com/c/gis/33) om hulp te zoeken en in contact te komen met andere gebruikers en ontwikkelaars.

### Biedt Aspose.GIS tijdelijke licenties?
Ja, je kunt tijdelijke licenties voor Aspose.GIS verkrijgen van [hier](https://purchase.aspose.com/temporary-license/).

### Waar kan ik Aspose.GIS kopen?
Je kunt Aspose.GIS kopen via de aankooppagina [hier](https://purchase.aspose.com/buy).

**Aanvullende V&A**

**Q:** Wat is de beste manier om grote polygoondatasets te verwerken?  
**A:** Laad geometrieën lui en hergebruik een enkele `GeometryFactory`‑instantie om het geheugenverbruik te verminderen.

**Q:** Kan ik meerdere punten op het oppervlak ophalen?  
**A:** `GetPointOnSurface()` retourneert één intern punt. Om meerdere interne punten te genereren, kun je een willekeurige puntgenerator gebruiken binnen de begrenzingsbox van de polygoon en elk punt testen met `SpatiallyContains()`.

**Q:** Is het mogelijk om de polygoon na creatie naar een shapefile te exporteren?  
**A:** Ja, Aspose.GIS biedt de klassen `FeatureSet` en `ShapefileWriter` om geometrieën naar het Shapefile‑formaat te schrijven.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.GIS 24.11 for .  
**Author:** Aspose