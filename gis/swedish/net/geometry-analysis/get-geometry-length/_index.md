---
date: 2026-08-13
description: Lär dig hur du beräknar geometrilängd i .NET med Aspose.GIS för effektiv
  hantering av rumsliga data. Inkluderar exempel för att hämta linjelängd i C# och
  beräkna linjelängd i C#.
keywords:
- calculate geometry length .net
- Aspose.GIS length calculation
- C# geometry length
lastmod: 2026-08-13
linktitle: Hämta geometrilängd
og_description: Beräkna geometrilängd i .NET med Aspose.GIS. Hämta linjelängd i C#
  och polygon perimeter-exempel i en kortfattad, högpresterande guide för .NET‑utvecklare.
og_image_alt: Developer guide showing how to calculate geometry length in .NET with
  Aspose.GIS
og_title: Beräkna geometrilängd i .NET med Aspose.GIS – Snabba rumsliga mätningar
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  headline: How to Calculate Geometry Length .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  name: How to Calculate Geometry Length .NET with Aspose.GIS
  steps:
  - name: Create geometry objects
    text: To begin with, create the geometry objects representing the shapes for which
      you want to calculate the length. This can include lines, polygons, or any other
      geometrical shapes.
  - name: Calculate line length in C#
    text: Once you have created the line geometry, you can calculate its length using
      the `GetLength()` method. This demonstrates **calculate line length c#** in
      a single line of code.
  - name: Create polygon geometry
    text: Similarly, you can create polygon geometry objects using the `Polygon` and
      `LinearRing` classes.
  - name: Get length of a polygon
    text: For polygons, the `GetLength()` method returns the perimeter, which is effectively
      the **how to get length** of the shape.
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET is compatible with .NET Framework 4.6.1 or later versions,
      as well as .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all .NET frameworks?
  - answer: Yes, you can avail of a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: You can find support and assistance from the Aspose.GIS community forum
      [here](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: You can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Yes, Aspose.GIS for .NET provides various formatting options to customize
      the output format as per your requirements.
    question: Can I customize the output format for geometry length calculations?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry length
- Aspose.GIS
- C# GIS
- spatial calculations
- line length
title: Hur man beräknar geometrilängd i .NET med Aspose.GIS
url: /sv/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man beräknar geometrilängd .NET med Aspose.GIS

## Introduktion
Om du letar efter ett tydligt, praktiskt sätt att **beräkna geometrilängd .NET**, har du kommit till rätt ställe. Aspose.GIS för .NET ger dig ett rikt urval av GIS‑inriktade API:er som gör rumsliga beräkningar—som att mäta linjelängd eller polygonperimeter—enkla och presterande. I den här handledningen går vi igenom hela processen, från att sätta upp miljön till att skriva C#‑koden som returnerar korrekta längdvärden.

## Snabba svar
- **Vad returnerar “GetLength()”?** För linjer returnerar den linjelängden; för polygoner returnerar den omkretsen.  
- **Vilket namnrymd krävs?** `Aspose.Gis.Geometries`.  
- **Kan jag använda detta med .NET 6?** Ja, Aspose.GIS stöder .NET 5, .NET 6 och senare.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.  
- **Är beräkningen enhetsmedveten?** Längden returneras i koordinatsystemets enheter (t.ex. meter för projicerade CRS).

## Vad är geometrilängd?
Geometry.GetLength() beräknar det totala linjära avståndet för ett geometriskt objekt baserat på dess koordinatvärden. För en LineString summerar den avstånden mellan på varandra följande hörn, och returnerar linjens längd. När den tillämpas på en Polygon lägger den till längderna på alla kanter, vilket i praktiken ger figurens omkrets.

## Varför använda Aspose.GIS för längdberäkningar?
Aspose.GIS erbjuder ett helt hanterat .NET‑bibliotek som utför rumsliga beräkningar utan att kräva inhemska binärer, vilket gör distribution enkel på Windows, Linux och macOS. Det stöder över femtio koordinatreferenssystem, levererar högprecisions‑dubbelprecisionresultat även för linjesträngar på flera hundra kilometer, och integreras sömlöst med .NET 5/6/7‑projekt, vilket säkerställer konsekvent prestanda och noggrannhet.

## Förutsättningar
Innan vi börjar, se till att du har följande:

### 1. Aspose.GIS för .NET-biblioteket
Först och främst måste du ha Aspose.GIS för .NET‑biblioteket installerat i din utvecklingsmiljö. Om du inte redan har gjort det kan du ladda ner det från sidan [Aspose.GIS för .NET-dokumentation](https://reference.aspose.com/gis/net/).

### 2. .NET‑utvecklingsmiljö
Se till att du har en .NET‑utvecklingsmiljö installerad på din maskin. Detta inkluderar att ha Visual Studio eller någon annan kompatibel IDE installerad.

### 3. Grundläggande förståelse för C#
En grundläggande förståelse för programmeringsspråket C# är nödvändig för att kunna följa med i den här handledningen.

## Importera namnrymder
För att kunna använda funktionerna som tillhandahålls av Aspose.GIS för .NET måste du importera de nödvändiga namnrymderna i ditt C#‑projekt.

### Importera Aspose.GIS‑namnrymd
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hur man får linjelängd C#
En `LineString` i Aspose.GIS representerar en serie av två‑eller‑fler punkter som är sammankopplade med raka linjesegment, vilket modellerar linjära objekt såsom vägar, floder eller ledningslinjer inom ett givet koordinatreferenssystem.  
Efter att ha konstruerat `LineString` med de önskade hörnen, returnerar anropet av metoden `GetLength()` den totala avståndet mätt i geometrins CRS‑enheter, vilket gör att du snabbt kan få precisa linjemätningar för ruttplanering, avståndsbaserad analys eller rapportering, och kan vidarebehandlas eller lagras vid behov.

### Steg 1: Skapa geometriska objekt
För att börja, skapa geometriska objekt som representerar de former du vill beräkna längden för. Detta kan inkludera linjer, polygoner eller andra geometriska former.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Steg 2: Beräkna linjelängd i C#
När du har skapat linjegeometrin kan du beräkna dess längd med metoden `GetLength()`. Detta demonstrerar **beräkna linjelängd c#** i en enda kodrad.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Hur man beräknar linjelängd C# för polygoner
En `Polygon` i Aspose.GIS består av en yttre `LinearRing` som definierar dess gräns och valfria inre ringar för hål, vilket representerar områdesfunktioner såsom tomter, sjöar eller administrativa zoner inom en specifik rumslig referens.  
Skapa den yttre `LinearRing` genom att ange polygonens hörnpunkter, och instansiera sedan en `Polygon` med den ringen; genom att anropa `GetLength()` på polygonen beräknas den totala omkretsen, vilket är användbart för uppgifter som att uppskatta stängselns längd, gränsrapportering eller konvertera omkretsvärden till andra enheter.

### Steg 3: Skapa polygongeometri
På liknande sätt kan du skapa polygongeometriobjekt med hjälp av klasserna `Polygon` och `LinearRing`.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### Steg 4: Hämta längden på en polygon
För polygoner returnerar metoden `GetLength()` omkretsen, vilket i praktiken är **hur man får längd** på formen.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Oväntad nollängd** | Verifiera att geometrins koordinatsystem matchar de data du har angett; duplicerade punkter kan orsaka segment med noll längd. |
| **Fel enheter** | Kom ihåg att `GetLength()` returnerar värden i CRS‑enheterna. Konvertera till meter/fot om det behövs. |
| **Prestanda med stora datamängder** | Återanvänd geometriska objekt när det är möjligt och undvik att skapa tusentals temporära punkter i täta loopar. |

## Vanliga frågor

**Q: Är Aspose.GIS för .NET kompatibel med alla .NET‑ramverk?**  
A: Aspose.GIS för .NET är kompatibel med .NET Framework 4.6.1 eller senare versioner, samt .NET 5/6/7.

**Q: Kan jag prova Aspose.GIS för .NET innan jag köper?**  
A: Ja, du kan få en gratis provversion av Aspose.GIS för .NET från [här](https://releases.aspose.com/).

**Q: Var kan jag hitta support för Aspose.GIS för .NET?**  
A: Du kan hitta support och hjälp i Aspose.GIS‑communityforumet [här](https://forum.aspose.com/c/gis/33).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.GIS för .NET?**  
A: Du kan skaffa en tillfällig licens från [här](https://purchase.aspose.com/temporary-license/).

**Q: Kan jag anpassa utdataformatet för beräkningar av geometrilängd?**  
A: Ja, Aspose.GIS för .NET erbjuder olika formateringsalternativ för att anpassa utdataformatet efter dina krav.

## Slutsats
I den här handledningen har vi gått igenom **hur man beräknar geometrilängd .NET** för både linje- och polygongeometrier med hjälp av Aspose.GIS för .NET. Genom att följa de steg‑för‑steg‑exempel kan du nu integrera precisa rumsliga mätningar i vilken .NET‑applikation som helst, oavsett om det är ett skrivbords‑GIS‑verktyg, en webbtjänst eller en backend‑databehandlingspipeline.

---

**Senast uppdaterad:** 2026-08-13  
**Testat med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Lär dig hur du skapar LineString-geometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Hur man beräknar area med Aspose.GIS för .NET](/gis/net/geometry-analysis/get-geometry-area/)
- [Hur man skapar punktgeometri och får geometrityp med Aspose.GIS för .NET](/gis/net/geometry-analysis/get-geometry-type/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}