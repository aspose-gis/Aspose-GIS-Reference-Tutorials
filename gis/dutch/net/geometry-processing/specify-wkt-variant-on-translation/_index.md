---
date: 2026-09-15
description: Leer hoe u een coördinatensysteem toewijst, de WKT-variant instelt en
  de decimale precisie beheert bij het maken van puntgeometrie in C# met Aspose.GIS
  voor .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: WKT-variant specificeren bij vertaling
og_description: Leer hoe u een coördinatensysteem toewijst, de WKT-variant instelt
  en de decimale precisie beheert bij het maken van puntgeometrie in C# met Aspose.GIS
  voor .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Coördinatensysteem toewijzen, WKT-variant instellen met Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Coördinatensysteem toewijzen, WKT-variant instellen met Aspose.GIS
url: /nl/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Coördinaatsysteem toewijzen, WKT-variant instellen met Aspose.GIS

## Introductie
In deze tutorial leer je hoe je een **coördinaatsysteem toewijst**, de juiste WKT-variant kiest en de decimale precisie regelt wanneer je **puntgeometrie maakt** in C# met Aspose.GIS voor .NET. Of je nu een kaartservice bouwt, ruimtelijke analyses uitvoert of gegevens uitwisselt tussen GIS-platformen, deze instellingen zorgen ervoor dat je output zowel interoperabel als gemakkelijk leesbaar is. Laten we stap voor stap door het proces lopen.

## Snelle antwoorden
- **Wat betekent “assign coordinate system”?** Het bindt een geometrie aan een specifiek coördinatenreferentiesysteem zoals WGS‑84.  
- **Welke WKT-varianten worden ondersteund?** Iso, SimpleFeatureAccessOutdated en ExtendedPostGis.  
- **Hoe kan ik de decimale precisie regelen?** Gebruik de `NumericFormat`‑enum (`General`, `RoundTrip`, `Flat`).  
- **Heb ik een licentie nodig voor Aspose.GIS?** Er is een gratis proefversie beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Welke .NET‑versies zijn compatibel?** .NET Framework 4.0+ en .NET Core/5/6+.

## Wat is “assign coordinate system”?
Het toewijzen van een ruimtelijk referentiesysteem (of spatial reference system, SRS) vertelt GIS‑software hoe de coördinatenwaarden van een geometrie geïnterpreteerd moeten worden, door de getallen te koppelen aan een echt‑wereld coördinatensysteem zoals WGS‑84. Zonder een SRS hebben de breedte‑ en lengtegraadcijfers van een punt geen betekenis in de echte wereld.

## Waarom de WKT-variant en numeriek formaat controleren?
Meer dan 30 GIS‑tools verwachten specifieke WKT‑syntaxis, dus het kiezen van de juiste variant voorkomt importfouten. Het instellen van het numerieke formaat vermindert afrondingsruis en houdt de output beknopt, wat vooral belangrijk is wanneer log‑ of bestandsgegevens programmatisch worden geparseerd.

## Vereisten
1. Aspose.GIS for .NET – download van de [downloadpagina](https://releases.aspose.com/gis/net/).  
2. Een .NET‑ontwikkelomgeving (Visual Studio, VS Code of Rider).  
3. Basiskennis van C# en het .NET‑framework.

## Namespaces importeren
Voordat je Aspose.GIS‑klassen gebruikt, importeer je de benodigde namespaces:

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

## Hoe een coördinaatsysteem toewijzen aan een punt?
Laad een `Point`‑instantie en koppel vervolgens een ruimtelijk referentiesysteem (SRS) met de `SpatialReference`‑klasse. Dit twee‑stappenpatroon zorgt ervoor dat de geometrie zijn coördinaatsysteem‑metadata meedraagt bij export, zodat downstream‑tools de coördinaten correct kunnen interpreteren. De `Point`‑klasse vertegenwoordigt een enkele locatie gedefinieerd door X (longitude) en Y (latitude) coördinaten.

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Stap 2: ruimtelijk referentiesysteem (SRS) toewijzen
Nu **wijzigen we het ruimtelijk referentiesysteem** van het punt. `SpatialReference` vertegenwoordigt een coördinatenreferentiesysteem geïdentificeerd door een SRID. Hier gebruiken we het breed ondersteunde WGS‑84‑systeem (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Stap 3: gewenste WKT-variant opgeven
Kies de WKT‑variant die overeenkomt met je downstream‑applicatie:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Hoe decimale precisie instellen voor WKT‑output?
Regel hoeveel cijfers er in de uiteindelijke string verschijnen met de `NumericFormat`‑enum, die opmaakregels definieert zoals `General`, `RoundTrip` of `Flat`. Het kiezen van `RoundTrip` behoudt de volledige coördinatenfideliteit voor round‑tripping‑scenario's, terwijl `General` een beknopte weergave biedt die geschikt is voor de meeste visualisatietaken. De `NumericFormat`‑enum bepaalt hoe coördinatennummers worden opgemaakt in de WKT‑output.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Veelvoorkomende valkuilen & tips
- **Valkuil:** Het vergeten instellen van de SRS vóór het aanroepen van `AsText` kan leiden tot ontbrekende SRID‑informatie.  
- **Tip:** Gebruik `NumericFormat.RoundTrip` wanneer je verliesloze round‑tripping van coördinaten nodig hebt.  
- **Tip:** De `Iso`‑variant is het meest draagbaar; kies `ExtendedPostGis` alleen wanneer je een SRID moet insluiten.

## Conclusie
Je weet nu hoe je een **coördinaatsysteem toewijst**, de juiste WKT‑variant kiest en **decimale precisie instelt** wanneer je **puntgeometrie maakt** met Aspose.GIS. Deze instellingen geven je de flexibiliteit om te voldoen aan de exacte eisen van elke GIS‑workflow, van eenvoudige visualisatie tot hoog‑precisie ruimtelijke analyse.

## Veelgestelde vragen

**V:** Is Aspose.GIS compatibel met alle versies van .NET?  
**A:** Ja, Aspose.GIS ondersteunt .NET Framework 4.0 en hoger, evenals .NET Core/5/6.

**V:** Kan ik Aspose.GIS gebruiken voor commerciële projecten?  
**A:** Absoluut. Een commerciële licentie is vereist voor productiegebruik, maar er is een gratis proefversie beschikbaar voor evaluatie.

**V:** Ondersteunt Aspose.GIS andere ruimtelijke dataformaten?  
**A:** Ja, het werkt met meer dan 30 formaten, waaronder ESRI Shapefile, GeoJSON, KML, CSV en nog veel meer.

**V:** Waar kan ik een gratis proefversie downloaden?  
**A:** Je kunt een gratis proefversie van Aspose.GIS downloaden via de [Aspose.GIS gratis proefdownloadpagina](https://releases.aspose.com/).

**V:** Hoe krijg ik hulp als ik tegen problemen aanloop?  
**A:** Plaats je vragen op het Aspose.GIS‑community [forum](https://forum.aspose.com/c/gis/33) waar zowel Aspose‑medewerkers als community‑leden kunnen assisteren.

---

**Laatst bijgewerkt:** 2026-09-15  
**Getest met:** Aspose.GIS for .NET (latest release)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Create a Vector Layer and Set Its Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [How to Translate Geometry to WKT with Aspose.GIS for .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [How to Limit Precision Writing Geometries with Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}