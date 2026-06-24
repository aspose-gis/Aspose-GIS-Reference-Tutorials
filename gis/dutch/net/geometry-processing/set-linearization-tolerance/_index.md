---
date: 2026-05-31
description: Leer hoe je GeoJSON maakt, GeoJSON-opties configureert en een feature
  toevoegt aan een laag met Aspose.GIS voor .NET. Volg deze stapsgewijze handleiding.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Stel linearisatietolerantie in
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hoe GeoJSON met tolerantie te maken met Aspose.GIS voor .NET
url: /nl/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe GeoJSON met tolerantie te maken met Aspose.GIS voor .NET

## Inleiding
Als je **leren hoe GeoJSON te maken** bestanden wilt, de curve‑precisie wilt beheersen en het resultaat wilt exporteren als een kant‑klaar document, maakt Aspose.GIS voor .NET het eenvoudig. In deze tutorial ontdek je hoe je GeoJSON‑opties configureert, de linearization tolerance instelt, en **feature aan laag toevoegen** objecten, terwijl je de code schoon en productie‑klaar houdt.

## Snelle antwoorden
- **Wat betekent “create vector layer”?** Het maakt een nieuwe GIS‑vector dataset (bijv. een GeoJSON‑bestand) die geometrieën en attributen kan opslaan.  
- **Hoe stel ik de linearization tolerance in?** Stel de `LinearizationTolerance`‑eigenschap in op een `GeoJsonOptions`‑instantie voordat je de laag maakt.  
- **Kan ik een GeoJSON‑bestand direct exporteren?** Ja—gebruik `VectorLayer.Create` met de `Drivers.GeoJson`‑driver en de geconfigureerde opties.  
- **Heb ik een licentie nodig?** Een geldige Aspose.GIS‑licentie ontgrendelt alle functies; een tijdelijke evaluatiesleutel werkt voor testen.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is “create vector layer”?
Een vectorlaag maken betekent het initialiseren van een nieuwe GIS‑container (zoals een GeoJSON‑bestand) die punten, lijnen, polygonen en bijbehorende attribuutgegevens kan bevatten. Deze laag wordt het doelwit voor elke geometrie die je maakt en alle attributen die je toevoegt.

## Waarom GeoJSON‑opties configureren?
Het configureren van GeoJSON‑opties—met name de **linearization tolerance**—zorgt ervoor dat gebogen geometrieën (bijv. `CircularString`) worden benaderd met een precisie die voldoet aan de nauwkeurigheidseisen van je applicatie. Een juiste configuratie verkleint de bestandsgrootte terwijl de visuele getrouwheid behouden blijft, wat cruciaal is wanneer de GeoJSON wordt gebruikt door webkaarten of ruimtelijke analysetools.

## Voorvereisten
1. **Visual Studio** (een recente versie).  
2. **Aspose.GIS license** (of een tijdelijke evaluatiesleutel).  
3. **Aspose.GIS for .NET** bibliotheek die in je project is gerefereerd.  
4. Basiskennis van **C#**.

## Importeer namespaces
Importeer eerst de benodigde namespaces zodat de compiler weet waar de GIS‑klassen te vinden zijn:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stapsgewijze handleiding

### Stap 1: GeoJSON‑opties configureren (hoe tolerantie in te stellen)
`GeoJsonOptions` specificeert de serialisatie‑instellingen die worden gebruikt bij het schrijven van GeoJSON‑bestanden.  
`GeoJsonOptions` bepaalt hoe Aspose.GIS GeoJSON serialiseert, inclusief linearization tolerance, coördinatenprecisie en andere uitvoerinstellingen.  
We maken een `GeoJsonOptions`‑object aan en vertellen Aspose.GIS hoe dicht de gelineariseerde geometrie bij de oorspronkelijke curve moet liggen.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Stap 2: Definieer het uitvoerpad (hoe GeoJSON te exporteren)
Geef het volledige bestandspad op waar de resulterende GeoJSON wordt opgeslagen. Zorg ervoor dat de map bestaat en dat de applicatie schrijfrechten heeft.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Stap 3: **Create Vector Layer** met de geconfigureerde opties
De `VectorLayer`‑klasse vertegenwoordigt een GIS‑container die ruimtelijke gegevens kan lezen en schrijven.  
`Drivers.GeoJson` is de driver‑identifier voor het schrijven van GeoJSON‑bestandsformaten.  
Het gebruik van `VectorLayer.Create` samen met de `Drivers.GeoJson`‑driver en de eerder geconfigureerde `GeoJsonOptions` maakt een nieuw GeoJSON‑bestand klaar voor het invoegen van features.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Stap 4: Construeer een geometrie (bijv. een circular string)
`CircularString` is een gebogen lijngeometrie die Aspose.GIS kan lineariseren op basis van de ingestelde tolerantie. Je kunt dit vervangen door elke geldige WKT‑representatie zoals `POINT`, `LINESTRING` of `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Stap 5: **Add Feature to Layer** en opslaan
`Feature` is het object dat een geometrie koppelt aan attribuutgegevens. Na het aanmaken van een `Feature`‑instantie wijs je de geometrie toe, voeg je eventueel attribuutwaarden toe, en roep je `layer.Add(feature)` aan om deze op te slaan. Wanneer het `using`‑blok eindigt, wordt de laag automatisch naar het bestand geschreven dat in `path` is gedefinieerd.

Wanneer het `using`‑blok eindigt, wordt de laag automatisch naar het bestand geschreven dat in `path` is gedefinieerd, waardoor je een kant‑klaar GeoJSON‑bestand krijgt.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

## Veelvoorkomende problemen & tips
- **Onjuist pad** – Controleer of de map bestaat en of je schrijfrechten hebt.  
- **Tolerance te laag** – Het instellen van `LinearizationTolerance` op een zeer kleine waarde kan de bestandsgrootte drastisch verhogen; een tolerantie van 0.001 balanseert meestal precisie en grootte.  
- **Licentiefouten** – Als je licentie‑waarschuwingen ziet, zorg dan dat het licentiebestand wordt geladen vóór enige Aspose.GIS‑aanroep.  
- **Prestatie‑opmerking** – Aspose.GIS ondersteunt het verwerken van bestanden tot 2 GB zonder het volledige document in het geheugen te laden, dankzij de streaming‑architectuur.

## Veelgestelde vragen

**Q: Is Aspose.GIS voor .NET compatibel met andere .NET‑frameworks?**  
A: Ja, het werkt met .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6/7.

**Q: Kan ik Aspose.GIS gebruiken in commerciële projecten?**  
A: Absoluut. Een commerciële licentie verwijdert alle evaluatiebeperkingen en biedt volledige technische ondersteuning.

**Q: Ondersteunt Aspose.GIS andere GIS‑formaten naast GeoJSON?**  
A: Ja, het ondersteunt meer dan 30 formaten — waaronder Shapefile, KML, GML en CSV — waardoor naadloze conversie tussen hen mogelijk is.

**Q: Is er een proefversie beschikbaar?**  
A: Je kunt een gratis proefperiode van 30 dagen downloaden van de Aspose‑website; deze bevat alle functies.

**Q: Waar kan ik ondersteuning krijgen?**  
A: Gebruik de Aspose‑forums, het speciale ondersteuningsportaal, of de link “Contact Support” in het productdashboard.

## Conclusie
Door deze stappen te volgen weet je nu **hoe GeoJSON te maken**, de linearization tolerance te configureren, en **feature aan laag toevoegen** voor een naadloze GeoJSON‑export. Verken extra geometrietypen, attribuutverwerking en bulk‑verwerkingsscenario's om Aspose.GIS volledig te benutten in je .NET GIS‑projecten.

---

**Laatst bijgewerkt:** 2026-05-31  
**Getest met:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe GeoJSON te converteren – Aspose.GIS voor .NET](/gis/net/geo-data-conversion/)
- [Vectorlaag maken, precisie beperken met Aspose.GIS voor .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Vectorlaag maken in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}