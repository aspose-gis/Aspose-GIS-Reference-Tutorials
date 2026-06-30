---
date: 2026-06-30
description: Leer hoe je een shapefile maakt met Aspose.GIS voor .NET. Deze stapsgewijze
  handleiding laat zien hoe je een vectorlaag definieert, een datumattribuut toevoegt
  en ruimtelijke gegevens efficiënt beheert.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Nieuwe Shapefile maken
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hoe maak je een Shapefile met Aspose.GIS voor .NET
url: /nl/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een nieuw shapefile

## Introductie
Als je je verdiept in geografische informatiesystemen (GIS) ontwikkeling met .NET, is Aspose.GIS jouw oplossing voor **hoe je een shapefile maakt** via code. Deze bibliotheek geeft je volledige controle over vectorlagen, attribuutschema's en bestandsformaatconformiteit, zodat je gegevens‑pipelines kunt automatiseren of testdatasets in enkele minuten kunt genereren.

## Snelle antwoorden
- **Wat leert deze tutorial?** Hoe je een nieuw shapefile maakt, een vectorlaag definieert en attributen toevoegt (inclusief een datumveld).  
- **Welke bibliotheek is vereist?** Aspose.GIS voor .NET.  
- **Heb ik een licentie nodig?** Een gratis proefversie volstaat voor leren; een commerciële licentie is vereist voor productie.  
- **Welke IDE moet ik gebruiken?** Visual Studio (elke recente versie).  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor het basisvoorbeeld.

## Hoe maak je een shapefile met Aspose.GIS voor .NET?
Laad de Aspose.GIS‑bibliotheek, stel de uitvoermap in, maak een `VectorLayer`, definieer attributen en voeg features toe — deze volledige workflow kan in minder dan 30 regels C# worden geschreven. De bibliotheek behandelt geometriecreatie, attribuuttypen en bestands­schrijven automatisch, zodat je zelf geen low‑level Shapefile‑specificaties hoeft te beheren.

## Vereisten
Voordat we aan de tutorial beginnen, zorg dat je de volgende zaken hebt:
- Basiskennis van de programmeertaal C#.  
- Visual Studio geïnstalleerd op je machine.  
- Aspose.GIS voor .NET‑bibliotheek. Je kunt deze downloaden [hier](https://releases.aspose.com/gis/net/).

## Namespaces importeren
Begin met het importeren van de benodigde namespaces om de functionaliteit van Aspose.GIS te benutten:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Stap 1: Stel je project in
Begin met het aanmaken van een nieuw C#‑project in Visual Studio en voeg de Aspose.GIS‑bibliotheek toe.

## Stap 2: Definieer de documentdirectory
```csharp
string dataDir = "Your Document Directory";
```
Vervang *Your Document Directory* door het daadwerkelijke pad waar je het nieuwe shapefile wilt opslaan.

## Stap 3: Maak een VectorLayer
De `VectorLayer`‑klasse vertegenwoordigt een enkele shapefile‑laag die geometrie‑ en attribuutgegevens opslaat.  
In deze stap definiëren we een vectorlaag en declareren we drie attributen: een tekstveld (`name`), een geheel getal veld (`age`) en een datum‑tijd veld (`dob`). Het toevoegen van het datumattribuut is cruciaal voor **temporale GIS‑shapefile**‑analyses.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Stap 4: Voeg features toe
### Geval 1: Waarden afzonderlijk instellen
De `SetValues`‑methode kent attribuutwaarden toe aan een feature in de volgorde waarin ze zijn gedefinieerd.  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Hier maken we twee punten, stellen elk attribuut apart in en voegen de features toe aan de laag.

### Geval 2: Nieuwe waarden voor alle attributen instellen
Alternatief kun je alle attribuutwaarden in één keer doorgeven met `SetValues` en een object‑array.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
In deze benadering vullen we alle attribuutwaarden in één oproep met een object‑array — handig wanneer je veel attributen hebt.

## Waarom is dit belangrijk?
Een shapefile programmatisch maken stelt je in staat om gegevens‑pipelines te automatiseren, testdatasets te genereren of GIS‑output direct in webservices te embedden. Aspose.GIS ondersteunt **30+ vector‑ en rasterformaten** en kan shapefiles van honderden pagina’s schrijven zonder het volledige bestand in het geheugen te laden, wat zowel snelheid als schaalbaarheid biedt.

## Veelvoorkomende valkuilen & tips
- **Pad‑scheidingstekens:** Gebruik `Path.Combine` voor cross‑platform compatibiliteit in plaats van string‑concatenatie.  
- **Attribuutvolgorde:** De volgorde van waarden in `SetValues` moet overeenkomen met de volgorde waarin je attributen hebt toegevoegd.  
- **Datumafhandeling:** Gebruik altijd `DateTimeKind.Utc` als je GIS‑gegevens over tijdzones heen worden gedeeld.

## Conclusie
Gefeliciteerd! Je hebt met succes een nieuw shapefile gemaakt met Aspose.GIS voor .NET. Deze tutorial besprak de basis van het opzetten van je project, het definiëren van een vectorlaag en het toevoegen van features — inclusief een datumattribuut. Naarmate je verder gaat, raadpleeg dan de [documentatie](https://reference.aspose.com/gis/net/) voor geavanceerde functies en mogelijkheden.

## Veelgestelde vragen
**V: Kan ik Aspose.GIS gebruiken met andere programmeertalen?**  
A: Aspose.GIS ondersteunt voornamelijk .NET, maar er zijn ook versies beschikbaar voor Java.  

**V: Is er een gratis proefversie beschikbaar?**  
A: Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) verkrijgen.  

**V: Waar vind ik ondersteuning voor Aspose.GIS?**  
A: Bezoek het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en discussies.  

**V: Hoe kan ik een tijdelijke licentie verkrijgen?**  
A: Haal je tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) op.  

**V: Waar kan ik Aspose.GIS voor .NET kopen?**  
A: Je kunt de bibliotheek [hier](https://purchase.aspose.com/buy) aanschaffen.

---

**Laatst bijgewerkt:** 2026-06-30  
**Getest met:** Aspose.GIS 24.11 voor .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Get Layer Attributes – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Create Vector Layer and Set Layer Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}