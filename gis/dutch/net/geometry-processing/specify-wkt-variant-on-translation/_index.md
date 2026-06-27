---
date: 2026-04-09
description: Leer hoe u een ruimtelijke referentie toewijst en de decimale precisie
  instelt bij het maken van een punt in C# met Aspose.GIS voor .NET in uw .NET-toepassingen.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Specificeer WKT-variant bij vertaling
second_title: Aspose.GIS .NET API
title: Ruimtelijke referentie toewijzen & WKT-variant instellen met Aspose.GIS
url: /nl/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Toewijzen van ruimtelijke referentie & instellen van WKT-variant met Aspose.GIS

## Inleiding
In deze tutorial leer je hoe je **assign spatial reference** toewijst aan een geometrie en het exacte WKT-uitvoerformaat regelt met Aspose.GIS voor .NET. Of je nu **create point C#** objecten moet maken voor kaartvisualisatie, analyse of gegevensuitwisseling, het kunnen kiezen van de juiste WKT-variant en numerieke precisie maakt je ruimtelijke gegevens interoperabel en gemakkelijk leesbaar. Laten we het proces stap voor stap doorlopen.

## Snelle antwoorden
- **What does “assign spatial reference” mean?** Het koppelt een geometrie aan een specifiek coördinatensysteem zoals WGS‑84.  
- **Which WKT variants are supported?** Iso, SimpleFeatureAccessOutdated, en ExtendedPostGis.  
- **How can I control decimal precision?** Gebruik de `NumericFormat` opties zoals `General`, `RoundTrip`, of `Flat`.  
- **Do I need a license?** Een gratis proefversie is beschikbaar; een commerciële licentie is vereist voor productie.  
- **What .NET versions are compatible?** .NET Framework 4.0+ en .NET Core/5/6+.

## Wat is “assign spatial reference”?
Het toewijzen van een spatial reference (of spatial reference system, SRS) vertelt GIS‑software hoe de coördinaatwaarden van een geometrie geïnterpreteerd moeten worden. Zonder een SRS hebben de breedte‑graad‑lengte‑getallen van een punt geen betekenis in de echte wereld.

## Waarom de WKT-variant en numeriek formaat regelen?
Verschillende GIS‑tools verwachten iets verschillende WKT‑syntaxis. Het kiezen van de juiste variant zorgt voor naadloze gegevensuitwisseling, terwijl het instellen van de decimale precisie afrondingsfouten of te lange getallen voorkomt die log‑ en bestandsuitvoer vervuilen.

## Voorvereisten
1. Aspose.GIS for .NET – download van de [download page](https://releases.aspose.com/gis/net/).  
2. Een .NET‑ontwikkelomgeving (Visual Studio, VS Code, of Rider).  
3. Basiskennis van C# en het .NET‑framework.

## Importeer namespaces
Voordat je Aspose.GIS‑klassen gebruikt, importeer je de vereiste namespaces:

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

## Stap 1: Maak een Point‑object (create point C#)
We beginnen met het construeren van een `Point` met latitude, longitude en een optionele measure (M) waarde:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Stap 2: Wijs Spatial Reference System (SRS) toe
Nu **assign spatial reference** we aan het punt. Hier gebruiken we het breed ondersteunde WGS‑84‑systeem (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Stap 3: Specificeer de gewenste WKT-variant
Kies de WKT-variant die overeenkomt met je downstream‑applicatie:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Stap 4: Stel decimale precisie in voor de WKT-uitvoer
Regel hoeveel cijfers er in de uiteindelijke string verschijnen met `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Veelvoorkomende valkuilen & tips
- **Pitfall:** Het vergeten instellen van de SRS vóór het aanroepen van `AsText` kan resulteren in ontbrekende SRID‑informatie.  
- **Tip:** Gebruik `NumericFormat.RoundTrip` wanneer je verliesloze round‑tripping van coördinaten nodig hebt.  
- **Tip:** De `Iso`‑variant is het meest draagbaar; kies `ExtendedPostGis` alleen wanneer je SRID ingebed nodig hebt.

## Conclusie
Je weet nu hoe je **assign spatial reference** kunt doen, de juiste WKT-variant kunt kiezen, en **set decimal precision** wanneer je **create point C#** objecten maakt met Aspose.GIS. Deze instellingen geven je de flexibiliteit om te voldoen aan de exacte eisen van elke GIS‑workflow, van eenvoudige visualisatie tot hoog‑precisie ruimtelijke analyse.

## Veelgestelde vragen

**Q:** Is Aspose.GIS compatible with all versions of .NET?  
**A:** Ja, Aspose.GIS ondersteunt .NET Framework 4.0 en hoger, evenals .NET Core/5/6.

**Q:** Kan ik Aspose.GIS gebruiken voor commerciële projecten?  
**A:** Absoluut. Een commerciële licentie is vereist voor productiegebruik, maar een gratis proefversie is beschikbaar voor evaluatie.

**Q:** Ondersteunt Aspose.GIS andere ruimtelijke gegevensformaten?  
**A:** Ja, het werkt met ESRI Shapefile, GeoJSON, KML, en nog veel meer formaten.

**Q:** Waar kan ik een gratis proefversie downloaden?  
**A:** Je kunt een gratis proefversie van Aspose.GIS downloaden van [hier](https://releases.aspose.com/).

**Q:** Hoe krijg ik hulp als ik tegen problemen aanloop?  
**A:** Plaats je vragen op het Aspose.GIS community [forum](https://forum.aspose.com/c/gis/33) waar zowel Aspose‑medewerkers als community‑leden kunnen helpen.

---

**Laatst bijgewerkt:** 2026-04-09  
**Getest met:** Aspose.GIS for .NET (latest release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}