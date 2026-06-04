---
date: 2026-02-08
description: Lär dig hur du utför en nätverksruttkontroll genom att upptäcka berörda
  geometrier med Aspose.GIS för .NET, ett kraftfullt bibliotek för att hantera rumsliga
  data och möjliggöra rumslig analys.
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: 'Kontroll av nätverksrouting: Berörande geometrier med Aspose.GIS'
url: /sv/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nätverksruttkontroll: Berörande geometrier med Aspose.GIS för .NET

## Introduktion
När du behöver **utföra en nätverksruttkontroll** mellan två rumsliga objekt, ger Aspose.GIS för .NET dig ett rent, typ‑säkert API som gör jobbet enkelt. I den här handledningen kommer du att se hur man skapar linjesträngar, punkter och sedan använder `Touches`‑metoden för att avgöra om geometrierna bara delar en gräns. Denna operation är en hörnsten i många **spatial analysis .NET**‑scenarier såsom ruttvalidering, kartöverlagringsverifiering och närhetsfrågor.

## Snabba svar
- **Vad betyder “touching”?** Två geometrier delar minst en gränspunkt men deras innandömen skär inte varandra.  
- **Vilken metod kontrollerar det?** `Geometry.Touches(otherGeometry)`.  
- **Behöver jag en licens för den här funktionen?** En provversion fungerar för utveckling; en permanent licens krävs för produktion.  
- **Stödda .NET‑versioner?** .NET Framework, .NET Core, .NET 5/6/7 – alla täcks av Aspose.GIS.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter för ett grundläggande exempel.  

## Så utför du en nätverksruttkontroll med berörande geometrier
Nedan går vi igenom de exakta stegen du behöver för att **kontrollera berörande** geometrier och integrera resultatet i ett rutt‑valideringsflöde.

### Vad betyder “Touching” i spatial analys?
I GIS‑terminologi beskriver *touching* ett rumsligt förhållande där två geometrier möts vid sina kanter men inte överlappar. Det skiljer sig från *intersects* (som inkluderar överlappning av innandömen) och används ofta när du behöver validera att funktioner bara möts vid en gräns—till exempel vägssegment som ansluter vid en korsning utan att korsa varandra.

## Varför använda Aspose.GIS för spatial analysis .NET?
Aspose.GIS tillhandahåller ett helt hanterat .NET‑bibliotek som låter dig **hantera rumsliga data** utan inhemska GIS‑installationer. Det stödjer ett brett spektrum av format (Shapefile, GeoJSON, KML, etc.) och erbjuder högpresterande geometriska operationer som `Touches`, `Intersects`, `Contains` och mer. Eftersom det är rent .NET kan du bädda in det direkt i webbtjänster, skrivbordsapplikationer eller molnfunktioner.

## Förutsättningar
1. **Visual Studio** (valfri nyare version) installerad på din maskin.  
2. **Aspose.GIS for .NET** – ladda ner det senaste paketet från den [officiella nedladdningssidan](https://releases.aspose.com/gis/net/).  
3. **En giltig licens** (eller en gratis provversion) – skaffa den från [här](https://releases.aspose.com/).  

### Konfigurera din miljö
1. Installera Visual Studio om du inte redan har gjort det.  
2. Ladda ner Aspose.GIS för .NET från länken ovan och lägg till NuGet‑paketet i ditt projekt.  
3. Applicera din licensfil i koden (eller använd en tillfällig licens för testning).

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

## Steg 1: Skapa linjesträngar (och en punkt)
Nedan **skapar vi linjesträngs**‑objekt och en punkt som kommer att användas för att testa den berörande relationen.

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
- `geometry1` och `geometry2` delar ändpunkten `(2, 2)`.  
- `geometry3` är en punkt som ligger exakt på den delade ändpunkten.  
- `geometry4` korsar samma område men **delar inte** en gräns med `geometry1`.

## Steg 2: Kontrollera berörande relationer
Nu anropar vi `Touches`‑metoden för att se vilka par som anses berörande.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Resultat*:  
- De första tre kontrollerna returnerar **True** eftersom geometrierna möts vid en enda punkt utan innandömsöverlappning.  
- Den sista kontrollen returnerar **False** eftersom de två linjesträngarna skär varandra över ett linjesegment, inte bara vid en gränspunkt.

## Vanliga problem & tips
- **Precision problem** – GIS‑beräkningar är flyttalsbaserade. Om du får oväntade `False`‑resultat, överväg att normalisera koordinater eller använda en tolerans med `Geometry.EqualsExact(other, tolerance)`.  
- **Blandade geometrityper** – `Touches` fungerar över punkter, linjer och polygoner, men semantiken skiljer sig; verifiera alltid den förväntade relationen för din datamodell.  
- **Prestanda** – För stora dataset, batcha kontrollerna eller använd rumsliga index (t.ex. R‑tree) som tillhandahålls av Aspose.GIS för att undvika O(N²)-jämförelser.

## Vanliga frågor

**Q: Är Aspose.GIS kompatibel med alla .NET‑ramverk?**  
A: Ja. Det stödjer .NET Framework, .NET Core, .NET 5+ och .NET 6+, vilket ger dig flexibilitet över skrivbords-, webb- och molnprojekt.

**Q: Kan jag prova Aspose.GIS innan jag köper en licens?**  
A: Absolut. Du kan få en gratis provversion från Aspose‑webbplatsen [här](https://purchase.aspose.com/temporary-license/) för att utforska alla funktioner, inklusive `Touches`‑operationen.

**Q: Var kan jag hitta support för Aspose.GIS‑relaterade frågor?**  
A: Besök det officiella [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för att ställa frågor, dela exempel och få hjälp från både communityn och Aspose‑ingenjörer.

**Q: Hur ofta släpps uppdateringar för Aspose.GIS?**  
A: Aspose släpper regelbundna uppdateringar som lägger till stöd för nya format, prestandaförbättringar och buggfixar, vilket säkerställer kompatibilitet med de senaste .NET‑utgåvorna.

**Q: Kan jag få en tillfällig licens för Aspose.GIS?**  
A: Ja, en tillfällig licens finns tillgänglig [här](https://purchase.aspose.com/temporary-license/) för utvärderingsändamål.

**Q: Hur hjälper `Touches`‑metoden med en nätverksruttkontroll?**  
A: Genom att bekräfta att vägssegment bara möts vid delade ändpunkter (touch) kan du validera att ett rutt‑nätverk är korrekt anslutet utan oavsiktliga överlappningar.

---

**Senast uppdaterad:** 2026-02-08  
**Testad med:** Aspose.GIS for .NET 24.11 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}