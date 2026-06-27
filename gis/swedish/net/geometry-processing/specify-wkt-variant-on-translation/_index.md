---
date: 2026-04-09
description: Lär dig hur du tilldelar en rumslig referens och ställer in decimalprecision
  när du skapar en punkt i C# med Aspose.GIS för .NET i dina .NET‑applikationer.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Ange WKT-variant vid översättning
second_title: Aspose.GIS .NET API
title: Tilldela rumslig referens och ange WKT-variant med Aspose.GIS
url: /sv/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tilldela rumslig referens & ange WKT-variant med Aspose.GIS

## Introduktion
I den här handledningen kommer du att lära dig hur du **tilldelar en rumslig referens** till en geometri och styr det exakta WKT-utdataformatet med Aspose.GIS för .NET. Oavsett om du behöver **skapa point C#**-objekt för kartläggning, analys eller datautbyte, gör möjligheten att välja rätt WKT-variant och numerisk precision dina rumsliga data interoperabla och lätta att läsa. Låt oss gå igenom processen steg för steg.

## Snabba svar
- **Vad betyder “assign spatial reference”?** Det binder en geometri till ett specifikt koordinatsystem som WGS‑84.  
- **Vilka WKT-varianter stöds?** Iso, SimpleFeatureAccessOutdated och ExtendedPostGis.  
- **Hur kan jag kontrollera decimalprecision?** Använd `NumericFormat`-alternativen som `General`, `RoundTrip` eller `Flat`.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktion.  
- **Vilka .NET-versioner är kompatibla?** .NET Framework 4.0+ och .NET Core/5/6+.

## Vad är “assign spatial reference”?
Att tilldela en rumslig referens (eller spatialt referenssystem, SRS) talar om för GIS‑programvaran hur koordinatavärdena för en geometri ska tolkas. Utan ett SRS har ett punkts latitud‑longitud‑nummer ingen verklig betydelse.

## Varför kontrollera WKT-varianten och numeriskt format?
Olika GIS‑verktyg förväntar sig något olika WKT‑syntaxer. Att välja rätt variant säkerställer sömlös datautbyte, medan inställning av decimalprecision förhindrar avrundningsfel eller alltför långa tal som skräpar ner loggar och filer.

## Förutsättningar
1. Aspose.GIS för .NET – ladda ner från [download page](https://releases.aspose.com/gis/net/).  
2. En .NET‑utvecklingsmiljö (Visual Studio, VS Code eller Rider).  
3. Grundläggande kunskap om C# och .NET‑ramverket.

## Importera namnrymder
Innan du använder några Aspose.GIS‑klasser, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Steg 1: Skapa ett Point‑objekt (create point C#)
Vi börjar med att konstruera en `Point` med latitud, longitud och ett valfritt mått (M)-värde:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Steg 2: Tilldela Spatial Reference System (SRS)
Nu **tilldelar vi en rumslig referens** till punkten. Här använder vi det allmänt stödda WGS‑84‑systemet (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Steg 3: Ange önskad WKT-variant
Välj den WKT-variant som matchar ditt nedströmsprogram:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Steg 4: Ställ in decimalprecision för WKT‑utdata
Styr hur många siffror som visas i den slutliga strängen med `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Vanliga fallgropar & tips
- **Fallgrop:** Att glömma att sätta SRS innan du anropar `AsText` kan leda till att SRID‑information saknas.  
- **Tips:** Använd `NumericFormat.RoundTrip` när du behöver förlustfri rundresa av koordinater.  
- **Tips:** `Iso`‑varianten är den mest portabla; välj `ExtendedPostGis` endast när du behöver SRID inbäddat.

## Slutsats
Du vet nu hur du **tilldelar en rumslig referens**, väljer rätt WKT-variant och **ställer in decimalprecision** när du **skapar point C#**-objekt med Aspose.GIS. Dessa kontroller ger dig flexibiliteten att uppfylla de exakta kraven för vilket GIS‑arbetsflöde som helst, från enkel visualisering till högprecisions‑spatial analys.

## Vanliga frågor

**Q:** Är Aspose.GIS kompatibel med alla versioner av .NET?  
**A:** Ja, Aspose.GIS stödjer .NET Framework 4.0 och högre, samt .NET Core/5/6.

**Q:** Kan jag använda Aspose.GIS för kommersiella projekt?  
**A:** Absolut. En kommersiell licens krävs för produktionsanvändning, men en gratis provversion finns tillgänglig för utvärdering.

**Q:** Stöder Aspose.GIS andra rumsliga dataformat?  
**A:** Ja, det fungerar med ESRI Shapefile, GeoJSON, KML och många fler format.

**Q:** Var kan jag ladda ner en gratis provversion?  
**A:** Du kan ladda ner en gratis provversion av Aspose.GIS från [här](https://releases.aspose.com/).

**Q:** Hur får jag hjälp om jag stöter på problem?  
**A:** Posta dina frågor på Aspose.GIS‑community‑[forum](https://forum.aspose.com/c/gis/33) där både Aspose‑personal och community‑medlemmar kan hjälpa till.

---

**Senast uppdaterad:** 2026-04-09  
**Testat med:** Aspose.GIS för .NET (senaste version)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}