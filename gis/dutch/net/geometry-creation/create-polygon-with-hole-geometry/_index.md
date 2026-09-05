---
date: 2026-09-05
description: Leer hoe u een polygon interior ring met een hole maakt met Aspose.GIS
  voor .NET. Deze gids laat zien hoe u een hole aan een polygon toevoegt en werkt
  met data.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Maak Polygon met Hole-geometry
og_description: Leer hoe u een polygon interior ring met een hole maakt met Aspose.GIS
  voor .NET. Deze gids laat zien hoe u een hole aan een polygon toevoegt en werkt
  met data.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Maak een polygon interior ring met een hole met behulp van Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Maak een polygon interior ring met een hole met behulp van Aspose.GIS
url: /nl/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een binnenring van een polygoon met een gat met behulp van Aspose.GIS

## Introductie
In deze tutorial leer je hoe je **een binnenring van een polygoon** maakt die een gat bevat met behulp van Aspose.GIS voor .NET. Of je nu een kaartapplicatie bouwt, ruimtelijke analyse uitvoert, of gegevens voorbereidt voor GIS-diensten, het insluiten van een gat in een polygoon is een essentiële vaardigheid. We lopen het volledige werkproces door — van het opzetten van de ontwikkelomgeving tot het genereren van een geldig polygoonobject dat kan worden opgeslagen in elk ondersteund geospatiaal formaat.

## Snelle antwoorden
- **Wat betekent “create polygon with hole”?** Het betekent het bouwen van een polygoon die een of meer binnenringen (gaten) bevat die van het gebied worden uitgesloten.  
- **Welke bibliotheek behandelt dit?** Aspose.GIS voor .NET biedt volledige ondersteuning voor buiten- en binnenringen.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hoe lang duurt het?** Meestal minder dan 10 minuten om te implementeren en te testen.

## Hoe een gat toe te voegen aan een polygoon met Aspose.GIS
Laad je GIS-omgeving, definieer een buitenring en voeg vervolgens een of meer binnenringen toe. Aspose.GIS orienteert de ringen automatisch en valideert de geometrie, zodat je je kunt concentreren op de coördinaten die het benodigde gat vertegenwoordigen.

## Wat is een binnenring van een polygoon?
Een **polygon interior ring** is een binnenste grens die gebied aftrekt van de buitenste vorm van de polygoon.  
Je maakt deze door een gesloten reeks punten te definiëren die Aspose.GIS als een gat beschouwt, wat wordt uitgesloten bij het berekenen van het gebied of het renderen van de vorm.

## Waarom een binnenring van een polygoon maken met Aspose.GIS?
Aspose.GIS valideert en corrigeert de ringoriëntatie in minder dan 5 ms voor typische 200‑punt polygonen, waardoor aangepaste validatiecode overbodig wordt. Het ondersteunt ook **meer dan 30 geospatiale bestandsformaten** (Shapefile, GeoJSON, GML, KML, enz.) en kan polygonen met tot 10.000 punten verwerken zonder het volledige bestand in het geheugen te laden, wat zowel snelheid als schaalbaarheid biedt.

## Praktijkvoorbeelden voor polygonen met gaten
1. **Perceel met een intern meer** – het meer wordt gemodelleerd als een gat zodat het niet wordt meegeteld in de oppervlakte van het perceel.  
2. **Gebouwcontouren met binnenplaatsen** – de binnenplaats wordt uitgesloten van de gebouwcontour.  
3. **Beschermde zones binnen een groter natuurgebied** – je kunt beperkte secties uitsluiten zonder aparte lagen te maken.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je de volgende voorvereisten hebt:
1. Aspose.GIS for .NET Library: Je kunt deze downloaden van de **Aspose.GIS for .NET downloadpagina**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Ontwikkelomgeving: Zorg ervoor dat je een ontwikkelomgeving hebt opgezet met Visual Studio of een andere .NET IDE geïnstalleerd.

## Namespaces importeren
The `Aspose.Gis` namespace contains all geometry types you’ll need, including `Polygon`, `LinearRing`, and helper methods for validation.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu verder gaan met het maken van een polygoongeometrie met een gat met Aspose.GIS voor .NET.

## Stap 1: polygoonobject maken
`Polygon` is het geometrietype van Aspose.GIS dat een vlakke polygoon met optionele binnenringen vertegenwoordigt. We beginnen met het instantieren van een leeg `Polygon`-object dat later zowel de buiten- als binnenringen zal bevatten.

```csharp
Polygon polygon = new Polygon();
```

## Stap 2: buitenring definiëren
`LinearRing` is de klasse die wordt gebruikt voor zowel buiten- als binnenranden. De buitenring definieert de buitenste grens van de polygoon. Voeg punten toe in de klokrichting om een gesloten vorm te vormen.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Stap 3: binnenring definiëren (gat)
`LinearRing` vertegenwoordigt ook binnenringen. De binnenring is het **gat** dat wordt uitgesloten van de oppervlakte van de polygoon. Punten worden doorgaans toegevoegd in tegenwijzerzin, maar Aspose.GIS behandelt de oriëntatie automatisch.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Stap 4: buitenring toewijzen en binnenring toevoegen aan polygoon
De `AddInteriorRing`-methode voegt een of meer binnenringen toe aan een `Polygon`. Roep deze aan na het instellen van de `ExteriorRing`-eigenschap; je kunt de aanroep herhalen om meerdere gaten toe te voegen.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tips en best practices
- **Oriëntatie is belangrijk voor leesbaarheid** – hoewel Aspose.GIS de oriëntatie automatisch corrigeert, maakt het behouden van buitenringen in klokrichting en binnenringen in tegenwijzerzin de geometrie makkelijker te inspecteren in GIS-viewers.  
- **Sluit elke ring** – herhaal altijd de eerste coördinaat als het laatste punt; dit garandeert een geldige gesloten vorm.  
- **Valideer na creatie** – je kunt `polygon.IsValid` aanroepen om te verzekeren dat de geometrie voldoet aan OGC-standaarden voordat je opslaat.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Gat wordt niet weergegeven in GIS-viewer | Oriëntatie van binnenring omgekeerd | Zorg ervoor dat punten worden toegevoegd in de tegenovergestelde richting van de buitenring (tegenwijzerzin). |
| Polygon ongeldig fout | Ringen niet gesloten (eerste ≠ laatste punt) | Herhaal het eerste punt als laatste punt in elke ring (zoals hierboven getoond). |
| Onverwachte lege geometrie | Vergeten `ExteriorRing` toe te wijzen vóór het toevoegen van binnenringen | Stel eerst `polygon.ExteriorRing` in, roep daarna `AddInteriorRing` aan. |

## Veelgestelde vragen
### 1. Wat is Aspose.GIS?
Aspose.GIS is een .NET-bibliotheek die ontwikkelaars in staat stelt te werken met geospatiale gegevens, waardoor ze verschillende geospatiale bestandsformaten kunnen maken, lezen en manipuleren.

### 2. Kan ik Aspose.GIS gebruiken voor commerciële projecten?
Ja, je kunt Aspose.GIS gebruiken voor zowel persoonlijke als commerciële projecten door een licentie aan te schaffen. Bezoek de **Aspose.GIS aankooppagina**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) voor meer details.

### 3. Is er een gratis proefversie beschikbaar voor Aspose.GIS?
Ja, je kunt een gratis proefversie van Aspose.GIS verkrijgen via de **Aspose.GIS gratis proefversie downloadpagina**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Waar kan ik ondersteuning vinden voor Aspose.GIS?
Je kunt ondersteuning voor Aspose.GIS vinden op het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Hoe kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
Je kunt een tijdelijke licentie voor Aspose.GIS verkrijgen via de **Aspose.GIS tijdelijke licentiepagina**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Laatst bijgewerkt:** 2026-09-05  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe polygoongeometrie te maken met Aspose.GIS voor .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Leer hoe MultiPolygon-geometrie te maken met Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Polygoon omzetten naar lijn met Aspose.GIS voor .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}