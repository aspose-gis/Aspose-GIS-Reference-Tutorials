---
date: 2025-12-28
description: Lär dig hur du läser GeoJSON från en ström med Aspose.GIS för .NET. Denna
  C#‑guide för att läsa GeoJSON ger ett steg‑för‑steg‑exempel för att integrera geospatiala
  data.
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: Hur man läser GeoJSON från en ström med Aspose.GIS för .NET
url: /sv/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read GeoJSON from Stream with Aspose.GIS for .NET

## Introduktion
Om du undrar **how to read geojson** i en .NET-applikation, har du kommit till rätt ställe. I den här handledningen går vi igenom ett komplett **c# geojson example** som visar hur man konverterar en GeoJSON-sträng, öppnar ett GeoJSON-lager från ett minnesström, och extraherar GeoJSON-egenskaper med Aspose.GIS. I slutet har du ett återanvändbart mönster som du kan lägga in i vilket projekt som helst som behöver arbeta med geografiska data.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.GIS for .NET  
- **Kan jag läsa GeoJSON direkt från en ström?** Ja – använd `VectorLayer.Open` med `AbstractPath.FromStream`.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Är det enkelt att extrahera egenskaper?** Ja – anropa `GetValue<T>(columnName)` på ett feature.

## Vad är “how to read geojson”?
Att läsa GeoJSON innebär att tolka det JSON‑baserade formatet som beskriver geografiska funktioner (punkter, linjer, polygoner) och göra dessa funktioner tillgängliga som objekt som du kan fråga, redigera eller render applikation.

## Varför använda Aspose.GIS för att **open geojson layer**?
Aspose.GIS abstraherar de lågnivå‑parsningsdetaljerna och ger dig ett konsekvent API för många GIS-format. Det låter dig **open geojson layer** direkt från en ström, hantera stora filer effektivt och komma åt attribut för funktioner utan att skriva egna JSON‑parsers.

## Förutsättningar
1. **Grundläggande kunskap om C#** – du bör vara bekväm med .NET‑syntax och Visual Studio‑IDE:n.  
2. **Aspose.GIS installerat** – ladda ner biblioteket från [here](https://releases.aspose.com/gis/net/).  
3. **En utvecklingsmiljö** – Visual Studio, Visual Studio Code eller JetBrains Rider fungerar bra.  

## Importera namnrymder
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Steg 1: **Convert GeoJSON string** – ett **c# geojson example**
Först skapar vi en JSON‑sträng som representerar en enkel `FeatureCollection`. Detta är **convert geojson string**‑delen av arbetsflödet.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Steg 2: **Open GeoJSON layer** från ström och **extract geojson properties**
Nu matar vi strängen i en `MemoryStream`, öppnar den som ett GIS‑lager och demonstrerar hur man läser attributvärden (steg **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Proffstips:** `VectorLayer.Open` upptäcker automatiskt GeoJSON‑formatet när du anger `Drivers.GeoJson`. Du kan också öppna filer direkt genom att ange en filsökväg istället för en ström.

## Vanliga problem & lösningar
| Problem | Lösning |
|---------|----------|
| **Invalid JSON format** | Verifiera att GeoJSON‑strängen är väl‑formad; använd en JSON‑validator. |
| **Encoding problems** | Säkerställ att strömmen använder UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Missing properties** | Kontrollera att egenskapsnamnet är stavat korrekt (`"name"` i exemplet). |
| **License exception** | Använd en provlicens för testning; tillämpa en permanent licens för produktion. |

## Vanliga frågor
### Är Aspose.GIS kompatibel med andra GIS-format?
Ja, Aspose.GIS stödjer GeoJSON, Shapefile, KML, GML och många fler format.

### Kan jag prova Aspose.GIS innan jag köper?
Ja, du kan ladda ner en gratis provversion av Aspose.GIS från [here](https://releases.aspose.com/).

### Var kan jag hitta dokumentation för Aspose.GIS?
Du kan hitta dokumentationen för Aspose.GIS [here](https://reference.aspose.com/gis/net/).

### Hur kan jag få support för Aspose.GIS?
Du kan få support för Aspose.GIS på Aspose‑forumet [here](https://forum.aspose.com/c/gis/33).

### Behöver jag en tillfällig licens för att använda Aspose.GIS?
Du kan skaffa en tillfällig licens för Aspose.GIS från [here](https://purchase.aspose.com/temporary-license/).

## Slutsats
I den här guiden gick vi igenom **how to read geojson** från ett minnesström med Aspose.GIS för .NET, demonstrerade ett **c# read geojson**‑arbetsflöde och visade hur man **extract geojson properties** från det öppnade lagret. Med dessa steg kan du sömlöst integrera hantering av geografiska data i vilken .NET‑applikation som helst.

---

**Senast uppdaterad:** 2025-12-28  
**Testat med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}