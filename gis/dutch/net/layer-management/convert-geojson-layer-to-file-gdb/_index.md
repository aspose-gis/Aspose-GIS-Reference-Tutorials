---
title: GeoJSON naar bestand GDB-conversie gedemystificeerd
linktitle: Converteer GeoJSON-laag naar GDB-bestand
second_title: Aspose.GIS .NET-API
description: Ontgrendel georuimtelijke wonderen met Aspose.GIS voor .NET! Converteer GeoJSON-lagen moeiteloos naar bestandsgeodatabases. Probeer het nu! #Aspose #GIS
type: docs
weight: 17
url: /nl/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## Invoering
In de dynamische wereld van geografische informatiesystemen (GIS) is de mogelijkheid om gegevens naadloos tussen verschillende formaten te converteren cruciaal. Aspose.GIS voor .NET komt naar voren als een krachtige bondgenoot en biedt een uitgebreid pakket tools voor het moeiteloos verwerken van georuimtelijke gegevens. In deze tutorial gaan we dieper in op het proces van het converteren van een GeoJSON-laag naar een File Geodatabase (File GDB) met behulp van Aspose.GIS voor .NET.
## Vereisten
Voordat u aan deze georuimtelijke reis begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Een praktische kennis van .NET-programmering.
-  Aspose.GIS voor .NET geïnstalleerd. Zo niet, download het dan van[hier](https://releases.aspose.com/gis/net/) en volg de installatie-instructies.
## Naamruimten importeren
Om het conversieproces een vliegende start te geven, begint u met het importeren van de benodigde naamruimten:
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
Laten we het proces nu in een stapsgewijze handleiding opsplitsen:
## Stap 1: Stel de GeoJSON-laag in
Begin met het maken van een GeoJSON-laag met relevante attributen en features. Hier is een fragment om u te begeleiden:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Voeg attributen toe
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Creëer en voeg functies toe
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Stap 2: Kopieer de testgegevensset
Om de integriteit van uw testgegevens te behouden, maakt u een kopie van de gegevensset. Gebruik het volgende codefragment:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Stap 3: Converteer GeoJSON naar GDB-bestand
Nu is het tijd om de conversie uit te voeren. Gebruik de volgende code:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Kopieer attributen
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Voeg functies toe
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Conclusie
In deze tutorial navigeerden we door het intrigerende terrein van het converteren van een GeoJSON-laag naar een File Geodatabase met behulp van Aspose.GIS voor .NET. Gewapend met deze kennis bent u nu uitgerust om georuimtelijke gegevens naadloos te manipuleren in uw .NET-toepassingen.
## Veelgestelde vragen
### Is Aspose.GIS compatibel met het nieuwste .NET-framework?
Ja, Aspose.GIS is compatibel met de nieuwste .NET-frameworkversies.
### Kan ik andere georuimtelijke formaten converteren met Aspose.GIS?
Absoluut! Aspose.GIS ondersteunt een breed scala aan georuimtelijke formaten voor veelzijdige gegevensmanipulatie.
### Is er een proefversie beschikbaar voor Aspose.GIS?
 Ja, u kunt de functionaliteiten van Aspose.GIS verkennen door de proefversie te downloaden[hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.GIS-gerelateerde vragen?
 Ga naar Aspose.GIS[forum](https://forum.aspose.com/c/gis/33) voor toegewijde ondersteuning.
### Kan ik een tijdelijke licentie krijgen voor Aspose.GIS?
 Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).