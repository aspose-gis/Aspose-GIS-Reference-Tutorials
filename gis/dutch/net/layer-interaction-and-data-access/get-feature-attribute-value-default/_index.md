---
title: Functiekenmerkwaarde ophalen (standaard)
linktitle: Functiekenmerkwaarde ophalen (standaard)
second_title: Aspose.GIS .NET-API
description: Ontgrendel de kracht van Aspose.GIS voor .NET! Met deze stapsgewijze handleiding kunt u functieattribuutwaarden moeiteloos ophalen en manipuleren. Download nu uw proefversie!
weight: 14
url: /nl/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Functiekenmerkwaarde ophalen (standaard)

## Invoering
Welkom in de wereld van Aspose.GIS voor .NET! In deze uitgebreide handleiding duiken we in de fijne kneepjes van het ophalen van kenmerkattribuutwaarden met behulp van de krachtige mogelijkheden van Aspose.GIS. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze tutorial biedt u een stapsgewijze uitleg, zodat u het volledige potentieel van deze opmerkelijke tool kunt benutten.
## Vereisten
Voordat we aan dit programmeeravontuur beginnen, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:
- Een praktische kennis van C# en .NET framework.
-  Aspose.GIS voor .NET geïnstalleerd. Zo niet, download het dan van[hier](https://releases.aspose.com/gis/net/).
- Een code-editor, zoals Visual Studio, om naadloos mee te volgen.
## Naamruimten importeren
Zorg ervoor dat u in uw C#-project de benodigde naamruimten opneemt:
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
Laten we nu elk voorbeeld opsplitsen in een reeks eenvoudig te volgen stappen.
## Functiekenmerkwaarde ophalen (standaard)
### Stap 1: Stel de omgeving in
Begin met het definiëren van het pad naar uw documentenmap:
```csharp
string dataDir = "Your Document Directory";
```
### Stap 2: Maak een GeoJson-laag
Maak een GeoJson-laag en definieer een attribuut met standaardwaarden:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Stap 3: Construeer een functie
Construeer een object met behulp van het gedefinieerde attribuut:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Stap 4: Waarden ophalen
Attribuutwaarden ophalen met verschillende scenario's:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // waarde == nul
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // waarde == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // waarde == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Standaardwaarden instellen
### Stap 1: Maak nog een GeoJson-laag
Herhaal het proces met een andere GeoJson-laag en een dubbel attribuut:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Stap 2: Bouw een feature (opnieuw)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Stap 3: waarden ophalen en instellen
Attribuutwaarden ophalen en instellen, met standaardwaarden:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // waarde == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // waarde == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // waarde == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Gefeliciteerd! U hebt met succes de kracht van Aspose.GIS voor .NET benut bij het ophalen en manipuleren van kenmerkwaarden.
## Conclusie
In deze zelfstudie hebben we de nuances onderzocht van het ophalen van functieattribuutwaarden met behulp van Aspose.GIS voor .NET. Met zijn intuïtieve API en robuuste mogelijkheden opent Aspose.GIS een wereld aan mogelijkheden voor GIS-ontwikkeling in .NET-omgevingen.
## Veel Gestelde Vragen
### Is Aspose.GIS compatibel met .NET Core?
Ja, Aspose.GIS is volledig compatibel met .NET Core en biedt platformonafhankelijke ondersteuning.
### Kan ik Aspose.GIS gebruiken voor commerciële projecten?
Absoluut! Aspose.GIS wordt geleverd met een commerciële licentie waarmee u het zonder enige beperking in uw commerciële toepassingen kunt gebruiken.
### Waar kan ik aanvullende ondersteuning en hulpmiddelen vinden?
 Bezoek de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) voor gemeenschapsondersteuning en verken de[documentatie](https://reference.aspose.com/gis/net/) voor diepgaande informatie.
### Is er een gratis proefversie beschikbaar?
 Ja, u kunt Aspose.GIS verkennen met een gratis proefperiode. Download het[hier](https://releases.aspose.com/).
### Hoe verkrijg ik een tijdelijke licentie voor testdoeleinden?
 Ga voor tijdelijke licenties naar[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
