---
date: 2026-05-31
description: Lär dig hur du begränsar precision när du skriver geometries med Aspose.GIS
  för .NET, minskar GeoJSON-storlek och behåller coordinate control.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Begränsa precision vid skrivning av geometries
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Hur man begränsar precision vid skrivning av geometries med Aspose.GIS
url: /sv/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man begränsar precision vid skrivning av geometrier med Aspose.GIS

Om du undrar **hur man begränsar precision** när du skriver geometrier i en .NET GIS-applikation, Aspose.GIS för .NET tillhandahåller ett enkelt, högpresterande sätt att kontrollera koordinatrundning. I den här handledningen går vi igenom hela processen—från att sätta upp miljön till att verifiera att resultatet följer de precisionsregler du definierar.

## Snabba svar
- **Vad betyder “limit precision”?** Det rundar koordinatvärden till ett definierat antal bråkdelssiffror när en rumslig fil skrivs.  
- **Vilket format används i exemplet?** GeoJSON, men samma alternativ gäller för andra stödda format.  
- **Behöver jag en licens för att prova detta?** En gratis provperiod fungerar för utveckling och testning; en kommersiell licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kan jag kontrollera Z‑koordinatens precision separat?** Ja—använd `ZPrecisionModel` för att ange exakta eller avrundade värden.

## Så begränsar du precision vid skrivning av geometrier

Ladda din GeoJSON-skrivare med ett `GeoJsonOptions`-objekt som specificerar önskad X/Y- och Z-precision, skriv sedan geometrin och läs tillbaka den—detta hela arbetsflöde ryms på under tio kodrader och garanterar att alla koordinater avrundas exakt som du har definierat.

Att begränsa precision är viktigt när du behöver en konsekvent koordinatrepresentation över olika GIS-verktyg, minska filstorlek eller följa dataväxlingsstandarder. Nedan kommer vi att definiera precisionsalternativ, skriva en geometri och sedan läsa tillbaka den för att bekräfta avrundningen.

## Vad är precisionbegränsning?

Precisionbegränsning är processen att avrunda den bråkdeliga delen av koordinatvärden till ett fast antal siffror innan geometrin sparas i ett filformat. Detta säkerställer att varje mottagare av filen ser samma numeriska värden, vilket hjälper till att undvika små avvikelser som kan orsaka topologifel.

## Varför använda Aspose.GIS för precisionskontroll?

Aspose.GIS stöder **50+** in- och utdataformat—inklusive GeoJSON, Shapefile, KML och GML—och kan bearbeta filer med **hundratusentals funktioner** utan att ladda hela datasetet i minnet. Dess inbyggda precisionsmodeller låter dig avrunda koordinater i ett enda anrop, vilket eliminerar behovet av manuella efterbearbetningsskript.

## Förutsättningar

### 1. Nedladdning och installation
Hämta det senaste Aspose.GIS för .NET-paketet från den officiella webbplatsen: [download link](https://releases.aspose.com/gis/net/). Följ installationsguiden för att lägga till NuGet-paketet i ditt projekt.

### 2. Import av namnrymd
Lägg till de nödvändiga namnrymderna så att du kan komma åt GIS-klasserna och hjälputrustningarna.

## Steg‑för‑steg‑guide

### Steg 1: Definiera precisionsalternativ
`GeoJsonOptions`-klassen låter dig ange hur många bråkdelssiffror som ska behållas för X/Y- och Z-koordinater.

`PrecisionModel` definierar hur koordinatvärden avrundas eller behålls exakt under skrivning.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Steg 2: Ange utdataväg
Ange var den resulterande GeoJSON-filen ska sparas.

`VectorLayer` är Aspose.GIS:s behållare för en samling funktioner som delar samma schema; den skriver till den sökväg du anger med de tidigare inställda alternativen.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Steg 3: Skapa och fyll på geometri
Öppna ett nytt `VectorLayer` med de ovan definierade alternativen, konstruera en `Point`-geometri och lägg till den i lagret.

`Point` representerar en enda koordinat (X, Y, valfri Z) i ett rumsligt referenssystem. Det är den enklaste geometritypen och används här för att demonstrera precisionsavrundning.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Steg 4: Läs och verifiera precision
Öppna filen du just skapade och skriv ut koordinaterna. Du bör se X/Y‑värdena avrundade till tre decimaler medan Z‑värdet förblir exakt.

När du läser tillbaka filen parsar Aspose.GIS de avrundade värdena direkt, så `Point` i minnet återspeglar den precision du definierade under skrivning.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Vanliga problem & tips

- **Sökvägsfel:** Säkerställ att katalogen i `path` finns eller använd `Path.Combine` med `Environment.CurrentDirectory` för att bygga en säker filsökväg.  
- **Precision tillämpas inte:** Verifiera att du passerar `GeoJsonOptions`-objektet när du skapar lagret; annars används standardprecision (full double).  
- **Stora dataset:** För massoperationer, överväg att återanvända en enda `VectorLayer`-instans och batch‑lägga till funktioner för att förbättra prestanda.

## Vanliga frågor

**Q: Är Aspose.GIS för .NET kompatibel med andra GIS-format?**  
A: Ja, den stöder **50+** format—inklusive Shapefile, GeoJSON, KML, GML och CSV—vilket möjliggör sömlös konvertering mellan dem.

**Q: Kan jag prova Aspose.GIS för .NET innan jag köper?**  
A: Absolut. En gratis provperiod finns tillgänglig på nedladdningssidan, vilket ger dig full åtkomst till alla funktioner för utvärdering.

**Q: Hur får jag en tillfällig licens för testning?**  
A: Tillfälliga utvärderingslicenser kan genereras via Aspose licensportal; de är giltiga i 30 dagar.

**Q: Var kan jag få hjälp om jag stöter på problem?**  
A: Aspose.GIS-forumet och Stack Overflow-taggen `aspose-gis` är bra ställen att ställa frågor och hitta community‑lösningar.

**Q: Fungerar biblioteket både för små skript och företags‑skala applikationer?**  
A: Ja, Aspose.GIS är designat för att hantera allt från snabba prototyper till hög‑genomströmning serverarbetsbelastningar, och bearbetar multi‑gigabyte dataset med låg minnesanvändning.

---

**Senast uppdaterad:** 2026-05-31  
**Testat med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa vektorlager, begränsa precision med Aspose.GIS för .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Hur man konverterar GeoJSON – Aspose.GIS för .NET](/gis/net/geo-data-conversion/)
- [Hur man kontrollerar geometri med Aspose.GIS för .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}