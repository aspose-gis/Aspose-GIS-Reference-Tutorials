---
date: 2026-06-05
description: Lär dig hur du jämför geometrier i .NET med Aspose.GIS, upptäcker dubblettgeometrier
  och kontrollerar geometrilikhet i dina applikationer.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Hur man jämför geometrier för likhet
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur man jämför geometrier för likhet med Aspose.GIS för .NET
url: /sv/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man jämför geometrier för likhet med Aspose.GIS för .NET

## Introduktion
I den här handledningen kommer du att lära dig **hur man jämför geometrier** med Aspose.GIS för .NET, en uppgift som är avgörande när du behöver upptäcka dubblettgeometrier, validera rumsliga data eller upprätthålla topologiska regler. Oavsett om du bygger en karttjänst, kör batch‑rumslig analys eller helt enkelt verifierar att två former upptar samma plats, guidar denna handledning dig genom att skapa, modifiera och testa geometrilikahet med ren, produktionsklar C#‑kod.

## Snabba svar
- **Vad betyder “compare geometries”?** Det kontrollerar om två geometriska objekt upptar samma utrymme, oavsett hur de är konstruerade.  
- **Vilken metod används?** `SpatiallyEquals` från Aspose.GIS API.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Stödda .NET‑versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Typisk implementeringstid?** Omkring 5‑10 minuter för en grundläggande likhetskontroll.  

## Vad är geometrilikahet?
Geometrilikahet, även kallad rumslig likhet, betyder att två geometrier representerar exakt samma mängd punkter på jordens yta. Även om en geometri är byggd som en `MultiLineString` och den andra som en enkel `LineString`, anses de vara lika när varje koordinat matchar inom den definierade toleransen. Denna definition gör det möjligt för utvecklare att på ett pålitligt sätt upptäcka dubblettgeometrier över heterogena datakällor.

## Varför använda Aspose.GIS för att jämföra geometrier?
Aspose.GIS erbjuder en högpresterande, offline geometrimotor som eliminerar behovet av externa tjänster. Den **stödjer mer än 30 vektor‑ och rasterformat** (inklusive WKT, GeoJSON, Shapefile, KML, GML) och kan bearbeta filer med **hundratusentals hörn** samtidigt som minnesanvändningen hålls under 50 MB. Bibliotekets `SpatiallyEquals`‑metod är precision‑medveten och ger deterministiska resultat även med flyttalskoordinater.

### Varför detta är viktigt för utvecklare
När du behöver **upptäcka dubblettgeometrier** i batch‑processer, realtidsvalideringspipelines eller GIS‑datamigreringar, tar ett beprövat bibliotek bort gissningsarbetet och garanterar konsekventa resultat över olika dataleverantörer.

## Förutsättningar
Innan du börjar, se till att du har följande:

- **.NET Framework eller .NET Core installerat** – vilken version som helst som stöds av Aspose.GIS.  
- **Aspose.GIS för .NET‑bibliotek** – ladda ner från [Aspose.GIS nedladdningssida](https://releases.aspose.com/gis/net/).  
- **En utvecklings‑IDE** – Visual Studio, Rider eller VS Code med C#‑tillägg.

## Importera namnrymder
I ditt .NET‑projekt lägger du till de nödvändiga `using`‑satserna så kompilatorn vet var GIS‑klasserna finns:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg 1: Definiera geometrierna
`MultiLineString` representerar en samling linjekomponenter, medan `LineString` definierar en enda kontinuerlig linje. Båda klasserna ärver från den grundläggande typen `Geometry`.

Först skapar vi två geometrier som vi ska jämföra. I detta exempel är `geometry1` en `MultiLineString` bestående av två linjesegment, medan `geometry2` är en enkel `LineString` som sträcker sig över samma start‑ och slutpunkter.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Steg 2: Kontrollera geometrier för likhet
`SpatiallyEquals` utvärderar om två geometrier upptar samma mängd punkter, och kan valfritt ta emot ett toleransvärde för flyttalsimprecision.

Nu använder vi `SpatiallyEquals`‑metoden för att se om de två formerna anses lika av GIS‑motorn.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Konsolen skriver ut `True` eftersom, trots den olika konstruktionen, båda geometrierna täcker samma linje från (0,0) till (2,2).

## Steg 3: Modifiera en geometri
För att illustrera hur en förändring påverkar likheten lägger vi till en extra punkt i `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Steg 4: Kontrollera likhet igen efter modifiering
Efter modifieringen är geometrierna inte längre lika, så `SpatiallyEquals` returnerar `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Utdata `False` bekräftar att den extra punkten bröt den rumsliga likheten.

## Hur man upptäcker dubblettgeometrier?
Läs in varje geometri, anropa `SpatiallyEquals` med en lämplig tolerans och filtrera bort de som returnerar `True`. Detta mönster skalar bra med LINQ, vilket låter dig identifiera dubblettformer i stora samlingar med bara några rader kod. Du kan också kombinera det med `GroupBy` för att samla identiska geometrier och minska lagringskostnader.

## Vanliga problem & tips
- **Precisionproblem** – Om du arbetar med mycket högprecisionskoordinater, överväg att avrunda eller använda tolerans‑överladdningen av `SpatiallyEquals`.  
- **Olika SRID:n** – Se till att båda geometrierna har samma Spatial Reference System Identifier (SRID) innan jämförelse.  
- **Prestanda** – För stora samlingar kan batch‑jämförelser med LINQ eller parallella loopar minska overheaden dramatiskt.  

## Vanliga frågor
**Q: Kan jag använda Aspose.GIS för .NET med andra .NET‑ramverk?**  
A: Ja, Aspose.GIS fungerar med .NET Framework, .NET Core och .NET Standard‑projekt.

**Q: Finns det en gratis provversion tillgänglig?**  
A: Absolut. Ladda ner en provversion från [Aspose.GIS releases-sida](https://releases.aspose.com/).

**Q: Var kan jag hitta den fullständiga API‑dokumentationen?**  
A: Detaljerad dokumentation finns på [Aspose.GIS dokumentationssida](https://reference.aspose.com/gis/net/).

**Q: Hur får jag hjälp om jag stöter på ett problem?**  
A: Ställ din fråga på Aspose.GIS‑community‑forumet [här](https://forum.aspose.com/c/gis/33).

**Q: Kan jag köpa en tillfällig licens för utvärdering?**  
A: Ja, tillfälliga licenser finns på [köpsida](https://purchase.aspose.com/temporary-license/).

## Slutsats
Du vet nu **hur man jämför geometrier** med Aspose.GIS för .NET, från att skapa objekten till att kontrollera rumslig likhet och hantera modifieringar. Denna funktion är en byggsten för mer avancerade rumsliga analyser såsom topologivalidering, dubblettdetektering och geometribaserad filtrering.

---

**Senast uppdaterad:** 2026-06-05  
**Testad med:** Aspose.GIS for .NET 24.11  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Skapa polygongeometri C# och kontrollera korsning med Aspose.GIS för .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Hur man utför rumslig överlappningsanalys av geometrier med Aspose.GIS för .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Nätverksruttkontroll: Berörande geometrier med Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}