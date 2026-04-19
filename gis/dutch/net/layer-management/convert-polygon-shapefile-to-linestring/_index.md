---
date: 2026-01-10
description: Leer hoe je een shapefile in C# leest en een polygon‑shapefile converteert
  naar een linestring met Aspose.GIS voor .NET. Versterk je GIS‑ontwikkeling met duidelijke
  stapsgewijze begeleiding.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Shapefile lezen C# – Polygon Shapefile omzetten naar Linestring
url: /nl/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile lezen C# – Polygon Shapefile converteren naar Linestring

## Inleiding
Als je werkt met geografische informatiesystemen (GIS) in .NET, is **read shapefile c#** een veelvoorkomende eerste stap voordat je de gegevens kunt manipuleren. Aspose.GIS maakt dit proces eenvoudig, waardoor je een Polygon Shapefile kunt converteren naar een Linestring met slechts een paar regels code. Deze mogelijkheid is vooral handig wanneer je lineaire kenmerken uit polygonale datasets moet extraheren voor taken zoals routeplanning, netwerk‑analyse of datavisualisatie.

## Snelle antwoorden
- **Welke bibliotheek helpt je bij het lezen van shapefile c#?** Aspose.GIS for .NET  
- **Kun je een polygon converteren naar een lijn?** Ja – use `LineString` with the polygon’s exterior ring.  
- **Heb ik een licentie nodig voor productie?** A commercial license is required for production use.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is er een proefversie beschikbaar?** Absolutely – download a free trial from the Aspose site.

## Wat is “read shapefile c#”?
Een shapefile lezen in C# betekent het laden van het `.shp`‑bestand in het geheugen zodat je de geometrieën kunt opvragen, wijzigen of transformeren. Aspose.GIS biedt een eenvoudige API die de low‑level details abstraheert en je in staat stelt je te concentreren op de GIS‑logica.

## Waarom polygon converteren naar een lijn met Aspose.GIS?
- **Preserve topology** – the conversion keeps the exact outer boundary of each polygon.  
- **Performance** – the library is optimized for large datasets, making batch conversions fast.  
- **Flexibility** – you can later write the linestrings to another shapefile, GeoJSON, or any supported format.

## Vereisten
Voordat we aan de tutorial beginnen, zorg ervoor dat je het volgende hebt:

- **Aspose.GIS Library** – Download en installeer de Aspose.GIS‑bibliotheek vanaf de [website](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Zorg voor een Polygon Shapefile die klaar is voor conversie. Als je er geen hebt, kun je voorbeeldgegevens vinden of zelf maken.  
- **Development Environment** – Stel je .NET‑ontwikkelomgeving in met de benodigde tools (Visual Studio, .NET SDK, enz.).

## Namespaces importeren
In je C#‑code moet je de Aspose.GIS‑namespaces importeren om toegang te krijgen tot de benodigde klassen en methoden. Voeg de volgende namespaces toe aan het begin van je codebestand:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hoe shapefile converteren van polygon naar lijn?
Hieronder vind je een stapsgewijze handleiding die laat zien **hoe shapefile** gegevens van een polygon naar een lijn te converteren met Aspose.GIS.

### Stap 1: Stel de documentdirectory in
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Vervang `"Your Document Directory"` door het daadwerkelijke pad waar je shapefile zich bevindt.

### Stap 2: Open de bron‑Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Deze regel **opent de bron‑Polygon Shapefile** zodat je de features kunt lezen.

### Stap 3: Maak de bestemmings‑Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Hier **maken we een nieuwe Linestring Shapefile** die de geconverteerde geometrieën zal opslaan.

### Stap 4: Doorloop de bron‑features
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
De lus doorloopt elk polygon‑feature in het originele bestand.

### Stap 5: Converteer polygon naar Linestring en schrijf naar bestemming
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
In dit blok **converteren we polygon naar lijn** (`LineString`) en voegen we de nieuwe feature toe aan de bestemmings‑shapefile.

## Veelvoorkomende problemen en tips
- **Coordinate System Mismatch** – Zorg ervoor dat zowel bron‑ als bestemmingslagen dezelfde ruimtelijke referentie gebruiken; anders kunnen de lijnen verschoven verschijnen.  
- **Large Files** – Bij het verwerken van zeer grote shapefiles, overweeg om features te streamen in plaats van ze allemaal in één keer in het geheugen te laden.  
- **Null Geometries** – Bescherm tegen features met lege geometrieën om runtime‑exceptions te voorkomen.

## Veelgestelde vragen

**V: Is Aspose.GIS compatibel met alle versies van .NET?**  
A: Ja, Aspose.GIS ondersteunt verschillende .NET‑versies, waardoor het compatibel is met je ontwikkelomgeving.

**V: Kan ik Aspose.GIS gebruiken voor commerciële projecten?**  
A: Ja, dat kan. Om Aspose.GIS in commerciële projecten te gebruiken, overweeg een licentie aan te schaffen [hier](https://purchase.aspose.com/buy).

**V: Zijn er voorbeelden of documentatie beschikbaar?**  
A: Ja, je kunt uitgebreide documentatie en voorbeelden vinden op de [documentatiepagina](https://reference.aspose.com/gis/net/).

**V: Is er een proefversie beschikbaar?**  
A: Ja, je kunt Aspose.GIS verkennen met een gratis proefversie via [deze link](https://releases.aspose.com/).

**V: Waar kan ik hulp of ondersteuning vinden?**  
A: Bezoek het [Aspose.GIS‑forum](https://forum.aspose.com/c/gis/33) voor hulp of ondersteuningsgerelateerde vragen.

---

**Laatst bijgewerkt:** 2026-01-10  
**Getest met:** Aspose.GIS for .NET (latest release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}