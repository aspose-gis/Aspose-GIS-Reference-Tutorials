---
date: 2026-06-20
description: Leer hoe u geojson naar gdb kunt converteren met Aspose.GIS voor .NET.
  Deze stapsgewijze handleiding behandelt het lezen van GeoJSON in C#, het maken van
  een File Geodatabase en het oplossen van veelvoorkomende problemen.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: GeoJSON-laag converteren naar GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hoe GeoJSON naar GDB converteren met Aspose.GIS voor .NET
url: /nl/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe GeoJSON omzetten naar GDB met Aspose.GIS voor .NET

## Introductie
Als je **convert geojson to gdb** snel en betrouwbaar wilt uitvoeren, ben je hier aan het juiste adres. Deze tutorial leidt je stap voor stap—van het lezen van een GeoJSON‑bestand in C# tot het aanmaken van een File Geodatabase (GDB) met Aspose.GIS. Je ziet waarom Aspose.GIS een voorkeursbibliotheek is voor geospatiale gegevensconversie, hoe je de omgeving instelt, en hoe je de conversie in slechts enkele minuten uitvoert.

## Snelle antwoorden
- **Wat leert deze gids?** Een GeoJSON‑laag omzetten naar een GDB met Aspose.GIS voor .NET.  
- **Welk primair trefwoord wordt getarget?** *convert geojson to gdb*.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Ondersteunde .NET‑versies?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementatietijd?** Ongeveer 10‑15 minuten voor een basisconversie.

## Wat is GeoJSON en File GDB?
GeoJSON is een lichtgewicht, tekstgebaseerd formaat voor geografische objecten, terwijl File GDB een mapgebaseerde, high‑performance ESRI‑geodatabase is.  
GeoJSON slaat punten, lijnen en polygonen op als platte tekst, waardoor het eenvoudig te delen en te bewerken is, terwijl File GDB gegevens in binaire bestanden opslaat die snelle ruimtelijke queries en robuuste attribuuthantering mogelijk maken. Samen dekken ze zowel web‑vriendelijke uitwisseling als high‑speed desktop‑GIS‑verwerking.

## Waarom Aspose.GIS gebruiken voor geospatiale gegevensconversie?
Aspose.GIS biedt een enkele, consistente API die format‑specifieke eigenaardigheden verbergt. Het ondersteunt **30+ geospatiale formaten**, kan bestanden tot **2 GB** verwerken zonder de volledige dataset in het geheugen te laden, en behoudt automatisch coördinatenreferentiesystemen. Dit betekent dat je minder tijd besteedt aan het schrijven van parsers en meer tijd aan het bouwen van je applicatielogica.

## Vereisten
- Bekendheid met C# en .NET‑projectstructuur.  
- Aspose.GIS for .NET geïnstalleerd. Als je het nog niet hebt geïnstalleerd, download het dan van [here](https://releases.aspose.com/gis/net/) en volg de installatiehandleiding. Je kunt ook andere Aspose‑producten verkennen op [here](https://releases.aspose.com/).

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

## Hoe GeoJSON lezen in C#?
Laad het GeoJSON‑bestand met de `GeoJsonReader`‑klasse, die de JSON parseert en een in‑memory `FeatureCollection` maakt. De reader detecteert automatisch het coördinatenreferentiesysteem, zodat je geen CRS‑parsing handmatig hoeft af te handelen. Het ondersteunt ook het streamen van grote bestanden, behoudt attribuuttypen, en kan worden gecombineerd met aangepaste geometrie‑transformaties indien nodig.

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

## Stap 1: GeoJSON‑laag instellen
Maak een tijdelijk GeoJSON‑bestand aan dat de attributen en objecten bevat die je wilt converteren. Dit voorbeeld voegt twee eenvoudige puntobjecten toe.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Stap 2: Testdataset kopiëren
Om de originele testgegevens onaangeroerd te laten, dupliceer je de bestaande File GDB‑dataset. Dit zorgt voor een schone omgeving voor de conversie.

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

## Stap 3: GeoJSON omzetten naar GDB
`FileGdb` vertegenwoordigt een File Geodatabase‑container en biedt methoden om lagen te beheren. Open de GeoJSON‑laag, maak een nieuwe laag aan binnen de gekopieerde File GDB, kopieer attributen en verplaats elk object. Dit is de kern van het **Aspose.GIS conversion**‑proces.

CODE_BLOCK_PLACEHOLDER_4_END

## Hoe GeoJSON omzetten naar GDB?
Laad de GeoJSON met `GeoJsonReader`, instantiateer een `FileGdb`‑object dat naar je bestemmingsmap wijst, maak een nieuwe feature‑laag aan, en iterate vervolgens over elk object om het in te voegen. In de praktijk is het een drie‑stappen‑flow—lezen, aanmaken, kopiëren—die in minder dan een minuut voltooid is voor typische datasets.

## Veelvoorkomende problemen en oplossingen
- **Ontbrekende ruimtelijke referentie:** Zorg ervoor dat de bron‑GeoJSON een CRS‑definitie bevat of stel expliciet `SpatialReferenceSystem.Wgs84` in bij het aanmaken van de GDB‑laag.  
- **Attribuut‑type mismatch:** De attribuut‑datatypes in GeoJSON moeten overeenkomen met het doelschema; anders zal Aspose.GIS een uitzondering werpen.  
- **Bestands‑toegang fouten:** Controleer of de bestemmingsmap schrijfrechten heeft en dat geen ander proces de GDB‑bestanden vergrendelt.

## Veelgestelde vragen
### Is Aspose.GIS compatibel met het nieuwste .NET‑framework?
Ja, Aspose.GIS werkt met .NET Framework 4.5+, .NET Core 3.1+, .NET 5 en .NET 6+.

### Kan ik andere geospatiale formaten omzetten met Aspose.GIS?
Absoluut! Aspose.GIS ondersteunt meer dan 30 invoer‑ en uitvoerformaten, waaronder Shapefile, KML, GML en SQLite.

### Is er een proefversie beschikbaar voor Aspose.GIS?
Ja, je kunt de functionaliteit van Aspose.GIS verkennen door de proefversie te downloaden [here](https://releases.aspose.com/).

### Hoe kan ik ondersteuning krijgen voor Aspose.GIS‑gerelateerde vragen?
Ga naar het Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) voor toegewijde hulp van de community en het productteam.

### Kan ik een tijdelijke licentie voor Aspose.GIS verkrijgen?
Ja, je kunt een tijdelijke licentie verkrijgen [here](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-06-20  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Create File Geodatabase .NET Dataset with Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Read Features from File Geodatabase In Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}