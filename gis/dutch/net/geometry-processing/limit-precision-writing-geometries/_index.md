---
date: 2026-05-31
description: Leer hoe u de precisie kunt beperken bij het schrijven van geometrieën
  met Aspose.GIS voor .NET, waardoor de grootte van GeoJSON wordt verkleind en de
  coördinatencontrole behouden blijft.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Beperk precisie bij het schrijven van geometrieën
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Hoe de precisie beperken bij het schrijven van geometrieën met Aspose.GIS
url: /nl/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de precisie beperken bij het schrijven van geometrieën met Aspose.GIS

Als je je afvraagt **hoe je de precisie kunt beperken** bij het schrijven van geometrieën in een .NET GIS‑applicatie, biedt Aspose.GIS voor .NET een eenvoudige, hoge‑prestaties manier om coördinatenafronding te regelen. In deze tutorial lopen we het volledige proces door — van het opzetten van de omgeving tot het verifiëren dat de output voldoet aan de precisieregels die je definieert.

## Snelle antwoorden
- **Wat betekent “limit precision”?** Het rondt coördinatenwaarden af tot een gedefinieerd aantal fractionele cijfers bij het schrijven van een ruimtelijk bestand.  
- **Welk formaat wordt in het voorbeeld gebruikt?** GeoJSON, maar dezelfde opties gelden voor andere ondersteunde formaten.  
- **Heb ik een licentie nodig om dit te proberen?** Een gratis proefversie werkt voor ontwikkeling en testen; een commerciële licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kan ik de Z‑coördinaatprecisie apart regelen?** Ja — gebruik `ZPrecisionModel` om exacte of afgeronde waarden in te stellen.

## Hoe de precisie beperken bij het schrijven van geometrieën

Laad je GeoJSON‑schrijver met een `GeoJsonOptions`‑object dat de gewenste X/Y‑ en Z‑precisie specificeert, schrijf vervolgens de geometrie en lees deze terug — deze volledige workflow past in minder dan tien regels code en garandeert dat alle coördinaten precies worden afgerond zoals je hebt gedefinieerd.

Het beperken van precisie is essentieel wanneer je een consistente coördinatenrepresentatie nodig hebt over verschillende GIS‑tools, de bestandsgrootte wilt verkleinen, of wilt voldoen aan data‑uitwisselingsstandaarden. Hieronder definiëren we precisie‑opties, schrijven we een geometrie, en lezen we deze terug om de afronding te bevestigen.

## Wat is precisiebeperking?

Precisiebeperking is het proces waarbij het fractionele deel van coördinatenwaarden wordt afgerond tot een vast aantal cijfers voordat de geometrie wordt opgeslagen in een bestandsformaat. Dit zorgt ervoor dat elke gebruiker van het bestand dezelfde numerieke waarden ziet, wat helpt om kleine afwijkingen die topologiefouten kunnen veroorzaken te vermijden.

## Waarom Aspose.GIS gebruiken voor precisie‑controle?

Aspose.GIS ondersteunt **50+** invoer‑ en uitvoerformaten — waaronder GeoJSON, Shapefile, KML en GML — en kan bestanden met **honderdduizenden features** verwerken zonder de volledige dataset in het geheugen te laden. De ingebouwde precisiemodellen laten je coördinaten in één enkele oproep afronden, waardoor handmatige post‑processing‑scripts overbodig worden.

## Voorvereisten

### 1. Downloaden en installatie
Download het nieuwste Aspose.GIS voor .NET‑pakket van de officiële site: [download link](https://releases.aspose.com/gis/net/). Volg de installatiehandleiding om het NuGet‑pakket aan je project toe te voegen.

### 2. Namespace‑import
Voeg de benodigde namespaces toe zodat je toegang hebt tot de GIS‑klassen en hulpprogramma's.

## Stapsgewijze handleiding

### Stap 1: Precisie‑opties definiëren
De `GeoJsonOptions`‑klasse laat je opgeven hoeveel fractionele cijfers je wilt behouden voor X/Y‑ en Z‑coördinaten.

`PrecisionModel` definieert hoe coördinatenwaarden tijdens het schrijven worden afgerond of exact behouden.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Stap 2: Uitvoerpad instellen
Geef op waar het resulterende GeoJSON‑bestand moet worden opgeslagen.

`VectorLayer` is de container van Aspose.GIS voor een verzameling features die hetzelfde schema delen; het schrijft naar het pad dat je opgeeft met behulp van de eerder ingestelde opties.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Stap 3: Geometrie maken en vullen
Open een nieuwe `VectorLayer` met de hierboven gedefinieerde opties, maak een `Point`‑geometrie aan en voeg deze toe aan de laag.

`Point` vertegenwoordigt een enkele coördinaat (X, Y, optioneel Z) in een ruimtelijk referentiesysteem. Het is het eenvoudigste geometrietype en wordt hier gebruikt om precisie‑afronding te demonstreren.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Stap 4: Precisie lezen en verifiëren
Open het bestand dat je zojuist hebt aangemaakt en print de coördinaten. Je zou de X/Y‑waarden afgerond moeten zien op drie decimalen, terwijl de Z‑waarde exact blijft.

Wanneer je het bestand terugleest, parseert Aspose.GIS de afgeronde waarden direct, zodat de `Point` in het geheugen de precisie weerspiegelt die je tijdens het schrijven hebt gedefinieerd.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Veelvoorkomende problemen & tips
- **Padfouten:** Zorg ervoor dat de map in `path` bestaat of gebruik `Path.Combine` met `Environment.CurrentDirectory` om een veilig bestandspad te bouwen.  
- **Precisie niet toegepast:** Controleer of je het `GeoJsonOptions`‑object doorgeeft bij het aanmaken van de laag; anders wordt de standaardprecisie (volledige double) gebruikt.  
- **Grote datasets:** Overweeg voor bulkbewerkingen een enkele `VectorLayer`‑instantie te hergebruiken en features in batches toe te voegen om de prestaties te verbeteren.

## Veelgestelde vragen

**Q: Is Aspose.GIS voor .NET compatibel met andere GIS‑formaten?**  
A: Ja, het ondersteunt **50+** formaten — waaronder Shapefile, GeoJSON, KML, GML en CSV — waardoor naadloze conversie tussen hen mogelijk is.

**Q: Kan ik Aspose.GIS voor .NET uitproberen voordat ik koop?**  
A: Zeker. Een gratis proefversie is beschikbaar vanaf de downloadpagina, waarmee je volledige toegang krijgt tot alle functies voor evaluatie.

**Q: Hoe verkrijg ik een tijdelijke licentie voor testen?**  
A: Tijdelijke evaluatielicenties kunnen worden gegenereerd via het Aspose‑licentieportaal; ze zijn 30 dagen geldig.

**Q: Waar kan ik hulp krijgen als ik problemen ondervind?**  
A: Het Aspose.GIS‑forum en de Stack Overflow‑tag `aspose-gis` zijn uitstekende plekken om vragen te stellen en community‑oplossingen te vinden.

**Q: Werkt de bibliotheek zowel voor kleine scripts als voor enterprise‑schaal toepassingen?**  
A: Ja, Aspose.GIS is ontworpen om alles aan te kunnen, van snelle prototypes tot high‑throughput server workloads, en verwerkt multi‑gigabyte datasets met een lage geheugentoename.

---

**Laatst bijgewerkt:** 2026-05-31  
**Getest met:** Aspose.GIS 24.11 voor .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Vectorlaag maken, precisie beperken met Aspose.GIS voor .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [GeoJSON converteren – Aspose.GIS voor .NET](/gis/net/geo-data-conversion/)
- [Geometrie controleren met Aspose.GIS voor .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}