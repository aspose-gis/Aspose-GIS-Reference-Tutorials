---
date: 2026-06-30
description: Leer hoe u een laag toevoegt aan een File GDB-dataset met Aspose.GIS
  en ruimtelijke referentie WGS84. Volg deze stapsgewijze handleiding om een laag
  toe te voegen in .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Laag toevoegen aan File GDB-dataset
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hoe een laag toevoegen aan een File GDB-dataset met ruimtelijke referentie
  WGS84 met Aspose.GIS
url: /nl/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# hoe een laag toe te voegen – ruimtelijke referentie wgs84 met Aspose.GIS

## Introductie
Klaar om je GIS-werkstroom te verbeteren met Aspose.GIS voor .NET? In deze tutorial leer je **een laag toevoegen** aan een File GDB-dataset terwijl je werkt met het **spatial reference WGS84** coördinatensysteem. We lopen elke stap door, van het voorbereiden van je gegevensmap tot het valideren van de nieuw aangemaakte laag, zodat je geografische data zelfverzekerd en efficiënt kunt manipuleren.

## Snelle antwoorden
- **Wat is het primaire coördinatensysteem dat wordt gebruikt?** spatial reference wgs84 (WGS 84)  
- **Welke bibliotheek levert de API?** Aspose.GIS for .NET  
- **Heb ik een licentie nodig voor testen?** Ja – een tijdelijke Aspose-licentie is beschikbaar.  
- **Kan ik attributen toevoegen aan de nieuwe laag?** Absoluut, je kunt een willekeurig aantal feature-attributen definiëren.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Wat is spatial reference wgs84?
De spatial reference wgs84 (World Geodetic System 1984) is het meest gebruikte geografische coördinatensysteem. Het definieert breedte- en lengtegraad in graden en dient als de standaard CRS voor veel GIS-datasets, inclusief degene die we in deze gids zullen maken.

## Waarom Aspose.GIS gebruiken om een laag toe te voegen?
Laad je GIS-gegevens zonder derden‑binaries en behoud volledige controle over de schema‑definitie. Aspose.GIS ondersteunt **40+ spatial reference systems**, kan bestanden groter dan **2 GB** verwerken zonder de volledige dataset in het geheugen te laden, en draait op Windows, Linux en macOS. Dit maakt het een betrouwbare, cross‑platform oplossing voor enterprise‑grade GIS‑automatisering.

## Vereisten
- Aspose.GIS for .NET Library: Download en installeer de bibliotheek vanaf de [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Maak een speciale map op je computer aan om GIS‑bestanden op te slaan.  
- Een tijdelijke Aspose-licentie (optioneel voor evaluatie) – zie de FAQ hieronder voor de downloadlink.

## Namespaces importeren
Add the required `using` statements to your C# project so you can access Aspose.GIS classes:

*Er is hier geen codeblok vereist; voeg simpelweg de volgende regels toe aan het begin van je bestand:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Stap 1: Map kopiëren
**Definition anchor:** Een File GDB-dataset is een map‑gebaseerde ESRI-geodatabase die ruimtelijke gegevens opslaat in een reeks bestanden.  
Dupliceer eerst de map die de originele GDB-dataset bevat. Het behouden van een kopie beschermt de brongegevens terwijl je experimenteert.

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

## Stap 2: Dataset openen en creatiemogelijkheid verifiëren
`Dataset` vertegenwoordigt een verzameling GIS‑lagen die zijn opgeslagen in een File GDB. Open de nieuw gekopieerde dataset en bevestig dat deze nieuwe lagen kan maken. De `CanCreateLayers`‑eigenschap moet **True** retourneren. **`CanCreateLayers` is een booleaanse eigenschap die aangeeft of de dataset het maken van nieuwe lagen ondersteunt.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Stap 3: Een nieuwe laag maken en vullen met spatial reference wgs84
Nu maken we een laag met de naam **data** en stellen we expliciet de spatial reference in op **Wgs84**. We voegen ook een eenvoudig attribuut genaamd **Name** toe en voegen één punt‑feature in. **`CreateLayer` maakt een nieuwe laag in de dataset met de opgegeven naam en spatial reference.** **`SpatialReference` vertegenwoordigt het coördinatensysteem dat door een laag wordt gebruikt.** **`Feature` is een individueel geografisch object (punt, lijn of polygoon) dat in een laag wordt opgeslagen.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Stap 4: Laag openen en valideren
Open tenslotte de laag die je zojuist hebt gemaakt en controleer de inhoud. De console zal tonen dat de laag één feature bevat en dat het **Name**‑attribuut overeenkomt met wat we hebben ingesteld. **`Layer.Open` opent een bestaande laag voor lezen of bewerken.** Dit bevestigt dat de laag correct is toegevoegd en dat de spatial reference WGS84 is.

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

## Hoe een laag toevoegen aan een File GDB-dataset?
Laad de dataset, roep `CreateLayer` aan met de gewenste naam en spatial reference, definieer het attribuutschema en voeg vervolgens features toe. Dit alles kan worden gedaan met een handvol Aspose.GIS‑methoden, en de API behandelt automatisch bestandsvergrendeling en schema‑validatie. Het proces zorgt ervoor dat de nieuwe laag voldoet aan de spatial reference van de dataset, dat attribuutdefinities worden opgeslagen in het schema van de laag, en dat de gegevens toegankelijk zijn voor elke GIS‑software die File GDB ondersteunt.

## Veelvoorkomende problemen & tips
- **Incorrect path:** Zorg ervoor dat `dataDir` eindigt met een pad‑scheidingsteken (`/` of `\`) zodat de samengevoegde strings geldige bestandspaden vormen.  
- **License errors:** Als je licentie‑waarschuwingen ziet, pas dan een tijdelijke licentie van het Aspose‑portaal toe voordat je de code uitvoert.  
- **CRS mismatch:** Wanneer je de laag later opent in een andere GIS‑tool, controleer dan of de tool WGS 84 (EPSG:4326) herkent als het coördinatensysteem.  
- **Large datasets:** Voor datasets groter dan 1 GB, overweeg `Dataset.OpenReadOnly` te gebruiken om het geheugenverbruik te verminderen.

## Veelgestelde vragen
### V: Kan ik Aspose.GIS voor .NET gebruiken met andere GIS‑bibliotheken?
A: Ja, Aspose.GIS werkt onafhankelijk maar kan worden gecombineerd met bibliotheken zoals GDAL of NetTopologySuite voor geavanceerde verwerking.

### V: Is er een tijdelijke licentie beschikbaar voor testdoeleinden?
A: Ja, je kunt een tijdelijke licentie verkrijgen via [hier](https://purchase.aspose.com/temporary-license/) voor testen en evaluatie.

### V: Welke spatial reference systemen ondersteunt Aspose.GIS voor .NET?
A: Aspose.GIS ondersteunt meer dan **40 EPSG-codes**, inclusief populaire systemen zoals WGS84 (EPSG:4326), Web Mercator (EPSG:3857) en NAD83 (EPSG:4269). Bekijk de uitgebreide documentatie [hier](https://reference.aspose.com/gis/net/).

### V: Kan ik bijdragen aan de Aspose.GIS‑community?
A: Absoluut! Doe mee aan de discussies en deel je ervaringen op het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### V: Waar kan ik gedetailleerde documentatie vinden voor Aspose.GIS voor .NET?
A: Bekijk de uitgebreide documentatie [hier](https://reference.aspose.com/gis/net/) voor diepgaande informatie over alle klassen, methoden en best practices.

---

**Laatst bijgewerkt:** 2026-06-30  
**Getest met:** Aspose.GIS for .NET (latest stable version)  
**Auteur:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Gerelateerde tutorials

- [Maak File Geodatabase .NET Dataset met Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Maak vectorlaag in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Maak File GDB-dataset en stel toleranties in voor een laag](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}