---
title: GIS-beheersing - Voeg lagen toe aan GDB met Aspose.GIS voor .NET
linktitle: Laag toevoegen aan bestand GDB-gegevensset
second_title: Aspose.GIS .NET-API
description: Ontgrendel de kracht van GIS met Aspose.GIS voor .NET! Leer in deze stapsgewijze zelfstudie hoe u lagen kunt toevoegen aan File GDB-gegevenssets. #geografische gegevens #Aspose #GIS
type: docs
weight: 16
url: /nl/net/layer-management/add-layer-to-file-gdb-dataset/
---
## Invoering
Bent u klaar om uw GIS-mogelijkheden te verbeteren met Aspose.GIS voor .NET? In deze stapsgewijze handleiding leiden we u door het proces van het toevoegen van een laag aan een File Geodatabase (GDB)-gegevensset. Aspose.GIS voor .NET biedt krachtige functies voor het manipuleren van geografische informatie, en met deze tutorial kunt u naadloos extra lagen in uw datasets integreren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.GIS voor .NET-bibliotheek: Download en installeer de bibliotheek van de[Aspose.GIS voor .NET-documentatie](https://reference.aspose.com/gis/net/).
- Documentmap: Creëer een speciale documentmap op uw machine om GIS-gerelateerde bestanden op te slaan en te beheren.
## Naamruimten importeren
Zorg ervoor dat u in uw .NET-project de benodigde naamruimten importeert om toegang te krijgen tot de Aspose.GIS-functionaliteiten. Gebruik het volgende codefragment:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Stap 1: Kopieer map
Voordat u doorgaat, dupliceert u de map met uw GDB-gegevensset. Deze stap zorgt ervoor dat de originele dataset intact blijft. Gebruik het meegeleverde codefragment:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Stap 2: Open de dataset en controleer de creatiemogelijkheden
 Open de gedupliceerde gegevensset en controleer of deze lagen kan maken. Dit wordt bevestigd door de aanwezigheid van`True` in de console-uitvoer.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // WAAR
```
## Stap 3: Maak een nieuwe laag en vul deze in
Maak een nieuwe laag binnen de gegevensset, waarbij u het ruimtelijke referentiesysteem, de attributen en een voorbeeldobject definieert. Dit codefragment demonstreert het proces:
```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```
## Stap 4: Open en valideer de toegevoegde laag
Open de laag die u zojuist hebt gemaakt en valideer de inhoud ervan. Controleer het aantal en haal attribuutwaarden op met behulp van de volgende code:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Naam_1"
}
```
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u een laag kunt toevoegen aan een File GDB-gegevensset met behulp van Aspose.GIS voor .NET. Met deze nieuwe vaardigheden kunt u geografische gegevens in uw GIS-projecten efficiënt manipuleren.
## Veel Gestelde Vragen
### Vraag: Kan ik Aspose.GIS voor .NET gebruiken met andere GIS-bibliotheken?
Aspose.GIS voor .NET is ontworpen om zelfstandig te werken, maar kan worden geïntegreerd met andere bibliotheken voor verbeterde functionaliteit.
### Vraag: Is er een tijdelijke licentie beschikbaar voor testdoeleinden?
 Ja, u kunt een tijdelijke licentie verkrijgen via[hier](https://purchase.aspose.com/temporary-license/) voor testen en evalueren.
### Vraag: Welke ruimtelijke referentiesystemen ondersteunt Aspose.GIS voor .NET?
Aspose.GIS voor .NET ondersteunt een breed scala aan ruimtelijke referentiesystemen en biedt flexibiliteit bij de verwerking van geografische gegevens.
### Vraag: Kan ik bijdragen aan de Aspose.GIS-gemeenschap?
 Absoluut! Neem deel aan de discussies en deel uw ervaringen op de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33).
### Vraag: Waar kan ik gedetailleerde documentatie vinden voor Aspose.GIS voor .NET?
 Ontdek de uitgebreide documentatie[hier](https://reference.aspose.com/gis/net/) voor diepgaande informatie over Aspose.GIS voor .NET.