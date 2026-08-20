---
date: 2026-07-05
description: Leer hoe u een shapefile naar geojson kunt converteren met Aspose.GIS
  voor .NET. De gids behandelt ook het kopiëren van attributen tussen lagen en het
  genereren van een geojson-bestand met C#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Kenmerken extraheren naar GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Converteer Shapefile naar GeoJSON met Aspose.GIS voor .NET
url: /nl/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converteer Shapefile naar GeoJSON met Aspose.GIS voor .NET

## Introductie
In deze uitgebreide, stapsgewijze tutorial leer je **hoe je een shapefile naar geojson converteert** met behulp van de krachtige Aspose.GIS bibliotheek voor .NET. Of je nu een webservice voor kaarten bouwt, data voorbereidt voor een mobiele GIS-app, of gewoon gegevens tussen formaten moet uitwisselen, deze gids laat je precies zien wat je moet doen, waarom elke stap belangrijk is en hoe je veelvoorkomende valkuilen kunt vermijden.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Het converteren van een Shapefile naar een GeoJSON‑bestand, attributen kopiëren tussen lagen, en het genereren van de output met C#.
- **Welke bibliotheek is vereist?** Aspose.GIS voor .NET.
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productie; een gratis proefversie werkt voor evaluatie.
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisconversie.
- **Kan ik dit uitvoeren op .NET Core/.NET 6?** Ja – de code werkt op alle ondersteunde .NET‑versies.

## Wat is het converteren van een shapefile naar geojson?
Het converteren van een Shapefile naar GeoJSON betekent het lezen van vectorfeatures uit het klassieke ESRI Shapefile‑formaat en deze wegschrijven als een modern, web‑vriendelijk GeoJSON‑document. Deze transformatie stelt je in staat GIS‑gegevens rechtstreeks te voeden aan JavaScript‑kaartenbibliotheken zoals Leaflet of Mapbox GL, en vereenvoudigt de gegevensuitwisseling tussen desktop‑GIS‑tools en web‑API's.

## Waarom Aspose.GIS gebruiken voor deze conversie?
Aspose.GIS abstraheert laag‑niveau binaire parsing, ondersteunt meer dan 50 invoer‑ en uitvoerformaten, en kan datasets van honderden pagina's verwerken zonder het volledige bestand in het geheugen te laden. De bibliotheek biedt bovendien een nette, objectgeoriënteerde API die werkt op .NET Framework, .NET Core en .NET 5/6, zodat je tijd besteedt aan bedrijfslogica in plaats van aan format‑eigenaardigheden.

## Voorwaarden
- Aspose.GIS voor .NET: Zorg ervoor dat je de bibliotheek geïnstalleerd hebt. Zo niet, kun je deze downloaden van de [Aspose.GIS voor .NET-pagina](https://releases.aspose.com/gis/net/).
- Shapefile‑gegevens: Zorg voor een Shapefile die klaar is voor invoer. Als je voorbeeldgegevens nodig hebt, kun je die vinden in de [Aspose.GIS‑documentatie](https://reference.aspose.com/gis/net/).
- .NET‑omgeving: Richt een .NET‑omgeving in om de meegeleverde code uit te voeren.
- Documentmap: Definieer het pad naar je documentmap in het code‑fragment.

Nu alles klaar is, laten we beginnen met het converteren van shapefile naar geojson!

## Hoe converteer je Shapefile naar GeoJSON
Laad de bron‑Shapefile, maak een doel‑GeoJSON‑laag, kopieer het attribuutschema, filter records en schrijf de resultaten — allemaal in een handvol beknopte stappen. De volledige workflow past comfortabel in één `using`‑blok, waardoor bronnen automatisch worden vrijgegeven.

### Stap 1: Open invoer‑Shapefile
De methode `VectorLayer.Open` leest een Shapefile en retourneert een doorzoekbare collectie van `Feature`‑objecten waar je over kunt itereren.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Stap 2: Maak uitvoer‑GeoJSON
`VectorLayer.Create` met de `Drivers.GeoJson` driver maakt een leeg GeoJSON‑bestand dat klaar is om features te ontvangen.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Stap 3: Kopieer attributen tussen lagen
`CopyAttributes` kopieert het attribuutschema (veld‑namen en gegevenstypen) van de bron‑Shapefile naar de nieuwe GeoJSON‑laag in één enkele oproep.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Stap 4: Verwerk features
Itereer door elke feature in de Shapefile zodat je aangepaste logica kunt toepassen voordat je deze wegschrijft.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Stap 5: Filter features op datum
In dit voorbeeld slaan we records over waarvan het `dob` (geboortedatum) veld ontbreekt of eerder is dan 1 jan 1982. Pas de filter aan om aan je eigen gegevensvereisten te voldoen.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Stap 6: Maak een nieuwe feature (C# GeoJSON‑bestand genereren)
Een `Feature` vertegenwoordigt een enkel ruimtelijk element met geometrie‑ en attribuutgegevens.  
Hier bouwen we een nieuwe `Feature` voor de GeoJSON‑laag, kopiëren we de geometrie en attribuutwaarden, en voegen we deze toe aan de output. Dit is de kern van *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Gefeliciteerd! Je hebt met succes **shapefile naar geojson geconverteerd** en geleerd hoe je **attributen tussen lagen kunt kopiëren** onderweg.

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Uitvoerbestand is leeg | `CopyAttributes` aangeroepen nadat de uitvoerlaag is gesloten | Zorg ervoor dat het `using`‑blok voor `outputLayer` open blijft tot nadat alle features zijn toegevoegd. |
| Datumfilter verwijdert alle records | Verkeerde veldnaam of onverwacht datumformaat | Controleer de attribuutnaam (`dob`) en gebruik `GetValue<string>` als datums als strings zijn opgeslagen. |
| Licentie‑exceptie | Uitvoeren zonder een geldige Aspose.GIS‑licentie in productie | Pas een tijdelijke of volledige licentie toe zoals beschreven in de Aspose‑documentatie. |

## Veelgestelde vragen
**Q: Waar kan ik meer documentatie vinden?**  
A: Bezoek de [Aspose.GIS‑documentatie](https://reference.aspose.com/gis/net/) voor diepgaande informatie.

**Q: Hoe kan ik een tijdelijke licentie krijgen?**  
A: Je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik ondersteuning vinden?**  
A: Word lid van het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en discussies.

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja, je kunt de gratis proefversie vinden [hier](https://releases.aspose.com/).

**Q: Waar kan ik Aspose.GIS voor .NET kopen?**  
A: Je kunt het product kopen [hier](https://purchase.aspose.com/buy).

## Conclusie
In deze tutorial hebben we het volledige proces van **shapefile naar geojson converteren** met Aspose.GIS voor .NET verkend, laten we zien hoe je **attributen tussen lagen kunt kopiëren**, en een nette manier getoond om *c# generate geojson file* te doen. Experimenteer met verschillende filters, grotere datasets of extra geometrie‑transformaties om de mogelijkheden van de bibliotheek volledig te benutten.

---

**Laatst bijgewerkt:** 2026-07-05  
**Getest met:** Aspose.GIS voor .NET (laatste stabiele release)  
**Auteur:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Gerelateerde tutorials

- [Hoe GeoJSON naar File GDB converteren met Aspose.GIS voor .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Hoe GeoJSON lezen vanuit stream met Aspose.GIS voor .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hoe GeoJSON naar TopoJSON converteren met Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}