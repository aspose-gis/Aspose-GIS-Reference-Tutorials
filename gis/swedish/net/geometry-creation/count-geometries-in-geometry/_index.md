---
date: 2025-12-11
description: Lär dig hur du räknar geometrier och lägger till geometrier i en samling
  med Aspose.GIS för .NET. Steg‑för‑steg‑handledning med kodexempel för utvecklare.
linktitle: Count Geometries in Geometry
second_title: Aspose.GIS .NET API
title: Hur man räknar geometrier i Geometry med Aspose.GIS
url: /sv/net/geometry-creation/count-geometries-in-geometry/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man räknar geometrier i Geometry med Aspose.GIS

## Introduktion
Om du behöver **hur man räknar geometrier** i en sammansatt form, gör Aspose.GIS för .NET det enkelt. Oavsett om du bygger en kartapplikation, en platsbaserad tjänst eller en spatial‑analysmotor, är förmågan att räkna de enskilda geometrierna i en samling en grundläggande uppgift. I den här handledningen går vi igenom hur man skapar enkla geometrier, lägger till dem i en samling och slutligen använder API:et för att hämta geometriräkningen.

## Snabba svar
- **Vad är den primära metoden?** Använd `Count`‑egenskapen på en `GeometryCollection`.
- **Vilket namnrymd krävs?** `Aspose.Gis.Geometries`.
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.
- **Kan jag lägga till olika geometrityper?** Ja – punkter, linjer, polygoner osv. kan alla läggas till i samma samling.
- **Är detta kompatibelt med .NET Core?** Absolut, Aspose.GIS stödjer .NET Framework och .NET Core.

## Vad betyder “hur man räknar geometrier”?
Att räkna geometrier innebär att bestämma hur många enskilda geometriska objekt (punkter, linjer, polygoner osv.) som lagras i en sammansatt struktur som en `GeometryCollection`. API:et exponerar denna information via en enkel heltals‑egenskap, vilket eliminerar behovet av manuell iteration.

## Varför lägga till geometrier i en samling?
Att lägga till geometrier i en samling (`add geometries to collection`) låter dig behandla flera former som en enda logisk enhet. Detta är användbart för batch‑behandling, spatiala frågor och rendering av flera funktioner samtidigt utan att hantera varje enskild separat.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Visual Studio** – någon nyare version (2019, 2022 eller senare).  
2. **Aspose.GIS för .NET** – ladda ner och installera den från [nedladdningssidan](https://releases.aspose.com/gis/net/).  
3. **Grundläggande C#‑kunskaper** – du bör vara bekväm med att skapa en konsolapplikation och lägga till NuGet‑paket.

## Importera namnrymder
Först importerar du namnrymderna som ger dig åtkomst till geometriklasserna.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 1: Skapa en punktgeometri
En `Point` representerar ett enda koordinatpar (latitud, longitud). Här skapar vi en för New York City.

```csharp
Point point = new Point(40.7128, -74.006);
```

## Steg 2: Skapa en LineString‑geometri
En `LineString` är en serie av sammankopplade punkter. Vi lägger till två godtyckliga punkter för att illustrera.

```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

## Steg 3: Lägg till geometrier i en samling
Nu kombinerar vi punkten och linjen till en enda `GeometryCollection`. Detta är där vi **lägger till geometrier i samling**.

```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```

## Steg 4: Hur man räknar geometrier
`Count`‑egenskapen returnerar det totala antalet geometrier som lagras i samlingen.

```csharp
int geometriesCount = geometryCollection.Count;
```

## Steg 5: Visa räkningen
Till sist skriver du ut räkningen till konsolen. I detta exempel är resultatet `2`.

```csharp
Console.WriteLine(geometriesCount); // 2
```

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Count always returns 0** | Samlingen fylldes aldrig. | Se till att du anropar `Add` för varje geometri innan du hämtar `Count`. |
| **Invalid coordinate order** | Punktkonstruktorn förväntar sig latitud först, sedan longitud. | Verifiera parameterns ordning när du skapar `Point` eller `LineString`. |
| **Missing namespace error** | `Aspose.Gis.Geometries` är inte importerad. | Lägg till `using Aspose.Gis.Geometries;` högst upp i filen. |

## Vanliga frågor

**Q: Kan jag blanda olika geometrityper i samma samling?**  
A: Ja, du kan lägga till punkter, linjer, polygoner och till och med andra samlingar i en enda `GeometryCollection`.

**Q: Stöder Aspose.GIS GeoJSON‑export för en samling?**  
A: Absolut. Du kan använda `geometryCollection.ToGeoJson()` för att serialisera samlingen.

**Q: Finns det ett sätt att iterera över varje geometri efter räkning?**  
A: Ja, `foreach (var geom in geometryCollection)` låter dig bearbeta varje geometri individuellt.

**Q: Behöver jag en licens för utvecklingsbyggen?**  
A: En gratis provversion fungerar för utvärdering, men en licensierad version krävs för produktionsdistributioner.

### Är Aspose.GIS för .NET lämplig för både skrivbords- och webbapplikationer?  
Ja, Aspose.GIS för .NET kan användas i både skrivbords- och webbapplikationer sömlöst.

### Kan jag utföra spatiala frågor med Aspose.GIS för .NET?  
Absolut, Aspose.GIS för .NET erbjuder robust stöd för att utföra spatiala frågor på geometrier.

### Stöder Aspose.GIS för .NET olika GIS‑filformat?  
Ja, Aspose.GIS för .NET stödjer ett brett spektrum av GIS‑filformat inklusive SHP, KML och GeoJSON.

### Finns det en gratis provversion av Aspose.GIS för .NET?  
Ja, du kan ladda ner en gratis provversion från [webbplatsen](https://releases.aspose.com/).

### Var kan jag hitta support för Aspose.GIS för .NET?  
Du kan hitta support på [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33).

## Slutsats
I den här guiden har vi gått igenom **hur man räknar geometrier** i en `GeometryCollection` och demonstrerat de praktiska stegen för att **lägga till geometrier i samling** med Aspose.GIS för .NET. Med dessa grunder kan du nu bygga rikare spatiala funktioner, utföra batch‑operationer och integrera geospatial intelligens i vilken .NET‑applikation som helst.

---

**Senast uppdaterad:** 2025-12-11  
**Testad med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}