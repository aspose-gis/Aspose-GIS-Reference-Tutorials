---
date: 2026-09-15
description: Lär dig hur du tilldelar koordinatsystem, anger WKT-varianten och styr
  decimalprecision när du skapar punktgeometri i C# med Aspose.GIS för .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Ange WKT-variant vid översättning
og_description: Lär dig hur du tilldelar koordinatsystem, anger WKT-varianten och
  styr decimalprecision när du skapar punktgeometri i C# med Aspose.GIS för .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Tilldela koordinatsystem, ange WKT-variant med Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Tilldela koordinatsystem, ange WKT-variant med Aspose.GIS
url: /sv/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tilldela koordinatsystem, ange WKT-variant med Aspose.GIS

## Introduktion
I den här handledningen kommer du att lära dig hur du **tilldelar koordinatsystem**, väljer rätt WKT-variant och styr decimalprecision när du **skapar punktgeometri** i C# med Aspose.GIS för .NET. Oavsett om du bygger en karttjänst, utför rumslig analys eller utbyter data mellan GIS-plattformar, garanterar dessa inställningar att ditt resultat är både interoperabelt och lättläst. Låt oss gå igenom processen steg för steg.

## Snabba svar
- **Vad betyder “assign coordinate system”?** Det binder en geometri till ett specifikt koordinatreferenssystem såsom WGS‑84.  
- **Vilka WKT-varianter stöds?** Iso, SimpleFeatureAccessOutdated och ExtendedPostGis.  
- **Hur kan jag kontrollera decimalprecision?** Använd `NumericFormat`-enumet (`General`, `RoundTrip`, `Flat`).  
- **Behöver jag en licens för Aspose.GIS?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktionsanvändning.  
- **Vilka .NET-versioner är kompatibla?** .NET Framework 4.0+ och .NET Core/5/6+.

## Vad är “assign coordinate system”?
Att tilldela en rumslig referens (eller spatialt referenssystem, SRS) talar om för GIS-programvaran hur koordinatvärdena för en geometri ska tolkas, genom att koppla siffrorna till ett verkligt koordinatsystem såsom WGS‑84. Utan ett SRS har en punkts latitud‑longitud‑värden ingen verklig betydelse.

## Varför kontrollera WKT-varianten och numeriskt format?
Över 30 GIS-verktyg förväntar sig specifika WKT-syntaxer, så att välja rätt variant förhindrar importfel. Att ställa in numeriskt format minskar avrundningsbrus och håller resultatet koncist, vilket är särskilt viktigt när loggar eller filer parsas programmässigt.

## Förutsättningar
1. Aspose.GIS för .NET – ladda ner från [nedladdningssidan](https://releases.aspose.com/gis/net/).  
2. En .NET‑utvecklingsmiljö (Visual Studio, VS Code eller Rider).  
3. Grundläggande kunskap om C# och .NET‑ramverket.

## Importera namnrymder
Innan du använder några Aspose.GIS-klasser, importera de nödvändiga namnrymderna:

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

## Hur tilldelar man koordinatsystem till en punkt?
Läs in en `Point`-instans och fäst sedan ett spatialt referenssystem (SRS) med hjälp av `SpatialReference`-klassen. Detta tvåstegs‑mönster säkerställer att geometrin bär med sig metadata om sitt koordinatsystem vid export, så att efterföljande verktyg kan tolka koordinaterna korrekt. `Point`-klassen representerar en enskild plats definierad av X (longitude) och Y (latitude) koordinater.

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Steg 2: tilldela spatialt referenssystem (SRS)
Nu **tilldelar vi spatial referens** till punkten. `SpatialReference` representerar ett koordinatreferenssystem identifierat av ett SRID. Här använder vi det allmänt stödjade WGS‑84-systemet (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Steg 3: ange önskad WKT-variant
Välj den WKT-variant som matchar din efterföljande applikation:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Hur ställer man in decimalprecision för WKT-utdata?
Styr hur många siffror som visas i den slutgiltiga strängen med hjälp av `NumericFormat`‑enumet, som definierar formateringsregler såsom `General`, `RoundTrip` eller `Flat`. Att välja `RoundTrip` bevarar full koordinatnoggrannhet för round‑tripping‑scenarier, medan `General` ger en koncis representation som passar de flesta visualiseringsuppgifter. `NumericFormat`‑enumet styr hur koordinatsiffror formateras i WKT‑utdata.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Vanliga fallgropar & tips
- **Fallgrop:** Att glömma att sätta SRS innan du anropar `AsText` kan leda till att SRID‑information saknas.  
- **Tips:** Använd `NumericFormat.RoundTrip` när du behöver förlustfri round‑tripping av koordinater.  
- **Tips:** `Iso`‑varianten är den mest portabla; välj `ExtendedPostGis` endast när du behöver SRID inbäddat.

## Slutsats
Du vet nu hur du **tilldelar koordinatsystem**, väljer rätt WKT-variant och **ställer in decimalprecision** när du **skapar punktgeometri** med Aspose.GIS. Dessa kontroller ger dig flexibiliteten att uppfylla de exakta kraven för vilket GIS‑arbetsflöde som helst, från enkel visualisering till högprecisions‑rumslig analys.

## Vanliga frågor

**Q:** Är Aspose.GIS kompatibel med alla versioner av .NET?  
**A:** Ja, Aspose.GIS stödjer .NET Framework 4.0 och högre, samt .NET Core/5/6.

**Q:** Kan jag använda Aspose.GIS för kommersiella projekt?  
**A:** Absolut. En kommersiell licens krävs för produktionsanvändning, men en gratis provversion finns tillgänglig för utvärdering.

**Q:** Stöder Aspose.GIS andra rumsliga dataformat?  
**A:** Ja, den fungerar med över 30 format, inklusive ESRI Shapefile, GeoJSON, KML, CSV och många fler.

**Q:** Var kan jag ladda ner en gratis provversion?  
**A:** Du kan ladda ner en gratis provversion av Aspose.GIS från [Aspose.GIS gratis provnedladdningssida](https://releases.aspose.com/).

**Q:** Hur får jag hjälp om jag stöter på problem?  
**A:** Posta dina frågor på Aspose.GIS‑communityns [forum](https://forum.aspose.com/c/gis/33) där både Aspose‑personal och community‑medlemmar kan hjälpa till.

---

**Senast uppdaterad:** 2026-09-15  
**Testad med:** Aspose.GIS för .NET (senaste versionen)  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa ett vektorlager och ange dess spatiala referenssystem](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Hur man översätter geometri till WKT med Aspose.GIS för .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Hur man begränsar precision vid skrivning av geometrier med Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}