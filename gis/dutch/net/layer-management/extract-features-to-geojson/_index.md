---
title: Extraheer functies naar GeoJSON
linktitle: Extraheer functies naar GeoJSON
second_title: Aspose.GIS .NET-API
description: Verken de stapsgewijze handleiding over het gebruik van Aspose.GIS voor .NET om functies naar GeoJSON te extraheren. Benut de kracht van GIS met gemak! #Aspose #GIS
type: docs
weight: 23
url: /nl/net/layer-management/extract-features-to-geojson/
---
## Invoering
Welkom bij onze stapsgewijze zelfstudie over het extraheren van functies naar GeoJSON met behulp van Aspose.GIS voor .NET! Of u nu een doorgewinterde ontwikkelaar bent of net begint aan uw reis in GIS-programmering, deze gids begeleidt u door het proces, zodat u de volledige kracht van Aspose.GIS voor .NET kunt benutten.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
-  Aspose.GIS voor .NET: Zorg ervoor dat de bibliotheek geïnstalleerd is. Als dit niet het geval is, kunt u deze downloaden van de[Aspose.GIS voor .NET-pagina](https://releases.aspose.com/gis/net/).
-  Shapefile-gegevens: Zorg ervoor dat u een Shapefile gereed heeft voor invoer. Als u voorbeeldgegevens nodig heeft, kunt u deze vinden in de[Aspose.GIS-documentatie](https://reference.aspose.com/gis/net/).
- .NET-omgeving: Zet een .NET-omgeving op om de meegeleverde code uit te voeren.
- Documentmap: definieer het pad naar uw documentmap in het codefragment.
Nu je alles op zijn plaats hebt, gaan we beginnen met het extraheren van functies naar GeoJSON!
## Naamruimten importeren
Neem eerst de benodigde naamruimten op in uw code:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Deze naamruimten zijn essentieel voor het werken met Aspose.GIS functionaliteiten.
## Stap 1: Open het invoer-shapebestand
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Uw code voor het verwerken van het invoer-shapefile komt hier terecht
}
```
 Open het ingevoerde Shapefile met behulp van de`VectorLayer.Open` methode.
## Stap 2: Maak uitvoer-GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Uw code voor het maken van de uitvoer GeoJSON komt hier terecht
}
```
 Maak de uitvoer GeoJSON met behulp van de`VectorLayer.Create` methode.
## Stap 3: Kenmerken kopiëren
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Kopieer attributen van de invoerlaag naar de uitvoerlaag met behulp van de`CopyAttributes` methode.
## Stap 4: Procesfuncties
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Hier vindt u uw code voor het verwerken van elke invoerfunctie
}
```
Doorloop elk object in de invoerlaag en verwerk ze afzonderlijk.
## Stap 5: Filter functies op datum
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filter functies op basis van een datumvoorwaarde. In dit voorbeeld worden elementen met een geboortedatum vóór 1982 overgeslagen.
## Stap 6: Bouw een nieuwe functie
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Construeer een nieuw object voor de uitvoerlaag, waarbij de geometrie en waarden van het invoerobject worden gekopieerd.
Gefeliciteerd! U hebt met succes functies naar GeoJSON geëxtraheerd met behulp van Aspose.GIS voor .NET.
## Conclusie
In deze zelfstudie hebben we het proces van het extraheren van functies naar GeoJSON onderzocht met behulp van Aspose.GIS voor .NET. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor GIS-ontwikkeling. Experimenteer met verschillende datasets en functionaliteiten om het volledige potentieel van Aspose.GIS te ontsluiten.
## Veelgestelde vragen
### Vraag: Waar kan ik meer documentatie vinden?
 Bezoek de[Aspose.GIS-documentatie](https://reference.aspose.com/gis/net/) voor diepgaande informatie.
### Vraag: Hoe kan ik een tijdelijke licentie krijgen?
 U kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Waar kan ik ondersteuning zoeken?
 Sluit je aan bij de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) voor gemeenschapsondersteuning en discussies.
### Vraag: Is er een gratis proefversie beschikbaar?
 Ja, u kunt de gratis proefversie vinden[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik Aspose.GIS voor .NET kopen?
 U kunt het product kopen[hier](https://purchase.aspose.com/buy).