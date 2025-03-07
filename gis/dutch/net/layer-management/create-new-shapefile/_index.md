---
title: Maak een nieuw vormbestand
linktitle: Maak een nieuw vormbestand
second_title: Aspose.GIS .NET-API
description: Leer hoe u een nieuw shapefile maakt met Aspose.GIS voor .NET. Volg onze stapsgewijze handleiding en ontgrendel de kracht van manipulatie van ruimtelijke gegevens.
weight: 12
url: /nl/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een nieuw vormbestand

## Invoering
Als u zich verdiept in de ontwikkeling van geografische informatiesystemen (GIS) met .NET, is Aspose.GIS uw beste oplossing. Deze krachtige bibliotheek stelt ontwikkelaars in staat naadloos met ruimtelijke gegevens te werken, en in deze tutorial begeleiden we u door het proces van het maken van een nieuw shapefile met behulp van Aspose.GIS voor .NET.
## Vereisten
Voordat we met de zelfstudie beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van de programmeertaal C#.
- Visual Studio is op uw computer geïnstalleerd.
-  Aspose.GIS voor .NET-bibliotheek. Je kunt het downloaden[hier](https://releases.aspose.com/gis/net/).
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten om de functionaliteit van Aspose.GIS te benutten:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Stap 1: Stel uw project in
Begin met het maken van een nieuw C#-project in Visual Studio en voeg de Aspose.GIS-bibliotheek toe.
## Stap 2: Definieer de documentmap
```csharp
string dataDir = "Your Document Directory";
```
Vervang "Uw documentenmap" door het daadwerkelijke pad waar u uw nieuwe shapefile wilt opslaan.
## Stap 3: Maak een vectorlaag
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //voeg attributen toe voordat u features toevoegt
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Dit codesegment stelt de vectorlaag in en definieert attributen voor uw objecten.
## Stap 4: Functies toevoegen
### Geval 1: Waarden individueel instellen
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
### Geval 2: Stelt nieuwe waarden in voor alle attributen
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Conclusie
 Gefeliciteerd! U hebt met succes een nieuw shapefile gemaakt met Aspose.GIS voor .NET. Deze tutorial behandelde de basisprincipes van het opzetten van uw project, het definiëren van attributen en het toevoegen van features. Als u verder onderzoekt, raadpleegt u de[documentatie](https://reference.aspose.com/gis/net/) voor geavanceerde functies en functionaliteiten.
## Veel Gestelde Vragen
### Vraag: Kan ik Aspose.GIS gebruiken met andere programmeertalen?
Aspose.GIS ondersteunt voornamelijk .NET, maar er zijn ook versies beschikbaar voor Java.
### Vraag: Is er een gratis proefversie beschikbaar?
 Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/).
### Vraag: Waar kan ik ondersteuning vinden voor Aspose.GIS?
 Bezoek de[Aspose.GIS-forum](https://forum.aspose.com/c/gis/33) voor gemeenschapsondersteuning en discussies.
### Vraag: Hoe kan ik een tijdelijke licentie verkrijgen?
 Haal uw tijdelijke licentie[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Waar kan ik Aspose.GIS voor .NET kopen?
 Je kunt de bibliotheek kopen[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
