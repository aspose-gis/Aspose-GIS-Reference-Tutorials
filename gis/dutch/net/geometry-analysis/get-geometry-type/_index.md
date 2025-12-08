---
date: 2025-12-08
description: Leer hoe je **geometrietype** van een punt kunt ophalen met Aspose.GIS
  voor .NET. Deze stapsgewijze gids behandelt GIS-voorkennis, het maken van een puntobject
  en het werken met ruimtelijke gegevens in C#.
language: nl
linktitle: Get Geometry Type
second_title: Aspose.GIS .NET API
title: Geometriektype ophalen met Aspose.GIS voor .NET
url: /net/geometry-analysis/get-geometry-type/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometrie Type Opvragen met Aspose.GIS voor .NET

## Introduction
Als je de **get geometry type** van een ruimtelijk kenmerk in een .NET‑applicatie moet opvragen, maakt Aspose.GIS het een fluitje van een cent. In deze tutorial lopen we het volledige proces door—van het opzetten van je GIS‑omgeving tot het maken van een puntobject en het extraheren van zijn geometrie type. Aan het einde begrijp je hoe je **work with spatial data** efficiënt kunt werken en ben je klaar om het voorbeeld uit te breiden naar lijnen, polygonen en meer.

## Quick Answers
- **Wat betekent “get geometry type”?** Het retourneert de enum‑waarde (bijv. Point, LineString) die de vorm van een geometrie‑object identificeert.  
- **Welke bibliotheek biedt deze functionaliteit?** Aspose.GIS for .NET.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET 5, .NET 6, .NET Core 3.1 en later.  
- **Hoe lang duurt de installatie?** Meestal minder dan 10 minuten voor een basis punt‑voorbeeld.

## What is “get geometry type” in Aspose.GIS?
`GeometryType` is een enumeratie die het type geometrie beschrijft waarmee je werkt—Point, LineString, Polygon, enz. Het benaderen van deze eigenschap stelt je in staat beslissingen te nemen in je code op basis van de vorm van de gegevens die je verwerkt.

## Why use Aspose.GIS for .NET?
- **Volledig uitgeruste GIS‑engine** – geen externe native afhankelijkheden.  
- **Rijke API** – maak, bewerk en analyseer ruimtelijke data direct vanuit C#.  
- **Cross‑platform** – werkt op Windows, Linux en macOS.  
- **Uitstekende documentatie** – snelle referentie en voorbeelden voor elke klasse.

## GIS Prerequisites for .NET (gis prerequisites .net)
Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **.NET SDK** – nieuwste versie (download vanaf de officiële .NET‑site).  
2. **IDE** – Visual Studio, Rider of VS Code met C#‑extensies.  
3. **Aspose.GIS for .NET** – verkrijg de bibliotheek via de officiële [download link](https://releases.aspose.com/gis/net/).  
4. **API Documentatie** – houd de [Aspose.GIS for .NET docs](https://reference.aspose.com/gis/net/) bij de hand voor referentie.

## Import Namespaces
In elk .NET‑project dat Aspose.GIS gebruikt, moet je de benodigde namespaces importeren. Dit geeft je toegang tot geometrie‑klassen, collecties en hulpmethoden.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to get geometry type from a point
Hieronder staat een **point example .net** die de volledige flow demonstreert—van het maken van het punt tot het ophalen van zijn geometrie type.

### Step 1: Create a Point Object
```csharp
Point point = new Point(40.7128, -74.006);
```
*Pro tip:* De `Point`‑constructor verwacht eerst **latitude** en daarna **longitude**, overeenkomstig de conventionele GIS‑volgorde.

### Step 2: Retrieve Geometry Type
```csharp
GeometryType geometryType = point.GeometryType;
```
Hier benaderen we de `GeometryType`‑eigenschap, die de enum‑waarde `GeometryType.Point` retourneert.

### Step 3: Display Geometry Type
```csharp
Console.WriteLine(geometryType); // Point
```
De console‑output bevestigt dat het object inderdaad een **point** is, en je hebt succesvol **get geometry type** ervan verkregen.

## Common Issues & Solutions
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **`GeometryType` returns `Unknown`** | De geometrie was niet correct geïnitialiseerd. | Zorg ervoor dat je de juiste constructor gebruikt (`new Point(lat, lon)`). |
| **Compilation errors** | Ontbrekende Aspose.GIS‑referentie. | Voeg het NuGet‑pakket `Aspose.GIS` toe aan je project. |
| **Runtime exception on Linux** | Incompatibele native bibliotheken. | Gebruik de .NET Core‑versie van Aspose.GIS, die volledig cross‑platform is. |

## Frequently Asked Questions

**Q: Is Aspose.GIS compatibel met alle versies van .NET?**  
A: Ja, Aspose.GIS ondersteunt .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 en later.

**Q: Kan ik Aspose.GIS uitproberen voordat ik aankoop?**  
A: Zeker. Een gratis proefversie is beschikbaar via de [download link](https://releases.aspose.com/).

**Q: Waar kan ik ondersteuning vinden voor Aspose.GIS‑gerelateerde vragen?**  
A: Bezoek het Aspose.GIS [support forum](https://forum.aspose.com/c/gis/33) voor community‑hulp en officiële ondersteuning.

**Q: Hoe verkrijg ik een tijdelijke licentie voor ontwikkeling?**  
A: Tijdelijke licenties worden verstrekt op de [temporary license](https://purchase.aspose.com/temporary-license/) pagina.

**Q: Waar kan ik een volledige licentie voor productie aanschaffen?**  
A: Je kunt een licentie direct kopen via de Aspose.GIS aankooppagina [hier](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

---