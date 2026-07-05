---
date: 2026-07-05
description: Lär dig hur du konverterar shapefile till geojson med Aspose.GIS för
  .NET. Guiden täcker också hur du kopierar attribut mellan lager och c# genererar
  geojson-fil.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Extrahera features till GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Konvertera Shapefile till GeoJSON med Aspose.GIS för .NET
url: /sv/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera Shapefile till GeoJSON med Aspose.GIS för .NET

## Introduktion
I den här omfattande, steg‑för‑steg‑handledningen kommer du att lära dig **hur man konverterar shapefile till geojson** med det kraftfulla Aspose.GIS‑biblioteket för .NET. Oavsett om du bygger en karttjänst på webben, förbereder data för en mobil GIS‑app eller helt enkelt behöver utbyta data mellan format, visar den här guiden exakt vad du ska göra, varför varje steg är viktigt och hur du undviker vanliga fallgropar.

## Snabba svar
- **Vad täcker den här handledningen?** Konvertera en Shapefile till en GeoJSON‑fil, kopiera attribut mellan lager och generera utdata med C#.
- **Vilket bibliotek krävs?** Aspose.GIS för .NET.
- **Behöver jag en licens?** En tillfällig eller full licens krävs för produktion; en gratis provversion fungerar för utvärdering.
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för en grundläggande konvertering.
- **Kan jag köra detta på .NET Core/.NET 6?** Ja – koden fungerar på alla stödda .NET‑versioner.

## Vad är konvertering av shapefile till geojson?
Att konvertera en Shapefile till GeoJSON innebär att läsa vektor‑features från det klassiska ESRI Shapefile‑formatet och skriva ut dem som ett modernt, webbvänligt GeoJSON‑dokument. Denna transformation låter dig mata GIS‑data direkt in i JavaScript‑kartbibliotek som Leaflet eller Mapbox GL, och den förenklar datautbyte mellan desktop‑GIS‑verktyg och webb‑API:er.

## Varför använda Aspose.GIS för denna konvertering?
Aspose.GIS abstraherar låg‑nivå binär parsning, stödjer över 50 in‑ och utdataformat och kan bearbeta dataset med hundratals sidor utan att ladda hela filen i minnet. Biblioteket erbjuder också ett rent, objekt‑orienterat API som fungerar över .NET Framework, .NET Core och .NET 5/6, så att du kan fokusera på affärslogik istället för format‑quirks.

## Förutsättningar
Innan vi dyker ner, se till att du har följande:

- Aspose.GIS för .NET: Se till att du har biblioteket installerat. Om inte, kan du ladda ner det från [Aspose.GIS för .NET-sidan](https://releases.aspose.com/gis/net/).
- Shapefile‑data: Ha en Shapefile redo för inmatning. Om du behöver exempeldata kan du hitta den i [Aspose.GIS‑dokumentationen](https://reference.aspose.com/gis/net/).
- .NET‑miljö: Ställ in en .NET‑miljö för att köra den medföljande koden.
- Dokumentkatalog: Definiera sökvägen till din dokumentkatalog i kodsnutten.

Nu när du har allt på plats, låt oss börja konvertera shapefile till geojson!

## Så konverterar du Shapefile till GeoJSON
Läs in käll‑Shapefile, skapa ett mål‑GeoJSON‑lager, kopiera attributschemat, filtrera poster och skriv resultatet – allt i ett fåtal koncisa steg. Det kompletta arbetsflödet får plats bekvämt i ett enda `using`‑block, vilket säkerställer att resurser frigörs automatiskt.

### Steg 1: Öppna indata Shapefile
Metoden `VectorLayer.Open` läser en Shapefile och returnerar en enumererbar samling av `Feature`‑objekt som du kan iterera över.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Steg 2: Skapa utdata GeoJSON
`VectorLayer.Create` med `Drivers.GeoJson`‑drivrutinen skapar en tom GeoJSON‑fil som är redo att ta emot features.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Steg 3: Kopiera attribut mellan lager
`CopyAttributes` kopierar attributschemat (fält namn och datatyper) från käll‑Shapefile till det nya GeoJSON‑lagret i ett enda anrop.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Steg 4: Bearbeta features
Iterera genom varje feature i Shapefile så att du kan tillämpa anpassad logik innan du skriver ut den.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Steg 5: Filtrera features efter datum
I det här exemplet hoppar vi över poster vars `dob`‑fält (födelsedatum) saknas eller är tidigare än 1 jan 1982. Justera filtret så att det matchar dina egna datakrav.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Steg 6: Skapa ett nytt Feature (C# generera GeoJSON-fil)
Ett `Feature` representerar ett enskilt rumsligt element som innehåller geometri och attributdata.  
Här bygger vi ett nytt `Feature` för GeoJSON‑lagret, kopierar geometrin och attributvärdena och lägger till det i utdata. Detta är kärnan i *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Grattis! Du har framgångsrikt **konverterat shapefile till geojson** och lärt dig hur man **kopierar attribut mellan lager** på vägen.

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| Utdatafilen är tom | `CopyAttributes` anropas efter att utdata‑lagret har stängts | Se till att `using`‑blocket för `outputLayer` förblir öppet tills alla features har lagts till. |
| Datumfiltret tar bort alla poster | Fel fältnamn eller oväntat datumformat | Verifiera attributnamnet (`dob`) och använd `GetValue<string>` om datum lagras som strängar. |
| Licensundantag | Kör utan en giltig Aspose.GIS‑licens i produktion | Applicera en tillfällig eller full licens enligt beskrivningen i Aspose‑dokumentationen. |

## Vanliga frågor
**Q: Var kan jag hitta mer dokumentation?**  
A: Besök [Aspose.GIS‑dokumentationen](https://reference.aspose.com/gis/net/) för djupgående information.

**Q: Hur kan jag få en tillfällig licens?**  
A: Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag få support?**  
A: Gå med i [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för gemenskapsstöd och diskussioner.

**Q: Finns det en gratis provversion tillgänglig?**  
A: Ja, du kan hitta den gratis provversionen [här](https://releases.aspose.com/).

**Q: Var kan jag köpa Aspose.GIS för .NET?**  
A: Du kan köpa produkten [här](https://purchase.aspose.com/buy).

## Slutsats
I den här handledningen har vi utforskat hela processen för **konvertera shapefile till geojson** med Aspose.GIS för .NET, demonstrerat hur man **kopierar attribut mellan lager** och visat ett rent sätt att *c# generate geojson file*. Experimentera med olika filter, större dataset eller ytterligare geometritransformationer för att fullt utnyttja bibliotekets möjligheter.

---

**Senast uppdaterad:** 2026-07-05  
**Testat med:** Aspose.GIS för .NET (senaste stabila releasen)  
**Författare:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Relaterade handledningar

- [Hur man konverterar GeoJSON till File GDB med Aspose.GIS för .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Hur man läser GeoJSON från Stream med Aspose.GIS för .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Hur man konverterar GeoJSON till TopoJSON med Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}