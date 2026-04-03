---
date: 2026-04-03
description: Leer hoe u een polygoon met gatgeometrie maakt met Aspose.GIS voor .NET.
  Deze gids laat u zien hoe u een gat in een polygoon maakt en werkt met geospatiale
  gegevens.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Polygon met gatgeometrie maken
second_title: Aspose.GIS .NET API
title: Polygon met gatgeometrie maken met Aspose.GIS
url: /nl/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Polygon met gat geometrie maken met Aspose.GIS

## Inleiding
In deze tutorial **maak je een polygon met gat** geometrie met Aspose.GIS voor .NET. Of je nu een kaartapplicatie bouwt, ruimtelijke analyse uitvoert, of gegevens voorbereidt voor GIS‑services, weten hoe je een gat in een polygon moet insluiten is essentieel. We lopen het volledige proces stap‑voor‑stap door, van het opzetten van de omgeving tot het genereren van het uiteindelijke polygon‑object.

## Snelle antwoorden
- **Wat betekent “polygon met gat maken”?** Het betekent het bouwen van een polygon die één of meer interne ringen (gaten) bevat die van het gebied worden uitgesloten.  
- **Welke bibliotheek behandelt dit?** Aspose.GIS voor .NET biedt volledige ondersteuning voor externe en interne ringen.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hoe lang duurt het?** Meestal minder dan 10 minuten om te implementeren en te testen.

## Hoe een gat toe te voegen aan een polygon met Aspose.GIS
Een gat toevoegen is simpelweg een kwestie van een **interne ring** definiëren en deze aan de polygon koppelen. De bibliotheek zorgt voor de oriëntatie en geldigheid, zodat je je kunt concentreren op de coördinaten die de lege ruimte vertegenwoordigen.

## Wat is “polygon met gat maken”?
Het maken van een polygon met een gat houdt in dat je een **externe ring** definieert die de buitenste grens schetst en één of meer **interne ringen** die lege ruimtes uitsnijden. De interne ringen worden vaak *gaten* genoemd omdat ze gebieden vertegenwoordigen die niet tot het oppervlak van de polygon behoren.

## Waarom een gat in een polygon maken met Aspose.GIS?
- **Nauwkeurige ruimtelijke modellering:** Werkelijke kenmerken zoals meren binnen percelen of binnenplaatsen in gebouwen vereisen gaten.  
- **Interoperabiliteit:** Formaten zoals Shapefile, GeoJSON en GML ondersteunen interne ringen natively; Aspose.GIS behoudt ze.  
- **Prestaties:** De bibliotheek beheert de geldigheid van geometrieën, zodat je geen eigen validatiecode hoeft te schrijven.

## Praktijkvoorbeelden voor polygonen met gaten
1. **Perceel met een intern meer** – het meer wordt gemodelleerd als een gat zodat het niet wordt meegeteld in de oppervlakte van het perceel.  
2. **Gebouwcontouren met binnenplaatsen** – de binnenplaats wordt uitgesloten van de gebouwcontour.  
3. **Beschermde zones binnen een groter natuurgebied** – je kunt beperkte secties uitsluiten zonder aparte lagen te maken.

## Voorvereisten
Voordat we beginnen, zorg dat je de volgende zaken hebt:
1. Aspose.GIS for .NET Library: Je kunt het downloaden van [here](https://releases.aspose.com/gis/net/).  
2. Development Environment: Zorg dat je een ontwikkelomgeving hebt opgezet met Visual Studio of een andere .NET‑IDE geïnstalleerd.

## Namespaces importeren
Eerst moet je de benodigde namespaces importeren om met de functionaliteiten van Aspose.GIS te werken. Zo doe je dat:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu verder gaan met het maken van een polygon met een gat geometrie met Aspose.GIS voor .NET.

## Stap 1: Polygon-object maken
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

## Stap 3: Interne ring (gat) definiëren
Vervolgens maken we een interne ring—dit is het **gat** dat wordt uitgesloten van de oppervlakte van de polygon. Punten worden doorgaans toegevoegd in een tegen‑klokrichting, maar Aspose.GIS handelt de oriëntatie automatisch af.

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

## Tips en beste praktijken
- **Oriëntatie is belangrijk voor leesbaarheid** – hoewel Aspose.GIS de oriëntatie automatisch corrigeert, maakt het behouden van externe ringen met de klokrichting en interne ringen tegen de klokrichting de geometrie makkelijker te inspecteren in GIS‑viewers.  
- **Sluit elke ring** – herhaal altijd het eerste coördinaat als het laatste punt; dit garandeert een geldige gesloten vorm.  
- **Valideer na creatie** – je kunt `polygon.IsValid` aanroepen om te zorgen dat de geometrie voldoet aan OGC‑normen voordat je deze opslaat.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Gat wordt niet weergegeven in GIS‑viewer | Interne ring‑oriëntatie omgekeerd | Zorg dat punten in de tegenovergestelde richting van de externe ring worden toegevoegd (tegen‑klokrichting). |
| Polygon‑ongeldige fout | Ringen niet gesloten (eerste ≠ laatste punt) | Herhaal het eerste punt als laatste punt in elke ring (zoals hierboven getoond). |
| Onverwachte lege geometrie | Vergeten `ExteriorRing` toe te wijzen vóór het toevoegen van interne ringen | Stel eerst `polygon.ExteriorRing` in, roep daarna `AddInteriorRing` aan. |

## Veelgestelde vragen
### 1. Wat is Aspose.GIS?
Aspose.GIS is een .NET‑bibliotheek die ontwikkelaars in staat stelt om met geografische gegevens te werken, zodat ze verschillende geospatiale bestandsformaten kunnen creëren, lezen en manipuleren.

### 2. Kan ik Aspose.GIS gebruiken voor commerciële projecten?
Ja, je kunt Aspose.GIS gebruiken voor zowel persoonlijke als commerciële projecten door een licentie aan te schaffen. Bezoek [here](https://purchase.aspose.com/buy) voor meer details.

### 3. Is er een gratis proefversie beschikbaar voor Aspose.GIS?
Ja, je kunt een gratis proefversie van Aspose.GIS verkrijgen via [here](https://releases.aspose.com/).

### 4. Waar kan ik ondersteuning vinden voor Aspose.GIS?
Je kunt ondersteuning vinden voor Aspose.GIS op het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Hoe kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
Je kunt een tijdelijke licentie voor Aspose.GIS verkrijgen via [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}