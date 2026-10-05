---
date: 2026-10-05
description: Lär dig hur du läser geojson från en ström med Aspose.GIS för .NET. Denna
  steg‑för‑steg‑guide visar hur du laddar geojson‑ström, parsar den och extraherar
  egenskaper i C#.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: Läs GeoJSON från Ström
og_description: Lär dig hur du läser geojson från en ström med Aspose.GIS för .NET,
  inklusive parsning, öppning av ett geojson‑lager och extrahering av egenskaper i
  C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: Hur man läser geojson från en ström med Aspose.GIS för .NET
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: Hur man läser geojson från en ström med Aspose.GIS för .NET
url: /sv/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser geojson från en ström med Aspose.GIS för .NET

## Introduktion
Om du undrar **hur man läser geojson** i en .NET‑applikation, har du kommit till rätt ställe. I den här handledningen går vi igenom ett komplett **C# GeoJSON‑exempel** som visar hur man konverterar en GeoJSON‑sträng, **läser in geojson‑ström** i ett minnesström, öppnar ett GeoJSON‑lager och extraherar GeoJSON‑egenskaper med Aspose.GIS. I slutet har du ett återanvändbart mönster som du kan lägga in i vilket projekt som helst som behöver arbeta med geografiska data.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.GIS för .NET – det hanterar 30+ GIS‑format direkt ur lådan.  
- **Kan jag läsa GeoJSON direkt från en ström?** Ja – anropa `VectorLayer.Open` med `AbstractPath.FromStream`.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en full licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Är det enkelt att extrahera egenskaper?** Absolut – använd `GetValue<T>(columnName)` på ett objekt.

**VectorLayer.Open** öppnar ett GIS‑lager från en datakälla såsom en fil eller ström. **AbstractPath.FromStream** skapar ett abstrakt sökvägsobjekt som representerar den angivna strömmen för GIS‑drivrutinen. **GetValue<T>(columnName)** läser värdet för det angivna attributet från ett objekt och returnerar det som typ T.

## Vad är hur man läser geojson?
Att läsa geojson är processen att konvertera en GeoJSON‑formaterad sträng eller ström till geografiska objekt i minnet. Detta format kodar punkter, linjer och polygoner med JSON, vilket gör det enkelt att utbyta rumsliga data mellan webbtjänster, databaser och klientapplikationer. När den har parsats kan du fråga, redigera eller rendera objekten med vilket GIS‑medvetet .NET‑bibliotek som helst, såsom Aspose.GIS.

## Varför använda Aspose.GIS för att öppna ett geojson‑lager?
Aspose.GIS låter dig öppna ett GeoJSON‑lager direkt från en ström, vilket eliminerar behovet av temporära filer och minskar I/O‑belastning. Biblioteket stöder 30+ GIS‑format och kan bearbeta filer upp till 2 GB utan att ladda hela dokumentet i minnet, vilket är idealiskt för stora datamängder. Det normaliserar också koordinatreferenssystem automatiskt, så du kan fokusera på affärslogik istället för låg‑nivå‑parsning.

## När skulle du läsa in en geojson‑ström?
Du skulle läsa in en GeoJSON‑ström när du får rumsliga data från ett API, behöver hantera användaruppladdade filer utan att spara dem på disk, eller generera GeoJSON i farten från en databasfråga. Strömning undviker onödiga skrivningar till disk, förbättrar prestanda i scenarier med hög genomströmning och håller din applikation stateless, vilket är särskilt värdefullt i molnbaserade mikrotjänster.

## Förutsättningar
Innan vi dyker ner, se till att du har:

1. **Grundläggande kunskap i C#** – du bör vara bekväm med .NET‑syntax och Visual Studio‑IDE:n.  
2. **Aspose.GIS installerat** – ladda ner biblioteket från [Aspose.GIS .NET download page](https://releases.aspose.com/gis/net/).  
3. **En utvecklingsmiljö** – Visual Studio, Visual Studio Code eller JetBrains Rider fungerar bra.  

## Importera namnrymder
`Aspose.GIS`‑namnrymden tillhandahåller de centrala GIS‑klasserna. `System.IO` ger dig `MemoryStream`, och `System.Text` levererar verktyg för UTF‑8‑kodning. Att importera dessa namnrymder gör den efterföljande koden kortfattad och läsbar.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Steg 1: konvertera geojson‑sträng – ett C# GeoJSON‑exempel
Först skapar vi en JSON‑sträng som representerar en enkel `FeatureCollection`. Detta är delen **convert geojson string** i arbetsflödet.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Steg 2: läs in geojson‑ström och extrahera geojson‑egenskaper
Nu matar vi strängen i ett `MemoryStream`, öppnar den som ett GIS‑lager och demonstrerar hur man läser attributvärden (steg **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Pro tip:** `VectorLayer.Open` upptäcker automatiskt GeoJSON‑formatet när du skickar `Drivers.GeoJson`. Du kan också öppna filer direkt genom att ange en filsökväg istället för en ström.

## Vanliga problem & lösningar
| Problem | Lösning |
|-------|----------|
| **Invalid JSON format** | Verifiera att GeoJSON‑strängen är väl‑formad; använd en JSON‑validator. |
| **Encoding problems** | Säkerställ att strömmen använder UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Missing properties** | Kontrollera att egenskapsnamnet är stavat korrekt (`"name"` i exemplet). |
| **License exception** | Använd en provlicens för testning; tillämpa en permanent licens för produktion. |

## Vanliga frågor
### Är Aspose.GIS kompatibel med andra GIS‑format?
Ja, Aspose.GIS stöder GeoJSON, Shapefile, KML, GML och 20+ ytterligare format, vilket gör att du kan växla mellan datakällor utan att ändra kod.

### Kan jag prova Aspose.GIS innan jag köper?
Du kan ladda ner en gratis provversion av Aspose.GIS från [Aspose.GIS free trial download page](https://releases.aspose.com/).

### Var kan jag hitta dokumentation för Aspose.GIS?
Du kan hitta dokumentationen för Aspose.GIS [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/).

### Hur kan jag få support för Aspose.GIS?
Du kan få support för Aspose.GIS på Aspose GIS‑forumet [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

### Behöver jag en tillfällig licens för att använda Aspose.GIS?
Du kan skaffa en tillfällig licens för Aspose.GIS från [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Slutsats
I den här guiden gick vi igenom **how to read geojson** från ett minnesström med Aspose.GIS för .NET, demonstrerade ett **C# read geojson**‑arbetsflöde och visade hur man **extract geojson properties** från det öppnade lagret. Med dessa steg kan du sömlöst integrera hantering av geografiska data i vilken .NET‑applikation som helst.

---

**Senast uppdaterad:** 2026-10-05  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skriver GeoJSON till ström med Aspose.GIS för .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [Hur man konverterar GeoJSON till GDB med Aspose.GIS för .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Konvertera Shapefile till GeoJSON med Aspose.GIS för .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}