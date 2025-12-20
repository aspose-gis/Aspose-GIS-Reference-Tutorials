---
date: 2025-12-20
description: Leer hoe u een polygoon met gatgeometrie maakt met Aspose.GIS voor .NET.
  Deze gids laat u zien hoe u een gat in een polygoon maakt en werkt met georuimtelijke
  gegevens.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Polygon met gatgeometrie maken met Aspose.GIS
url: /nl/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Polygon met gat geometrie maken met Aspose.GIS

## Introductie
In deze tutorial **maak je een polygon met gat** geometrie met Aspose.GIS voor .NET. Of je nu een kaartapplicatie bouwt, ruimtelijke analyses uitvoert of data voorbereidt voor GIS‑services, weten hoe je een gat in een polygon kunt plaatsen is essentieel. We lopen het volledige proces stap‑voor‑stap door, van het opzetten van de omgeving tot het genereren van het uiteindelijke polygon‑object.

## Snelle antwoorden
- **Wat betekent “polygon met gat maken”?** Het betekent het bouwen van een polygon die één of meer binnenste ringen (gaten) bevat die van het gebied zijn uitgesloten.  
- **Welke bibliotheek regelt dit?** Aspose.GIS voor .NET biedt volledige ondersteuning voor buitenste en binnenste ringen.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hoe lang duurt het?** Meestal minder dan 10 minuten om te implementeren en te testen.

## Wat is “polygon met gat maken”?
Een polygon met een gat maken houdt in dat je een **externe ring** definieert die de buitenste grens vormt en één of meer **interne ringen** die lege ruimtes uitsnijden. De interne ringen worden vaak *gaten* genoemd omdat ze gebieden vertegenwoordigen die niet tot het oppervlak van de polygon behoren.

## Waarom een gat in een polygon maken met Aspose.GIS?
- **Nauwkeurige ruimtelijke modellering:** Werkelijke kenmerken zoals meren binnen percelen of binnenplaatsen binnen gebouwen vereisen gaten.  
- **Interoperabiliteit:** Formaten zoals Shapefile, GeoJSON en GML ondersteunen van nature interne ringen; Aspose.GIS behoudt ze.  
- **Prestaties:** De bibliotheek beheert de geldigheid van geometrieën, zodat je geen eigen validatiecode hoeft te schrijven.

## Vereisten
Voordat we beginnen, zorg dat je de volgende zaken hebt:
1. Aspose.GIS for .NET Library: Je kunt deze downloaden van [here](https://releases.aspose.com/gis/net/).  
2. Ontwikkelomgeving: Zorg dat je een ontwikkelomgeving hebt opgezet met Visual Studio of een andere .NET‑IDE geïnstalleerd.

## Namespaces importeren
Allereerst moet je de benodigde namespaces importeren om met de functionaliteiten van Aspose.GIS te werken. Zo doe je dat:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu verder gaan met het maken van een polygon met een gat geometrie met Aspose.GIS voor .NET.

## Stap 1: Polygon‑object maken
We beginnen met het instantieren van een leeg `Polygon`‑object dat later zowel de externe als de interne ringen zal bevatten.

```csharp
Polygon polygon = new Polygon();
```

## Stap 2: Externe ring definiëren
De externe ring definieert de buitenste grens van de polygon. Voeg punten in een klokrichting toe om een gesloten vorm te vormen.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Stap 3: Interne ring definiëren (gat)
Vervolgens maken we een interne ring—dit is het **gat** dat van het oppervlak van de polygon wordt uitgesloten. Punten worden doorgaans in tegen‑klokrichting toegevoegd, maar Aspose.GIS handelt de oriëntatie automatisch af.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Stap 4: Externe ring toewijzen en interne ring toevoegen aan polygon
Ten slotte koppel je de externe ring aan de polygon en voeg je vervolgens de interne ring (het gat) toe. De `AddInteriorRing`‑methode kan meerdere keren worden aangeroepen als je verschillende gaten nodig hebt.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Gat wordt niet weergegeven in GIS‑viewer | Oriëntatie van de interne ring omgekeerd | Zorg dat punten in de tegenovergestelde richting van de externe ring worden toegevoegd (tegen‑klok). |
| Polygon‑ongeldigheidsfout | Ringen zijn niet gesloten (eerste ≠ laatste punt) | Herhaal het eerste punt als laatste punt in elke ring (zoals hierboven getoond). |
| Onverwacht lege geometrie | Vergeet `ExteriorRing` toe te wijzen vóór het toevoegen van interne ringen | Stel eerst `polygon.ExteriorRing` in, daarna `AddInteriorRing` aanroepen. |

## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je **polygon met gat** geometrie maakt met Aspose.GIS voor .NET. Deze techniek is fundamenteel voor veel geospatiale scenario's waarin je complexe vormen met interne leegtes moet weergeven.

## Veelgestelde vragen
### 1. Wat is Aspose.GIS?
Aspose.GIS is een .NET‑bibliotheek die ontwikkelaars in staat stelt om met geospatiale data te werken, waardoor ze verschillende geospatiale bestandsformaten kunnen maken, lezen en manipuleren.

### 2. Kan ik Aspose.GIS gebruiken voor commerciële projecten?
Ja, je kunt Aspose.GIS zowel voor persoonlijke als commerciële projecten gebruiken door een licentie aan te schaffen. Bezoek [here](https://purchase.aspose.com/buy) voor meer details.

### 3. Is er een gratis proefversie beschikbaar voor Aspose.GIS?
Ja, je kunt een gratis proefversie van Aspose.GIS verkrijgen via [here](https://releases.aspose.com/).

### 4. Waar kan ik ondersteuning vinden voor Aspose.GIS?
Je kunt ondersteuning vinden voor Aspose.GIS op het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Hoe kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
Je kunt een tijdelijke licentie voor Aspose.GIS verkrijgen via [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}