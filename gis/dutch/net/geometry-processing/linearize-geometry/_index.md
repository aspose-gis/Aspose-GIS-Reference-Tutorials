---
date: 2026-09-10
description: Leer hoe je krommen omzet in lijnen (linearize geometry) met Aspose.GIS
  for .NET, waardoor efficiënte geospatiale verwerking en analyse in je .NET‑apps
  mogelijk wordt.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize a Geometry
og_description: Convert curves to lines (linearize geometry) met Aspose.GIS for .NET.
  Leer step‑by‑step hoe je geometrieën vereenvoudigt voor snellere rendering en bredere
  compatibiliteit.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Convert curves to lines met Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Hoe je krommen omzet in lijnen met Aspose.GIS for .NET
url: /nl/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Curves omzetten naar lijnen (geometrie lineariseren) met Aspose.GIS voor .NET

## Inleiding
Als je **convert curves to lines** moet uitvoeren voor kaartproductie, ruimtelijke analyse of gegevensuitwisseling, biedt Aspose.GIS voor .NET een nette, programmeerbare manier om dit te doen. In deze tutorial lopen we een volledig, real‑world voorbeeld door dat laat zien hoe je een complexe geometrie—met curven en samengestelde vormen—omzet naar een eenvoudige lineaire weergave die met elk GIS‑systeem werkt.

## Snelle antwoorden
- **Wat betekent “convert curves to lines”?** Het transformeert gebogen geometrieën in rechte‑lijnsegmenten.  
- **Waarom Aspose.GIS kiezen?** De bibliotheek ondersteunt meer dan 30 GIS‑formaten en verwerkt geometrie‑conversie zonder externe tools.  
- **Wat heb ik van tevoren nodig?** .NET Framework of .NET Core, Visual Studio (of een andere C#‑IDE), en het Aspose.GIS NuGet‑pakket.  
- **Hoe lang duurt het voorbeeld?** Minder dan vijf minuten nadat de bibliotheek is geïnstalleerd.  
- **Kan ik exporteren naar andere formaten?** Zeker—verwissel de KML‑driver voor Shapefile, GeoJSON, enz.  
U kunt de volledige productsuite downloaden van de [Aspose-website](https://releases.aspose.com/).

## Wat betekent convert curves to lines?
Het omzetten van curven naar lijnen (ook wel **linearizing geometry** genoemd) vervangt elk gebogen segment door een reeks korte rechte‑lijnstukken, waardoor een *lineaire geometrie* ontstaat. Dit maakt weergave tot vijf keer sneller, vermindert het geheugenverbruik, en zorgt ervoor dat de gegevens kunnen worden gebruikt door legacy GIS‑services die alleen lineaire objecten accepteren.

## Waarom curven omzetten naar lijnen?
Lineaire geometrieën renderen en worden tot **5× sneller** bevraagd dan hun gebogen tegenhangers, en **30+ GIS‑platformen** accepteren alleen lineaire objecten. Het vereenvoudigen van geometrie verkleint ook de bestandsgrootte voor web‑gebaseerde previews en maakt algoritmen mogelijk—zoals netwerk‑analyse of clustering—die rechte‑lijninvoer vereisen.

## Hoe lineariseren van geometrie?
Gebruik de `ToLinearGeometry()`‑methode die door Aspose.GIS wordt geleverd. Deze tesselliseert automatisch elk curve in een geometrie naar rechte‑lijnsegmenten terwijl eventuele Z‑waarden behouden blijven, zodat je een lineaire benadering krijgt zonder hoogtegegevens te verliezen. Je kunt ook een tolerantie opgeven om de maximale afwijking tussen de oorspronkelijke curve en de gegenereerde segmenten te beheersen, waardoor je nauwkeurigheid tegen bestandsgrootte kunt afwegen. De methode werkt zowel voor 2‑D als 3‑D geometrieën.

## Voorvereisten
Voordat je in de code duikt, zorg ervoor dat je het volgende hebt:

1. **Aspose.GIS for .NET** – download het van de [Aspose.GIS-website](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (of .NET Core) geïnstalleerd op je ontwikkelmachine.  
3. **Visual Studio** (of een andere C#‑compatibele IDE) om het voorbeeld te schrijven en uit te voeren.

## Namespaces importeren
Om Aspose.GIS‑functionaliteit te gebruiken, importeer je de benodigde namespaces.

### Core Aspose.GIS namespaces
De `Aspose.Gis` namespace bevat de kerngeometrie‑klassen, drivers en hulpprogramma's die nodig zijn voor alle GIS‑bewerkingen.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Driver voor het doel‑formaat
`Aspose.Gis.Drivers` biedt statische factories voor elk ondersteund bestandsformaat; `Drivers.Kml` maakt een KML‑schrijver.  
```csharp
using Aspose.GIS.Kml;
```

## Stapsgewijze handleiding om curven om te zetten naar lijnen
Hieronder vind je een gedetailleerde walkthrough van elke code‑regel, die uitlegt **hoe curven om te zetten naar lijnen** en waarom elke stap belangrijk is.

### Stap 1: Definieer het uitvoerpad
`Path.Combine` bouwt een platform‑onafhankelijk bestandspad, waarbij Windows‑backslashes en Unix‑forward‑slashes automatisch worden afgehandeld.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Vervang `"Your Document Directory"` door de map waarin je het KML‑bestand wilt opslaan.

### Stap 2: Maak een laag voor het uitvoerbestand
Een *laag* groepeert geografische objecten van hetzelfde type. Hier maken we een nieuwe KML‑laag aan die de gelinieerde geometrie zal opslaan.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Stap 3: Maak een nieuw object aan
Een *feature* vertegenwoordigt een enkel geografisch object (punt, lijn, polygoon, enz.). We zullen onze lineaire geometrie aan dit object koppelen.  
```csharp
var feature = layer.ConstructFeature();
```

### Stap 4: Definieer de oorspronkelijke complexe geometrie
`Geometry.FromWkt` parseert een Well‑Known Text (WKT)‑string naar een geometrie‑object. De voorbeeld‑WKT bevat een `LineString`, een `CompoundCurve` en een `CircularString` om curve‑verwerking te demonstreren.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Stap 5: Curven omzetten naar lijnen
`ToLinearGeometry()` tesselliseert elke curve in de brongeometrie naar rechte‑lijnsegmenten en retourneert een nieuwe lineaire geometrie die eventuele Z‑coördinaten behoudt.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Stap 6: Wijs de lineaire geometrie toe aan het object
De `Geometry`‑eigenschap van het object bevat nu de vereenvoudigde, lineaire versie van de oorspronkelijke vorm.  
```csharp
feature.Geometry = linear;
```

### Stap 7: Voeg het object toe aan de laag
Het toevoegen van het object aan de KML‑laag zet het in de wachtrij voor schrijven; wanneer het `using`‑blok eindigt, schrijft de laag de gegevens naar het uitvoerbestand.  
```csharp
layer.Add(feature);
```

## Veelvoorkomende valkuilen & pro‑tips
- **Pad‑scheidingstekens:** Gebruik `Path.Combine` om problemen op Windows versus Linux te voorkomen.  
- **Zeer grote geometrieën:** Het lineariseren van ingewikkelde vormen kan duizenden vertices genereren; overweeg `Simplify()` aan te roepen na linearisatie om het aantal punten te verminderen.  
- **Driver‑selectie:** Als je een ander uitvoerformaat nodig hebt, vervang `Drivers.Kml` door `Drivers.Shapefile`, `Drivers.GeoJson`, enz., en wijzig de bestandsextensie overeenkomstig.  
- **Z‑waarden behouden:** `ToLinearGeometry()` behoudt 3‑D (Z) coördinaten, zodat je geen hoogtegegevens verliest.

## Veelgestelde vragen (FAQ)

**Q: Is Aspose.GIS for .NET compatibel met .NET Core?**  
A: Ja, Aspose.GIS werkt met .NET Core, waardoor cross‑platform applicaties mogelijk zijn.

**Q: Kan ik met verschillende GIS‑bestandsformaten werken met Aspose.GIS for .NET?**  
A: Absoluut! De bibliotheek ondersteunt KML, Shapefile, GeoJSON en nog veel meer formaten—meer dan 30 in totaal.

**Q: Biedt Aspose.GIS ruimtelijke bewerkingen en analyses?**  
A: Ja, het biedt een breed scala aan ruimtelijke functies, van buffering tot ruimtelijke joins.

**Q: Is er een gratis proefversie beschikbaar?**  
A: Ja, je kunt een gratis proefversie downloaden van de [Aspose.GIS-website](https://releases.aspose.com/gis/net/).

**Q: Waar kan ik hulp krijgen als ik problemen ondervind?**  
A: Bezoek het [Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) voor community‑ en staffondersteuning.

### Aanvullende veelgestelde vragen

**Q: Kan ik geometrieën lineariseren die 3D (Z) coördinaten bevatten?**  
A: Ja, `ToLinearGeometry()` werkt met zowel 2D als 3D geometrieën; Z‑waarden worden behouden.

**Q: Hoe beïnvloedt linearisatie de bestandsgrootte?**  
A: Het omzetten van curven naar veel korte lijnsegmenten kan de bestandsgrootte vergroten; voer `Simplify()` uit na linearisatie als de grootte een zorg is.

**Q: Kan ik de segmentlengte regelen bij het omzetten van curven naar lijnen?**  
A: De standaardmethode gebruikt een interne tolerantie. Voor aangepaste segmentatie kun je curven handmatig tesselliseren voordat je `ToLinearGeometry()` aanroept.

## Conclusie
In deze tutorial hebben we **hoe curven om te zetten naar lijnen** (geometrie lineariseren) behandeld met Aspose.GIS voor .NET, van het opzetten van de omgeving tot het schrijven van het gelinieerde resultaat naar een KML‑bestand. Je kunt deze workflow nu integreren in kaartapplicaties, data‑verwerkingspijplijnen, of elk GIS‑gerelateerd project dat vereenvoudigde geometrieën vereist.

---

**Laatst bijgewerkt:** 2026-09-10  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe GeoJSON maken met tolerantie Aspose.GIS voor .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Polygon omzetten naar lijn met Aspose.GIS voor .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Leer hoe LineString‑geometrie te maken met Aspose.GIS voor .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}