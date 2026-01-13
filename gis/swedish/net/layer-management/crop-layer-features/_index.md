---
date: 2026-01-13
description: Lär dig hur du beskär lagerfunktioner med Aspose.GIS för .NET, inklusive
  hur du beskär raster med polygon, extraherar rastercellens storlek och hämtar rasterutbredning.
  Ladda ner din gratis provversion nu.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Hur man beskär lagerfunktioner med Aspose.GIS för .NET
url: /sv/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man beskär lagerfunktioner

## Introduktion
I den här handledningen kommer du att lära dig **how to crop layer**-funktioner med Aspose.GIS för .NET, ett kraftfullt tillvägagångssätt som låter dig **crop raster with polygon**, **extract raster cell size** och **retrieve raster extent** för exakt geospatial analys. Oavsett om du förbereder data för en webbkarta, beskär satellitbilder eller isolerar ett intresseområde, visar denna steg‑för‑steg‑guide exakt hur du utför uppgiften.

## Snabba svar
- **What does “crop layer” mean?** Det beskär ett raster‑ eller vektorlager till gränserna för en angiven geometri.  
- **Which geometry is used in this example?** En polygon definierad i WKT-format.  
- **Can I extract cell size after cropping?** Ja – `CellSize`‑egenskapen ger den informationen.  
- **Do I need a license to run the code?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “how to crop layer”?
Att beskära ett lager innebär att begränsa datasetet till ett specifikt geografiskt område och kasta bort allt utanför den definierade formen. Detta minskar filstorleken, snabbar upp bearbetningen och fokuserar analysen på den region du är intresserad av.

## Why use Aspose.GIS for cropping?
- **High‑performance raster handling** – ideal för stora GeoTiff‑filer.  
- **Simple API** – en‑rad `Crop`‑anrop med vilken geometri som helst.  
- **Full .NET compatibility** – fungerar i skrivbords-, server- och molnapplikationer.  
- **Accurate spatial reference handling** – bevarar CRS‑information automatiskt.

## Prerequisites
Innan du dyker ner i den magiska geospatiala manipulationen, se till att du har följande förutsättningar på plats:

- Aspose.GIS för .NET‑biblioteket: Säkerställ att du har Aspose.GIS‑biblioteket installerat i ditt .NET‑projekt. Du kan ladda ner det från [here](https://releases.aspose.com/gis/net/).  
- Dokumentkatalog: Skapa en katalog för att lagra dina dokument. Ersätt `"Your Document Directory"` i den medföljande koden med den faktiska sökvägen till din dokumentkatalog.

Nu, låt oss dyka in i steg‑för‑steg‑guiden.

## Import Namespaces
Börja med att importera de nödvändiga namnutrymmena för att utnyttja hela kraften i Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Steg 1: Öppna och beskära lagret (crop raster with polygon)
Börja med att öppna GeoTiff‑lagret och beskära det baserat på en definierad polygon. Detta säkerställer att dina geospatiala data förfinas till ett specifikt intresseområde.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Steg 2: Hämta rasterinformation (extract raster cell size & retrieve raster extent)
När lagret har beskärts, extrahera viktig information om rasterdata, såsom cellstorlek, spatialt referenssystem och gränser.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Steg 3: Visa information
Skriv ut den extraherade informationen för att förstå hur beskärningsprocessen påverkar dina geospatiala data.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Upprepa dessa steg efter behov för att förfina och anpassa dina geospatiala data så att de uppfyller specifika projektkrav.

## Common Issues and Solutions
| Problem | Lösning |
|-------|----------|
| **Fel polygonorientering** | Se till att WKT‑polygonen följer högerhandsregeln (moturs för yttre ringar). |
| **Saknad spatial referens** | Verifiera att käll‑GeoTiff innehåller ett CRS; annars, ange ett manuellt innan beskärning. |
| **Prestandaförsämring på stora raster** | Använd `layer.Crop` på en nedskalad kopia eller bearbeta rastern i tile‑format. |

## Frequently Asked Questions
### Q: Är en tillfällig licens tillgänglig för Aspose.GIS för .NET?
A: Ja, du kan skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

### Q: Var kan jag hitta omfattande dokumentation för Aspose.GIS för .NET?
A: Dokumentationen finns [here](https://reference.aspose.com/gis/net/).

### Q: Hur kan jag få support eller ansluta till communityn för Aspose.GIS för .NET?
A: Besök [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) för support och community‑engagemang.

### Q: Kan jag ladda ner en gratis provversion av Aspose.GIS för .NET?
A: Ja, du kan ladda ner en gratis provversion [here](https://releases.aspose.com/).

### Q: Var kan jag köpa Aspose.GIS för .NET?
A: Du kan köpa biblioteket [here](https://purchase.aspose.com/buy).

### Q: Kan jag beskära flera lager i ett och samma körning?
A: Ja—loopa över varje lager och applicera samma `Crop`‑anrop med önskad geometri.

### Q: Stöder API:et andra rasterformat (t.ex. JPEG2000)?
A: Aspose.GIS stödjer alla format som de underliggande GDAL‑drivrutinerna exponerar, inklusive JPEG2000, PNG och fler.

## Slutsats
Genom att följa den här guiden vet du nu hur du effektivt **how to crop layer**‑funktioner med Aspose.GIS för .NET. Du kan enkelt **crop raster with polygon**, **extract raster cell size** och **retrieve raster extent** för att passa alla projekts behov. Utforska ytterligare API:er för reprojektion, raster‑styling och vektoranalyser för att låsa upp hela potentialen i dina geospatiala arbetsflöden.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose