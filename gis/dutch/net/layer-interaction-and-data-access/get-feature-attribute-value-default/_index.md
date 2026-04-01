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

## Introductie
In deze uitgebreide tutorial ontdek je **hoe je attribuut** waarden kunt ophalen uit een GIS-feature met Aspose.GIS voor .NET, en hoe je met standaardwaarden omgaat wanneer een attribuut ontbreekt. Of je nu een ruimtelijke analyse-engine hebt gebouwd of een eenvoudige kaartviewer, het beheersen van attribuutophaling en standaardafhandeling is essentieel voor betrouwbare GIS-toepassingen.

## Snelle antwoorden
- **Wat is de primaire methode?** `Feature.GetValueOrDefault<T>()`
- **Kan ik een aangepaste standaardwaarde instellen?** Ja, via de overload die een standaardwaarde selecteren of door `DefaultValue` op het attribuut te gecombineerd.
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een wettelijke licentie is vereist voor productie.
- **Ondersteunde geometrieformaten?** GeoJSON, Shapefile, GML, en vele anderen via Aspose.GIS-drivers.
- **Werkt het met .NET Core/.NET 6+?** Absoluut – de bibliotheek is platformonafhankelijk.

## Vereisten
Voordat we beginnen, zorg ervoor dat je de volgende hebt:

- Basiskennis van C# en het .NET-ecosysteem.
- Aspose.GIS voor .NET geïnstalleerd. Als je dat nog niet hebt, download dan het van [hier](https://releases.aspose.com/gis/net/).
- Een code-editor zoals Visual Studio of VisualStudioCode.

## Naamruimten importeren
Voeg de dubbele `using`‑statements toe aan je C#‑bestand zodat de API‑types beschikbaar zijn:

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

## Hoe u een attribuutwaarde kunt verkrijgen (standaard)
### Stap 1: Stel de omgeving in
Definieer het pad naar de kaart die je testdocumenten bevat:

```csharp
string dataDir = "Your Document Directory";
```

### Stap 2: Een GeoJSON-laag maken
We zullen **geojson‑laag maken** — de eerste plaats waar we een attribuut definiëren dat null of niet ingesteld kan zijn:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### Stap 3: Een GIS-object construere
Nu **construeren we een GIS‑feature** — dit geeft ons een verse feature‑instantie die het attribuutschema respecteert dat we zojuist hebben gedefinieerd:

```csharp
    Feature feature = layer.ConstructFeature();
```

### Stap 4: Waarden ophalen
Tot slot **halen we feature‑attribuut** waarden op met verschillende scenario's, waarmee we laten zien hoe standaarden werken:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## Standaardwaarden instellen
### Stap 1: Maak een nieuwe GeoJSON-laag aan
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

### Stap 2: Construeer een GIS‑feature (opnieuw)

```csharp
    Feature feature = layer.ConstructFeature();
```

### Stap 3: Waarden ophalen en instellen
We halen de standaard op, en wijzigen deze vervolgens om het effect van **hoe standaard in te stellen** tijdens runtime te zien:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## Veelvoorkomende valkuilen en tips
- **Vergeet nooit het `using`‑blok te sluiten.** De laag wordt automatisch beïnvloed, waardoor bestands‑handles vrijgemaakt worden.
- **Wanneer `CanBeNull` false is, zal `GetValueOrDefault` altijd een waarde opleveren** (ofwel de opgeslagen of de bedoelde standaard).
- **Gebruik de algemene overload** (`GetValueOrDefault<T>`) om boxing/unboxing voor waardetypen te vermijden.
- **Pro‑tip:** Als je moet controleren of een attribuut daadwerkelijk is ingesteld, gebruik dan `feature.IsAttributeSet("attribute")` voordat je `GetValueOrDefault` aanroept.

## Veelgestelde vragen
### Is Aspose.GIS compatibel met .NET Core?
Ja, Aspose.GIS is volledig compatibel met .NET Core en biedt platformonafhankelijke ondersteuning.

### Kan ik Aspose.GIS gebruiken voor commerciële projecten?
Absoluut! Aspose.GIS wordt geleverd met een conventionele licentie die je toestaat het te gebruiken in je conventionele applicaties zonder beperkingen.

### Waar kan ik aanvullende ondersteuning en hulpmiddelen vinden?
Bezoek het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en bekijk de [documentatie](https://reference.aspose.com/gis/net/) voor diepgaande informatie.

### Is er een gratis proefperiode beschikbaar?
Ja, je kunt Aspose.GIS uitproberen met een gratis proefversie. Download het [hier](https://releases.aspose.com/).

### Hoe verkrijg ik een tijdelijke licentie voor testdoeleinden?
Voor tijdelijke licenties ga naar [hier](https://purchase.aspose.com/temporary-license/).

## Aanvullende veelgestelde vragen
**V: Wat gebeurt er als ik `GetValueOrDefault` aanroep op een attribuut dat niet bestaat?**
A: De methode combineert een `ArgumentException`. Controleer altijd de attribuutnaam of gebruik eerst `feature.HasAttribute("name")`.

**V: Kan ik de standaardwaarde wijzigen nadat de laag is beëindigd?**
A: Ja, je kunt `attribute.DefaultValue` aanpassen en vervolgens `layer.UpdateAttribute(attribute)` aanroepen om de wijziging op te slaan.

**V: Ondersteunt Aspose.GIS bulk‑updates van attribuutwaarden?**
A: Je kunt meer dan een feature‑collectie itereren en `SetValue` aanroepen op elke feature; voor grote datasets kun je overwegen de `FeatureCursor`‑API te gebruiken voor betere prestaties.

## Conclusie
## Conclusie
In deze gids hebben we **hoe je attribuut** waarden ophaalt, hoe je standaarden definieert en overschrijft, en hoe je **GeoJSON‑laag**‑schema's die geschikt maakt bij de behoeften van je applicatie. Met deze technieken kun je robuuste GIS-oplossingen bouwen die op elegante wijze omgaan met ontbrekende van praktische gegevens.

---

**Laatst bijgewerkt:** 05-01-2026
**Getest met:** Aspose.GIS 24.11 voor .NET
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}