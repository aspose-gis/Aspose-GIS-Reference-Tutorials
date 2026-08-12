---
date: 2026-05-21
description: Lär dig hur du skriver GeoJSON till en ström med Aspose.GIS för .NET.
  Denna GeoJSON‑handledning för .NET visar steg‑för‑steg konvertering av punkter och
  generering av GeoJSON C#‑kod.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: Skriv GeoJSON till ström
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur man skriver GeoJSON till ström med Aspose.GIS för .NET
url: /sv/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skriv GeoJSON till ström

## Introduktion
I den här handledningen kommer du att lära dig **hur man skriver GeoJSON till en ström** i en .NET-applikation med Aspose.GIS. Vi går igenom varje steg, från att konfigurera miljön till att producera ett giltigt GeoJSON-dokument, så att du kan integrera geografiska data sömlöst i dina tjänster.

## Snabba svar
- **Vad är den primära klassen för GeoJSON-utmatning?** `VectorLayer` med `GeoJsonDriver`.
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kan jag konvertera punktkollektioner till GeoJSON?** Ja – använd `Feature`-klassen och definiera punktgeometri.
- **Stöds strömning för stora dataset?** Absolut; `MemoryStream` låter dig skriva utan mellanfiler.

## Vad är GeoJSON?
GeoJSON är ett öppet standardformat för att koda en mängd geografiska datastrukturer med JSON. Det definierar objekt som FeatureCollection, Feature och geometrityper (Point, LineString, Polygon). Denna lätta, webb‑vänliga representation möjliggör enkel utbyte och visualisering av rumsliga data över många plattformar och programmeringsspråk.

## Varför använda Aspose.GIS för GeoJSON-generering?
Aspose.GIS stöder mer än 30 rumsliga filformat och kan bearbeta filer större än 2 GB utan att ladda hela dokumentet i minnet. Dess högpresterande strömningsmotor skriver GeoJSON direkt till strömmar, vilket minskar I/O‑kostnader. Detta gör det idealiskt för företags‑skaliga geospatiala arbetsbelastningar, molntjänster och real‑tidsapplikationer.

## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
1. Aspose.GIS för .NET-bibliotek: Se till att du har Aspose.GIS för .NET-biblioteket installerat. Du kan ladda ner det [här](https://releases.aspose.com/gis/net/).
2. Dokumentkatalog: Ha en dokumentkatalog konfigurerad i ditt projekt och notera dess sökväg.

Nu, låt oss komma igång med handledningen!

## Hur skriver jag GeoJSON till en ström?
VectorLayer representerar en vektordataset som kan sparas i olika format, inklusive GeoJSON.  
GeoJsonDriver är den drivrutin som används av Aspose.GIS för att läsa och skriva GeoJSON-filer.  
`layer.Save` skriver lagerinnehållet till den angivna strömmen med angivna sparalternativ.  

Läs in en `VectorLayer` med `GeoJsonDriver`, lägg till funktioner som innehåller punktgeometri och anropa sedan `layer.Save(stream, new GeoJsonSaveOptions())`. Detta skriver ett komplett, standard‑kompatibelt GeoJSON-dokument direkt in i den angivna `MemoryStream` på bara några kodrader. Metoden serialiserar funktionssamlingen, hanterar attributdata och geometrikonvertering automatiskt, så du får en färdig‑till‑använd JSON‑payload utan manuell strängmanipulation.

## Importera namnrymder
Först och främst, se till att inkludera de nödvändiga namnrymderna för att komma åt Aspose.GIS-funktionerna i din kod:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Steg 1: Konfigurera dokumentkatalogen
```csharp
string dataDir = "Your Document Directory";
```
Ersätt "Your Document Directory" med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Skapa en Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Steg 3: Skapa ett Vector Layer med GeoJSON-drivrutin
Klassen `VectorLayer` representerar ett vektordataset som kan sparas i olika format, inklusive GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Steg 4: Definiera funktionsattribut
Definiera attributschemat för dina funktioner (t.ex. ID, Name).
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Steg 5: Konstruera och lägg till funktioner
Skapa `Feature`-objekt, tilldela punktgeometri, sätt attributvärden och lägg till dem i lagret.
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Steg 6: Visa GeoJSON-utdata
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Grattis! Du har framgångsrikt skrivit GeoJSON till en ström med Aspose.GIS för .NET.

## Vanliga problem och lösningar
- **Tom utdataström:** Se till att du återställer strömmens position (`stream.Position = 0`) innan du läser.
- **Fel koordinatordning:** GeoJSON förväntar sig longitud‑latitud‑ordning; verifiera dina punktvärden.
- **Stora dataset:** Använd `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` för att strömma funktioner inkrementellt.

## Vanliga frågor
### Kan jag använda Aspose.GIS för .NET i både Windows- och Linux-miljöer?
Ja, Aspose.GIS för .NET är kompatibel med både Windows- och Linux-system.

### Finns en gratis provversion tillgänglig?
Absolut! Du kan utforska en gratis provversion [här](https://releases.aspose.com/).

### Var kan jag hitta detaljerad dokumentation?
Kolla in dokumentationen [här](https://reference.aspose.com/gis/net/).

### Hur kan jag få tillfällig licens?
Tillfälliga licenser finns tillgängliga [här](https://purchase.aspose.com/temporary-license/).

### Behöver du hjälp eller har fler frågor?
Besök vårt supportforum [här](https://forum.aspose.com/c/gis/33).

**Q: Kan jag generera GeoJSON från en samling av latitud/longitud-punkter?**  
A: Ja – skapa ett `Feature` för varje punkt, tilldela en `Point`-geometri och lägg till det i `VectorLayer`.  

**Q: Stöder Aspose.GIS att skriva komprimerad GeoJSON (gzip)?**  
A: Du kan omsluta `MemoryStream` i en `GZipStream` innan du sparar för att producera en komprimerad payload.  

**Q: Vad är den maximala storleken på en GeoJSON-fil som Aspose.GIS kan hantera?**  
A: Biblioteket kan strömma filer som överstiger 2 GB; minnesanvändningen förblir låg eftersom data skrivs inkrementellt.  

---

**Senast uppdaterad:** 2026-05-21  
**Testat med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man läser GeoJSON från ström med Aspose.GIS för .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hur man konverterar GeoJSON till TopoJSON med Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Hur man konverterar Shapefile till GeoJSON med Aspose.GIS för .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}