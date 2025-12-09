---
date: 2025-12-09
description: Leer hoe u een buffer maakt met Aspose.GIS voor .NET, inclusief het installeren
  van Aspose, het importeren van namespaces en het controleren van ruimtelijke containment
  voor effectieve ruimtelijke analyse.
linktitle: How to Create Buffer Using Aspose.GIS for .NET
second_title: Aspose.GIS .NET API
title: Hoe een buffer maken met Aspose.GIS voor .NET
url: /nl/net/geometry-analysis/create-geometry-buffer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een buffer te maken met Aspose.GIS voor .NET

## Introduction
Als je werkt met geografische gegevens in een .NET‑omgeving, is het weten **hoe je een buffer** rond geometrieën maakt essentieel voor taken zoals nabijheidsanalyse, zone‑indeling en generalisatie van objecten. In deze tutorial lopen we het volledige proces door met Aspose.GIS voor .NET—beginnend bij installatie, het importeren van de benodigde namespaces, het genereren van buffers voor zowel lijn‑ als polygoongeometrieën, en uiteindelijk het controleren van ruimtelijke containment. Aan het einde heb je een solide, praktische kennis van hoe je ruimtelijke analyse met buffers uitvoert in je eigen applicaties.

## Quick Answers
- **Wat is een geometrische buffer?** Een polygoon die alle punten omsluit die zich binnen een opgegeven afstand van een brongeometrie bevinden.  
- **Waarom Aspose.GIS gebruiken voor buffering?** Het biedt een eenvoudige, hoge‑prestaties API die werkt op .NET Framework, .NET Core en .NET 5/6+.  
- **Hoe installeer je Aspose.GIS?** Download de bibliotheek van de officiële site en voeg deze toe als referentie in Visual Studio.  
- **Hoe controleer je containment?** Gebruik de `SpatiallyContains`‑methode om te testen of een punt binnen de gegenereerde buffer ligt.  
- **Kan ik ruimtelijke analyse uitvoeren naast buffering?** Ja—operaties zoals intersectie, unie en afstandsberekeningen worden ook ondersteund.

## What is a Geometry Buffer?
Een geometrische buffer creëert een zone rond een object (punt, lijn of polygoon) op een door de gebruiker gedefinieerde afstand. Deze zone is nuttig voor het identificeren van nabijgelegen objecten, het creëren van impactgebieden, of het vereenvoudigen van complexe vormen.

## Why Use Aspose.GIS for Buffer Creation?
- **Cross‑platform ondersteuning:** Werkt op Windows, Linux en macOS.  
- **Geen externe afhankelijkheden:** Geen noodzaak voor native GIS‑bibliotheken.  
- **Rijke API:** Bevat buffering, ruimtelijke predicaten en transformaties van coördinatensystemen.  
- **Prestaties‑geoptimaliseerd:** Verwerkt grote datasets efficiënt.

## Prerequisites
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- **Visual Studio 2019 of later** (of een andere compatibele .NET‑IDE).  
- **.NET 6 SDK** (of .NET Core 3.1+).  
- **Aspose.GIS for .NET bibliotheek** – zie de installatie‑stappen hieronder.  

### How to Install Aspose.GIS for .NET
1. Download de Aspose.GIS for .NET bibliotheek van de [download link](https://releases.aspose.com/gis/net/).  
2. In Visual Studio, klik met de rechtermuisknop op je project → **Add** → **Reference…** → blader naar de gedownloade DLL en voeg deze toe.  
3. Verkrijg een licentie van [Aspose](https://purchase.aspose.com/buy) of gebruik een [temporary license](https://purchase.aspose.com/temporary-license/) voor evaluatie.

## Importing Namespaces
Om de API te gaan gebruiken, importeer je de benodigde namespaces in je C#‑bestand.

### How to Import Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nu gaan we het buffer‑creatieproces stap voor stap ontleden.

## Step‑by‑Step Guide

### Step 1: Create a Geometry Buffer
**Stap 1: Een geometrische buffer maken**  
Eerst definiëren we een eenvoudige `LineString` geometrie die als bron voor onze buffer zal dienen.

```csharp
// Define a LineString geometry
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```

In dit fragment maken we een `LineString` aan en voegen twee punten toe, waardoor een diagonale lijn ontstaat van (0,0) naar (3,3).

### Step 2: Generate Buffer for LineString
**Stap 2: Buffer genereren voor LineString**  
Vervolgens genereren we een buffer rond de lijn met een **positieve afstand** van 1 eenheid.

```csharp
// Generate a buffer for the LineString with a positive distance
var lineBuffer = line.GetBuffer(distance: 1);
```

De `GetBuffer`‑methode retourneert een polygoon die elk punt omvat dat zich binnen 1 eenheid van de oorspronkelijke lijn bevindt.

### Step 3: Check Spatial Containment
**Stap 3: Ruimtelijke containment controleren**  
Nu demonstreren we **hoe je containment controleert** door te testen of specifieke punten binnen de buffer vallen.

```csharp
// Check spatial containment of points within the buffer
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     // True
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); // True
```

De `SpatiallyContains`‑predicate retourneert `true` als het punt binnen de buffer‑polygoon ligt.

### Step 4: Define a Polygon Geometry
**Stap 4: Een polygoongeometrie definiëren**  
We maken ook een `Polygon` geometrie aan om buffering met een **negatieve afstand** te illustreren, wat de vorm verkleint.

```csharp
// Define a Polygon geometry
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```

De polygoon stelt een vierkant voor met hoekpunten op (0,0), (0,3), (3,3) en (3,0).

### Step 5: Generate Buffer for Polygon
**Stap 5: Buffer genereren voor polygoon**  
Door een negatieve afstand van –1 eenheid toe te passen, wordt de polygoon naar binnen toe verkleind.

```csharp
// Generate a buffer for the Polygon with a negative distance
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```

De resulterende `polygonBuffer` is een kleiner vierkant, nuttig voor het creëren van binnenzones.

### Step 6: Access Buffer Exterior Ring Points
**Stap 6: Toegang tot de punten van de buitenring van de buffer**  
Tenslotte halen we de coördinaten van de buitenring van de buffer op en geven deze weer.

```csharp
// Access points of the exterior ring of the buffer Polygon
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```

Deze lus print elke hoekpunt van de verkleinde polygoon, waarmee de buffergeometrie wordt bevestigd.

## Common Issues and Solutions
| Probleem | Oplossing |
|----------|-----------|
| **Buffer returns `null`** | Zorg ervoor dat de afstandswaarde geschikt is voor het coördinatensysteem van de geometrie. |
| **`SpatiallyContains` always returns `false`** | Controleer of beide geometrieën dezelfde ruimtelijke referentie (CRS) delen. |
| **Performance slowdown with large datasets** | Verwerk geometrieën in batches en hergebruik dezelfde `GeometryFactory`‑instantie. |

## Frequently Asked Questions

**Q: Is Aspose.GIS for .NET compatible with other .NET frameworks?**  
A: Yes, it works with .NET Framework, .NET Core, .NET 5, and .NET 6.

**Q: Can I perform spatial analysis using Aspose.GIS for .NET?**  
A: Absolutely. The library supports buffering, intersecting, distance calculations, and more.

**Q: Are there limits on dataset size?**  
A: The API is optimized for large datasets, but memory consumption depends on the size of the geometries you load.

**Q: Does Aspose.GIS support different spatial reference systems?**  
A: Yes, it handles a wide range of coordinate systems and allows on‑the‑fly transformations.

**Q: Where can I get technical support?**  
A: Visit the Aspose.GIS community forum at [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33) for assistance.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}