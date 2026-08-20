---
date: 2026-08-13
description: Lär dig hur du kontrollerar point inside polygon med Aspose.GIS för .NET,
  skapar polygon geometry och hämtar point on surface i C#. Steg‑för‑steg guide med
  fullständigt kodexempel.
keywords:
- check point inside polygon
- how to test polygon
- Aspose.GIS geometry
- .NET spatial analysis
lastmod: 2026-08-13
linktitle: Kontrollera point inside polygon och hämta point on surface
og_description: Lär dig hur du kontrollerar point inside polygon och hämtar point
  on surface med Aspise.GIS för .NET. Detaljerat C#-exempel och bästa praxis för spatial
  analysis.
og_image_alt: Screenshot of Aspose.GIS code checking point inside polygon in C#
og_title: Kontrollera point inside polygon – Aspose.GIS .NET guide
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to check point inside polygon using Aspose.GIS for .NET,
    create polygon geometry, and get point on surface in C#. Step‑by‑step guide with
    full code example.
  headline: Check point inside polygon and get point on surface
  type: TechArticle
- description: Learn how to check point inside polygon using Aspose.GIS for .NET,
    create polygon geometry, and get point on surface in C#. Step‑by‑step guide with
    full code example.
  name: Check point inside polygon and get point on surface
  steps:
  - name: create polygon geometry in C#
    text: First, we need to **create a polygon** geometry. We define the exterior
      ring of the polygon by specifying its vertices.
  - name: get point on surface
    text: The `GetPointOnSurface()` method returns a single interior point guaranteed
      to lie inside the polygon’s area. Next, we retrieve a point on the surface of
      the polygon using this method. This is the **get point on surface** step.
  - name: check point inside polygon
    text: The `SpatiallyContains()` method evaluates whether a geometry completely
      contains another geometry, returning true or false. We can verify whether the
      retrieved point lies inside the polygon using this method. This demonstrates
      **retrieving point on polygon** and then checking it.
  type: HowTo
- questions:
  - answer: It verifies whether a given coordinate lies within the boundaries of a
      polygon geometry.
    question: What does “check point inside polygon” mean?
  - answer: '`GetPointOnSurface()` returns a point guaranteed to be inside the polygon.'
    question: Which method returns a point on a polygon’s interior?
  - answer: A free trial works for evaluation; a full license is required for production.
    question: Do I need a license to run the example?
  - answer: .NET Framework, .NET Core, and .NET Standard are all compatible.
    question: Which .NET versions are supported?
  - answer: About 5‑10 minutes to copy, compile, and run.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- check point inside polygon
- Aspose.GIS
- .NET geometry
- C# spatial operations
title: Kontrollera point inside polygon och hämta point on surface
url: /sv/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kontrollera punkt i polygon och hämta punkt på ytan

## Introduktion
I den här handledningen kommer du att lära dig **hur man kontrollerar om en punkt ligger i en polygon** med Aspose.GIS för .NET och även se hur man **hämtar en punkt på ytan** av en geometri. Vi går igenom hur man skapar en polygongeometri i C#, hämtar en punkt som ligger på polygonens yta och verifierar att punkten verkligen befinner sig inom polygonen. I slutet har du ett färdigt kodexempel som du kan använda i vilken .NET-geospatial applikation som helst.

## Snabba svar
- **Vad betyder “check point inside polygon”?** Det verifierar om en given koordinat ligger inom gränserna för en polygongeometri.  
- **Vilken metod returnerar en punkt i en polygons inre?** `GetPointOnSurface()` returnerar en punkt som garanterat ligger inom polygonen.  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework, .NET Core och .NET Standard är alla kompatibla.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter för att kopiera, kompilera och köra.

## Vad är “check point inside polygon”?
Att kontrollera en punkt i en polygon avgör om en specifik koordinat ligger inom det slutna område som definieras av polygonens hörn. Operationen returnerar true när punkten är helt omsluten och false när den ligger utanför eller på gränsen. Detta grundläggande rumsliga test driver geofencing, platsbaserad analys och kartdrivna valideringsscenarier.

## Varför använda Aspose.GIS för denna uppgift?
Aspose.GIS erbjuder ett helt hanterat .NET‑API som bearbetar polygonoperationer upp till 200 MB i minnes‑effektivt läge, stöder över 50 koordinatreferenssystem och körs på .NET Framework, .NET Core och .NET Standard utan inhemska beroenden.  
`GetPointOnSurface()` returnerar en punkt som garanterat ligger i geometriens inre.  
`SpatiallyContains()` avgör om en geometri helt innehåller en annan.  
Bibliotekets kedjekopplade metoder — såsom `SpatiallyContains()` och `GetPointOnSurface()` — ger deterministiska resultat och eliminerar behovet av externa GIS‑motorer.

## Förutsättningar
Innan vi börjar, se till att du har följande:

### Miljöinställning
1. Installera Aspose.GIS för .NET: Ladda ner och installera Aspose.GIS för .NET‑biblioteket från **Aspose.GIS för .NET nedladdningssida**([here](https://releases.aspose.com/gis/net/)).  
2. Ställ in din utvecklingsmiljö: Använd Visual Studio, Rider eller någon .NET‑kompatibel IDE du föredrar.  
3. Grundläggande kunskap i C#: Du bör vara bekväm med klasser, metoder och enkla konsol‑app‑projekt.  
4. Tillgång till dokumentation: Ha **Aspose.GIS-dokumentationen**([documentation](https://reference.aspose.com/gis/net/)) till hands för referens under hela handledningen.

## Importera namnrymder
Innan vi går in på implementeringen, låt oss börja med att importera de nödvändiga namnrymderna:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg‑för‑steg‑guide

### Steg 1: skapa polygongeometri i C#
Först måste vi **skapa en polygon**‑geometri. Vi definierar polygonens yttre ring genom att ange dess hörn.

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

### Steg 2: hämta punkt på ytan
`GetPointOnSurface()`‑metoden returnerar en enda inre punkt som garanterat ligger inom polygonens område. Därefter hämtar vi en punkt på polygonens yta med denna metod. Detta är steget **hämta punkt på ytan**.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

### Steg 3: kontrollera punkt i polygon
`SpatiallyContains()`‑metoden utvärderar om en geometri helt innehåller en annan geometri och returnerar true eller false. Vi kan verifiera om den hämtade punkten ligger i polygonen med denna metod. Detta demonstrerar **hämtning av punkt på polygon** och sedan kontrollen.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Hur man testar polygoninnehåll i C#
Du testar polygoninnehåll genom att skapa polygongeometrin, anropa `GetPointOnSurface()` för att få en inre punkt och sedan använda `SpatiallyContains()` för att verifiera att punkten är innanför. Detta tvåstegs‑mönster fungerar för alla giltiga polygoner och skalar till stora datamängder när det kombineras med lazy loading.

## Vanliga problem och lösningar
- **Tom polygon** – Se till att den yttre ringen har minst tre distinkta hörn; annars kan `GetPointOnSurface()` returnera en odefinierad punkt.  
- **Medurs vs. moturs** – Ringens orientering påverkar inte innehållskontrollen, men att hålla en konsekvent varvningsordning underlättar andra rumsliga operationer.  
- **Koordinatsystem** – Exemplet använder ett enkelt kartesiskt plan; när du arbetar med verkliga koordinater, se till att CRS (koordinatreferenssystem) är korrekt definierat.

## Vanliga frågor

### FAQ

#### Är Aspose.GIS kompatibel med andra .NET-ramverk?
Ja, Aspose.GIS stöder olika .NET-ramverk, inklusive .NET Framework, .NET Core och .NET Standard.

#### Kan jag prova Aspose.GIS innan jag köper?
Ja, du kan ladda ner en gratis provversion av Aspose.GIS från **Aspose.GIS gratis provnedladdningssida**([here](https://releases.aspose.com/)).

#### Hur kan jag få support för Aspose.GIS?
Du kan besöka **Aspose.GIS-forum**([here](https://forum.aspose.com/c/gis/33)) för att söka hjälp och interagera med andra användare och utvecklare.

#### Erbjuder Aspose.GIS tillfälliga licenser?
Ja, du kan skaffa tillfälliga licenser för Aspose.GIS från **tillfällig licenssida**([here](https://purchase.aspose.com/temporary-license/)).

#### Var kan jag köpa Aspose.GIS?
Du kan köpa Aspose.GIS från **Aspose.GIS köpsida**([here](https://purchase.aspose.com/buy)).

### Ytterligare Q&A

**Q:** Vad är det bästa sättet att hantera stora polygondatamängder?  
**A:** Ladda geometrier lazily och återanvänd en enda `GeometryFactory`‑instans för att minska minnesbelastningen.

**Q:** Kan jag hämta flera punkter på ytan?  
**A:** `GetPointOnSurface()` returnerar en enda inre punkt. För att generera flera inre punkter kan du använda en slumpmässig punktgenerator inom polygonens omgivningsruta och testa varje med `SpatiallyContains()`.

**Q:** Är det möjligt att exportera polygonen till en shapefil efter skapandet?  
**A:** Ja, Aspose.GIS tillhandahåller `FeatureSet`‑ och `ShapefileWriter`‑klasser för att skriva geometrier till Shapefile‑format.

## Slutsats
I den här handledningen har vi lärt oss hur man **kontrollerar om en punkt ligger i en polygon** med Aspose.GIS för .NET, får en **punkt på ytan** och verifierar dess innehåll. Med Aspose.GIS blir hantering av geospatial data effektiv och enkel, vilket ger dig möjlighet att bygga robusta geospatiala applikationer som skalar från enkla kartor till företagsklassade rumsliga analyser.

---

**Last Updated:** 2026-08-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man skapar polygongeometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [punkt i polygon c# – Kontrollera om geometri innehåller en annan](/gis/net/geometry-analysis/check-geometry-contains-another/)
- [Hur man beräknar geometrins centroid med Aspose.GIS för .NET](/gis/net/geometry-analysis/get-geometry-centroid/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}