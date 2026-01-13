---
date: 2026-01-13
description: Leer hoe u een nieuw shapefile maakt met Aspose.GIS voor .NET. Deze stapsgewijze
  handleiding laat u zien hoe u een vectorlaag definieert, een datumattribuut toevoegt
  en ruimtelijke gegevens beheert.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Nieuwe shapefile maken
url: /nl/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nieuwe Shapefile Maken

## Inleiding
Als je je verdiept in de ontwikkeling van geografische informatiesystemen (GIS) met .NET, is Aspose.GIS jouw go‑to‑oplossing. Deze krachtige bibliotheek stelt ontwikkelaars in staat om naadloos met ruimtelijke gegevens te werken, en in deze tutorial leiden we je stap voor stap door het **maken van een nieuwe shapefile** met Aspose.GIS voor .NET. Je zult zien waarom het definiëren van een vectorlaag en het toevoegen van een datum‑attribuut essentiële stappen zijn voor robuuste GIS‑projecten.

## Snelle Antwoorden
- **Wat leert deze tutorial?** Hoe je een nieuwe shapefile maakt, een vectorlaag definieert en attributen toevoegt (inclusief een datumveld).  
- **Welke bibliotheek is vereist?** Aspose.GIS voor .NET.  
- **Heb ik een licentie nodig?** Een gratis proefversie is voldoende voor leren; een commerciële licentie is vereist voor productie.  
- **Welke IDE moet ik gebruiken?** Visual Studio (een recente versie).  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor het basisvoorbeeld.

## Vereisten
Voordat we aan de tutorial beginnen, zorg ervoor dat je de volgende vereisten hebt:
- Basiskennis van de programmeertaal C#.
- Visual Studio geïnstalleerd op je computer.
- Aspose.GIS voor .NET bibliotheek. Je kunt deze downloaden [hier](https://releases.aspose.com/gis/net/).

## Importer Namespaces
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
Begin met het maken van een nieuw C#‑project in Visual Studio en voeg de Aspose.GIS‑bibliotheek toe.

## Stap 2: Definieer de documentdirectory
```csharp
string dataDir = "Your Document Directory";
```
Vervang *Your Document Directory* door het daadwerkelijke pad waar je de nieuwe shapefile wilt opslaan.

## Stap 3: Maak een VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Dit code‑segment **definieert een vectorlaag** en declareert drie attributen: een tekstveld (`name`), een geheel getal veld (`age`) en een datum‑tijd veld (`dob`). Het toevoegen van het datum‑attribuut is cruciaal voor temporele GIS‑analyses.

## Stap 4: Voeg features toe
### Geval 1: Stelt waarden individueel in
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
Hier maken we twee punten, stellen elk attribuut afzonderlijk in en voegen de features toe aan de laag.

### Geval 2: Stelt nieuwe waarden voor alle attributen in
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
In deze aanpak vullen we alle attribuutwaarden in één oproep met behulp van een object‑array—handig wanneer je veel attributen hebt.

## Waarom dit belangrijk is
Het programmatically maken van een shapefile stelt je in staat om datapijplijnen te automatiseren, testdatasets te genereren of GIS‑output direct in webservices te integreren. Door **het maken van een shapefile** met Aspose.GIS onder de knie te krijgen, krijg je volledige controle over feature‑geometrie, attribuutschema en bestandsformaat‑conformiteit.

## Veelvoorkomende valkuilen & tips
- **Pad‑scheidingstekens:** Gebruik `Path.Combine` voor cross‑platform compatibiliteit in plaats van string‑concatenatie.  
- **Attribuutvolgorde:** De volgorde van waarden in `SetValues` moet overeenkomen met de volgorde waarin je attributen hebt toegevoegd.  
- **Datumafhandeling:** Gebruik altijd `DateTimeKind.Utc` als je GIS‑gegevens over tijdzones heen worden gedeeld.

## Conclusie
Gefeliciteerd! Je hebt met succes een nieuwe shapefile gemaakt met Aspose.GIS voor .NET. Deze tutorial besprak de basis van het opzetten van je project, het definiëren van een vectorlaag en het toevoegen van features—incl. een datum‑attribuut. Naarmate je verder verkent, raadpleeg dan de [documentatie](https://reference.aspose.com/gis/net/) voor geavanceerde functies en mogelijkheden.

## Veelgestelde vragen
### Q: Kan ik Aspose.GIS gebruiken met andere programmeertalen?
Aspose.GIS ondersteunt voornamelijk .NET, maar er zijn ook versies beschikbaar voor Java.

### Q: Is er een gratis proefversie beschikbaar?
Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) benaderen.

### Q: Waar kan ik ondersteuning voor Aspose.GIS vinden?
Bezoek het [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) voor community‑ondersteuning en discussies.

### Q: Hoe kan ik een tijdelijke licentie verkrijgen?
Haal je tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/).

### Q: Waar kan ik Aspose.GIS voor .NET aanschaffen?
Je kunt de bibliotheek [hier](https://purchase.aspose.com/buy) kopen.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}