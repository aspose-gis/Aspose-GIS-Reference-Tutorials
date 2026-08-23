---
date: 2026-08-03
description: Lär dig hur du skapar linestring c# med Aspose.GIS för .NET, lägger till
  punkter i en linestring och utför en kontroll av punkt på linje med hjälp av covers‑metoden.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Skapa linestring c# – Kontrollera att geometri täcker en annan
og_description: Skapa linestring c# och verifiera punkt på linje med Aspose.GIS covers‑metod.
  Lär dig exakta geometri‑kontroller för .NET‑applikationer. (150‑160 tecken)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Skapa linestring c# – Kontrollera att geometri täcker en annan (50‑60 tecken)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Skapa linestring c# – Kontrollera att geometri täcker en annan
url: /sv/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kontrollera att geometri täcker en annan

## Introduktion
I den här handledningen kommer du att lära dig **hur man skapar linestring c#** med Aspose.GIS för .NET, lägga till punkter i en linestring och utföra en pålitlig **punkt‑på‑linje‑kontroll** med metoderna `Covers` och `CoveredBy`. Oavsett om du bygger ett kartverktyg, utför spatial analys eller helt enkelt behöver verifiera geometriska relationer, kommer behärskning av dessa operationer att ge din applikation den precision den behöver.

## Snabba svar
- **Vad betyder “create linestring c#”?** Det betyder att instansiera ett `LineString`-geometriobjekt och fylla det med koordinatpunkter.  
- **Vilken metod kontrollerar om en punkt ligger på en linje?** Använd `Covers`-metoden på `LineString` eller `CoveredBy` på `Point`.  
- **Behöver jag en licens för att köra exemplet?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Kan detta användas med .NET Core?** Ja, Aspose.GIS stöder .NET Framework och .NET Core.  
- **Hur många punkter kan jag lägga till i en linestring?** Det finns ingen hård gräns; du kan lägga till så många punkter som behövs för din spatiala analys.  

## Vad är create linestring c#?
En `LineString` är en geometrisk form som består av en ordnad lista av punkter som är sammankopplade med raka linjesegment. I C# skapar du den genom att instansiera `LineString`-klassen från `Aspose.Gis.Geometries`‑namnutrymmet och sedan **lägger till punkter i linestring** med `AddPoint`‑metoden. Detta objekt fungerar som grund för all linjär spatial analys, såsom ruttkartering eller nätverksspårning.

## Varför använda Aspose.GIS för en punkt‑på‑linje‑kontroll?
`Covers` är en spatial predikat‑metod som returnerar true när den första geometrin helt innehåller den andra geometrin.  
Aspose.GIS tillhandahåller en deterministisk, högprecisionimplementation av spatiala predikat. Den stödjer över 50 in‑ och utdata‑GIS‑format, kan hantera linjenätverk på flera hundra kilometer utan att ladda hela datasetet i minnet, och körs på .NET Framework, .NET Core och .NET 5/6+. Genom att använda dess `Covers`‑metod garanteras att flyttalsavrundningsfel beaktas, vilket levererar pålitliga punkt‑på‑linje‑resultat även i krävande företagsmiljöer.

## Förutsättningar
Innan du dyker ner i att använda Aspose.GIS för .NET, se till att du har följande förutsättningar på plats:

### 1. Installera Visual Studio
Se till att du har Visual Studio installerat på ditt system. Aspose.GIS för .NET integreras sömlöst med Visual Studio och ger en smidig utvecklingsupplevelse.

### 2. Skaffa Aspose.GIS för .NET
Ladda ner Aspose.GIS för .NET‑biblioteket från [webbplatsen](https://releases.aspose.com/gis/net/). Du kan antingen ladda ner biblioteket direkt eller använda en paket‑hanterare som NuGet för att installera det i ditt projekt.

### 3. Bekantskap med .NET Framework
Grundläggande kunskap om .NET‑ramverket och C#‑programmeringsspråket är nödvändig för att effektivt kunna använda Aspose.GIS för .NET.

### 4. Tillgång till dokumentation och support
Se [dokumentationen](https://reference.aspose.com/gis/net/) för detaljerad information om Aspose.GIS‑API:er och funktioner. Om du stöter på problem eller har frågor, använd [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för hjälp.

### 5. Valfritt: tillfällig licens
Om du utforskar Aspose.GIS för .NET kan du skaffa en tillfällig licens från [sidan för tillfällig licens](https://purchase.aspose.com/temporary-license/) för att utvärdera bibliotekets funktioner.

## Importera namnrymder
Innan du använder Aspose.GIS för .NET i ditt projekt måste du importera de nödvändiga namnrymderna:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nu ska vi gå igenom det medföljande exemplet i flera steg för att förstå hur man **kontrollerar om en geometri täcker en annan** med Aspose.GIS för .NET.

## Hur man skapar linestring c# – steg‑för‑steg‑guide
Läs in ditt projekt, importera de nödvändiga namnrymderna och följ sedan de fem kortfattade stegen nedan. På bara några kodrader kommer du att ha ett `LineString`‑objekt, ett `Point`‑objekt och två booleska kontroller som visar om linjen täcker punkten och om punkten täcks av linjen.

### Step 1: skapa ett linestring‑objekt
`LineString`‑klassen representerar en sekvens av punkter som är sammankopplade med raka linjesegment i ett tvådimensionellt plan.  
```csharp
var line = new LineString();
```
Här instansierar vi ett nytt `LineString`‑objekt, som representerar en sekvens av sammankopplade linjesegment i ett tvådimensionellt rum.

### Step 2: lägg till punkter i linestring
`AddPoint` lägger till ett koordinatpar i slutet av `LineString`‑samlingen och bevarar insättningsordningen.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
Vi **lägger till punkter i linestring** med `AddPoint`‑metoden. I detta exempel lägger vi till två punkter: (0, 0) och (1, 1), vilket bildar ett enkelt diagonalt linjesegment.

### Step 3: skapa ett point‑objekt
`Point`‑klassen modellerar en enskild plats i ett tvådimensionellt koordinatsystem.  
```csharp
var point = new Point(0, 0);
```
Instansiera ett `Point`‑objekt som representerar en enskild punkt i ett tvådimensionellt rum. Här skapar vi en punkt på koordinaterna (0, 0).

### Step 4: utför en punkt‑på‑linje‑kontroll – täcker linjen punkten?
`Covers` avgör om den första geometrin helt innehåller den andra geometrin och returnerar true endast när varje punkt i den andra geometrin ligger inom den första.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Använd `Covers`‑metoden för att kontrollera om linjen täcker punkten. I detta fall returnerar den `True` eftersom punkten (0, 0) ligger exakt på linjen.

### Step 5: verifiera det omvända förhållandet – är punkten täckt av linjen?
`CoveredBy` är inversen till `Covers`; den returnerar true när den anropande geometrin är helt inuti målgeometrin.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
På samma sätt, använd `CoveredBy`‑metoden för att kontrollera om punkten är täckt av linjen. Eftersom punkten (0, 0) ligger på linjen returnerar den också `True`.

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|-------------------|--------|
| `line.Covers(point)` returnerar `False` även om punkten verkar ligga på linjen | Punktens koordinater är inte exakt samma på grund av flyttalsprecision. | Använd `Math.Round` på koordinaterna eller använd en toleransbaserad kontroll med `line.Distance(point) < epsilon`. |
| Saknad `using Aspose.Gis.Geometries;` | Namnutrymmet är inte importerat, vilket orsakar kompileringsfel. | Se till att import‑satsen finns (se avsnittet **Importera namnrymder**). |
| Licensundantag vid körning | Ingen giltig licens laddad för produktion. | Läs in en tillfällig eller full licens med `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Vanliga frågor

**Q: Kan jag använda Aspose.GIS för .NET i mina kommersiella projekt?**  
A: Ja, du kan använda Aspose.GIS för .NET i både kommersiella och icke‑komersiella projekt efter att ha skaffat rätt licens.

**Q: Är Aspose.GIS för .NET kompatibel med .NET Core?**  
A: Ja, Aspose.GIS för .NET är kompatibel med både .NET Framework och .NET Core‑miljöer.

**Q: Stöder Aspose.GIS för .NET olika GIS‑format?**  
A: Ja, Aspose.GIS för .NET stödjer ett brett spektrum av GIS‑format inklusive Shapefile, GeoJSON, KML och fler.

**Q: Kan jag bidra till utvecklingen av Aspose.GIS för .NET?**  
A: Aspose.GIS för .NET är ett proprietärt bibliotek utvecklat av Aspose, så externa bidrag accepteras inte. Du kan dock ge feedback och förslag för att förbättra biblioteket.

**Q: Hur ofta släpps uppdateringar för Aspose.GIS för .NET?**  
A: Uppdateringar för Aspose.GIS för .NET släpps regelbundet för att introducera nya funktioner, förbättringar och buggfixar. Kontrollera [webbplatsen](https://releases.aspose.com/gis/net/) för de senaste versionerna.

## Slutsats
Genom att följa stegen ovan vet du nu hur man **skapar linestring c#**, **lägger till punkter i linestring** och utför en pålitlig **punkt‑på‑linje‑kontroll** med `Covers`‑ och `CoveredBy`‑metoderna. Denna funktion förbättrar ditt programs spatiala analysfunktioner och öppnar dörren till mer avancerade GIS‑operationer såsom ruttvalidering, nätverkstopologikontroller och närhetsfrågor.

---

**Senast uppdaterad:** 2026-08-03  
**Testat med:** Aspose.GIS för .NET (senaste version)  
**Författare:** Aspose

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Lär dig hur man skapar LineString-geometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Hur man lägger till punkt i LineString och konverterar geometri till redigerbart format med Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [punkt inuti polygon c# – Kontrollera om geometri innehåller en annan](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}