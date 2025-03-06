---
title: Vertaal geometrie van WKT met Aspose.GIS in .NET
linktitle: Vertaal geometrie van WKT
second_title: Aspose.GIS .NET-API
description: Leer hoe u geometrie uit bekende tekst kunt vertalen met Aspose.GIS voor .NET. Een stap-voor-stap handleiding voor naadloze integratie.
weight: 21
url: /nl/net/geometry-processing/translate-geometry-from-wkt/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vertaal geometrie van WKT met Aspose.GIS in .NET

## Invoering
In deze tutorial zullen we ons verdiepen in het proces van het vertalen van geometrie uit Well-Known Text (WKT) met behulp van Aspose.GIS voor .NET. Aspose.GIS is een krachtige .NET API waarmee ontwikkelaars moeiteloos met georuimtelijke gegevens kunnen werken. Of u nu een doorgewinterde ontwikkelaar bent of net begint met georuimtelijk programmeren, deze tutorial begeleidt u stap voor stap door het proces.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1.  Aspose.GIS voor .NET API: u kunt het downloaden van[hier](https://releases.aspose.com/gis/net/).
2. Basiskennis van de programmeertaal C#.

## Naamruimten importeren
Laten we eerst de benodigde naamruimten in ons C#-project importeren:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Stap 1: Maak een LineString van WKT
De eerste stap is het maken van een LineString-object op basis van de Well-Known Text-weergave:
```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```
## Stap 2: Tel de punten in LineString
Laten we vervolgens het aantal punten in de LineString tellen:
```csharp
Console.WriteLine(line.Count); // Uitgang: 3
```

## Conclusie
In deze tutorial hebben we onderzocht hoe je geometrie uit bekende tekst kunt vertalen met Aspose.GIS voor .NET. Door deze eenvoudige stappen te volgen, kunt u de verwerking van georuimtelijke gegevens naadloos integreren in uw .NET-toepassingen.
## Veelgestelde vragen
### Kan ik Aspose.GIS voor .NET gebruiken in mijn commerciële projecten?
Ja, dat kan. Aspose.GIS voor .NET heeft een licentie per ontwikkelaar, waardoor u het zonder enige beperking in commerciële projecten kunt gebruiken.
### Ondersteunt Aspose.GIS voor .NET naast WKT ook andere geometrische formaten?
Ja, Aspose.GIS voor .NET ondersteunt verschillende geometrische formaten, waaronder WKB, GeoJSON en Shapefile.
### Is er een gratis proefversie beschikbaar voor Aspose.GIS voor .NET?
Ja, u kunt een gratis proefperiode krijgen van[hier](https://releases.aspose.com/).
### Waar kan ik documentatie vinden voor Aspose.GIS voor .NET?
 U kunt de documentatie vinden[hier](https://reference.aspose.com/gis/net/).
### Hoe kan ik ondersteuning krijgen voor Aspose.GIS voor .NET?
 U kunt ondersteuning krijgen van het Aspose.GIS-forum[hier](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
