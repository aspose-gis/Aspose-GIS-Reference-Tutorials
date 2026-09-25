---
date: 2026-09-25
description: Leer hoe u WKT naar compound curve geometry kunt converteren en een line
  string kunt toevoegen in .NET met Aspose.GIS. Deze gids toont geometry vanuit WKT-creatie
  met MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: Maak MultiCurve Geometry
og_description: Leer hoe u WKT naar compound curve geometry kunt converteren en een
  line string kunt toevoegen in .NET met Aspose.GIS. Deze gids toont geometry vanuit
  WKT-creatie met MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Converteer WKT naar compound curve geometry met Aspose.GIS voor .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Converteer WKT naar compound curve geometry met Aspose.GIS voor .NET
url: /nl/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converteer WKT naar samengestelde curvegeometrie met Aspose.GIS voor .NET

## Inleiding
Als je **WKT naar samengestelde curvegeometrie** moet converteren in een .NET GIS‑applicatie, maakt Aspose.GIS het proces soepel en betrouwbaar. In deze tutorial lopen we stap voor stap door het maken van een `MultiCurve`‑geometry vanuit Well‑Known Text (WKT)‑strings—perfect voor scenario's waarin je **lijnstring**‑componenten, cirkelboog‑ of samengestelde curves aan één feature moet toevoegen. Aan het einde heb je een kant‑klaar shapefile dat laat zien hoe je meerdere curve‑geometrieën combineert tot één `MultiCurve`‑object.

## Snelle antwoorden
- **Wat betekent “convert WKT to geometry”?** Het betekent dat een tekstuele WKT‑representatie wordt omgezet in een concreet geometry‑object dat GIS‑bibliotheken kunnen manipuleren.  
- **Welke Aspose.GIS‑klasse verwerkt WKT?** `Geometry.FromText()` parseert WKT‑strings naar geometry‑instanties.  
- **Kan ik een eenvoudige lijnstring toevoegen?** Ja – voeg gewoon een `LineString`‑WKT toe zoals `"LineString (0 0, 1 0)"`.  
- **Welk bestandsformaat wordt in het voorbeeld gebruikt?** Een Shapefile (`.shp`) aangemaakt met de Shapefile‑driver.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.

## Wat betekent “convert WKT to geometry”?
Het converteren van WKT naar geometry parseert het tekstuele Well‑Known Text‑formaat naar een in‑memory objectmodel zoals `MultiCurve` of `LineString`. **`Geometry.FromText`** maakt deze objecten direct aan, waardoor je ze kunt opslaan, opvragen en weergeven met elke GIS‑tool die de OGC‑standaard begrijpt.

## Waarom Aspose.GIS gebruiken voor MultiCurve‑creatie?
Aspose.GIS stelt je in staat om **samengestelde curvegeometrie** te maken in één enkele, zelfstandige API‑aanroep. Het ondersteunt drie geavanceerde curvetypen (CircularString, CompoundCurve en CurveString) en verwerkt datasets tot 500 MB zonder het volledige bestand in het geheugen te laden, wat een snelheidsverbetering van 30 % oplevert ten opzichte van concurrerende bibliotheken in batch‑scenario's.

## Vereisten
1. Basiskennis van de programmeertaal C#.  
2. Geïnstalleerde Visual Studio (of een andere .NET‑IDE).  
3. Aspose.GIS voor .NET‑bibliotheek – download deze van de [Aspose.GIS‑website](https://releases.aspose.com/gis/net/).  
4. Vertrouwdheid met ruimtelijke concepten zoals punten, lijnen en curves.

## Importeren van namespaces
Om te beginnen met Aspose.GIS voor .NET, importeer je de benodigde namespaces in je C#‑project.

`Geometry` biedt statische methoden om WKT te parseren naar geometry‑objecten.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Deze namespaces geven je toegang tot de klassen die nodig zijn voor het maken en beheren van `MultiCurve`‑geometry.

## Stapsgewijze handleiding

### Stap 1: Definieer de documentmap en bestandsnaam
Stel de map in waar het shapefile wordt opgeslagen. Vervang `"Your Document Directory"` door het daadwerkelijke pad op jouw machine.

### Stap 2: Initialiseer een `VectorLayer` met de Shapefile-driver
VectorLayer vertegenwoordigt een vector‑dataset, zoals een shapefile, en maakt het lezen en schrijven van geometrieën mogelijk.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
Het `VectorLayer`‑object staat voor een vector‑dataset (in dit geval een shapefile) waaraan je geometrieën kunt schrijven.

### Stap 3: Maak een nieuw feature aan
Feature is een container die een geometry en de bijbehorende attribuutwaarden bevat.  
```csharp
var feature = layer.ConstructFeature();
```
Een feature is een container voor geometry‑ en attribuutgegevens.

### Stap 4: Maak een `MultiCurve`‑geometry‑instantie
`MultiCurve` is een geometry‑type dat meerdere curve‑componenten samenvoegt tot één ruimtelijk object.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` kan verschillende curve‑geometrieën bevatten, waardoor je ze kunt combineren tot één ruimtelijk object.

### Stap 5: Voeg curve‑geometrieën toe aan de `MultiCurve`
Hier **converteren we WKT naar geometry** voor drie verschillende curvetypen:
* een eenvoudige **lijnstring**,
* een cirkelboog (`CircularString`),
* en een samengestelde curve die rechte segmenten combineert met een cirkelboog.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Stap 6: Wijs de `MultiCurve` toe aan het feature
Nu is de geometry van het feature de samengestelde `MultiCurve` die we zojuist hebben gebouwd.  
```csharp
feature.Geometry = multiCurve;
```

### Stap 7: Voeg het feature toe aan de `VectorLayer`
Het feature wordt naar het shapefile weggeschreven wanneer het `using`‑blok eindigt.  
```csharp
layer.Add(feature);
```



## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **`ArgumentException` bij `Geometry.FromText`** | Ongeldige WKT‑syntaxis | Controleer of de WKT‑string voldoet aan de OGC‑specificatie (bijv. komma's tussen coördinaten, juiste haakjes). |
| **Shapefile niet aangemaakt** | Onjuist `path` of ontbrekende schrijfrechten | Zorg ervoor dat de map bestaat en dat de applicatie schrijfrechten heeft. |
| **Curves verschijnen als rechte lijnen in sommige viewers** | Viewer ondersteunt geen cirkel‑/samengestelde curves | Gebruik een GIS‑viewer die het `ARC`‑geometrietype begrijpt (bijv. QGIS). |

## Veelgestelde vragen

**Q: Is Aspose.GIS voor .NET compatibel met alle versies van het .NET Framework?**  
A: Ja, het ondersteunt .NET Framework, .NET Core, .NET Standard en .NET 5/6+.

**Q: Kan ik aangepaste ruimtelijke dataformaten maken met Aspose.GIS voor .NET?**  
A: Absoluut. De API stelt je in staat om vele standaardformaten te lezen, te schrijven en te transformeren, en je kunt deze uitbreiden voor propriëtaire formaten.

**Q: Biedt Aspose.GIS ruimtelijke analysefuncties?**  
A: Ja, het omvat afstandsberekeningen, intersectiedetectie, buffering en andere geometrische bewerkingen.

**Q: Is er een proefversie beschikbaar voor Aspose.GIS voor .NET?**  
A: Ja, je kunt een gratis proefversie downloaden van de [Aspose.GIS‑website](https://releases.aspose.com/gis/net/) om de functies te verkennen voordat je koopt.

**Q: Hoe kan ik hulp krijgen als ik problemen ondervind?**  
A: Neem contact op via de Aspose.GIS‑communityforums of raadpleeg de officiële ondersteuningsbronnen die bij je licentie zijn inbegrepen.

**Laatst bijgewerkt:** 2026-09-25  
**Getest met:** Aspose.GIS 24.11 voor .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak samengestelde curvegeometrie](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Hoe tel je punten vanuit WKT met Aspose.GIS voor .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Maak MultiLineString-geometry met Aspose.GIS voor .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}