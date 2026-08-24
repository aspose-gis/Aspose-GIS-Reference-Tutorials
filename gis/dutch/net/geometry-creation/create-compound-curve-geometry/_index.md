---
date: 2026-08-24
description: Leer hoe je gebogen lijngeometrie maakt en krommen toevoegt met Aspose.GIS
  voor .NET, waardoor nauwkeurige verwerking van georuimtelijke gegevens mogelijk
  wordt.
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: Hoe je krommen toevoegt – Compound Curve Geometry
og_description: Leer hoe je gebogen lijngeometrie maakt met Aspose.GIS voor .NET.
  Deze tutorial laat stap‑voor‑stap zien hoe je krommen toevoegt en samengestelde
  krommen in enkele minuten bouwt.
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: Hoe maak je gebogen lijngeometrie met Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: Hoe maak je gebogen lijngeometrie met Aspose.GIS
url: /nl/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je gebogen lijngeometrie met Aspose.GIS

## Introductie
In deze gids ontdek je **hoe je gebogen lijngeometrie** maakt met Aspose.GIS voor .NET. Of je nu interactieve kaarten bouwt, ruimtelijke analyses uitvoert of GIS‑datasets genereert, het beheersen van het toevoegen van curves stelt je in staat om real‑world kenmerken te modelleren—zoals kronkelende wegen of slingerende rivieren—met hoge precisie. De tutorial leidt je stap voor stap, van het opzetten van het project tot het exporteren van een herbruikbare samengestelde curve‑geometrie.

## Snelle antwoorden
- **Wat is het primaire doel?** Een samengestelde curve‑geometrie bouwen die rechte lijnen en cirkelboogsegmenten combineert.  
- **Welke bibliotheek wordt gebruikt?** Aspose.GIS voor .NET.  
- **Vereisten?** Visual Studio, Aspose.GIS geïnstalleerd, en een C#‑project gericht op .NET 6 of later.  
- **Typische implementatietijd?** Ongeveer 10‑15 minuten voor een werkend voorbeeld.  
- **Ondersteund uitvoerformaat?** Shapefile (dezelfde code schrijft ook GeoJSON, KML en andere formaten).

## Wat is een samengestelde curve?
Een samengestelde curve is één geometrie die bestaat uit meerdere verbonden curve‑componenten—rechte `LineString`s en cirkelboogsegmenten—samengevoegd tot een complexere vorm. Het is ideaal wanneer een enkele eenvoudige lijn een pad niet nauwkeurig kan weergeven, zoals een snelweg met vloeiende bochten of een rivier die een natuurlijke boog volgt.

## Waarom Aspose.GIS gebruiken voor het toevoegen van curves?
Aspose.GIS biedt een **rijke geometrie‑API** die native ondersteuning biedt voor line strings, circular strings en samengestelde curves, waardoor externe GIS‑bibliotheken overbodig worden. De bibliotheek is **platform‑onafhankelijk**, werkt met .NET Framework 4.6+, .NET Core 2.0+, en .NET 5/6/7+. Hij **verwerkt datasets tot 500 pagina’s vectordata zonder het volledige bestand in het geheugen te laden**, wat snelle, geheugen‑efficiënte bewerkingen oplevert. Export is eenvoudig: je kunt direct naar Shapefile, GeoJSON, KML, GML en meer dan 30 andere formaten schrijven.

## Waarom dit belangrijk is
Het toevoegen van curves stelt je in staat real‑world kenmerken nauwkeuriger te modelleren, wat de visuele kwaliteit van kaart‑renderingen verbetert en de precisie van ruimtelijke analyses zoals nabijheids‑zoekopdrachten of netwerk‑routing verhoogt. Het beheersen van **hoe je gebogen lijngeometrie maakt** verhoogt dus de getrouwheid van elke GIS‑gedreven .NET‑oplossing.

## Veelvoorkomende toepassingsscenario's
- **Transportnetwerken:** Modelleer snelwegen, spoorwegen of fietspaden met vloeiende bochten.  
- **Hydrologie:** Geef rivierlopen weer die natuurlijke bochten volgen.  
- **Stedelijke planning:** Teken perceelgrenzen die gebogen secties bevatten.  
- **Aangepaste symbolen:** Maak decoratieve of schematische vormen voor kaart‑legenda’s.

## Vereisten
- Visual Studio (een recente editie).  
- Aspose.GIS voor .NET gedownload van de [downloadpagina](https://releases.aspose.com/gis/net/).  
- Een C#‑project gericht op .NET 6 (of een andere ondersteunde versie).

## Namespaces importeren
De `using`‑directieven brengen de benodigde Aspose.GIS‑types in scope.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stapsgewijze handleiding om samengestelde curve‑geometrie te maken

### Stap 1: definieer het uitvoerpad
Specificeer eerst waar het resulterende Shapefile moet worden opgeslagen. Vervang de placeholder door een geldige map op je machine.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Stap 2: maak een vectorlaag
`VectorLayer` vertegenwoordigt een ruimtelijke laag die features en hun geometrieën bevat binnen een GIS‑dataset. Het `using`‑blok zorgt ervoor dat het bestand correct wordt gesloten na het schrijven.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Stap 3: bouw het samengestelde curve‑object
De `CompoundCurve`‑klasse is het top‑level object van Aspose.GIS voor een geometrie die bestaat uit meerdere verbonden curve‑onderdelen. Hier maken we een lege samengestelde curve aan die later individuele componenten zal ontvangen.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Stap 4: definieer componentcurves
We bereiden vijf stukken voor—twee rechte `LineString`s, twee `CircularString`‑bogen, en een laatste `LineString`. `LineString` staat voor een eenvoudige rechte lijn gedefinieerd door een geordende lijst van punten. `CircularString` is de weergave van een cirkelboog in Aspose.GIS, gedefinieerd door drie punten (start, midden, einde) die op dezelfde cirkel liggen.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Stap 5: voeg componentcurves toe aan de samengestelde curve
Elke component wordt in volgorde toegevoegd, waarbij continuïteit en oriëntatie behouden blijven. De `Add`‑methode valideert automatisch dat het eindpunt van het ene segment overeenkomt met het startpunt van het volgende.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Stap 6: wijs geometrie toe aan het object
Nu wordt de samengestelde `CompoundCurve` de geometrie van het feature‑object dat we in de laag zullen opslaan.

```csharp
feature.Geometry = compoundCurve;
```

### Stap 7: voeg het object toe aan de laag
Tot slot schrijven we het feature‑object naar het Shapefile. Wanneer het `using`‑blok eindigt, wordt het bestand gesloten en is het klaar voor gebruik in elke GIS‑applicatie.

```csharp
layer.Add(feature);
```

## Veelvoorkomende problemen & tips
- **Coördinatenvolgorde:** Aspose.GIS verwacht coördinaten in `X Y`‑volgorde (longitude, latitude). Het omwisselen van de volgorde draait de geometrie om.  
- **CircularString‑syntaxis:** Het middenpunt moet op de beoogde boog liggen; anders valt de curve terug naar een rechte lijn.  
- **Bestand overschrijven:** `VectorLayer.Create` overschrijft een bestaand Shapefile zonder waarschuwing—gebruik een unieke bestandsnaam tijdens ontwikkeling.  
- **Prestaties:** Voor grote datasets, voeg features in batches toe in plaats van ze één‑voor‑één in het `using`‑blok in te voegen.  
- **Pro tip:** Hergebruik dezelfde `CompoundCurve`‑instantie bij het maken van veel gelijkaardige features; roep `compoundCurve.Clear()` aan voordat je opnieuw vult om toewijzingen te verminderen.

## Veelgestelde vragen

**Q: Kan ik Aspose.GIS voor .NET gebruiken met andere .NET‑frameworks?**  
A: Ja, Aspose.GIS werkt met .NET Framework, .NET Core en .NET Standard, en ondersteunt versies van 4.6 tot .NET 7.

**Q: Ondersteunt Aspose.GIS het lezen en schrijven van verschillende geospatiale bestandsformaten?**  
A: Absoluut. Het leest en schrijft Shapefile, GeoJSON, KML, GML en meer dan 30 extra formaten.

**Q: Is Aspose.GIS geschikt voor zowel desktop‑ als webapplicaties?**  
A: Ja, de bibliotheek kan worden gebruikt in desktop‑, web‑ en cloud‑services zonder platform‑specifieke afhankelijkheden.

**Q: Kan ik ruimtelijke analyses uitvoeren met Aspose.GIS voor .NET?**  
A: Ja, je kunt afstanden berekenen, geometrische bewerkingen uitvoeren en ruimtelijke queries direct op de geometrieën uitvoeren.

**Q: Waar kan ik community‑ondersteuning krijgen voor Aspose.GIS?**  
A: Bezoek het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) om vragen te stellen en ideeën te delen met andere ontwikkelaars.

---

**Laatst bijgewerkt:** 2026-08-24  
**Getest met:** Aspose.GIS voor .NET (nieuwste stabiele release)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak Vector Layer & Circular String in Aspose.GIS voor .NET](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Maak vectorlaag en curve‑polygon met Aspose.GIS](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Converteer WKT naar Geometry: MultiCurve met Aspose.GIS .NET](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}