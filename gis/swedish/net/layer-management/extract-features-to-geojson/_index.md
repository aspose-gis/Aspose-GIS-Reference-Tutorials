---
date: 2026-01-13
description: Lär dig hur du konverterar shapefile till geojson med Aspose.GIS för
  .NET. Guiden täcker också hur du kopierar attribut mellan lager och genererar en
  geojson‑fil i C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Hur man konverterar shapefile till GeoJSON med Aspose.GIS för .NET
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
- **Vad täcker den här handledningen?** Konvertera en Shapefile till en GeoJSON‑fil, kopiera attribut mellan lager och generera output med C#.
- **Vilket bibliotek krävs?** Aspose.GIS för .NET.
- **Behöver jag en licens?** En tillfällig eller full licens krävs för produktion; en gratis provversion fungerar för utvärdering.
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för en grundläggande konvertering.
- **Kan jag köra detta på .NET Core/.NET 6?** Ja – koden fungerar på alla stödjade .NET‑versioner.

## Förutsättningar
Innan vi dyker ner, se till att du har följande:

- Aspose.GIS för .NET: Se till att du har biblioteket installerat. Om inte, kan du ladda ner det från [Aspose.GIS för .NET-sidan](https://releases.aspose.com/gis/net/).
- Shapefile-data: Ha en Shapefile redo för inmatning. Om du behöver exempeldata kan du hitta den i [Aspose.GIS-dokumentationen](https://reference.aspose.com/gis/net/).
- .NET-miljö: Ställ in en .NET-miljö för att köra den medföljande koden.
- Dokumentkatalog: Definiera sökvägen till din dokumentkatalog i kodsnutten.

Nu när du har allt på plats, låt oss börja konvertera shapefile till geojson!

## Vad betyder “convert shapefile to geojson”?
Att konvertera en Shapefile till GeoJSON innebär att läsa vektor‑funktioner från det klassiska ESRI Shapefile‑formatet och skriva ut dem som ett modernt, webbvänligt GeoJSON‑dokument. GeoJSON används i stor utsträckning i JavaScript‑kartbibliotek (Leaflet, Mapbox GL) och API:er, vilket gör konverteringen till en vanlig uppgift inom GIS‑utveckling.

## Varför använda Aspose.GIS för denna konvertering?
Aspose.GIS abstraherar de lågnivå‑detaljer som rör filformat, låter dig kopiera attributtabeller utan ansträngning och erbjuder ett rent, objekt‑orienterat API som fungerar över .NET Framework, .NET Core och .NET 5/6. Detta betyder att du kan fokusera på affärslogik istället för att parsra binära filer.

## Importera namnrymder
Först, inkludera de nödvändiga namnrymderna i din kod:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Dessa namnrymder är nödvändiga för att arbeta med Aspose.GIS‑funktionalitet.

## Hur man konverterar Shapefile till GeoJSON
Nedan följer hela arbetsflödet uppdelat i tydliga steg. Varje steg innehåller en kort förklaring följt av exakt kodblock som du behöver kopiera in i ditt projekt.

### Steg 1: Öppna inmatnings‑Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Öppna inmatnings‑Shapefile med metoden `VectorLayer.Open`. Detta ger dig en enumererbar samling av `Feature`‑objekt.

### Steg 2: Skapa utdata‑GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Skapa utdatafilen med metoden `VectorLayer.Create` och ange drivrutinen `Drivers.GeoJson`.

### Steg 3: Kopiera attribut mellan lager
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Detta enkla rad kopierar attributschemat (fältnamn, typer) från käll‑Shapefile till det nya GeoJSON‑lagret – exakt vad det sekundära nyckelordet *copy attributes between layers* beskriver.

### Steg 4: Bearbeta funktioner
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Iterera genom varje funktion i Shapefile så att du kan applicera egen logik innan du skriver ut den.

### Steg 5: Filtrera funktioner efter datum
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
I detta exempel hoppar vi över poster vars `dob` (date of birth)‑fält saknas eller är tidigare än 1 jan 1982. Anpassa gärna filtret efter dina egna datakrav.

### Steg 6: Skapa en ny funktion (C# generera GeoJSON‑fil)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Här bygger vi en ny `Feature` för GeoJSON‑lagret, kopierar geometri och attributvärden och lägger till den i utdata. Detta är kärnan i *c# generate geojson file*.

Grattis! Du har framgångsrikt **konverterat shapefile till geojson** och lärt dig hur man kopierar attribut mellan lager på vägen.

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|---------|-------------------|--------|
| Utdatafilen är tom | `CopyAttributes` anropad efter att utdata‑lagret har stängts | Se till att `using`‑blocket för `outputLayer` förblir öppet tills alla funktioner har lagts till. |
| Datumfilter tar bort alla poster | Fel fältnamn eller oväntat datumformat | Verifiera attributnamnet (`dob`) och använd `GetValue<string>` om datum lagras som strängar. |
| Licensundantag | Kör utan en giltig Aspose.GIS‑licens i produktion | Applicera en tillfällig eller full licens enligt beskrivningen i Aspose‑dokumentationen. |

## Vanliga frågor
**Q: Var kan jag hitta mer dokumentation?**  
A: Besök [Aspose.GIS-dokumentationen](https://reference.aspose.com/gis/net/) för djupgående information.

**Q: Hur kan jag få en tillfällig licens?**  
A: Du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag få support?**  
A: Gå med i [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för gemenskapsstöd och diskussioner.

**Q: Finns det en gratis provversion?**  
A: Ja, du kan hitta den gratis provversionen [här](https://releases.aspose.com/).

**Q: Var kan jag köpa Aspose.GIS för .NET?**  
A: Du kan köpa produkten [här](https://purchase.aspose.com/buy).

## Slutsats
I den här handledningen har vi gått igenom hela processen för **convert shapefile to geojson** med Aspose.GIS för .NET, demonstrerat hur man kopierar attribut mellan lager och visat ett rent sätt att *c# generate geojson file*. Experimentera med olika filter, större dataset eller ytterligare geometritransformationer för att fullt utnyttja bibliotekets möjligheter.

---

**Senast uppdaterad:** 2026-01-13  
**Testad med:** Aspose.GIS för .NET (senaste stabila releasen)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}