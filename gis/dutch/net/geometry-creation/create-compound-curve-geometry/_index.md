---
date: 2026-08-24
description: Leer hoe u gebogen lijnen schrijft en samengestelde curve‑geometrieën
  maakt in .NET met Aspose.GIS, waardoor nauwkeurige verwerking van georuimtelijke
  gegevens mogelijk wordt.
keywords:
- write curved lines
- how to add curves
- create compound curve
- curve geometry .net
lastmod: 2026-08-24
linktitle: Hoe u curves toevoegt – Samengestelde curve‑geometrie
og_description: Schrijf gebogen lijnen met Aspose.GIS in .NET om nauwkeurige samengestelde
  curve‑geometrieën te bouwen. Deze gids toont stap‑voor‑stap code, veelvoorkomende
  valkuilen en best‑practice‑tips voor GIS‑ontwikkelaars.
og_image_alt: Developer guide showing how to write curved lines using Aspose.GIS in
  a .NET project
og_title: Schrijf gebogen lijnen met Aspose.GIS in .NET voor GIS‑gegevens
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to write curved lines and create compound curve geometries
    in .NET with Aspose.GIS, enabling precise geospatial data processing.
  headline: How to write curved lines using Aspose.GIS in .NET
  type: TechArticle
- description: Learn how to write curved lines and create compound curve geometries
    in .NET with Aspose.GIS, enabling precise geospatial data processing.
  name: How to write curved lines using Aspose.GIS in .NET
  steps:
  - name: define the output path
    text: Replace the placeholder path with a folder that exists on your machine.
  - name: create a vector layer
    text: A **vector layer** stores spatial features. **Definition anchor:** `VectorLayer`
      represents a container for features of a single geometry type and manages reading/writing
      of GIS files.
  - name: construct the compound curve feature
    text: Here we create a new `Feature` and an empty `CompoundCurve` that will hold
      the individual curve parts.
  - name: define component curves
    text: 'A `LineString` is a sequence of points connected by straight line segments.
      A `CircularString` defines a circular arc using three points: start, intermediate,
      and end. We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. **Definition anchor:** `Line'
  - name: add component curves to the compound curve
    text: Append each component in order so the geometry stays continuous and correctly
      oriented.
  - name: assign geometry to the feature
    text: The assembled `CompoundCurve` becomes the geometry of the feature we will
      store.
  - name: add the feature to the layer
    text: Write the feature into the Shapefile. When the `using` block ends, the file
      is closed and ready for any GIS application.
  type: HowTo
- questions:
  - answer: Yes, the library runs on .NET Framework, .NET Core, .NET Standard, and
      .NET 5/6+ without modification.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It handles Shapefile, GeoJSON, KML, GML, and more than 30
      additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the same API works in console apps, Windows services, ASP.NET Core
      web apps, and cloud‑based functions.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, perform geometric unions/intersections,
      and execute spatial queries directly on the geometry objects.
    question: Can I perform spatial analysis with Aspose.GIS?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions, share snippets, and learn from other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- write curved lines
- Aspose.GIS
- compound curve
- .NET GIS
- geospatial programming
title: Hoe u gebogen lijnen schrijft met Aspose.GIS in .NET
url: /nl/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe kromme lijnen te schrijven met Aspose.GIS in .NET

## Introductie
Als u **kromme lijnen** moet schrijven voor kaarten, routering of enige ruimtelijke analyse, biedt Aspose.GIS een schone, volledig beheerde .NET API om die geometrieën te bouwen. In deze tutorial leert u hoe u krommen kunt toevoegen, ze kunt samenvoegen tot een samengestelde curve, en het resultaat kunt exporteren als een Shapefile (of een ander ondersteund formaat). De stappen zijn snel, de code is eenvoudig, en het resultaat is klaar voor gebruik in elke GIS‑applicatie.

## Snelle antwoorden
- **Wat is het primaire doel?** Kromme lijnen schrijven en ze bundelen in één samengestelde curve‑geometrie.  
- **Welke bibliotheek doet het werk?** Aspose.GIS voor .NET, een puur beheerde GIS‑toolkit.  
- **Wat heeft u van tevoren nodig?** Visual Studio, het Aspose.GIS NuGet‑pakket, en een .NET 6 (of later) project.  
- **Hoe lang duurt een basisvoorbeeld?** Ongeveer 10‑15 minuten om van begin tot eind uit te voeren.  
- **Welke uitvoerformaten worden ondersteund?** Shapefile direct beschikbaar; dezelfde code werkt voor GeoJSON, KML, GML en meer.

## Wat is een samengestelde curve?
Een **samengestelde curve** is één geometrie die verschillende curve‑componenten—rechte lijnreeksen en cirkelbogen—samengevoegd tot één doorlopend pad. Hiermee kunt u kenmerken modelleren zoals kronkelende wegen, rivierbochten, of elk kenmerk dat niet nauwkeurig kan worden weergegeven met een eenvoudige rechte lijn.

## Waarom Aspose.GIS gebruiken voor het schrijven van kromme lijnen?
Een `VectorLayer` vertegenwoordigt een container voor ruimtelijke objecten van één geometrie‑type en behandelt bestands‑I/O voor GIS‑formaten.  
Een `CompoundCurve` is een geometrie die meerdere lijn‑ en boog‑componenten combineert tot één doorlopende vorm.  
Een `Feature` bevat geometrie‑ en attribuutgegevens die kunnen worden opgeslagen in een GIS‑laag.  

Aspose.GIS biedt een uitgebreide, volledig beheerde geometrie‑API waarmee ontwikkelaars lijnreeksen, cirkelreeksen en samengestelde curven kunnen maken en manipuleren zonder externe afhankelijkheden. Het abstraheert de verwerking van bestandsformaten, ondersteunt cross‑platform .NET‑runtime‑omgevingen, en zorgt voor hoge‑prestaties bij lezen/schrijven van GIS‑gegevens.

## Waarom dit belangrijk is
Wanneer kromme geometrieën nauwkeurig worden opgeslagen, kunnen kaart‑renderers vloeiende overgangen weergeven en leveren ruimtelijke berekeningen zoals lengte, buffer of netwerk‑analyse betrouwbare resultaten op. Dit verbetert zowel de visuele getrouwheid als de analytische precisie voor toepassingen variërend van navigatiesystemen tot milieumodellering. Nauwkeurige representaties van kromme lijnen verbeteren de visuele kwaliteit van kaarten en maken precieze ruimtelijke berekeningen mogelijk, zoals afstandsmeting, netwerk‑routering en nabijheidsanalyse. Het beheersen van het schrijven van kromme lijnen verhoogt de getrouwheid van elke GIS‑gedreven .NET‑oplossing.

## Veelvoorkomende toepassingen
- **Transportnetwerken:** Model snelwegen, spoorwegen of fietspaden met vloeiende bochten.  
- **Hydrologie:** Leg rivierbochten vast die natuurlijke bogen volgen.  
- **Stedelijke planning:** Definieer perceelgrenzen met gebogen secties.  
- **Aangepaste symbolen:** Maak decoratieve vormen voor kaartlegenda's of UI‑overlays.

## Voorvereisten
- **Visual Studio** (een recente editie).  
- **Aspose.GIS voor .NET** – download van de [downloadpagina](https://releases.aspose.com/gis/net/).  
- Een C#‑project dat zich richt op **.NET 6** (of een andere ondersteunde versie).

## Namespaces importeren
De volgende namespaces geven u toegang tot de geometrie‑ en I/O‑klassen die u nodig heeft.

**Definition anchor:** `Aspose.Gis` levert de kern‑GIS‑typen; `Aspose.Gis.Geometries` bevat geometrieklassen zoals `LineString` en `CompoundCurve`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hoe kromme lijnen te schrijven met Aspose.GIS?
Het proces omvat het instellen van een uitvoermap, het maken van een `VectorLayer`, het bouwen van een `CompoundCurve` door `LineString`‑ en `CircularString`‑onderdelen toe te voegen, de geometrie toewijzen aan een `Feature`, en tenslotte het object toevoegen aan de laag. Het `using`‑blok zorgt ervoor dat bronnen worden vrijgegeven en de Shapefile correct wordt weggeschreven.

### Stap 1: definieer het uitvoerpad
Vervang het tijdelijke pad door een map die op uw computer bestaat.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Stap 2: maak een vectorlaag
Een **vectorlaag** slaat ruimtelijke objecten op.  

**Definition anchor:** `VectorLayer` vertegenwoordigt een container voor objecten van één geometrie‑type en beheert het lezen/schrijven van GIS‑bestanden.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Stap 3: bouw de samengestelde curve‑feature
Hier maken we een nieuwe `Feature` en een lege `CompoundCurve` die de individuele curve‑onderdelen zal bevatten.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Stap 4: definieer componentcurves
Een `LineString` is een reeks punten verbonden door rechte lijnsegmenten.  
Een `CircularString` definieert een cirkelboog met drie punten: start, tussenliggend en eind.  

We bereiden vijf stukken voor — twee rechte `LineString`s, twee `CircularString`‑bogen, en een laatste `LineString`.  

**Definition anchor:** `LineString` is een reeks punten die een rechte‑lijn polyline vormen, terwijl `CircularString` een cirkelboog definieert met drie punten (start, tussenliggend, eind).  

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Stap 5: voeg componentcurves toe aan de samengestelde curve
Voeg elk component in volgorde toe zodat de geometrie doorlopend en correct georiënteerd blijft.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Stap 6: wijs geometrie toe aan de feature
De samengestelde `CompoundCurve` wordt de geometrie van de feature die we zullen opslaan.

```csharp
feature.Geometry = compoundCurve;
```

### Stap 7: voeg de feature toe aan de laag
Schrijf de feature naar de Shapefile. Wanneer het `using`‑blok eindigt, wordt het bestand gesloten en is het klaar voor elke GIS‑applicatie.

```csharp
layer.Add(feature);
```

## Veelvoorkomende problemen & tips
- **Coördinaatvolgorde:** Aspose.GIS verwacht `X Y` (longitude, latitude). Het omwisselen van de volgorde draait de geometrie om.  
- **CircularString‑syntaxis:** Het middelste punt moet op de beoogde boog liggen; anders valt de curve terug naar een rechte lijn.  
- **Bestand overschrijven:** `VectorLayer.Create` overschrijft een bestaande Shapefile zonder waarschuwing — gebruik een unieke bestandsnaam tijdens ontwikkeling.  
- **Prestatie‑tip:** Voeg bij grote datasets features in batches toe in plaats van ze één voor één in het `using`‑blok in te voegen.  
- **Pro‑tip:** Hergebruik dezelfde `CompoundCurve`‑instantie voor meerdere gelijkaardige features; maak de inhoud leeg met `compoundCurve.Clear()` voordat u opnieuw vult.

## Veelgestelde vragen

**Q: Kan ik Aspose.GIS voor .NET gebruiken met andere .NET‑frameworks?**  
A: Ja, de bibliotheek draait op .NET Framework, .NET Core, .NET Standard, en .NET 5/6+ zonder wijziging.

**Q: Ondersteunt Aspose.GIS het lezen en schrijven van verschillende geospatiale bestandsformaten?**  
A: Absoluut. Het verwerkt Shapefile, GeoJSON, KML, GML, en meer dan 30 extra formaten.

**Q: Is Aspose.GIS geschikt voor zowel desktop‑ als webapplicaties?**  
A: Ja, dezelfde API werkt in console‑apps, Windows‑services, ASP.NET Core web‑apps, en cloud‑gebaseerde functies.

**Q: Kan ik ruimtelijke analyse uitvoeren met Aspose.GIS?**  
A: Ja, u kunt afstanden berekenen, geometrische unies/doorsneden uitvoeren, en ruimtelijke query's direct op de geometrie‑objecten uitvoeren.

**Q: Waar kan ik community‑ondersteuning krijgen voor Aspose.GIS?**  
A: Bezoek het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) om vragen te stellen, fragmenten te delen, en te leren van andere ontwikkelaars.

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.GIS voor .NET (latest stable release)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe krommen om te zetten naar lijnen met Aspose.GIS voor .NET](/gis/net/geometry-processing/linearize-geometry/)
- [Leer hoe u LineString‑geometrie maakt met Aspose.GIS voor .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Maak MultiLineString‑geometrie met Aspose.GIS voor .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}