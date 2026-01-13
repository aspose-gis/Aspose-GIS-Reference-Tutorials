---
date: 2026-01-13
description: Leer hoe u een shapefile naar geojson kunt converteren met Aspose.GIS
  voor .NET. De gids behandelt ook het kopiëren van attributen tussen lagen en het
  genereren van een geojson‑bestand met C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Hoe een Shapefile converteren naar GeoJSON met Aspose.GIS voor .NET
url: /nl/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile converteren naar GeoJSON met Aspose.GIS voor .NET

## Inleiding
In deze uitgebreide, stap‑voor‑stap tutorial leer je **hoe je shapefile naar geojson converteert** met de krachtige Aspose.GIS bibliotheek voor .NET. Of je nu een mapping webservice bouwt, data voorbereidt voor een mobiele GIS‑app, of gewoon data tussen formaten moet uitwisselen, deze gids laat je precies zien wat je moet doen, waarom elke stap belangrijk is, en hoe je veelvoorkomende valkuilen kunt vermijden.

## Snelle antwoorden
- **Wat behandelt deze tutorial?** Het converteren van een Shapefile naar een GeoJSON‑bestand, attributen tussen lagen kopiëren, en de output genereren met C#.
- **Welke bibliotheek is vereist?** Aspose.GIS voor .NET.
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productie; een gratis proefversie werkt voor evaluatie.
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisconversie.
- **Kan ik dit uitvoeren op .NET Core/.NET 6?** Ja – de code werkt op alle ondersteunde .NET‑versies.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- Aspose.GIS voor .NET: Zorg ervoor dat je de bibliotheek geïnstalleerd hebt. Zo niet, kun je deze downloaden van de [Aspose.GIS for .NET page](https://releases.aspose.com/gis/net/).
- Shapefile‑gegevens: Zorg voor een Shapefile die klaar is voor invoer. Als je voorbeeldgegevens nodig hebt, kun je die vinden in de [Aspose.GIS documentation](https://reference.aspose.com/gis/net/).
- .NET‑omgeving: Stel een .NET‑omgeving in om de meegeleverde code uit te voeren.
- Documentmap: Definieer het pad naar je documentmap in het code‑fragment.

Nu je alles klaar hebt, laten we beginnen met het converteren van shapefile naar geojson!

## Wat betekent “shapefile naar geojson converteren”?
Een Shapefile naar GeoJSON converteren betekent het lezen van vectorfeatures uit het klassieke ESRI Shapefile‑formaat en deze wegschrijven als een modern, web‑vriendelijk GeoJSON‑document. GeoJSON wordt veel gebruikt in JavaScript‑mappingbibliotheken (Leaflet, Mapbox GL) en API’s, waardoor de conversie een veelvoorkomende taak is in GIS‑ontwikkeling.

## Waarom Aspose.GIS gebruiken voor deze conversie?
Aspose.GIS abstraheert de low‑level details van bestandsformaten, laat je attributentabellen moeiteloos kopiëren, en biedt een schone, object‑georiënteerde API die werkt op .NET Framework, .NET Core en .NET 5/6. Dit betekent dat je je kunt concentreren op de businesslogica in plaats van binaire bestanden te parseren.

## Namespaces importeren
Voeg eerst de benodigde namespaces toe in je code:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Deze namespaces zijn essentieel voor het werken met Aspose.GIS‑functionaliteiten.

## Hoe Shapefile naar GeoJSON converteren
Hieronder staat de volledige workflow opgesplitst in duidelijke stappen. Elke stap bevat een korte uitleg gevolgd door het exacte code‑fragment dat je moet kopiëren naar je project.

### Stap 1: Invoershapefile openen
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Open de invoer‑Shapefile met de `VectorLayer.Open`‑methode. Dit levert een enumerateerbare collectie van `Feature`‑objecten op.

### Stap 2: Output GeoJSON maken
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Maak het output‑bestand aan met de `VectorLayer.Create`‑methode, waarbij je de `Drivers.GeoJson`‑driver opgeeft.

### Stap 3: Attributen tussen lagen kopiëren
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Deze enkele regel kopieert het attribuutschema (veld‑namen, types) van de bron‑Shapefile naar de nieuwe GeoJSON‑laag — precies wat het secundaire trefwoord *copy attributes between layers* beschrijft.

### Stap 4: Features verwerken
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Itereer door elke feature in de Shapefile zodat je aangepaste logica kunt toepassen voordat je deze wegschrijft.

### Stap 5: Features filteren op datum
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
In dit voorbeeld slaan we records over waarvan het `dob` (date of birth)‑veld ontbreekt of eerder is dan 1 jan 1982. Pas de filter gerust aan om aan je eigen data‑eisen te voldoen.

### Stap 6: Een nieuwe feature construeren (C# GeoJSON‑bestand genereren)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Hier bouwen we een nieuwe `Feature` voor de GeoJSON‑laag, kopiëren we de geometrie en attribuutwaarden, en voegen we deze toe aan de output. Dit is de kern van *c# generate geojson file*.

Gefeliciteerd! Je hebt met succes **shapefile naar geojson geconverteerd** en geleerd hoe je attributen tussen lagen kunt kopiëren.

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Uitvoerbestand is leeg | `CopyAttributes` aangeroepen nadat de output‑laag is gesloten | Zorg ervoor dat het `using`‑blok voor `outputLayer` open blijft tot nadat alle features zijn toegevoegd. |
| Datumfilter verwijdert alle records | Verkeerde veldnaam of onverwacht datumformaat | Controleer de attribuutnaam (`dob`) en gebruik `GetValue<string>` als datums als strings zijn opgeslagen. |
| Licentie‑exception | Uitvoeren zonder een geldige Aspose.GIS‑licentie in productie | Pas een tijdelijke of volledige licentie toe zoals beschreven in de Aspose‑documentatie. |

## Veelgestelde vragen
**V: Waar kan ik meer documentatie vinden?**  
A: Bezoek de [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) voor gedetailleerde informatie.

**V: Hoe kan ik een tijdelijke licentie krijgen?**  
A: Je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

**V: Waar kan ik ondersteuning vinden?**  
A: Word lid van het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en discussies.

**V: Is er een gratis proefversie beschikbaar?**  
A: Ja, je kunt de gratis proefversie vinden [hier](https://releases.aspose.com/).

**V: Waar kan ik Aspose.GIS voor .NET kopen?**  
A: Je kunt het product kopen [hier](https://purchase.aspose.com/buy).

## Conclusie
In deze tutorial hebben we het volledige proces van **shapefile naar geojson converteren** met Aspose.GIS voor .NET verkend, laten zien hoe je attributen tussen lagen kunt kopiëren, en een nette manier getoond om *c# generate geojson file* uit te voeren. Experimenteer met verschillende filters, grotere datasets, of extra geometrie‑transformaties om de mogelijkheden van de bibliotheek volledig te benutten.

---

**Last Updated:** 2026-01-13  
**Getest met:** Aspose.GIS for .NET (latest stable release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}