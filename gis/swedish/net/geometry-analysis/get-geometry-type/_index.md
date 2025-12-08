---
date: 2025-12-08
description: Lär dig hur du **hämtar geometrityp** från en punkt med Aspose.GIS för
  .NET. Denna steg‑för‑steg‑guide täcker GIS‑förutsättningar, att skapa ett punktobjekt
  och att arbeta med rumsliga data i C#.
language: sv
linktitle: Get Geometry Type
second_title: Aspose.GIS .NET API
title: Hämta geometrityp med Aspose.GIS för .NET
url: /net/geometry-analysis/get-geometry-type/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta geometrityp med Aspose.GIS för .NET

## Introduktion
Om du behöver **get geometry type** av ett rumsligt objekt i en .NET-applikation gör Aspose.GIS det enkelt. I den här handledningen går vi igenom hela processen—från att sätta upp din GIS-miljö till att skapa ett punktobjekt och extrahera dess geometrityp. I slutet kommer du att förstå hur du **work with spatial data** effektivt och vara redo att utöka exemplet till linjer, polygoner och mer.

## Snabba svar
- **What does “get geometry type” mean?** Det returnerar enum‑värdet (t.ex. Point, LineString) som identifierar formen på ett geometriskt objekt.  
- **Which library provides this capability?** Aspose.GIS för .NET.  
- **Do I need a license to run the example?** En gratis provversion fungerar för utveckling; en licens krävs för produktion.  
- **What .NET versions are supported?** .NET 5, .NET 6, .NET Core 3.1 och senare.  
- **How long does the setup take?** Vanligtvis under 10 minuter för ett grundläggande punkt‑exempel.

## Vad är “get geometry type” i Aspose.GIS?
`GeometryType` är en uppräkning som beskriver vilken typ av geometri du arbetar med—Point, LineString, Polygon, etc. Att komma åt denna egenskap låter dig fatta beslut i din kod baserat på formen på de data du bearbetar.

## Varför använda Aspose.GIS för .NET?
- **Full‑featured GIS engine** – inga externa inhemska beroenden.  
- **Rich API** – skapa, redigera och analysera rumsliga data direkt från C#.  
- **Cross‑platform** – fungerar på Windows, Linux och macOS.  
- **Excellent documentation** – snabbreferens och exempel för varje klass.

## GIS‑förutsättningar för .NET (gis prerequisites .net)
Innan du börjar, se till att du har följande på plats:

1. **.NET SDK** – senaste versionen (ladda ner från den officiella .NET‑sidan).  
2. **IDE** – Visual Studio, Rider eller VS Code med C#‑tillägg.  
3. **Aspose.GIS for .NET** – hämta biblioteket från den officiella [download link](https://releases.aspose.com/gis/net/).  
4. **API Documentation** – ha [Aspose.GIS for .NET docs](https://reference.aspose.com/gis/net/) tillgänglig för referens.

## Importera namnrymder
I alla .NET‑projekt som använder Aspose.GIS måste du importera de nödvändiga namnrymderna. Detta ger dig åtkomst till geometriklasser, samlingar och hjälpfunktioner.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hur man får geometrityp från en punkt
Nedan är ett **point example .net** som demonstrerar hela flödet—från att skapa punkten till att hämta dess geometrityp.

### Steg 1: Skapa ett punktobjekt
```csharp
Point point = new Point(40.7128, -74.006);
```
*Pro tip:* `Point`‑konstruktorn förväntar sig **latitude** först och **longitude** som andra, i enlighet med den konventionella GIS‑ordningen.

### Steg 2: Hämta geometrityp
```csharp
GeometryType geometryType = point.GeometryType;
```
Här får vi åtkomst till egenskapen `GeometryType`, som returnerar enum‑värdet `GeometryType.Point`.

### Steg 3: Visa geometrityp
```csharp
Console.WriteLine(geometryType); // Point
```
Konsolutdata bekräftar att objektet faktiskt är en **point**, och du har framgångsrikt **get geometry type** från det.

## Vanliga problem & lösningar
| Problem | Orsak | Lösning |
|-------|-------|-----|
| **`GeometryType` returns `Unknown`** | Geometrin initierades inte korrekt. | Se till att du använder rätt konstruktor (`new Point(lat, lon)`). |
| **Compilation errors** | Saknad Aspose.GIS‑referens. | Lägg till NuGet‑paketet `Aspose.GIS` i ditt projekt. |
| **Runtime exception on Linux** | Inkompatibla inhemska bibliotek. | Använd .NET Core‑versionen av Aspose.GIS, som är helt plattformsoberoende. |

## Vanliga frågor

**Q: Är Aspose.GIS kompatibel med alla versioner av .NET?**  
A: Ja, Aspose.GIS stödjer .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 och senare.

**Q: Kan jag prova Aspose.GIS innan jag köper?**  
A: Absolut. En gratis provversion finns tillgänglig via [download link](https://releases.aspose.com/).

**Q: Var kan jag hitta support för Aspose.GIS‑relaterade frågor?**  
A: Besök Aspose.GIS [support forum](https://forum.aspose.com/c/gis/33) för gemenskaps‑hjälp och officiell assistans.

**Q: Hur får jag en tillfällig licens för utveckling?**  
A: Tillfälliga licenser finns på sidan [temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa en full licens för produktionsbruk?**  
A: Du kan köpa en licens direkt från Aspose.GIS‑köpsidan [here](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose