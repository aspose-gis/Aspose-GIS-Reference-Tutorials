---
date: 2026-06-05
description: Lär dig hur du skapar linjesträng i ASP.NET och utför en nätverksruttkontroll
  genom att upptäcka berörda geometrier med Aspose.GIS för .NET, ett kraftfullt bibliotek
  för hantering och analys av rumsliga data.
keywords:
- create line string asp.net
- touching geometries
- Aspose.GIS spatial analysis
linktitle: Hur man kontrollerar berörda geometrier
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  headline: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  type: TechArticle
- description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  name: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  steps:
  - name: '**Visual Studio** (any recent version).'
    text: '**Visual Studio** (any recent version).'
  - name: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
  - name: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
    text: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
  - name: Install Visual Studio if you haven’t already.
    text: Install Visual Studio if you haven’t already.
  - name: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
    text: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
  - name: Apply your license file in code (or use a temporary license for testing).
    text: Apply your license file in code (or use a temporary license for testing).
  type: HowTo
- questions:
  - answer: Yes. It supports .NET Framework, .NET Core, .NET 5+, and .NET 6+, giving
      you flexibility across desktop, web, and cloud projects.
    question: Is Aspose.GIS compatible with all .NET frameworks?
  - answer: Absolutely. You can obtain a free trial from the Aspose website [here](https://purchase.aspose.com/temporary-license/)
      to explore all features, including the `Touches` operation.
    question: Can I try Aspose.GIS before purchasing a license?
  - answer: Visit the official [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to ask questions, share examples, and get help from both the community and Aspose
      engineers.
    question: Where can I find support for Aspose.GIS‑related queries?
  - answer: Aspose releases regular updates that add new format support, performance
      improvements, and bug fixes, ensuring compatibility with the latest .NET releases.
    question: How often are updates released for Aspose.GIS?
  - answer: By confirming that road segments only meet at shared endpoints (touch),
      you can validate that a routing network is correctly connected without unintended
      overlaps.
    question: How does the `Touches` method help with a network routing check?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Skapa linjesträng i ASP.NET – Kontroll av berörda geometrier med Aspose.GIS
url: /sv/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa LineString ASP.NET – Kontroll av berörande geometrier med Aspose.GIS

## Introduktion
När du behöver **utföra en nätverksruttkontroll** mellan två rumsliga objekt är första steget att **skapa line string ASP.NET**-objekt som modellerar dina vägssegment. Aspose.GIS för .NET tillhandahåller ett rent, typ‑säkert API som gör denna operation trivial, så att du kan fokusera på affärslogik snarare än låg‑nivå geometri‑matematik. I den här handledningen går vi igenom hur man skapar line strings, lägger till en punkt och använder `Touches`‑metoden för att verifiera att geometrier endast möts vid sina gränser – ett nyckelkrav för ruttvalidering, kartöverlagringsverifiering och närhetsfrågor.

## Snabba svar
- **Vad betyder “touching”?** Två geometrier delar minst en gränspunkt men deras innandömen korsar inte varandra.  
- **Vilken metod kontrollerar detta?** `Geometry.Touches(otherGeometry)`.  
- **Behöver jag en licens för den här funktionen?** En provversion fungerar för utveckling; en permanent licens krävs för produktion.  
- **Stödda .NET‑versioner?** .NET Framework, .NET Core, .NET 5/6/7 – alla täcks av Aspose.GIS.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter för ett grundexempel.  

## Vad är “Touching” i rumslig analys?
**Touching** beskriver ett rumsligt förhållande där två geometrier möts vid sina kanter utan att deras innandömen överlappar. Detta skiljer sig från *intersects*, som också inkluderar innandömsöverlapp, och är avgörande när du behöver bekräfta att vägssegment endast kopplas ihop vid korsningar.

`Touches`‑metoden returnerar **true** när geometrierna delar en gränspunkt men inga innandöms­punkter, vilket gör den idealisk för att validera nätverksanslutning utan oavsiktliga korsningar.

## Varför använda Aspose.GIS för rumslig analys i .NET?
Aspose.GIS stöder **30+ in‑ och utdataformat** (inklusive Shapefile, GeoJSON, KML och GML) och kan bearbeta filer upp till **2 GB** utan att ladda hela dokumentet i minnet, tack vare sin streaming‑arkitektur. Biblioteket erbjuder högpresterande geometriska operationer—`Touches`, `Intersects`, `Contains`, `Distance`—alla helt hanterade i .NET, så att du kan bädda in rumslig analys direkt i webbtjänster, skrivbordsprogram eller Azure Functions utan externa GIS‑installationer.

## Förutsättningar
1. **Visual Studio** (någon nyare version).  
2. **Aspose.GIS for .NET** – ladda ner det senaste paketet från den [officiella nedladdningssidan](https://releases.aspose.com/gis/net/).  
3. **En giltig licens** (eller en gratis provversion) – skaffa den från [här](https://purchase.aspose.com/temporary-license/) eller se alla releaser på [här](https://releases.aspose.com/).  

### Konfigurera din miljö
1. Installera Visual Studio om du inte redan har gjort det.  
2. Lägg till Aspose.GIS NuGet‑paketet i ditt projekt (t.ex. `Install-Package Aspose.GIS`).  
3. Använd din licensfil i koden (eller en tillfällig licens för testning).

## Importera namnrymder
För att börja använda API:et, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hur kontrollerar man berörande geometrier i Aspose.GIS?
`Touches` är en metod som returnerar true när två geometrier endast delar en gränspunkt och inga innandöms­punkter. Läs in eller skapa geometrierna, och anropa sedan `Touches` för att utvärdera förhållandet. Metoden returnerar en Boolean som indikerar om de två formerna endast delar en gränspunkt. Denna enkla kontroll är tillräcklig för de flesta scenarier för ruttvalidering och kan köras i en tight loop för stora nätverk.

## Steg 1: Skapa LineStrings (och en punkt)
`LineString` är en geometrityp som representerar en serie av sammankopplade linjesegment definierade av ordnade punkter.  

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*Förklaring*:  
- `geometry1` och `geometry2` delar slutpunkten `(2, 2)`.  
- `geometry3` är en punkt som ligger exakt på den delade slutpunkten.  
- `geometry4` korsar samma område men **delar inte** en gräns med `geometry1`.

## Steg 2: Kontrollera berörande relationer
Nu anropar vi `Touches`‑metoden för att se vilka par som anses beröras.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Resultat*:  
- De första tre kontrollerna returnerar **True** eftersom geometrierna möts vid en enda punkt utan innandöms­överlapp.  
- Den sista kontrollen returnerar **False** eftersom de två linjesträngarna korsar varandra över ett linjesegment, inte bara vid en gränspunkt.

## Vanliga problem & tips
- **Precision problem** – GIS‑beräkningar är flyttalsbaserade. Om du får oväntade `False`‑resultat, överväg att normalisera koordinater eller använda en tolerans med `Geometry.EqualsExact(other, tolerance)`.  
- **Blandade geometrityper** – `Touches` fungerar över punkter, linjer och polygoner, men semantiken skiljer sig; verifiera alltid den förväntade relationen för din datamodell.  
- **Prestanda** – För stora dataset, batcha kontrollerna eller använd rumsliga index (t.ex. R‑tree) som tillhandahålls av Aspose.GIS för att undvika O(N²)-jämförelser.

## Vanliga frågor

**Q: Är Aspose.GIS kompatibel med alla .NET‑ramverk?**  
A: Ja. Den stöder .NET Framework, .NET Core, .NET 5+ och .NET 6+, vilket ger dig flexibilitet över skrivbords-, webb- och molnprojekt.

**Q: Kan jag prova Aspose.GIS innan jag köper en licens?**  
A: Absolut. Du kan skaffa en gratis provversion från Aspose‑webbplatsen [här](https://purchase.aspose.com/temporary-license/) för att utforska alla funktioner, inklusive `Touches`‑operationen.

**Q: Var kan jag hitta support för Aspose.GIS‑relaterade frågor?**  
A: Besök det officiella [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för att ställa frågor, dela exempel och få hjälp från både communityn och Aspose‑ingenjörer.

**Q: Hur ofta släpps uppdateringar för Aspose.GIS?**  
A: Aspose släpper regelbundna uppdateringar som lägger till stöd för nya format, prestandaförbättringar och buggfixar, vilket säkerställer kompatibilitet med de senaste .NET‑releaserna.

**Q: Hur hjälper `Touches`‑metoden med en nätverksruttkontroll?**  
A: Genom att bekräfta att vägssegment endast möts vid delade slutpunkter (touch) kan du validera att ett rutt‑nätverk är korrekt anslutet utan oavsiktliga överlappningar.

---

**Senast uppdaterad:** 2026-06-05  
**Testad med:** Aspose.GIS for .NET 24.11 (senaste vid skrivtillfället)  
**Författare:** Aspose

## Relaterade handledningar

- [Hantera geospatial data med Aspose.GIS för .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Skapa polygongeometri C# och kontrollera korsning med Aspose.GIS för .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Hur man beräknar längden på en geometri i .NET med Aspose.GIS](/gis/net/geometry-analysis/get-geometry-length/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}