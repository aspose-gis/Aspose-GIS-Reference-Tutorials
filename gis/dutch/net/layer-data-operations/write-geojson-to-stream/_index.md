---
title: Schrijf GeoJSON om te streamen
linktitle: Schrijf GeoJSON om te streamen
second_title: Aspose.GIS .NET-API
description: Ontdek de kracht van Aspose.GIS voor .NET! Schrijf GeoJSON om moeiteloos te streamen. Download nu voor naadloze georuimtelijke integratie.
weight: 25
url: /nl/net/layer-data-operations/write-geojson-to-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Schrijf GeoJSON om te streamen

## Invoering
Wilt u de kracht van GeoJSON benutten in uw .NET-applicatie met behulp van Aspose.GIS? Nou, je bent op de juiste plek! Deze stapsgewijze handleiding leidt u door het proces van het schrijven van GeoJSON naar een stream, waarbij gebruik wordt gemaakt van de robuuste mogelijkheden van Aspose.GIS voor .NET.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
1. Aspose.GIS voor .NET-bibliotheek: Zorg ervoor dat de Aspose.GIS voor .NET-bibliotheek is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/gis/net/).
2. Documentmap: Zorg ervoor dat er een documentmap in uw project is ingesteld en noteer het pad ervan.
Laten we nu aan de slag gaan met de tutorial!
## Naamruimten importeren
Zorg er allereerst voor dat u de benodigde naamruimten in uw code opneemt om toegang te krijgen tot de Aspose.GIS-functionaliteiten:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## Stap 1: Stel de documentmap in
```csharp
string dataDir = "Your Document Directory";
```
Vervang "Uw documentenmap" door het daadwerkelijke pad naar uw documentmap.
## Stap 2: Maak een geheugenstroom
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code voor de volgende stappen vindt u hier
}
```
## Stap 3: Maak een vectorlaag met GeoJSON Driver
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code voor de volgende stappen vindt u hier
}
```
## Stap 4: Functiekenmerken definiëren
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## Stap 5: Creëer en voeg functies toe
```csharp
// Eerste functie
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Tweede functie
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## Stap 6: Geef GeoJSON-uitvoer weer
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
Gefeliciteerd! U hebt GeoJSON met succes naar een stream geschreven met behulp van Aspose.GIS voor .NET.
## Conclusie
In deze zelfstudie hebben we de fundamentele stappen besproken om Aspose.GIS voor .NET in uw project te integreren, waarbij we ons specifiek richtten op het schrijven van GeoJSON naar een stream. Met deze eenvoudige maar krachtige stappen kunt u de georuimtelijke mogelijkheden van uw toepassing verbeteren.
## Veel Gestelde Vragen
### Kan ik Aspose.GIS voor .NET gebruiken in zowel Windows- als Linux-omgevingen?
Ja, Aspose.GIS voor .NET is compatibel met zowel Windows- als Linux-systemen.
### Is er een gratis proefversie beschikbaar?
 Absoluut! U kunt een gratis proefperiode verkennen[hier](https://releases.aspose.com/).
### Waar kan ik gedetailleerde documentatie vinden?
 Bekijk de documentatie[hier](https://reference.aspose.com/gis/net/).
### Hoe kan ik een tijdelijke licentie krijgen?
 Er zijn tijdelijke licenties beschikbaar[hier](https://purchase.aspose.com/temporary-license/).
### Hulp nodig of meer vragen?
 Bezoek ons ondersteuningsforum[hier](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
