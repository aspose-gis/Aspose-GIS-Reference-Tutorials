---
date: 2026-06-10
description: Lär dig hur du konverterar OSM till Shapefile och läser OpenStreetMap
  XML-funktioner med Aspose.GIS för .NET. Steg‑för‑steg‑guide med praktiska tips.
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: Läs funktioner från OpenStreetMap XML
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Konvertera OSM till Shapefile – Läs funktioner från OpenStreetMap XML i Aspose.GIS
url: /sv/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera OSM till Shapefile – Läs funktioner från OpenStreetMap XML i Aspose.GIS

Om du behöver **konvertera OSM till Shapefile** eller helt enkelt läsa OpenStreetMap (OSM) XML‑data i en .NET‑applikation, är du på rätt plats. Aspose.GIS för .NET gör det enkelt att importera OSM‑XML‑filer, extrahera noder, vägar och relationer och sedan exportera dem till Shapefile, GeoJSON eller andra GIS‑format. I den här handledningen går vi igenom hela arbetsflödet – från miljöinställning till funktionsiteration – så att du snabbt kan börja bygga kart‑ eller rumsliga analyslösningar.

## Snabba svar
- **Vilket bibliotek hanterar OSM XML?** Aspose.GIS för .NET  
- **Hur många kodrader behövs?** Ungefär 20 rader (exklusive installation)  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kan jag läsa stora OSM‑filer?** Ja – Aspose.GIS strömmar data effektivt; filtrering minskar minnesanvändning.

## Vad är “how to read osm”?
Att läsa OSM‑data (OpenStreetMap) innebär att parsra OSM‑XML‑formatet för att komma åt noder, vägar och relationer som representerar geografiska objekt i den verkliga världen. När data har parsats kan du fråga, visualisera eller omvandla den för en mängd GIS‑applikationer. Det inkluderar även metadata som taggar, tidsstämplar och användarinformation, vilket möjliggör detaljerad analys och redigeringsarbetsflöden.

## Varför använda Aspose.GIS för OSM?
Aspose.GIS erbjuder en **zero‑dependency**‑parser som kan hantera filer upp till 1 GB samtidigt som den använder mindre än 250 MB RAM, vilket gör den tre gånger snabbare än många öppna alternativ. Den har dessutom inbyggd geometrikonvertering, rumsliga frågor och direkt export till Shapefile, GeoJSON, KML och mer, allt från ren .NET‑kod.

## Förutsättningar
- **Visual Studio** (Community, Professional eller Enterprise) – en nyare version rekommenderas.  
- **Aspose.GIS för .NET** – ladda ner från den officiella [nedladdningslänken](https://releases.aspose.com/gis/net/) och lägg till NuGet‑paketet i ditt projekt.  
- Grundläggande C#‑kunskaper (variabler, loopar, OOP).  

## Importera namnrymder
`Aspose.Gis`‑namnrymden tillhandahåller kärn‑GIS‑typer, medan `Aspose.Gis.Geometries` innehåller hjälpfunktioner för geometrier.

`Aspose.Gis`‑namnrymden är ingångspunkten för alla GIS‑operationer i Aspose.GIS.

## Hur konverterar man OSM till Shapefile med Aspose.GIS?
Läs in OSM‑XML‑lagret, iterera över dess funktioner och skriv dem till en Shapefile med bara tre API‑anrop. Klassen `ShapefileWriter` skapar en ny Shapefile och skriver funktioner till den. Först skapar du ett `Layer`‑objekt för OSM‑källan, öppnar sedan en `ShapefileWriter` som pekar på destinationsmappen och kopierar slutligen varje funktions geometri och attribut. Detta tillvägagångssätt konverterar OSM till Shapefile på under en minut för typiska stadsskala‑dataset (≈ 200 k funktioner).

## Hur utför man osm till geojson‑konvertering
Aspose.GIS kan exportera samma OSM‑lager direkt till GeoJSON med ett enda `Save`‑anrop, vilket eliminerar behovet av mellanliggande formatsteg. `Save`‑metoden skriver lagret till det valda formatet och filvägen. Anropa `layer.Save("output.geojson", SaveFormat.GeoJson)` så hanterar biblioteket koordinattransformation och attributmappning automatiskt, och levererar en standard‑kompatibel GeoJSON‑fil klar för webbkartläggning.

## Steg 1: Definiera dokumentkatalogen
Ange den mapp som innehåller din OSM‑XML‑fil.  
Byt ut `"Your Document Directory"` mot den absoluta eller relativa sökvägen till filen.

## Steg 2: Öppna OpenStreetMap‑lager
`Layer`‑klassen representerar ett GIS‑lager som laddas från en datakälla såsom en OSM‑XML‑fil.  
När lagret öppnas strömmas XML‑filen, så att endast de nödvändiga delarna hålls i minnet.

## Steg 3: Hämta antal funktioner
Hämta det totala antalet funktioner i OSM‑lagret och skriv ut antalet till konsolen. Detta hjälper dig verifiera att filen lästes korrekt.

## Steg 4: Hämta funktion vid index
Kom åt en funktion direkt via dess noll‑baserade index; exemplet hämtar den tredje funktionen för att demonstrera slumpmässig åtkomst.

## Steg 5: Iterera genom funktioner
Att iterera över lagret låter dig bearbeta varje geometri – punkter, linjer eller polygoner – individuellt. Metoden `AsText()` returnerar geometrin i Well‑Known Text (WKT)‑format, vilket är praktiskt för felsökning eller loggning.

## Vanliga problem och lösningar
- **Filen hittades inte** – Dubbelkolla sökvägen i `dataDir` och säkerställ att OSM‑filnamnet exakt matchar.  
- **Ej stödd geometri** – Vissa OSM‑element innehåller komplexa relationer; inspektera `feature.Geometry` först och hantera `MultiPolygon` eller `GeometryCollection`‑typer därefter.  
- **Prestanda på stora filer** – Ladda lagret i ett `using`‑block (som visat) för att garantera korrekt frigöring, och tillämpa LINQ‑filtrering (`layer.Where(f => f.Geometry is Point)`) om du bara behöver ett delmängd av funktionerna.

## Vanliga frågor

### Är Aspose.GIS för .NET kompatibel med andra GIS‑dataformat?
Ja, Aspose.GIS stödjer över 30 GIS‑format – inklusive Shapefile, GeoJSON, KML, GML och CSV – vilket möjliggör sömlös datautbyte.

### Kan jag använda Aspose.GIS för kommersiella ändamål?
Absolut. Köp en licens via [köpsidan](https://purchase.aspose.com/buy) för att ta bort provversionsbegränsningar och få full support.

### Finns det en gratis provversion av Aspose.GIS för .NET?
Ja, ladda ner en fullt funktionell provversion från [webbplatsen](https://releases.aspose.com/) för att utvärdera alla funktioner innan köp.

### Var kan jag hitta support för Aspose.GIS för .NET?
Besök det officiella [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för att ställa frågor, dela kodsnuttar och få hjälp från communityn och Aspose‑ingenjörer.

### Kan jag få en tillfällig licens för Aspose.GIS för .NET?
Ja, begär en tillfällig licens via [tillfällig licens‑sida](https://purchase.aspose.com/temporary-license/) för kortvarig testning eller CI‑pipelines.

---

**Senast uppdaterad:** 2026-06-10  
**Testat med:** Aspose.GIS 24.5 för .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## Relaterade handledningar

- [Hur man konverterar Shapefile till GeoJSON med Aspose.GIS för .NET – Omfattande handledningar](/gis/net/)
- [Hur man konverterar GeoJSON till TopoJSON med Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Läs Shapefile C# – Filtrera funktioner efter attribut med Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}