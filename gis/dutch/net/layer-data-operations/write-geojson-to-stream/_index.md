---
date: 2026-05-21
description: Leer hoe u GeoJSON naar een stream schrijft met Aspose.GIS voor .NET.
  Deze GeoJSON‑tutorial voor .NET toont stap‑voor‑stap de conversie van punten en
  het genereren van GeoJSON C#‑code.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: GeoJSON naar stream schrijven
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hoe GeoJSON naar stream schrijven met Aspose.GIS voor .NET
url: /nl/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Schrijf GeoJSON naar Stream

## Introductie
In deze tutorial leer je **hoe je GeoJSON naar een stream schrijft** in een .NET‑applicatie met Aspose.GIS. We lopen elke stap door, van het opzetten van de omgeving tot het genereren van een geldig GeoJSON‑document, zodat je georuimtelijke gegevens naadloos kunt integreren in je services.

## Snelle Antwoorden
- **Wat is de primaire klasse voor GeoJSON‑output?** `VectorLayer` met de `GeoJsonDriver`.
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kan ik puntcollecties naar GeoJSON converteren?** Ja – gebruik de `Feature`‑klasse en definieer puntgeometrie.
- **Wordt streaming ondersteund voor grote datasets?** Absoluut; `MemoryStream` laat je schrijven zonder tussenliggende bestanden.

## Wat is GeoJSON?
GeoJSON is een open standaardformaat voor het coderen van verschillende geografische datastructuren met JSON. Het definieert objecten zoals FeatureCollection, Feature en geometrietypen (Point, LineString, Polygon). Deze lichtgewicht, web‑vriendelijke weergave maakt eenvoudige uitwisseling en visualisatie van ruimtelijke gegevens mogelijk over vele platformen en programmeertalen.

## Waarom Aspose.GIS gebruiken voor GeoJSON‑generatie?
Aspose.GIS ondersteunt meer dan 30 ruimtelijke bestandsformaten en kan bestanden groter dan 2 GB verwerken zonder het volledige document in het geheugen te laden. De high‑performance streaming‑engine schrijft GeoJSON direct naar streams, waardoor I/O‑overhead wordt verminderd. Dit maakt het ideaal voor enterprise‑scale georuimtelijke workloads, cloud‑services en realtime‑applicaties.

## Vereisten
Voordat we in de tutorial duiken, zorg ervoor dat je de volgende vereisten hebt:
1. Aspose.GIS for .NET Library: Zorg ervoor dat je de Aspose.GIS for .NET‑bibliotheek geïnstalleerd hebt. Je kunt het downloaden [hier](https://releases.aspose.com/gis/net/).
2. Document Directory: Zorg voor een documentdirectory in je project en noteer het pad.

Laten we nu beginnen met de tutorial!

## Hoe schrijf ik GeoJSON naar een stream?
VectorLayer vertegenwoordigt een vector dataset die kan worden opgeslagen in verschillende formaten, inclusief GeoJSON.  
GeoJsonDriver is de driver die door Aspose.GIS wordt gebruikt om GeoJSON‑bestanden te lezen en te schrijven.  
`layer.Save` schrijft de laaginhoud naar de opgegeven stream met de gespecificeerde opslaan‑opties.

Laad een `VectorLayer` met de `GeoJsonDriver`, voeg features toe die puntgeometrie bevatten, en roep vervolgens `layer.Save(stream, new GeoJsonSaveOptions())` aan. Dit schrijft een volledig, aan de standaarden voldaan GeoJSON‑document direct naar de opgegeven `MemoryStream` in slechts een paar regels code. De methode serialiseert de feature‑collectie, verwerkt attribuutgegevens en geometrie‑conversie automatisch, zodat je een kant‑klaar JSON‑payload krijgt zonder handmatige stringmanipulatie.

## Namespaces importeren
Allereerst, zorg ervoor dat je de benodigde namespaces opneemt om de Aspose.GIS‑functionaliteiten in je code te gebruiken:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Stap 1: Documentdirectory instellen
```csharp
string dataDir = "Your Document Directory";
```
Vervang "Your Document Directory" door het daadwerkelijke pad naar je documentdirectory.

## Stap 2: Maak een Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Stap 3: Maak een Vector Layer met GeoJSON‑driver
De `VectorLayer`‑klasse vertegenwoordigt een vector dataset die kan worden opgeslagen in verschillende formaten, inclusief GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Stap 4: Definieer Feature‑attributen
Definieer het attribuutschema voor je features (bijv. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Stap 5: Bouw en voeg Features toe
Maak `Feature`‑objecten aan, wijs puntgeometrie toe, stel attribuutwaarden in en voeg ze toe aan de laag.  
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

## Stap 6: Toon GeoJSON‑output
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Gefeliciteerd! Je hebt met succes GeoJSON naar een stream geschreven met Aspose.GIS voor .NET.

## Veelvoorkomende problemen en oplossingen
- **Lege output‑stream:** Zorg ervoor dat je de stream‑positie reset (`stream.Position = 0`) vóór het lezen.
- **Onjuiste coördinaatvolgorde:** GeoJSON verwacht longitude‑latitude volgorde; controleer je puntwaarden.
- **Grote datasets:** Gebruik `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` om features incrementeel te streamen.

## Veelgestelde vragen
### Kan ik Aspose.GIS voor .NET gebruiken in zowel Windows‑ als Linux‑omgevingen?
Ja, Aspose.GIS voor .NET is compatibel met zowel Windows‑ als Linux‑systemen.

### Is er een gratis proefversie beschikbaar?
Absoluut! Je kunt een gratis proefversie verkennen [hier](https://releases.aspose.com/).

### Waar kan ik gedetailleerde documentatie vinden?
Bekijk de documentatie [hier](https://reference.aspose.com/gis/net/).

### Hoe kan ik tijdelijke licenties krijgen?
Tijdelijke licenties zijn beschikbaar [hier](https://purchase.aspose.com/temporary-license/).

### Hulp nodig of meer vragen?
Bezoek ons ondersteuningsforum [hier](https://forum.aspose.com/c/gis/33).

**Q: Kan ik GeoJSON genereren uit een collectie van latitude/longitude‑punten?**  
A: Ja – maak een `Feature` voor elk punt, wijs een `Point`‑geometrie toe, en voeg deze toe aan de `VectorLayer`.

**Q: Ondersteunt Aspose.GIS het schrijven van gecomprimeerde GeoJSON (gzip)?**  
A: Je kunt de `MemoryStream` in een `GZipStream` wikkelen vóór het opslaan om een gecomprimeerde payload te produceren.

**Q: Wat is de maximale grootte van een GeoJSON‑bestand die Aspose.GIS aankan?**  
A: De bibliotheek kan bestanden groter dan 2 GB streamen; het geheugenverbruik blijft laag omdat gegevens incrementeel worden geschreven.

---

**Laatst bijgewerkt:** 2026-05-21  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe GeoJSON uit een stream lezen met Aspose.GIS voor .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hoe GeoJSON naar TopoJSON converteren met Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Hoe Shapefile naar GeoJSON converteren met Aspose.GIS voor .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}