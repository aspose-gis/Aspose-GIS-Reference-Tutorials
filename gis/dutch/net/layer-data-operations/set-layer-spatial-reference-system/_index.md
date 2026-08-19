---
date: 2026-06-15
description: Leer hoe u een vector layer maakt en het layer spatial reference system
  instelt met Aspose.GIS voor .NET. Beheers het definiëren van spatial reference,
  het toevoegen van een point feature, en het ophalen van de EPSG code.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Layer Spatial Reference System instellen
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vector Layer maken en Layer Spatial Reference System instellen
url: /nl/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vectorlaag maken en ruimtelijk referentiesysteem van laag instellen

## Inleiding
In het uitgestrekte landschap van Geographic Information Systems (GIS) onderscheidt **Aspose.GIS for .NET** zich als een robuuste, high‑performance bibliotheek die **70+** vector- en rasterformaten ondersteunt en bestanden groter dan **10 GB** kan verwerken zonder de volledige dataset in het geheugen te laden. In deze tutorial zul je **een vectorlaag maken**, de ruimtelijke referentie definiëren, **een puntfeature toevoegen**, en de EPSG‑code ophalen — allemaal met duidelijke, stap‑voor‑stap begeleiding. Of je nu een kaartservice, een data‑conversiepijplijn, of een ruimtelijke analyse‑engine bouwt, het beheersen van deze basisprincipes houdt het coördinatensysteem van je shapefile nauwkeurig en je GIS‑workflow betrouwbaar.

## Snelle antwoorden
- **Wat betekent “create vector layer”?** Het maakt een nieuwe GIS‑laag (bijv. een Shapefile) die geometrieën zoals punten, lijnen of polygonen kan opslaan.  
- **Welke EPSG‑code wordt in het voorbeeld gebruikt?** EPSG 26918 (NAD83 / UTM‑zone 18N).  
- **Kan ik een puntfeature toevoegen nadat de laag is aangemaakt?** Ja — gebruik `ConstructFeature()` en wijs een `Point`‑geometrie toe.  
- **Hoe haal ik het CRS van de laag op?** Lees `layer.SpatialReferenceSystem.EpsgCode` of `.Name`.  
- **Heb ik een licentie nodig voor Aspose.GIS?** Er is een gratis proefversie beschikbaar; een licentie is vereist voor productiegebruik.

## Wat is “create vector layer”?
De **create vector layer**‑operatie maakt een nieuwe vector dataset (zoals een Shapefile) aan die geometrische features en attributengegevens kan bevatten. In Aspose.GIS gebeurt dit door een `VectorLayer`‑object te instantieren met een driver en een ruimtelijk referentiesysteem.

## Waarom het coördinatensysteem (CRS) van de laag correct instellen?
Het instellen van het juiste coördinatenreferentiesysteem (CRS) zorgt ervoor dat elke geometrie die je opslaat, overeenkomt met andere ruimtelijke datasets. Met Aspose.GIS kun je het CRS definiëren met een standaard EPSG‑code, wat interoperabiliteit met GIS‑software wereldwijd garandeert. Bijvoorbeeld, EPSG 26918 definieert NAD83 / UTM‑zone 18N, een veelgebruikte projectie voor gegevens in het oosten van de Verenigde Staten.

## Vereisten
- Ervaring met .NET‑ontwikkeling (C# of VB.NET).  
- Visual Studio 2022 of later.  
- Aspose.GIS for .NET‑bibliotheek – download het **[hier](https://releases.aspose.com/gis/net/)**.  
- Basiskennis van ruimtelijke referentiesystemen (CRS/EPSG).

## Namespaces importeren
De `Aspose.Gis`‑namespace biedt de kern‑GIS‑klassen, terwijl `Aspose.Gis.Geometries` je geometrietypen zoals `Point` levert.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Hoe maak je een vectorlaag in Aspose.GIS for .NET?
VectorLayer vertegenwoordigt een vector dataset zoals een Shapefile en biedt methoden om features te maken, lezen en bewerken.  
SpatialReferenceSystem definieert het coördinatenreferentiesysteem met een EPSG‑code.  

Laad de doelmap, definieer een EPSG‑gecodeerd `SpatialReferenceSystem` en roep `VectorLayer.Create` aan met de Shapefile‑driver. Deze enkele oproep maakt een nieuw `.shp`‑bestand aan, schrijft de bijbehorende `.shx`‑ en `.dbf`‑bestanden, en voegt de CRS‑metadata toe, klaar voor efficiënte feature‑invoeging.

### Stap 1: Specificeer de documentdirectory
Begin met het opgeven van het pad naar je documentdirectory. Dit wordt de locatie waar je ruimtelijke gegevensbestanden worden opgeslagen.

```csharp
string dataDir = "Your Document Directory";
```

### Stap 2: Definieer ruimtelijk referentiesysteem en stel shapefile‑coördinatensysteem in
SpatialReferenceSystem vertegenwoordigt het CRS van een laag, geïdentificeerd door een EPSG‑code.  

Definieer het pad voor de Shapefile en **definieer de ruimtelijke referentie** met de EPSG‑code (26918 in dit voorbeeld). Deze stap **stelt het shapefile‑coördinatensysteem** voor de laag in.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Hoe kun je een puntfeature toevoegen aan een vectorlaag?
`Point` is een geometrietype dat een enkel X/Y‑coördinaatpaar vertegenwoordigt.  

Construeer een nieuwe feature, wijs een `Point`‑geometrie toe met de gewenste X/Y‑coördinaten, en voeg de feature toe aan de geopende `VectorLayer`. De operatie schrijft de geometrie naar het `.shp`‑bestand en het attribuutrecord naar het `.dbf`‑bestand in één transactie.

### Stap 3: Vectorlaag maken
`ConstructFeature` maakt een nieuw feature‑object aan dat geometrie en attributengegevens kan bevatten.  

Nu **maak je een vectorlaag** met het opgegeven Shapefile‑pad, driver‑type (Shapefile), en het ruimtelijk referentiesysteem dat je zojuist hebt gedefinieerd.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Stap 4: Puntfeature toevoegen aan de laag
Construeer een nieuwe feature en **voeg een puntfeature toe** door de geometrie in te stellen (een `Point` met coördinaten 60, 24). Voeg vervolgens de feature toe aan de vectorlaag.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Stap 5: Ruimtelijk referentiesysteeminformatie ophalen (EPSG‑code ophalen)
Open de Vector Layer en haal informatie op over het ruimtelijk referentiesysteem, zoals de EPSG‑code en de mens‑leesbare naam. Dit toont hoe je **de EPSG‑code kunt ophalen** en **het CRS van de laag kunt instellen**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Laag kan niet worden geopend** | Verkeerde driver of beschadigd bestandspad | Controleer `Drivers.Shapefile` en zorg dat `path` naar een bestaand `.shp`‑bestand wijst. |
| **Onjuist CRS weergegeven** | Gebruik van de verkeerde EPSG‑code | Controleer de EPSG‑code nogmaals met een gezaghebbende bron (bijv. EPSG.io). |
| **Feature niet opgeslagen** | Geen `layer.Add(feature)` aanroep binnen het `using`‑blok | Zorg ervoor dat de `Add`‑methode wordt uitgevoerd voordat de laag wordt vrijgegeven. |

## Veelgestelde vragen
**Q: Hoe wijzig ik het CRS van een bestaande Shapefile?**  
A: Open de laag, maak een nieuw `SpatialReferenceSystem` met de gewenste EPSG‑code, wijs het toe aan `layer.SpatialReferenceSystem`, en sla vervolgens de laag op.

**Q: Kan ik andere geometrietypen (bijv. polygonen) toevoegen met dezelfde aanpak?**  
A: Ja — vervang `new Point(x, y)` door `new Polygon(...)` of `new LineString(...)` indien nodig.

**Q: Is het mogelijk om efficiënt met grote datasets te werken?**  
A: Gebruik streaming‑API’s (`VectorLayer.Create` met `FeatureCollection`) en maak lagen direct vrij om bronnen vrij te geven.

**Q: Ondersteunt Aspose.GIS coördinatentransformatie?**  
A: Ja — gebruik `Geometry.Transform(targetSrs)` om geometrieën te reprojeteren tussen verschillende ruimtelijke referenties.

**Q: Welke .NET‑versies worden ondersteund?**  
A: Aspose.GIS werkt met .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

**Laatst bijgewerkt:** 2026-06-15  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Vectorlaag maken en linearisatietolerantie instellen met Aspose.GIS voor .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Vectorlaag maken in File GDB – Aspose.GIS .NET tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Laag toevoegen aan GDB met Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}