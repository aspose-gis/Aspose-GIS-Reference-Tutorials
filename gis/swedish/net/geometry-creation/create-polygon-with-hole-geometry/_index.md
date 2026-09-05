---
date: 2026-09-05
description: Lär dig hur du skapar en polygoninteriörring med ett hål med Aspose.GIS
  för .NET. Denna guide visar hur du lägger till ett hål i en polygon och arbetar
  med data.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Skapa polygon med hålgeometri
og_description: Lär dig hur du skapar en polygoninteriörring med ett hål med Aspose.GIS
  för .NET. Denna guide visar hur du lägger till ett hål i en polygon och arbetar
  med data.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Skapa en polygoninteriörring med ett hål med Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Skapa en polygoninteriörring med ett hål med Aspose.GIS
url: /sv/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa en polygoninteriörring med ett hål med hjälp av Aspose.GIS

## Introduktion
I den här handledningen kommer du att lära dig hur du **skapar en polygoninteriörring** som innehåller ett hål med hjälp av Aspose.GIS för .NET. Oavsett om du bygger en kartapplikation, utför rumslig analys eller förbereder data för GIS-tjänster, är det en grundläggande färdighet att bädda in ett hål i en polygon. Vi går igenom hela arbetsflödet — från att sätta upp utvecklingsmiljön till att generera ett giltigt polygonobjekt som kan sparas i vilket stödjt geospatialt format som helst.

## Snabba svar
- **Vad betyder “create polygon with hole”?** Det betyder att bygga en polygon som innehåller en eller flera interiöra ringar (hål) som exkluderas från området.  
- **Vilket bibliotek hanterar detta?** Aspose.GIS för .NET erbjuder fullt stöd för yttre och inre ringar.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hur lång tid tar det?** Vanligtvis under 10 minuter att implementera och testa.

## Hur man lägger till ett hål i en polygon med Aspose.GIS
Läs in din GIS-miljö, definiera en yttre ring och lägg sedan till en eller flera inre ringar. Aspose.GIS orienterar automatiskt ringarna och validerar geometrin, så du kan fokusera på de koordinater som representerar det tomrum du behöver.

## Vad är en polygoninteriörring?
En **polygoninteriörring** är en inre gräns som drar av area från polygonens yttre form.  
Du skapar den genom att definiera en sluten sekvens av punkter som Aspose.GIS behandlar som ett hål, vilket exkluderas vid beräkning av area eller rendering av formen.

## Varför skapa en polygoninteriörring med Aspose.GIS?
Aspose.GIS validerar och korrigerar ringorientering på under 5 ms för typiska 200‑punkts polygoner, vilket eliminerar behovet av egen valideringskod. Det stödjer också **30+ geospatiala filformat** (Shapefile, GeoJSON, GML, KML, etc.) och kan bearbeta polygoner med upp till 10 000 punkter utan att ladda hela filen i minnet, vilket ger både hastighet och skalbarhet.

## Verkliga scenarier för polygoner med hål
1. **Fastighetsdel med en intern sjö** – sjön modelleras som ett hål så den räknas inte med i fastighetens area.  
2. **Byggnadsytor med innergårdar** – innergården exkluderas från byggnadens fotavtryck.  
3. **Skyddade zoner inom ett större bevarandeområde** – du kan exkludera begränsade sektioner utan att skapa separata lager.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Aspose.GIS för .NET-biblioteket: Du kan ladda ner det från **Aspose.GIS för .NET nedladdningssida**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Utvecklingsmiljö: Se till att du har en utvecklingsmiljö konfigurerad med Visual Studio eller någon annan .NET-IDE installerad.

## Importera namnrymder
`Aspose.Gis`-namnrymden innehåller alla geometrityper du behöver, inklusive `Polygon`, `LinearRing` och hjälpfunktioner för validering.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nu går vi vidare till att skapa en polygon med ett hål‑geometri med hjälp av Aspose.GIS för .NET.

## Steg 1: skapa polygonobjekt
`Polygon` är Aspose.GIS:s geometrityp som representerar en plan polygon med valfria inre ringar. Vi börjar med att instansiera ett tomt `Polygon`‑objekt som senare kommer att innehålla både den yttre och de inre ringarna.

```csharp
Polygon polygon = new Polygon();
```

## Steg 2: definiera yttre ring
`LinearRing` är klassen som används för både yttre och inre gränser. Den yttre ringen definierar polygonens yttre gräns. Lägg till punkter i medurs ordning för att bilda en sluten form.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Steg 3: definiera inre ring (hål)
`LinearRing` representerar också inre ringar. Den inre ringen är **hålet** som kommer att exkluderas från polygonens area. Punkter läggs vanligtvis till i moturs ordning, men Aspose.GIS hanterar orienteringen automatiskt.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Steg 4: tilldela yttre ring och lägg till inre ring till polygon
`AddInteriorRing`‑metoden fäster en eller flera inre ringar till en `Polygon`. Anropa den efter att ha satt egenskapen `ExteriorRing`; du kan upprepa anropet för att lägga till flera hål.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tips och bästa praxis
- **Orientering är viktig för läsbarhet** – medan Aspose.GIS automatiskt korrigerar orientering, gör det geometrin lättare att inspektera i GIS‑visare om yttre ringar hålls medurs och inre ringar moturs.  
- **Stäng varje ring** – upprepa alltid den första koordinaten som sista punkten; detta garanterar en giltig sluten form.  
- **Validera efter skapande** – du kan anropa `polygon.IsValid` för att säkerställa att geometrin följer OGC‑standarder innan du sparar.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| Hålet visas inte i GIS‑visaren | Inre ringorientering omvänd | Se till att punkterna läggs till i motsatt riktning mot den yttre ringen (moturs). |
| Polygon ogiltig fel | Ringar inte stängda (första ≠ sista punkt) | Upprepa den första punkten som sista punkt i varje ring (som visas ovan). |
| Oväntad tom geometri | Glömt att tilldela `ExteriorRing` innan inre ringar läggs till | Sätt `polygon.ExteriorRing` först, anropa sedan `AddInteriorRing`. |

## Vanliga frågor
### 1. Vad är Aspose.GIS?
Aspose.GIS är ett .NET‑bibliotek som gör det möjligt för utvecklare att arbeta med geospatial data, så att de kan skapa, läsa och manipulera olika geospatiala filformat.

### 2. Kan jag använda Aspose.GIS för kommersiella projekt?
Ja, du kan använda Aspose.GIS för både personliga och kommersiella projekt genom att köpa en licens. Besök **Aspose.GIS‑köpsida**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) för mer information.

### 3. Finns det en gratis provversion av Aspose.GIS?
Ja, du kan få en gratis provversion av Aspose.GIS från **Aspose.GIS‑gratisprov‑nedladdningssida**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Var kan jag hitta support för Aspose.GIS?
Du kan hitta support för Aspose.GIS på [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33).

### 5. Hur kan jag få en tillfällig licens för Aspose.GIS?
Du kan få en tillfällig licens för Aspose.GIS från **Aspose.GIS‑tillfällig‑licens‑sida**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Senast uppdaterad:** 2026-09-05  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar polygongeometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Lär dig hur man skapar MultiPolygon‑geometri med Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Konvertera polygon till linje med Aspose.GIS för .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}