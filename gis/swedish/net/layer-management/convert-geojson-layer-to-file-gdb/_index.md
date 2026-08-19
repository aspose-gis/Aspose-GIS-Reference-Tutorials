---
date: 2026-06-20
description: Lär dig hur du konverterar geojson till gdb med Aspose.GIS för .NET.
  Denna steg-för-steg-guide täcker läsning av GeoJSON i C#, skapande av en File Geodatabase
  och hantering av vanliga problem.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: Konvertera GeoJSON-lager till GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur man konverterar GeoJSON till GDB med Aspose.GIS för .NET
url: /sv/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur du konverterar GeoJSON till GDB med Aspose.GIS för .NET

## Introduktion
Om du vill **konvertera geojson till gdb** snabbt och pålitligt, är du på rätt plats. Den här handledningen guidar dig genom varje steg—från att läsa en GeoJSON‑fil i C# till att skapa en File Geodatabase (GDB) med Aspose.GIS. Du får se varför Aspose.GIS är ett föredraget bibliotek för konvertering av geografiska data, hur du sätter upp miljön och hur du kör konverteringen på bara några minuter.

## Snabba svar
- **Vad lär den här guiden ut?** Konvertera ett GeoJSON‑lager till en GDB med Aspose.GIS för .NET.  
- **Vilket primärt nyckelord är målet?** *convert geojson to gdb*.  
- **Behöver jag en licens?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Stödda .NET‑versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementeringstid?** Ungefär 10‑15 minuter för en grundläggande konvertering.

## Vad är GeoJSON och File GDB?
GeoJSON är ett lättviktigt, textbaserat format för geografiska objekt, medan File GDB är en mappbaserad högpresterande ESRI‑geodatabas.  
GeoJSON lagrar punkter, linjer och polygoner som ren text, vilket gör det enkelt att dela och redigera, medan File GDB sparar data i binära filer som möjliggör snabba rumsliga frågor och robust attributhantering. Tillsammans täcker de både webbvänlig utbyte och högprestanda desktop‑GIS‑bearbetning.

## Varför använda Aspose.GIS för konvertering av geografiska data?
Aspose.GIS erbjuder ett enhetligt API som döljer format‑specifika egenskaper. Det stöder **30+ geografiska format**, kan bearbeta filer upp till **2 GB** utan att ladda hela datasetet i minnet, och bevarar automatiskt koordinatreferenssystem. Detta innebär att du spenderar mindre tid på att skriva parsers och mer tid på att bygga din applikationslogik.

## Förutsättningar
- Bekantskap med C# och .NET‑projektstruktur.  
- Aspose.GIS för .NET installerat. Om du ännu inte har installerat det, ladda ner det från [här](https://releases.aspose.com/gis/net/) och följ installationsguiden. Du kan också utforska andra Aspose‑produkter på [här](https://releases.aspose.com/).

## Importera namnrymder
Det första steget är att importera de nödvändiga namnrymderna.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hur läser man GeoJSON i C#?
Läs in GeoJSON‑filen med klassen `GeoJsonReader`, som parsar JSON‑filen och skapar en `FeatureCollection` i minnet. Läsaren upptäcker automatiskt koordinatreferenssystemet, så du behöver inte hantera CRS‑parsning manuellt. Den stödjer också streaming av stora filer, bevarar attributtyper och kan kombineras med anpassade geometritransformationer om så krävs.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Steg 1: Skapa GeoJSON‑lagret
Skapa en temporär GeoJSON‑fil som innehåller de attribut och objekt du vill konvertera. Detta exempel lägger till två enkla punktobjekt.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Steg 2: Kopiera testdatasetet
För att behålla de ursprungliga testdataen intakta, duplicera det befintliga File GDB‑datasetet. Detta säkerställer en ren miljö för konverteringen.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Steg 3: Konvertera GeoJSON till GDB
`FileGdb` representerar en File Geodatabase‑behållare och tillhandahåller metoder för att hantera lager. Öppna GeoJSON‑lagret, skapa ett nytt lager i den kopierade File GDB, kopiera attribut och överför varje objekt. Detta är kärnan i **Aspose.GIS‑konverteringsprocessen**.

CODE_BLOCK_PLACEHOLDER_4_END

## Hur konverterar man GeoJSON till GDB?
Läs in GeoJSON med `GeoJsonReader`, skapa ett `FileGdb`‑objekt som pekar på din destinationsmapp, skapa ett nytt funktionslager och iterera sedan över varje objekt för att infoga det. I praktiken är det ett trestegsförlopp—läsa, skapa, kopiera—som slutförs på under en minut för typiska dataset.

## Vanliga problem och lösningar
- **Saknad rumslig referens:** Se till att käll‑GeoJSON innehåller en CRS‑definition eller ange explicit `SpatialReferenceSystem.Wgs84` när du skapar GDB‑lagret.  
- **Felaktig attributtyp:** Attributdatatyperna i GeoJSON måste matcha målschemat; annars kastar Aspose.GIS ett undantag.  
- **Filåtkomstfel:** Verifiera att destinationsmappen har skrivbehörighet och att ingen annan process låser GDB‑filerna.

## Vanliga frågor
### Är Aspose.GIS kompatibel med den senaste .NET‑ramverket?
Ja, Aspose.GIS fungerar med .NET Framework 4.5+, .NET Core 3.1+, .NET 5 och .NET 6+.

### Kan jag konvertera andra geografiska format med Aspose.GIS?
Absolut! Aspose.GIS stöder mer än 30 in‑ och utdataformat, inklusive Shapefile, KML, GML och SQLite.

### Finns det en provversion av Aspose.GIS?
Ja, du kan utforska funktionerna i Aspose.GIS genom att ladda ner provversionen [här](https://releases.aspose.com/).

### Hur får jag support för Aspose.GIS‑relaterade frågor?
Gå till Aspose.GIS‑[forumet](https://forum.aspose.com/c/gis/33) för dedikerad hjälp från communityn och produktteamet.

### Kan jag få en tillfällig licens för Aspose.GIS?
Ja, du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-06-20  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa File Geodatabase .NET-dataset med Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Läs funktioner från File Geodatabase i Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Skapa vektorlager i File GDB – Aspose.GIS .NET-handledning](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}