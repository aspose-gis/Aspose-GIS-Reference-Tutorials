---
title: Geef object-ID en geometrieveldnamen op
linktitle: Geef object-ID en geometrieveldnamen op
second_title: Aspose.GIS .NET-API
description: Ontdek GIS-magie met Aspose.GIS voor .NET! Beheer georuimtelijke gegevens moeiteloos. Download nu en ontketen de kracht van ruimtelijke intelligentie.
type: docs
weight: 20
url: /nl/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---
## Invoering
Als je op reis gaat naar het rijk van geografische informatiesystemen (GIS) met behulp van Aspose.GIS voor .NET, gaat er een wereld van mogelijkheden open voor zowel ontwikkelaars als enthousiastelingen. Met deze krachtige bibliotheek kunt u moeiteloos georuimtelijke gegevens verwerken. In deze zelfstudie leiden we u door het proces van het opgeven van object-ID- en geometrieveldnamen, waarmee we de basis leggen voor uw GIS-inspanningen.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.GIS voor .NET: Download en installeer de bibliotheek van[hier](https://releases.aspose.com/gis/net/).
- Documentmap: Stel een map in voor uw documenten om de geodatabases op te slaan.
- .NET-omgeving: Zorg ervoor dat u over een werkende .NET-omgeving beschikt.
## Naamruimten importeren
Om de zaken op gang te brengen, moet u de benodigde naamruimten in uw project importeren. Deze naamruimten bieden de essentiële klassen en methoden voor interactie met Aspose.GIS voor .NET.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## Stap 1: Geef de object-ID en geometrieveldnamen op
In deze stap leert u hoe u de veldnamen Object ID en Geometrie voor uw GIS-gegevens instelt. Dit is cruciaal voor efficiënt databeheer.
## Stap 1.1: Documentmap instellen
Begin met het definiëren van het pad naar uw documentmap:
```csharp
string dataDir = "Your Document Directory";
```
## Stap 1.2: Maak een GeoDatabase en definieer opties
Maak een GeoDatabase met gespecificeerde object-ID- en geometrieveldnamen:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Geef de veldnaam Object-ID op
        GeometryFieldName = "POINT",       // Geef de veldnaam Geometrie op
    };
```
## Stap 1.3: Een laag maken en toevoegen
Maak een laag binnen de GeoDatabase en voeg een object toe met een specifieke geometrie:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Specificeer de geometrie (in dit geval een punt)
    layer.Add(feature);
}
```
## Stap 1.4: Gegevens openen en ophalen uit de laag
Open de laag en haal er gegevens uit op basis van de opgegeven object-ID:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Uitgang: 1
}
```
## Conclusie
Gefeliciteerd! U hebt met succes door het proces genavigeerd van het opgeven van object-ID- en geometrieveldnamen met behulp van Aspose.GIS voor .NET. Dit legt een solide basis voor uw GIS-projecten, waardoor u georuimtelijke gegevens gemakkelijk kunt beheren.
## Veel Gestelde Vragen
### Vraag: Kan ik Aspose.GIS voor .NET gebruiken in mijn webapplicaties?
A: Ja, Aspose.GIS voor .NET is geschikt voor zowel desktop- als webapplicaties en biedt veelzijdige geospatiale mogelijkheden.
### Vraag: Is er een proefversie beschikbaar voordat u deze aanschaft?
 A: Ja, u kunt de functies van Aspose.GIS voor .NET verkennen met een gratis proefversie[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.GIS voor .NET?
 A: U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.
### Vraag: Welke ruimtelijke referentiesystemen ondersteunt Aspose.GIS voor .NET?
A: Aspose.GIS voor .NET ondersteunt verschillende ruimtelijke referentiesystemen, waardoor flexibiliteit wordt geboden voor verschillende geografische datasets.
### Vraag: Waar kan ik hulp zoeken of Aspose.GIS-gerelateerde vragen bespreken?
 A: Bezoek het Aspose.GIS-forum[hier](https://forum.aspose.com/c/gis/33) voor ondersteuning en discussies.