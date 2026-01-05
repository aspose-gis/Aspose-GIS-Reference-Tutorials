---
date: 2026-01-05
description: Leer hoe u attribuutwaarden kunt ophalen en standaardwaarden kunt instellen
  in Aspose.GIS voor .NET. Deze stapsgewijze gids laat zien hoe u GeoJSON‑lagen maakt
  en GIS‑features construeert.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Hoe de attribuutwaarde (standaard) op te halen met Aspose.GIS voor .NET
url: /nl/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe attribuutwaarde (standaard) op te halen met Aspose.GIS voor .NET

## Introduction
In deze uitgebreide tutorial ontdek je **hoe je attribuut** waarden kunt ophalen uit een GIS-feature met Aspose.GIS voor .NET, en hoe je met standaardwaarden omgaat wanneer een attribuut ontbreekt. Of je nu een spatial analytics engine bouwt of een eenvoudige kaartviewer, het beheersen van attribuutophaling en standaardafhandeling is essentieel voor betrouwbare GIS-toepassingen.

## Quick Answers
- **Wat is de primaire methode?** `Feature.GetValueOrDefault<T>()`  
- **Kan ik een aangepaste standaardwaarde instellen?** Ja, via de overload die een standaardwaarde accepteert of door `DefaultValue` op het attribuut te definiëren.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Ondersteunde geometrieformaten?** GeoJSON, Shapefile, GML, en vele anderen via Aspose.GIS-drivers.  
- **Werkt het met .NET Core/.NET 6+?** Absoluut – de bibliotheek is cross‑platform.

## Prerequisites
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- Basiskennis van C# en het .NET-ecosysteem.  
- Aspose.GIS voor .NET geïnstalleerd. Als je dat nog niet hebt, download het van [hier](https://releases.aspose.com/gis/net/).  
- Een code‑editor zoals Visual Studio of Visual Studio Code.

## Import Namespaces
Voeg de benodigde `using`‑statements toe aan je C#‑bestand zodat de API‑types beschikbaar zijn:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Laten we nu elk voorbeeld stap‑voor‑stap doorlopen.

## How to Get Attribute Value (Default)
### Step 1: Set up the Environment
Definieer het pad naar de map die je testdocumenten bevat:

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create a GeoJSON Layer
We zullen **geojson‑laag maken** — de eerste plaats waar we een attribuut definiëren dat null of niet ingesteld kan zijn:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Step 3: Construct a GIS Feature
Nu **construeren we een GIS‑feature** — dit geeft ons een verse feature‑instantie die het attribuutschema respecteert dat we zojuist hebben gedefinieerd:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Step 4: Retrieve Values
Tot slot **halen we feature‑attribuut** waarden op met verschillende scenario's, waarmee we laten zien hoe standaarden werken:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## How to Set Default Values
### Step 1: Create Another GeoJSON Layer
Deze keer **stellen we attribuut‑standaard** direct in op het schema:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### Step 2: Construct a GIS Feature (Again)
### Stap 2: Construeer een GIS‑feature (opnieuw)

```csharp
    Feature feature = layer.ConstructFeature();
```

### Step 3: Retrieve and Set Values
We halen de standaard op, en wijzigen deze vervolgens om het effect van **hoe standaard in te stellen** tijdens runtime te zien:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Common Pitfalls & Tips
- **Vergeet nooit het `using`‑blok te sluiten.** De laag wordt automatisch vrijgegeven, waardoor bestands‑handles worden vrijgemaakt.  
- **Wanneer `CanBeNull` false is, zal `GetValueOrDefault` altijd een waarde retourneren** (ofwel de opgeslagen of de gedefinieerde standaard).  
- **Gebruik de generieke overload** (`GetValueOrDefault<T>`) om boxing/unboxing voor waardetypen te vermijden.  
- **Pro‑tip:** Als je moet controleren of een attribuut daadwerkelijk is ingesteld, gebruik dan `feature.IsAttributeSet("attribute")` voordat je `GetValueOrDefault` aanroept.

## Frequently Asked Questions
### Is Aspose.GIS compatible with .NET Core?
Ja, Aspose.GIS is volledig compatibel met .NET Core en biedt cross‑platform ondersteuning.

### Can I use Aspose.GIS for commercial projects?
Absoluut! Aspose.GIS wordt geleverd met een commerciële licentie die je toestaat het te gebruiken in je commerciële applicaties zonder beperkingen.

### Where can I find additional support and resources?
Bezoek het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en bekijk de [documentatie](https://reference.aspose.com/gis/net/) voor diepgaande informatie.

### Is there a free trial available?
Ja, je kunt Aspose.GIS uitproberen met een gratis proefversie. Download het [hier](https://releases.aspose.com/).

### How do I obtain a temporary license for testing purposes?
Voor tijdelijke licenties, ga naar [hier](https://purchase.aspose.com/temporary-license/).

## Additional FAQ
**V: Wat gebeurt er als ik `GetValueOrDefault` aanroep op een attribuut dat niet bestaat?**  
A: De methode gooit een `ArgumentException`. Controleer altijd de attribuutnaam of gebruik eerst `feature.HasAttribute("name")`.

**V: Kan ik de standaardwaarde wijzigen nadat de laag is aangemaakt?**  
A: Ja, je kunt `attribute.DefaultValue` aanpassen en vervolgens `layer.UpdateAttribute(attribute)` aanroepen om de wijziging op te slaan.

**V: Ondersteunt Aspose.GIS bulk‑updates van attribuutwaarden?**  
A: Je kunt over een feature‑collectie itereren en `SetValue` aanroepen op elke feature; voor grote datasets kun je overwegen de `FeatureCursor`‑API te gebruiken voor betere prestaties.

## Conclusion
## Conclusie
In deze gids hebben we **hoe je attribuut** waarden ophaalt, hoe je standaarden definieert en overschrijft, en hoe je **GeoJSON‑laag**‑schema's maakt die passen bij de behoeften van je applicatie. Met deze technieken kun je robuuste GIS‑oplossingen bouwen die op elegante wijze omgaan met ontbrekende of optionele gegevens.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}