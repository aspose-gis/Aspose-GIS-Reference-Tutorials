---
date: 2026-01-05
description: Lär dig hur du läser shapefiler i C# med Aspose.GIS för .NET, hämtar
  alla funktionsattributvärden och exporterar attributen effektivt.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Läs shapefile C# – Hämta alla attributvärden för objekt
url: /sv/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta alla attributvärden för funktioner

## Introduktion
Välkommen till världen av geospatial utveckling med Aspose.GIS för .NET! I den här handledningen kommer du att lära dig **hur man läser shapefile C#** och hämta varje attributvärde från dess funktioner. Oavsett om du bygger en kartapplikation eller bearbetar rumsliga data i batch, är det viktigt att behärska extrahering av attribut. Låt oss dyka ner och se koden i aktion.

## Snabba svar
- **Vad gör den här koden?** Den öppnar en Shapefile och läser alla, flera eller dumpade attributvärden från varje funktion.
- **Vilket bibliotek krävs?** Aspose.GIS för .NET (kompatibel med .NET Framework och .NET Core).
- **Behöver jag en licens?** En tillfällig licens fungerar för testning; en full licens krävs för produktion.
- **Kan jag läsa andra format?** Ja – samma API stödjer GeoJSON, KML och många fler.
- **Hur dupas attribut?** Använd `feature.GetValuesDump()` för att få en flexibel objektarray.

## Vad är "läs shapefile C#"?
Att läsa en Shapefile i C# innebär att öppna .shp‑filen med ett GIS‑bibliotek, iterera över dess vektorfunktioner och komma åt attributdata som lagras i den medföljande .dbf‑filen. Aspose.GIS abstraherar den låga filhanteringen så att du kan fokusera på de attributvärden du behöver.

## Varför använda Aspose.GIS för att läsa attribut?
- **Enkelt API** – intuitiva metoder som `GetValues` och `GetValuesDump`.
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS med .NET Core.
- **Rik formatstöd** – hantera Shapefile, GeoJSON, GML och mer utan extra plugins.
- **Prestandaoptimerad** – snabb iteration över stora dataset.

## Förutsättningar
Innan vi påbörjar denna spännande resa, se till att du har följande förutsättningar:
- Aspose.GIS för .NET: Ladda ner och installera biblioteket från [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Utvecklingsmiljö: Ställ i en .NET-utvecklingsmiljö, till exempel Visual Studio.
- Shapefile: Ha ett exempel-Shapefile (t.ex. "InputShapeFile.shp") gör om i din dokumentkatalog.

## Importera namnrymder
I din C#‑kod, börja med att importera de nödvändiga namnutrymmena för att utnyttja Aspose.GIS‑funktionaliteten:
```csharp
using System;
using Aspose.Gis;
```

## Steg 1: Ställ in dokumentkatalogen
```csharp
string dataDir = "Your Document Directory";
```
Ersätt "Your Document Directory" med den faktiska sökvägen där din Shapefile finns.

## Steg 2: Öppna vektorlagret
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Detta steg innebär att öppna Shapefile med Aspose.GIS, ange filsökvägen och formatet (i detta fall Shapefile).

## Steg 3: Hämta alla funktionsattributvärden
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Kodsnutten visar **hur man läser attribut** för varje funktion genom att ladda dem i en fast‑storleksarray.

## Steg 4: Hämta flera funktionsattributvärden
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Här demonstrerar vi **hur man läser specifika attributvärden** när du bara behöver ett delmängd av fält.

## Steg 5: Hämta attributvärden som objektdump
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Det sista steget visar **hur man dumpar attribut** med `GetValuesDump()`, vilket returnerar en flexibel samling som du kan inspektera eller serialisera.

## Vanliga problem och lösningar
- **Arraystorleksfel** – Se till att den array du skickar till `GetValues` matchar antalet attribut du förväntar dig; annars får du `null`-poster.
- **Fil ej hittad** – Verifiera att `dataDir` pekar på rätt mapp och att Shapefile‑namnet är stavat exakt.
- **Licensundantag** – Om du får en licensfel, applicera en tillfällig eller full licens innan du anropar några API‑metoder.

## Vanliga frågor
### Är Aspose.GIS kompatibel med .NET Core?
Ja, Aspose.GIS är fullt kompatibel med .NET Core, vilket gör att du kan bygga plattformsoberoende applikationer.

### Kan jag arbeta med olika GIS-filformat med Aspose.GIS?
Absolut! Aspose.GIS stödjer olika format, inklusive Shapefile, GeoJSON och fler.

### Finns det ett community‑forum för support av Aspose.GIS?
Ja, du kan hitta hjälp och engagera dig i Aspose.GIS‑gemenskapen på [supportforum](https://forum.aspose.com/c/gis/33).

### Hur kan jag skaffa en tillfällig licens för Aspose.GIS?
Du kan skaffa en tillfällig licens för teständamål [här](https://purchase.aspose.com/temporary-license/).

### Var kan jag hitta detaljerad dokumentation för Aspose.GIS?
Den omfattande dokumentationen finns [här](https://reference.aspose.com/gis/net/).

### Hur hämtar jag bara “Name”-attributet från varje funktion?
Använd `GetValues` med en arraystorlek på ett element och skicka indexet för “Name”-fältet, eller anropa `feature["Name"]` direkt.

### Vad är skillnaden mellan `GetValues` och `GetValuesDump`?
`GetValues` fyller en förallokerad array med råa värden, medan `GetValuesDump` returnerar en objektarray som kan enumereras utan att känna till schemat i förväg.

---

**Senast uppdaterad:** 2026-01-05
**Testad med:** Aspose.GIS för .NET (senaste utgåvan)
**Författare:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
