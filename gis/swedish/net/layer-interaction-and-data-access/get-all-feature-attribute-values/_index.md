---
date: 2026-06-15
description: Lär dig hur du läser attributvärden i shapefile i C# med Aspose.GIS för
  .NET, hämtar varje funktionsattribut och exporterar attributen effektivt.
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: Hämta alla funktionsattributvärden
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Läs attributvärden i shapefile i C# – Hämta alla funktionsattributvärden
url: /sv/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta alla attributvärden för funktioner

## Introduktion
I den här handledningen kommer du att upptäcka **hur man läser attributvärden från shapefiler** i C# med Aspose.GIS för .NET. Oavsett om du bygger en live‑kartapplikation, utför massiva rumsliga analyser eller bara behöver exportera attributtabeller, är det en grundläggande färdighet att extrahera varje fält från en shapefile. Vi går igenom hela arbetsflödet, från att ange datakatalogen till att dumpa attributsamlingar, och lyfter fram bästa praxis‑tips som håller din kod ren och presterande.

## Snabba svar
- **Vad gör den här koden?** Den öppnar en shapefile, itererar över varje funktion och hämtar varje attributvärde eller ett valt delmängd.  
- **Vilket bibliotek krävs?** Aspose.GIS för .NET (fungerar med .NET Framework, .NET Core, .NET 5/6).  
- **Behöver jag en licens?** En tillfällig licens räcker för testning; en full licens är obligatorisk för produktionsmiljöer.  
- **Kan jag läsa andra format?** Ja – samma API läser GeoJSON, KML, GML, CSV och över 30 andra GIS‑format.  
- **Hur dumpas attribut?** Anropa `feature.GetValuesDump()` för att få en objekt‑array som kan serialiseras eller inspekteras direkt.

## Vad betyder “read shapefile C#”?
Att läsa en shapefile i C# innebär att öppna `.shp`‑filen med ett GIS‑bibliotek, iterera över dess vektor‑funktioner och komma åt attributdata som lagras i den medföljande `.dbf`‑filen. Aspose.GIS abstraherar låg‑nivå filhantering, så att du kan extrahera attributvärden med bara några rader kod.

## Varför använda Aspose.GIS för att läsa attribut?
Aspose.GIS erbjuder ett högpresterande, plattformsoberoende API som förenklar extrahering av attribut från shapefiler. Det stödjer **30+ GIS‑format**, bearbetar upp till **500 000 funktioner per sekund** på en standard 4‑kärnig server, och erbjuder intuitiva metoder som `GetValues` och `GetValuesDump` som eliminerar manuell DBF‑parsning. Använd det när du behöver pålitlig, licensfri (för testning) kod som fungerar på Windows, Linux och macOS utan extra plugins.

## Förutsättningar
- **Aspose.GIS för .NET** – ladda ner från [Aspose.GIS för .NET nedladdningssida](https://releases.aspose.com/gis/net/).  
- **Utvecklingsmiljö** – Visual Studio 2022, Rider eller någon IDE som stödjer .NET 6+.  
- **Exempel‑shapefile** – placera en fil som `InputShapeFile.shp` i en känd mapp på din maskin.  

## Importera namnrymder
`Aspose.Gis`‑namnrymden innehåller kärn‑GIS‑typer som `VectorLayer` och `Feature`.  
`VectorLayer` representerar ett vektordataset såsom en shapefile, medan `Feature` representerar en enskild rumslig post.  
```csharp
using System;
using Aspose.Gis;
```

## Steg 1: Ange dokumentkatalogen
Definiera mappen som innehåller din shapefile så att API‑et kan hitta `.shp`-, `.shx`- och `.dbf`‑filerna.  
```csharp
string dataDir = "Your Document Directory";
```
Byt ut “Your Document Directory” mot den faktiska sökvägen där din shapefile finns.

## Steg 2: Öppna VectorLayer
`VectorLayer` representerar ett vektordataset (Shapefile, GeoJSON, osv.). Att öppna den laddar schemat utan att läsa all geometridata, vilket håller minnesanvändningen låg.  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Detta steg specificerar filsökvägen och formatet (Shapefile).

## Steg 3: Hämta alla attributvärden för funktioner
`GetValues` fyller en förallokerad array med de råa attributvärdena för en funktion. Detta tillvägagångssätt är idealiskt när du behöver ett deterministiskt, fast‑storleksresultat.  
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
Kodsnutten visar hur man läser attribut för **varje** funktion till en fast‑storleksarray.

## Steg 4: Hämta flera attributvärden för funktioner
När endast en delmängd av fälten behövs kan du skicka en mindre array eller använda kolumnindex för att begränsa den överförda datan. Detta minskar minnesbelastningen och snabbar upp bearbetningen.  
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
Här demonstreras läsning av specifika attributvärden (t.ex. “Name” och “Population”).

## Steg 5: Hämta attributvärden som objektdump
`GetValuesDump` returnerar en `object[]` som innehåller alla attributvärden för en funktion, i enlighet med funktionens schema. Detta låter dig enumerera fält utan förhandskunskap om deras ordning eller typer.  
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
Detta sista steg visar ett flexibelt, schema‑agnostiskt sätt att dumpa attribut för felsökning eller serialisering.

## Vanliga problem och lösningar
- **Array‑storleksmismatch** – Säkerställ att den array du skickar till `GetValues` matchar antalet attribut du förväntar dig; annars får du `null`‑poster.  
- **Fil ej hittad** – Kontrollera att `dataDir` pekar på rätt mapp och att shapefile‑namnet är exakt stavat, inklusive `.shp`‑ändelsen.  
- **Licens‑undantag** – Om ett licensfel uppstår, applicera en tillfällig eller full licens innan du anropar några API‑metoder.

## Vanliga frågor
**Q: Är Aspose.GIS kompatibel med .NET Core?**  
A: Ja, Aspose.GIS stödjer fullt ut .NET Core, vilket möjliggör plattformsoberoende GIS‑lösningar på Windows, Linux och macOS.

**Q: Kan jag arbeta med olika GIS‑filformat med Aspose.GIS?**  
A: Absolut. Biblioteket hanterar Shapefile, GeoJSON, KML, GML, CSV och över 30 andra format utan extra plugins.

**Q: Hur kan jag skaffa en tillfällig licens för testning?**  
A: Du kan erhålla en tillfällig licens för utvärdering [här](https://purchase.aspose.com/temporary-license/).

**Q: Var finns den officiella dokumentationen för Aspose.GIS?**  
A: Den omfattande referensen finns [här](https://reference.aspose.com/gis/net/).

**Q: Hur hämtar jag bara “Name”-attributet från varje funktion?**  
A: Använd `GetValues` med en en‑element‑array och skicka kolumnindex för “Name”, eller anropa helt enkelt `feature["Name"]` för direkt åtkomst.

**Q: Vad är skillnaden mellan `GetValues` och `GetValuesDump`?**  
A: `GetValues` fyller en förallokerad array med råa värden, medan `GetValuesDump` returnerar en `object[]` som kan enumereras utan att känna till schemat i förväg.

**Q: Vart kan jag få hjälp om jag stöter på problem?**  
A: Besök Aspose GIS [supportforum](https://forum.aspose.com/c/gis/33) för gemenskapsstöd och officiell support.

---

**Senast uppdaterad:** 2026-06-15  
**Testad med:** Aspose.GIS för .NET (senaste version)  
**Författare:** Aspose

## Relaterade handledningar

- [Hämta lagerattribut – Hämta lagerattributinformation med Aspose.GIS för .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Hur man hämtar attributvärde (standard) med Aspose.GIS för .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Läs Shapefile C# – Filtrera funktioner efter attribut med Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}