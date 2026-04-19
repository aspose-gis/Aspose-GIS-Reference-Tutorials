---
date: 2026-01-10
description: Leer hoe u GeoJSON naar File GDB kunt converteren met Aspose.GIS voor
  .NET. Deze stapsgewijze handleiding behandelt de conversie van georuimtelijke gegevens
  en Aspose GIS-conversie.
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: Hoe GeoJSON converteren naar File GDB met Aspose.GIS voor .NET
url: /nl/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe GeoJSON omzetten naar File GDB met Aspose.GIS voor .NET

## Introductie
Als je je afvraagt **hoe je GeoJSON** kunt omzetten naar een File Geodatabase (File GDB) voor robuuste GIS‑werkstromen, ben je hier aan het juiste adres. In deze tutorial lopen we je stap voor stap door het volledige proces met Aspose.GIS voor .NET, laten we zien waarom deze bibliotheek een topkeuze is voor geospatiale gegevensconversie en hoe je snel een file geodatabase kunt maken van een GeoJSON‑laag.

## Snelle antwoorden
- **Waar gaat de tutorial over?** Het converteren van een GeoJSON‑laag naar een File GDB met Aspose.GIS voor .NET.  
- **Welk primair trefwoord wordt getarget?** *how to convert geojson*.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisconversie.

## Wat is GeoJSON en File GDB?
GeoJSON is een lichtgewicht, tekstgebaseerd formaat voor het coderen van verschillende geografische datastructuren. Een File Geodatabase (File GDB) is een mapgebaseerd, hoog‑presterend formaat dat door veel desktop‑GIS‑toepassingen wordt gebruikt. Conversie tussen beide stelt je in staat de sterke punten van beide formaten in je projecten te benutten.

## Waarom Aspose.GIS gebruiken voor geospatiale gegevensconversie?
Aspose.GIS biedt een uniforme API die de complexiteit van formatafhandeling abstraheert. Met ingebouwde ondersteuning voor **geojson to file gdb** kun je:
- GeoJSON lezen in C# zonder derde‑partij parsers.  
- Programma­matig een file geodatabase aanmaken.  
- Attribuutgegevens en ruimtelijke referentie‑informatie automatisch behouden.  

## Voorvereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:
- Een werkende kennis van .NET‑programmeren.  
- Aspose.GIS voor .NET geïnstalleerd. Zo niet, download het van [hier](https://releases.aspose.com/gis/net/) en volg de installatie‑instructies.

## Namespaces importeren
De eerste stap is om de benodigde namespaces in scope te brengen.

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

## Stap 1: De GeoJSON‑laag instellen
Maak een tijdelijk GeoJSON‑bestand aan dat de attributen en objecten bevat die je wilt converteren. Dit voorbeeld voegt twee eenvoudige punt‑objecten toe.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
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

## Stap 2: Testdataset kopiëren
Om de originele testgegevens onaangeroerd te laten, dupliceer je de bestaande File GDB‑dataset. Dit zorgt voor een schone omgeving voor de conversie.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Stap 3: GeoJSON omzetten naar File GDB
Open de GeoJSON‑laag, maak een nieuwe laag aan binnen de gekopieerde File GDB, kopieer attributen en verplaats elk object. Dit is de kern van het **aspose gis conversion**‑proces.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Veelvoorkomende problemen en oplossingen
- **Ontbrekende ruimtelijke referentie:** Zorg ervoor dat de bron‑GeoJSON een CRS‑definitie bevat of stel expliciet `SpatialReferenceSystem.Wgs84` in bij het aanmaken van de File GDB‑laag.  
- **Attribuut‑type mismatch:** De attribuut‑datatypes in GeoJSON moeten overeenkomen met het doel‑schema; anders zal Aspose.GIS een uitzondering werpen.  
- **Bestands‑toegangsfouten:** Controleer of de doelmap schrijfrechten heeft en dat geen ander proces de GDB‑bestanden vergrendelt.  

## Veelgestelde vragen
### Is Aspose.GIS compatibel met het nieuwste .NET‑framework?
Ja, Aspose.GIS is compatibel met de nieuwste .NET‑frameworkversies.  

### Kan ik andere geospatiale formaten converteren met Aspose.GIS?
Absoluut! Aspose.GIS ondersteunt een breed scala aan geospatiale formaten voor veelzijdige gegevensmanipulatie.  

### Is er een proefversie beschikbaar voor Aspose.GIS?
Ja, je kunt de functionaliteiten van Aspose.GIS verkennen door de proefversie te downloaden [hier](https://releases.aspose.com/).  

### Hoe kan ik ondersteuning krijgen voor Aspose.GIS‑gerelateerde vragen?
Ga naar het Aspose.GIS‑[forum](https://forum.aspose.com/c/gis/33) voor toegewijde ondersteuning.  

### Kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
Ja, je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).  

---

**Laatst bijgewerkt:** 2026-01-10  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}