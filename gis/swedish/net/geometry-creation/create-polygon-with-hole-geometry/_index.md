---
date: 2026-04-03
description: Lär dig hur du skapar polygon med hålgeometri med Aspose.GIS för .NET.
  Den här guiden visar hur du skapar ett hål i en polygon och arbetar med geospatial
  data.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Skapa polygon med hålgeometri
second_title: Aspose.GIS .NET API
title: Skapa polygon med hålgeometri med Aspose.GIS
url: /sv/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa polygon med hål‑geometri med Aspose.GIS

## Introduktion
I den här handledningen kommer du att **skapa polygon med hål**‑geometri med Aspose.GIS för .NET. Oavsett om du bygger en kartapplikation, utför rumslig analys eller förbereder data för GIS‑tjänster är det viktigt att kunna bädda in ett hål i en polygon. Vi går igenom hela processen steg‑för‑steg, från att sätta upp miljön till att generera det färdiga polygon‑objektet.

## Snabba svar
- **Vad betyder “create polygon with hole”?** Det betyder att bygga en polygon som innehåller en eller flera inre ringar (hål) som exkluderas från området.  
- **Vilket bibliotek hanterar detta?** Aspose.GIS för .NET erbjuder fullt stöd för yttre och inre ringar.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hur lång tid tar det?** Vanligtvis under 10 minuter att implementera och testa.

## Hur man lägger till hål i en polygon med Aspose.GIS
Att lägga till ett hål är helt enkelt en fråga om att definiera en **inre ring** och fästa den på polygonen. Biblioteket tar hand om orientering och giltighet, så du kan fokusera på koordinaterna som representerar det tomrum du behöver.

## Vad är “create polygon with hole”?
Att skapa en polygon med ett hål innebär att definiera en **yttre ring** som avgränsar den yttre gränsen samt en eller flera **inre ringar** som skär ut tomma utrymmen. De inre ringarna kallas ofta *hål* eftersom de representerar områden som inte är en del av polygonens yta.

## Varför skapa hål i en polygon med Aspose.GIS?
- **Noggrann rumslig modellering:** Verkliga funktioner som sjöar inom markområden eller gårdar inom byggnader kräver hål.  
- **Interoperabilitet:** Format som Shapefile, GeoJSON och GML stöder inre ringar inbyggt; Aspose.GIS bevarar dem.  
- **Prestanda:** Biblioteket hanterar geometrins giltighet, så du slipper skriva egen valideringskod.

## Verkliga scenarier för polygoner med hål
1. **Markparcell med en intern sjö** – sjön modelleras som ett hål så att den inte räknas med i parcelns area.  
2. **Byggnadsytor med gårdar** – gården exkluderas från byggnadens yta.  
3. **Skyddade zoner inom ett större naturskyddsområde** – du kan utesluta restriktioner utan att skapa separata lager.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Aspose.GIS för .NET‑bibliotek: Du kan ladda ner det [här](https://releases.aspose.com/gis/net/).  
2. Utvecklingsmiljö: Säkerställ att du har en utvecklingsmiljö med Visual Studio eller någon annan .NET‑IDE installerad.

## Importera namnrymder
Först måste du importera de nödvändiga namnrymderna för att arbeta med Aspose.GIS‑funktioner. Så här gör du:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nu fortsätter vi med att skapa en polygon med hål‑geometri med Aspose.GIS för .NET.

## Steg 1: Skapa polygon‑objekt
Vi börjar med att instansiera ett tomt `Polygon`‑objekt som senare kommer att hålla både den yttre och de inre ringarna.

```csharp
Polygon polygon = new Polygon();
```

## Steg 2: Definiera yttre ring
Den yttre ringen definierar polygonens yttre gräns. Lägg till punkter i medurs‑ordning för att bilda en sluten form.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Steg 3: Definiera inre ring (hål)
Nästa steg är att skapa en inre ring—detta är **hålet** som kommer att exkluderas från polygonens area. Punkter läggs vanligtvis till i moturs‑ordning, men Aspose.GIS hanterar orienteringen automatiskt.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Steg 4: Tilldela yttre ring och lägg till inre ring i polygonen
Till sist fäster du den yttre ringen på polygonen och lägger sedan till den inre ringen (hålet). Metoden `AddInteriorRing` kan anropas flera gånger om du behöver flera hål.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tips och bästa praxis
- **Orientering är viktig för läsbarhet** – även om Aspose.GIS automatiskt korrigerar orientering, gör det geometrin enklare att inspektera i GIS‑visare om yttre ringar är medurs och inre ringar moturs.  
- **Stäng varje ring** – upprepa alltid den första koordinaten som den sista punkten; detta garanterar en giltig sluten form.  
- **Validera efter skapande** – du kan anropa `polygon.IsValid` för att säkerställa att geometrin följer OGC‑standarder innan du sparar.

## Vanliga problem och lösningar
| Problem | Orsak | Åtgärd |
|-------|--------|-----|
| Hålet visas inte i GIS‑visaren | Inre ring har fel orientering | Säkerställ att punkterna läggs till i motsatt riktning mot den yttre ringen (moturs). |
| Polygon‑ogiltigt fel | Ringar är inte stängda (första ≠ sista punkt) | Upprepa den första punkten som den sista i varje ring (som visat ovan). |
| Oväntad tom geometri | Glömt att tilldela `ExteriorRing` innan inre ringar läggs till | Sätt `polygon.ExteriorRing` först, anropa sedan `AddInteriorRing`. |

## Vanliga frågor
### 1. Vad är Aspose.GIS?
Aspose.GIS är ett .NET‑bibliotek som gör det möjligt för utvecklare att arbeta med geografiska data, skapa, läsa och manipulera olika geospatiala filformat.

### 2. Kan jag använda Aspose.GIS i kommersiella projekt?
Ja, du kan använda Aspose.GIS både i personliga och kommersiella projekt genom att köpa en licens. Besök [här](https://purchase.aspose.com/buy) för mer information.

### 3. Finns det en gratis provversion av Aspose.GIS?
Ja, du kan få en gratis provversion av Aspose.GIS [här](https://releases.aspose.com/).

### 4. Var kan jag få support för Aspose.GIS?
Du kan hitta support för Aspose.GIS på [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33).

### 5. Hur kan jag skaffa en tillfällig licens för Aspose.GIS?
Du kan skaffa en tillfällig licens för Aspose.GIS [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-04-03  
**Testat med:** Aspose.GIS 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}