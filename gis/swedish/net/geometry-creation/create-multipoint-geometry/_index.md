---
date: 2026-09-05
description: Lär dig hur du skapar MultiPoint Geometry .NET med Aspose.GIS för .NET.
  Steg‑för‑steg‑guide för utvecklare.
keywords:
- create multipoint geometry .net
- Aspose.GIS .NET
- multi‑point geometry tutorial
- GIS development .NET
- spatial data processing
lastmod: 2026-09-05
linktitle: Skapa MultiPoint Geometry
og_description: Lär dig hur du skapar MultiPoint Geometry .NET med Aspose.GIS. Denna
  koncisa handledning visar de exakta stegen, förutsättningarna och bästa praxis för
  .NET‑utvecklare.
og_image_alt: Screenshot of Aspose.GIS code editor creating a MultiPoint geometry
  in a .NET project
og_title: Skapa MultiPoint Geometry .NET med Aspose.GIS – snabbguide
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create multipoint geometry .net using Aspose.GIS for .NET.
    Step‑by‑step guide for developers.
  headline: Create MultiPoint Geometry .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to create multipoint geometry .net using Aspose.GIS for .NET.
    Step‑by‑step guide for developers.
  name: Create MultiPoint Geometry .NET with Aspose.GIS
  steps:
  - name: instantiate a MultiPoint object
    text: The `MultiPoint` class is Aspose.GIS's container for a set of points. Creating
      an empty instance prepares a holder for the coordinates you will add. Here we
      create an empty `MultiPoint` container that will hold our individual points.
  - name: add individual points
    text: Each call to `Add` inserts a new `Point` into the collection. The constructor
      arguments are the X (longitude) and Y (latitude) coordinates. > **Pro tip:**
      You can add as many points as you need—just keep calling `multipoint.Add(new
      Point(x, y));`.
  - name: (optional) use the geometry
    text: 'The `Contains` method checks if a geometry fully encloses another, while
      `Intersects` determines if geometries share any points. Once you have populated
      the `MultiPoint`, you can: - Export it to a file format (Shapefile, GeoJSON,
      etc.). - Perform spatial queries such as `Contains`, `Intersects`, or '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.0 and later, as well as .NET Core
      and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Yes, you can obtain a free trial from the Aspose [website](https://purchase.aspose.com/temporary-license/).
    question: Can I try Aspose.GIS for .NET before purchasing a license?
  - answer: Absolutely! It supports polygons, lines, multipolygons, multilinestrings,
      and many more geometry types.
    question: Does Aspose.GIS for .NET support other spatial data formats besides
      points?
  - answer: You can visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      for community help and access the full documentation [Aspose.GIS .NET documentation](https://reference.aspose.com/gis/net/).
    question: Where can I find additional resources and support for Aspose.GIS for
      .NET?
  - answer: Yes, a temporary license is available for evaluation or short‑term use
      cases.
    question: Can I purchase a temporary license for short‑term projects?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create multipoint geometry
- Aspose.GIS
- .NET GIS
- spatial programming
- geometry handling
title: Skapa MultiPoint Geometry .NET med Aspose.GIS
url: /sv/net/geometry-creation/create-multipoint-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa MultiPoint-geometri .NET med Aspose.GIS

## Introduktion

I världen av Geographic Information Systems (GIS) **Aspose.GIS for .NET** utmärker sig som ett kraftfullt bibliotek för utvecklare som behöver **create multipoint geometry .net**‑baserade lösningar. Oavsett om du bygger en kartapplikation, bearbetar rumsliga data eller helt enkelt behöver manipulera punktkollektioner, kommer den här handledningen att guida dig genom hela processen i en klar, konversativ stil. I slutet kommer du att kunna lägga till multi‑point-geometrier i dina projekt med självförtroende.

## Snabba svar
- **Vad betyder “multi‑point geometry”?** En samling av enskilda punkter lagrade som ett enda geometriskt objekt.  
- **Varför använda Aspose.GIS för .NET?** Den erbjuder ett rikt, typ‑säkert API utan externa beroenden.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter för ett grundläggande exempel.  
- **Behöver jag en licens?** En giltig licens eller en gratis provperiod krävs för produktionsanvändning.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.0+, .NET Core 3.1+, .NET 5/6/7.

## Vad är MultiPoint-geometri i Aspose.GIS?

**MultiPoint**‑geometrin är ett enda objekt som samlar många enskilda punkter som delar samma rumsliga referens. Den låter dig behandla en hel uppsättning platser—butiksuttag, sensordata eller way‑points—som en enhet, vilket förenklar lagring och rumsliga frågor.

## Varför skapa multipoint-geometri .net med Aspose.GIS?

Att skapa en MultiPoint‑geometri låter dig hantera dussintals eller tusentals platser som ett enda objekt, vilket minskar minnesbelastning och snabbar upp fil‑I/O. Aspose.GIS kan exportera detta objekt till mer än **50+** GIS‑format (Shapefile, GeoJSON, KML, GML, etc.) utan extra konverterare, och den bearbetar filer upp till **500 MB** i minnes‑effektiva strömmar.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. **Grundläggande C#-kunskaper** – du kommer att skriva några rader C#-kod.  
2. **Visual Studio** (någon nyare version) installerad på din maskin.  
3. **Aspose.GIS for .NET** installerat – ladda ner det från [Aspose.GIS .NET download](https://releases.aspose.com/gis/net/).  
4. **En giltig licens eller gratis provperiod** – skaffa en från [Aspose license page](https://releases.aspose.com/).

Nu när grunderna är lagda, låt oss dyka ner i koden.

## Importera namnrymder

Först, importera de nödvändiga namnrymderna så att vi kan komma åt geometriklasserna.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

> *Vi inkluderar `Aspose.Gis.Geometries` eftersom den innehåller `MultiPoint`‑ och `Point`‑klasserna som vi kommer att använda.*

## Steg‑för‑steg‑guide för att skapa MultiPoint-geometri

### Steg 1: skapa ett MultiPoint-objekt

`MultiPoint`‑klassen är Aspose.GIS:s behållare för en uppsättning punkter. Att skapa en tom instans förbereder en hållare för de koordinater du kommer att lägga till.

```csharp
MultiPoint multipoint = new MultiPoint();
```

Här skapar vi en tom `MultiPoint`‑behållare som kommer att hålla våra enskilda punkter.

### Steg 2: lägg till enskilda punkter

Varje anrop till `Add` lägger till en ny `Point` i samlingen. Konstruktorargumenten är X (longitude) och Y (latitude) koordinaterna.

```csharp
multipoint.Add(new Point(1, 2));
multipoint.Add(new Point(3, 4));
```

> **Pro tip:** Du kan lägga till så många punkter du behöver—fortsätt bara att anropa `multipoint.Add(new Point(x, y));`.

### Steg 3: (valfritt) använd geometrin

`Contains`‑metoden kontrollerar om en geometri helt omsluter en annan, medan `Intersects` avgör om geometrier delar några punkter. När du har fyllt `MultiPoint` kan du:

- Exportera den till ett filformat (Shapefile, GeoJSON, etc.).  
- Utföra rumsliga frågor såsom `Contains`, `Intersects` eller avståndsberäkningar.  
- Skicka den till andra Aspose.GIS API:er för vidare bearbetning.

## Vanliga fallgropar & felsökning

`SpatialReference` definierar koordinatsystemet som en geometri använder. Tilldela den innan export för att säkerställa att koordinater tolkas korrekt.

| Problem | Orsak | Lösning |
|-------|-------|-----|
| **Punkter visas inte i exporterad fil** | Glömt att sätta en spatial reference (SRID) | Tilldela `multipoint.SpatialReference = SpatialReference.Wgs84;` före export. |
| **Exception: “Object reference not set”** | Använder en oinitierad `MultiPoint` | Se till att `new MultiPoint()` anropas innan punkter läggs till. |
| **Felaktig koordinatordning** | Blandar ihop X/Y med latitud/longitud | Kom ihåg: `new Point(x, y)` → X = longitud, Y = latitud. |

## Vanliga frågor

**Q: Är Aspose.GIS för .NET kompatibel med alla versioner av .NET Framework?**  
A: Ja, den fungerar med .NET Framework 4.0 och senare, samt .NET Core och .NET 5/6/7.

**Q: Kan jag prova Aspose.GIS för .NET innan jag köper en licens?**  
A: Ja, du kan skaffa en gratis provperiod från Aspose [website](https://purchase.aspose.com/temporary-license/).

**Q: Stöder Aspose.GIS för .NET andra rumsliga dataformat förutom punkter?**  
A: Absolut! Den stöder polygoner, linjer, multipolygoner, multilinestrings och många fler geometrityper.

**Q: Var kan jag hitta ytterligare resurser och support för Aspose.GIS för .NET?**  
A: Du kan besöka [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för gemenskapsstöd och få tillgång till den fullständiga dokumentationen [Aspose.GIS .NET documentation](https://reference.aspose.com/gis/net/).

**Q: Kan jag köpa en tillfällig licens för korttidsprojekt?**  
A: Ja, en tillfällig licens finns tillgänglig för utvärdering eller korttidsbruk.

## Slutsats

Du har nu lärt dig hur du **create multipoint geometry .net** med Aspose.GIS. Genom att följa dessa enkla steg—instansiera ett `MultiPoint`, lägga till `Point`‑objekt och eventuellt exportera eller bearbeta geometrin—kan du sömlöst integrera rumsliga punktkollektioner i vilken .NET‑applikation som helst.

---

**Senast uppdaterad:** 2026-09-05  
**Testat med:** Aspose.GIS for .NET (latest release)  
**Författare:** Aspose

## Relaterade handledningar

- [Lär dig hur du skapar LineString-geometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Skapa MultiLineString-geometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)
- [Lär dig hur du skapar MultiPolygon-geometri med Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}