---
date: 2026-02-13
description: Lär dig hur du kontrollerar om en punkt ligger inom en polygon med Aspose.GIS
  för .NET, skapar polygongeometri och får en punkt på ytan i C#. Steg‑för‑steg‑guide
  med fullständigt kodexempel.
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: Kontrollera om punkt ligger i polygon och hämta punkt på ytan
url: /sv/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

 "**Last Updated:** 2026-02-13" -> "**Senast uppdaterad:** 2026-02-13"

"**Tested With:** Aspose.GIS 24.11 for .NET" -> "**Testad med:** Aspose.GIS 24.11 för .NET"

"**Author:** Aspose" -> "**Författare:** Aspose"

Then closing shortcodes.

Then backtop button shortcode unchanged.

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kontrollera punkt inom polygon och hämta punkt på ytan

## Introduktion
I den här handledningen kommer du att lära dig **hur man kontrollerar punkt inom polygon** med Aspose.GIS för .NET och även se hur man **hämtar punkt på ytan** för en geometri. Vi går igenom hur man skapar en polygongeometri i C#, hämtar en punkt som ligger på polygonens yta och verifierar att punkten verkligen befinner sig inom polygonen. I slutet har du ett färdigt kodexempel som du kan klistra in i vilken .NET-geospatial applikation som helst.

## Snabba svar
- **Vad betyder “check point inside polygon”?** Det verifierar om en given koordinat ligger inom gränserna för en polygongeometri.  
- **Vilken metod returnerar en punkt i en polygons inre?** `GetPointOnSurface()` returnerar en punkt som garanterat ligger inom polygonen.  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework, .NET Core och .NET Standard är alla kompatibla.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter att kopiera, kompilera och köra.

## Vad är “check point inside polygon”?
Att kontrollera en punkt inom en polygon är en grundläggande rumslig operation. Den svarar på frågan “Är denna koordinat placerad inom området som definieras av polygonen?” Detta är avgörande för uppgifter som geofence, kartanalys och rumslig validering.

## Varför använda Aspose.GIS för denna uppgift?
Aspose.GIS erbjuder ett högpresterande, helt hanterat API som hanterar komplexa geometriska operationer utan externa beroenden. Det stödjer ett brett spektrum av koordinatreferenssystem, fungerar på alla stora .NET‑runtime‑miljöer och erbjuder tydliga, kedjbara metoder som `SpatiallyContains()` och `GetPointOnSurface()`.

## Förutsättningar
Innan vi börjar, se till att du har följande:

### Miljöinställning
1. Installera Aspose.GIS för .NET: Ladda ner och installera Aspose.GIS för .NET‑biblioteket från [here](https://releases.aspose.com/gis/net/).  
2. Ställ in din utvecklingsmiljö: Säkerställ att du har en fungerande utvecklingsmiljö för .NET‑programmering. Om inte, kan du sätta upp Visual Studio eller någon annan .NET‑utvecklingsmiljö du föredrar.  
3. Grundläggande kunskap i C#: Bekanta dig med grunderna i C#‑programmeringsspråket om du ännu inte är bekant med det.  
4. Tillgång till dokumentation: Ha [dokumentation](https://reference.aspose.com/gis/net/) till hands för referens under hela handledningen.

## Importera namnrymder
Innan vi dyker ner i implementeringen, låt oss börja med att importera de nödvändiga namnrymderna:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg‑för‑steg guide

### Steg 1: Skapa polygongeometri i C#
Först måste vi **skapa en polygon** geometri. Vi definierar polygonens ytterring genom att ange dess hörn.

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

### Steg 2: Hämta punkt på ytan
Därefter hämtar vi en punkt på polygonens yta med metoden `GetPointOnSurface()`. Detta är steget **get point on surface**.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

### Steg 3: Kontrollera punkt inom polygon
Vi kan verifiera om den hämtade punkten ligger inom polygonen med metoden `SpatiallyContains()`. Detta demonstrerar **retrieving point on polygon** och sedan kontrollerar den.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Vanliga problem och lösningar
- **Tom polygon** – Säkerställ att ytterringen har minst tre distinkta hörn; annars kan `GetPointOnSurface()` returnera en odefinierad punkt.  
- **Medurs vs. moturs** – Ringens orientering påverkar inte innehållskontrollen, men att hålla en konsekvent varvningsordning underlättar andra rumsliga operationer.  
- **Koordinatsystem** – Exemplet använder ett enkelt kartesiskt plan; när du arbetar med verkliga koordinater, se till att CRS (coordinate reference system) är korrekt definierat.

## Vanliga frågor

### FAQ
#### Är Aspose.GIS kompatibel med andra .NET‑ramverk?
Ja, Aspose.GIS stödjer olika .NET‑ramverk, inklusive .NET Framework, .NET Core och .NET Standard.

#### Kan jag prova Aspose.GIS innan jag köper?
Ja, du kan ladda ner en gratis provversion av Aspose.GIS från [här](https://releases.aspose.com/).

#### Hur kan jag få support för Aspose.GIS?
Du kan besöka Aspose.GIS‑forumet [här](https://forum.aspose.com/c/gis/33) för att söka hjälp och interagera med andra användare och utvecklare.

#### Erbjuder Aspose.GIS temporära licenser?
Ja, du kan skaffa temporära licenser för Aspose.GIS från [här](https://purchase.aspose.com/temporary-license/).

#### Var kan jag köpa Aspose.GIS?
Du kan köpa Aspose.GIS från köpsidan [här](https://purchase.aspose.com/buy).

### Ytterligare Q&A

**Q:** Vad är det bästa sättet att hantera stora polygon‑dataset?  
**A:** Ladda geometrier lazily och återanvänd en enda `GeometryFactory`‑instans för att minska minnesbelastningen.

**Q:** Kan jag hämta flera punkter på ytan?  
**A:** `GetPointOnSurface()` returnerar en enda inre punkt. För att generera flera inre punkter kan du använda en slumpmässig punktgenerator inom polygonens omgivningsruta och testa varje med `SpatiallyContains()`.

**Q:** Är det möjligt att exportera polygonen till en shapefile efter skapandet?  
**A:** Ja, Aspose.GIS tillhandahåller `FeatureSet`‑ och `ShapefileWriter`‑klasser för att skriva geometrier till Shapefile‑format.

## Slutsats
I den här handledningen har vi lärt oss hur man **check point inside polygon** med Aspose.GIS för .NET, får en **point on surface** och verifierar dess innehåll. Med Aspose.GIS blir hantering av geospatial data effektiv och enkel, vilket ger utvecklare möjlighet att bygga robusta geospatiala applikationer.

---

**Senast uppdaterad:** 2026-02-13  
**Testad med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}