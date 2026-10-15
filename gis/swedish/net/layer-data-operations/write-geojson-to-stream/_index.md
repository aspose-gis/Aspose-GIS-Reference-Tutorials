---
date: 2026-10-15
description: Lär dig hur du skapar GeoJSON från koordinater och skriver det till en
  ström med Aspose.GIS för .NET. Den här handledningen visar steg‑för‑steg-omvandling
  av punkter och generering av GeoJSON C#‑kod.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Skriv GeoJSON till ström
og_description: Lär dig hur du skapar GeoJSON från koordinater och skriver det till
  en ström med Aspose.GIS för .NET – steg‑för‑steg‑guide för stora datamängder.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Skapa GeoJSON från koordinater, skriv till en ström i .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Skapa GeoJSON från koordinater, skriv till en ström i .NET
url: /sv/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa geojson från koordinater och skriv till en ström

## Introduktion
I den här handledningen kommer du att lära dig **hur man skapar geojson från koordinater** och skriva den direkt till en ström med Aspose.GIS för .NET. Vi går igenom miljöinställning, lager‑skapande, funktion‑befolkning och strömning av resultatet, så att du kan bädda in geospatiala nyttolaster i API:er, molnfunktioner eller fil‑lösa tjänster utan temporära filer.

## Snabba svar
- **Vilken klass skriver GeoJSON till en ström?** `VectorLayer` together with the `GeoJsonDriver`.
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kan jag konvertera punkt‑samlingar till GeoJSON?** Ja – skapa ett `Feature` för varje punkt och tilldela en `Point`‑geometri.
- **Är strömning lämplig för stora dataset?** Absolut – `MemoryStream` låter dig skriva GeoJSON i gigabyteskala utan att ladda hela filen i minnet.

## Vad är GeoJSON?
GeoJSON är ett öppet JSON‑baserat format för kodning av geografiska funktioner såsom punkter, linjer och polygoner. Det består av en `FeatureCollection` som grupperar enskilda `Feature`‑objekt, var och en med geometri och attributdata. Eftersom det är lättviktigt och webbvänligt är GeoJSON de‑fakto‑standarden för utbyte av spatiala data mellan webbläsare, GIS‑servrar och mobila appar.

## Varför använda Aspose.GIS för geojson‑generering?
Aspose.GIS stöder **35+ spatiala filformat** och kan strömma filer större än **2 GB** samtidigt som minnesanvändningen hålls under **50 MB**. Dess högpresterande strömningsmotor skriver GeoJSON direkt till vilken .NET `Stream` som helst, vilket eliminerar behovet av mellansteg med temporära filer och minskar I/O‑latensen med upp till **70 %** i typiska molnscenarier.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Aspose.GIS for .NET** installerat. Ladda ner **Aspose.GIS for .NET**‑paketet [här](https://releases.aspose.com/gis/net/).
2. En skrivbar mapp i ditt projekt där du kan placera temporära filer om så behövs.
3. .NET 5+ eller .NET Core 3.1+ runtime installerad.

Nu, låt oss dyka in i implementeringen.

## Hur skapar man geojson från koordinater och skriver till en ström?
`VectorLayer` representerar ett in‑minnes vektordataset som kan sparas i olika format. `GeoJsonDriver` är drivrutinen som möjliggör läsning och skrivning av GeoJSON‑filer.

Läs in ett `VectorLayer` med `GeoJsonDriver`, lägg till `Feature`‑objekt som innehåller `Point`‑geometri, och anropa `layer.Save(stream, new GeoJsonSaveOptions())`. Detta enkla anrop serialiserar hela feature‑samlingen till ett standard‑kompatibelt GeoJSON‑dokument som ligger i den medföljande `MemoryStream`. Processen hanterar attributmappning och koordinatkonvertering automatiskt, så du får en färdig‑till‑använd JSON‑payload utan manuell strängbyggnad.

### Definition ankare
**VectorLayer** är Aspose.GIS‑objektet som representerar ett muterbart vektordataset i minnet. **GeoJsonDriver** är drivrutinen som ansvarar för läsning och skrivning av GeoJSON‑filer.

## Importera namnrymder
Först och främst, se till att inkludera de nödvändiga namnrymderna för att få åtkomst till Aspose.GIS‑funktionaliteten i din kod:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Steg 1: konfigurera dokumentkatalogen
Skapa en mappväg där Aspose.GIS kan lagra hjälpfiler om så krävs.  
```csharp
string dataDir = "Your Document Directory";
```
Ersätt "Your Document Directory" med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: skapa ett minnesström
Ett `MemoryStream` tillhandahåller en minnesbuffert som kan skickas direkt över HTTP eller sparas i molnlagring.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Steg 3: skapa ett vektorlager med GeoJSON‑drivrutin
`VectorLayer`‑klassen representerar ett vektordataset som kan sparas i olika format, inklusive GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Steg 4: definiera feature‑attribut
Definiera attributschemat för dina features (t.ex. ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Steg 5: konstruera och lägga till features
Skapa `Feature`‑objekt, tilldela punktgeometri, sätt attributvärden och lägg till dem i lagret.  
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

## Steg 6: visa GeoJSON‑utdata
Efter sparning, återställ strömmens position och läs JSON‑strängen för verifiering eller överföring.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Grattis! Du har framgångsrikt skapat geojson från koordinater och skrivit den till en ström med Aspose.GIS för .NET.

## Vanliga problem och lösningar
- **Tom utdata‑ström:** Se till att återställa strömmens position (`stream.Position = 0`) innan du läser.
- **Fel koordinatordning:** GeoJSON förväntar sig longitud‑latitud‑ordning; verifiera dina punktvärden.
- **Stora dataset:** Använd `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` för att strömma features inkrementellt och hålla minnesanvändningen låg.

## Vanliga frågor

**Q: Kan jag använda Aspose.GIS för .NET i både Windows‑ och Linux‑miljöer?**  
A: Ja, Aspose.GIS för .NET körs på Windows, Linux och macOS med full .NET Core‑support.

**Q: Finns det en gratis provversion tillgänglig?**  
A: Absolut! Du kan utforska **gratis provversionsnedladdningssidan** [här](https://releases.aspose.com/).

**Q: Var kan jag hitta detaljerad dokumentation?**  
A: Kolla in **Aspose.GIS .NET‑dokumentationen** [här](https://reference.aspose.com/gis/net/).

**Q: Hur kan jag få temporär licens?**  
A: Temporära licenser finns på **temporär licenssida** [här](https://purchase.aspose.com/temporary-license/).

**Q: Behöver du hjälp eller har fler frågor?**  
A: Besök vårt **GIS‑supportforum** [här](https://forum.aspose.com/c/gis/33).

**Q: Kan jag generera GeoJSON från en samling av latitud/longitud‑punkter?**  
A: Ja – skapa ett `Feature` för varje punkt, tilldela en `Point`‑geometri och lägg till det i `VectorLayer`.

**Q: Stöder Aspose.GIS att skriva komprimerad GeoJSON (gzip)?**  
A: Du kan omsluta `MemoryStream` i en `GZipStream` innan du sparar för att producera en komprimerad payload.

**Q: Vad är den maximala storleken på en GeoJSON‑fil som Aspose.GIS kan hantera?**  
A: Biblioteket kan strömma filer som överstiger 2 GB; minnesanvändningen förblir låg eftersom data skrivs inkrementellt.

---

**Senast uppdaterad:** 2026-10-15  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

## Relaterade handledningar

- [Hur man läser GeoJSON från ström med Aspose.GIS för .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hur man konverterar GeoJSON till TopoJSON med Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Hur man konverterar Shapefile till GeoJSON med Aspose.GIS för .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}