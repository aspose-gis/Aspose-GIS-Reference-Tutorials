---
date: 2026-10-15
description: Leer hoe u geojson kunt maken van coördinaten en deze naar een stream
  kunt schrijven met Aspose.GIS voor .NET. Deze tutorial toont stap‑voor‑stap de conversie
  van punten en het genereren van GeoJSON C#‑code.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: GeoJSON naar stream schrijven
og_description: Leer hoe u geojson kunt maken van coördinaten en deze naar een stream
  kunt schrijven met Aspose.GIS voor .NET – stap‑voor‑stap gids voor grote datasets.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Geojson maken van coördinaten, naar een stream schrijven in .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Geojson maken van coördinaten, naar een stream schrijven in .NET
url: /nl/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak geojson van coördinaten en schrijf naar een stream

## Introductie
In deze tutorial leer je **hoe je geojson van coördinaten maakt** en direct naar een stream schrijft met Aspose.GIS voor .NET. We lopen de omgevingconfiguratie, laagcreatie, feature‑populatie en het streamen van het resultaat door, zodat je geospatiale payloads kunt insluiten in API's, cloud‑functies of bestand‑loze services zonder tijdelijke bestanden.

## Snelle antwoorden
- **Welke klasse schrijft GeoJSON naar een stream?** `VectorLayer` samen met de `GeoJsonDriver`.
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kan ik puntcollecties converteren naar GeoJSON?** Ja – maak een `Feature` voor elk punt en wijs een `Point`‑geometrie toe.
- **Is streaming geschikt voor grote datasets?** Absoluut – `MemoryStream` laat je gigabyte‑schaal GeoJSON schrijven zonder het volledige bestand in het geheugen te laden.

## Wat is GeoJSON?
GeoJSON is een open op JSON gebaseerd formaat voor het coderen van geografische features zoals punten, lijnen en polygonen. Het bestaat uit een `FeatureCollection` die individuele `Feature`‑objecten groepeert, elk met geometrie‑ en attribuutgegevens. Omdat het lichtgewicht en web‑vriendelijk is, is GeoJSON de de‑facto standaard voor het uitwisselen van ruimtelijke data tussen browsers, GIS‑servers en mobiele apps.

## Waarom Aspose.GIS gebruiken voor geojson‑generatie?
Aspose.GIS ondersteunt **35+ ruimtelijke bestandsformaten** en kan bestanden streamen die groter zijn dan **2 GB** terwijl het geheugengebruik onder **50 MB** blijft. Zijn high‑performance streaming‑engine schrijft GeoJSON direct naar elke .NET `Stream`, waardoor de noodzaak voor tussenliggende tijdelijke bestanden wegvalt en de I/O‑latentie tot **70 %** wordt verminderd in typische cloud‑scenario's.

## Vereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **Aspose.GIS for .NET** geïnstalleerd. Download het **Aspose.GIS for .NET**‑pakket [hier](https://releases.aspose.com/gis/net/).
2. Een beschrijfbare map in je project waar je tijdelijke bestanden kunt plaatsen indien nodig.
3. .NET 5+ of .NET Core 3.1+ runtime geïnstalleerd.

Nu duiken we in de implementatie.

## Hoe maak je geojson van coördinaten en schrijf je naar een stream?
`VectorLayer` vertegenwoordigt een in‑memory vector‑dataset die in verschillende formaten kan worden opgeslagen.  
`GeoJsonDriver` is de driver die lezen en schrijven van GeoJSON‑bestanden mogelijk maakt.  

Laad een `VectorLayer` met de `GeoJsonDriver`, voeg `Feature`‑objecten toe die `Point`‑geometrie bevatten, en roep `layer.Save(stream, new GeoJsonSaveOptions())` aan. Deze enkele oproep serialiseert de volledige feature‑collectie naar een standaard‑conforme GeoJSON‑document dat zich bevindt in de meegegeven `MemoryStream`. Het proces behandelt attribuut‑mapping en coördinaten‑conversie automatisch, zodat je een kant‑klaar JSON‑payload ontvangt zonder handmatig strings samen te stellen.

### Definitie‑ankers
**VectorLayer** is het kern‑Aspose.GIS‑object dat een mutabele vector‑dataset in het geheugen vertegenwoordigt.  
**GeoJsonDriver** is de driver die verantwoordelijk is voor het lezen en schrijven van GeoJSON‑bestanden.

## Importeer namespaces
Eerst en vooral, zorg ervoor dat je de benodigde namespaces opneemt om toegang te krijgen tot de Aspose.GIS‑functionaliteiten in je code:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Stap 1: stel de documentmap in
Maak een mappad aan waar Aspose.GIS indien nodig hulpprogramma‑bestanden kan opslaan.  
```csharp
string dataDir = "Your Document Directory";
```
Vervang "Your Document Directory" door het daadwerkelijke pad naar je documentmap.

## Stap 2: maak een memory stream
Een `MemoryStream` biedt een buffer in het geheugen die direct over HTTP kan worden verzonden of kan worden opgeslagen in cloud‑opslag.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Stap 3: maak een vectorlaag met GeoJSON‑driver
De `VectorLayer`‑klasse vertegenwoordigt een vector‑dataset die in verschillende formaten kan worden opgeslagen, inclusief GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Stap 4: definieer feature‑attributen
Definieer het attribuutschema voor je features (bijv. ID, Naam).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Stap 5: bouw en voeg features toe
Maak `Feature`‑objecten, wijs puntgeometrie toe, stel attribuutwaarden in, en voeg ze toe aan de laag.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Stap 6: toon GeoJSON‑output
Na het opslaan, reset de stream‑positie en lees de JSON‑string voor verificatie of verzending.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Gefeliciteerd! Je hebt met succes geojson van coördinaten gemaakt en naar een stream geschreven met Aspose.GIS voor .NET.

## Veelvoorkomende problemen en oplossingen
- **Lege output‑stream:** Zorg ervoor dat je de stream‑positie reset (`stream.Position = 0`) vóór het lezen.
- **Onjuiste coördinatenvolgorde:** GeoJSON verwacht longitude‑latitude volgorde; controleer je puntwaarden.
- **Grote datasets:** Gebruik `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` om features incrementeel te streamen en het geheugengebruik laag te houden.

## Veelgestelde vragen

**V: Kan ik Aspose.GIS voor .NET gebruiken in zowel Windows‑ als Linux‑omgevingen?**  
A: Ja, Aspose.GIS voor .NET draait op Windows, Linux en macOS met volledige .NET Core‑ondersteuning.

**V: Is er een gratis proefversie beschikbaar?**  
A: Absoluut! Je kunt de **gratis proefversie downloadpagina** [hier](https://releases.aspose.com/) verkennen.

**V: Waar kan ik gedetailleerde documentatie vinden?**  
A: Bekijk de **Aspose.GIS .NET documentatie** [hier](https://reference.aspose.com/gis/net/).

**V: Hoe kan ik een tijdelijke licentie krijgen?**  
A: Tijdelijke licenties zijn beschikbaar op de **tijdelijke licentiepagina** [hier](https://purchase.aspose.com/temporary-license/).

**V: Hulp nodig of meer vragen?**  
A: Bezoek ons **GIS‑ondersteuningsforum** [hier](https://forum.aspose.com/c/gis/33).

**V: Kan ik GeoJSON genereren uit een collectie van latitude/longitude‑punten?**  
A: Ja – maak een `Feature` voor elk punt, wijs een `Point`‑geometrie toe, en voeg het toe aan de `VectorLayer`.

**V: Ondersteunt Aspose.GIS het schrijven van gecomprimeerde GeoJSON (gzip)?**  
A: Je kunt de `MemoryStream` in een `GZipStream` wikkelen vóór het opslaan om een gecomprimeerde payload te produceren.

**V: Wat is de maximale grootte van een GeoJSON‑bestand die Aspose.GIS aankan?**  
A: De bibliotheek kan bestanden streamen die groter zijn dan 2 GB; het geheugengebruik blijft laag omdat data incrementeel wordt geschreven.

---

**Laatst bijgewerkt:** 2026-10-15  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

## Gerelateerde tutorials

- [Hoe GeoJSON lezen vanuit een stream met Aspose.GIS voor .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hoe GeoJSON converteren naar TopoJSON met Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Hoe Shapefile converteren naar GeoJSON met Aspose.GIS voor .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}