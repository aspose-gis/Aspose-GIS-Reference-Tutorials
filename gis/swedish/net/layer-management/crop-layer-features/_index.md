---
date: 2026-07-05
description: Lär dig hur du beskär lagerfunktioner med Aspose.GIS för .NET, inklusive
  hur du beskär raster med polygon, extraherar raster cell size och hämtar raster
  extent. Ladda ner din gratis provversion nu.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Hur man beskär lagerfunktioner
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
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
I den här handledningen kommer du att lära dig **how to crop layer** funktioner med Aspose.GIS för .NET, ett kraftfullt bibliotek som låter dig **crop raster with polygon**, **extract raster cell size**, och **retrieve raster extent** för exakt geospatial analys. Oavsett om du förbereder data för en webbkarta, beskär satellitbilder eller isolerar ett intresseområde, visar denna steg‑för‑steg‑guide exakt hur du får jobbet gjort snabbt och pålitligt.

## Snabba svar
- **Vad betyder “crop layer”?** Det beskär ett raster- eller vektorlager till gränserna för en angiven geometri och kastar bort allt utanför.  
- **Vilken geometri används i detta exempel?** En polygon definierad i WKT (Well‑Known Text) format.  
- **Kan jag extrahera cellstorlek efter beskärning?** Ja – `CellSize`‑egenskapen returnerar bredden och höjden på en rastercell.  
- **Behöver jag en licens för att köra koden?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktionsanvändning.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är “how to crop layer”?
**Att beskära ett lager betyder att begränsa datasetet till ett specifikt geografiskt område och kasta bort allt utanför.** Denna operation minskar filstorleken, snabbar upp efterföljande bearbetning och fokuserar analysen på den region du är intresserad av. Genom att begränsa data till intresseområdet förenklar du även efterföljande arbetsflöden såsom stilisering, analys och publicering, samtidigt som du bevarar det ursprungliga koordinatreferenssystemet och metadata.

## Varför använda Aspose.GIS för beskärning?
**Aspose.GIS bearbetar rasterfiler upp till 2 GB utan att ladda hela bilden i minnet och stödjer mer än 30 rasterformat, inklusive GeoTIFF, JPEG2000 och PNG.** Biblioteket erbjuder ett enradigt `Crop`‑anrop, automatisk CRS‑hantering och flertrådad prestanda som kan beskära en 500 MB GeoTIFF på under en sekund på en vanlig server.

## Förutsättningar
Innan du dyker ner i magin med geospatial manipulation, se till att du har följande förutsättningar på plats:

- Aspose.GIS för .NET-biblioteket: Se till att du har Aspose.GIS‑biblioteket installerat i ditt .NET‑projekt. Du kan ladda ner det från [here](https://releases.aspose.com/gis/net/).  
- Dokumentkatalog: Skapa en katalog för att lagra dina dokument. Ersätt `"Your Document Directory"` i den medföljande koden med den faktiska sökvägen till din dokumentkatalog.

Nu, låt oss dyka in i steg‑för‑steg‑guiden.

## Importera namnrymder
`Aspose.Gis`‑namnrymden innehåller alla kärntyper för raster- och vektorhantering. Importera den för att få åtkomst till `Layer`, `Geometry` och relaterade klasser.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Hur beskär jag ett lager med en polygon?
`Crop` är en metod i `Layer`‑klassen som extraherar en rasterdel definierad av en geometri.  
Läs in källraster, definiera en polygongeometri och anropa `Crop`‑metoden – hela operationen utförs i en enda kodrad. Metoden returnerar ett nytt raster som endast innehåller pixlarna inom polygonen och bevarar automatiskt den ursprungliga rumsliga referensen.

## Steg 1: Öppna och beskära lagret (crop raster with polygon)
`Layer` representerar ett rasterdataset som kan öppnas, frågas och redigeras.  
`Layer`‑klassen representerar ett rasterdataset som kan öppnas, frågas och redigeras. Att öppna en GeoTIFF och beskära den med en polygon isolerar intresseområdet med bara några få satser.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Steg 2: Hämta rasterinformation (extract raster cell size & retrieve raster extent)
`CellSize` ger bredden och höjden på varje rastercell i koordinatenheter.  
`Extent` returnerar rasterns geografiska omgivningsruta.  
`CellSize`‑egenskapen ger bredden och höjden på varje rastercell i koordinatenheter, medan `Extent`‑egenskapen returnerar den geografiska omgivningsrutan för det beskurna rasteret. Båda informationsdelarna är väsentliga för efterföljande beräkningar såsom arealmätning eller reprojektion.

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

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Fel polygonorientering** | Ensure the WKT polygon follows the right‑hand rule (counter‑clockwise for outer rings). |
| **Saknad rumslig referens** | Verify that the source GeoTiff contains a CRS; otherwise, set one manually before cropping. |
| **Prestandaförsämring på stora raster** | Use `layer.Crop` on a down‑sampled copy or process the raster in tiles. |

## Vanliga frågor
**Q: Är en tillfällig licens tillgänglig för Aspose.GIS för .NET?**  
A: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta omfattande dokumentation för Aspose.GIS för .NET?**  
A: The documentation is available [here](https://reference.aspose.com/gis/net/).

**Q: Hur kan jag söka support eller ansluta till communityn för Aspose.GIS för .NET?**  
A: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support and community engagement.

**Q: Kan jag ladda ner en gratis provversion av Aspose.GIS för .NET?**  
A: Yes, you can download a free trial [here](https://releases.aspose.com/).

**Q: Var kan jag köpa Aspose.GIS för .NET?**  
A: You can purchase the library [here](https://purchase.aspose.com/buy).

**Q: Kan jag beskära flera lager i ett enda kör?**  
A: Yes—loop over each layer and apply the same `Crop` call with the desired geometry.

**Q: Stöder API:et andra rasterformat (t.ex. JPEG2000)?**  
A: Aspose.GIS stödjer alla format som exponeras av de underliggande GDAL-drivrutinerna, inklusive JPEG2000, PNG och mer.

## Slutsats
Genom att följa den här guiden vet du nu hur du effektivt **how to crop layer** funktioner med Aspose.GIS för .NET. Du kan enkelt **crop raster with polygon**, **extract raster cell size** och **retrieve raster extent** för att passa alla projektbehov. Utforska ytterligare API:er för reprojektion, rasterstilering och vektoranlys för att låsa upp hela potentialen i dina geospatiala arbetsflöden.

---

**Senast uppdaterad:** 2026-07-05  
**Testad med:** Aspose.GIS 24.10 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man skapar polygongeometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Hämta lagerattribut – Hämta lagerattributinformation med Aspose.GIS för .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Skapa polygongeometri C# och kontrollera skärning med Aspose.GIS för .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}