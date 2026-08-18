---
date: 2026-06-10
description: Lär dig hur du skapar linestring-geometri i .NET och konverterar geometri
  till WKB med Aspose.GIS för .NET och ExtendedPostGis-varianten.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Specificera WKB-variant vid översättning
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Skapa Linestring-geometri & WKB-variant i Aspose.GIS för .NET
url: /sv/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Linestring-geometri & WKB-variant i Aspose.GIS för .NET

## Introduktion
Om du behöver **create linestring geometry .NET** och sedan översätta den geometrin till ett binärt format, ger Aspose.GIS för .NET dig ett rent, högpresterande API som fungerar över .NET Framework, .NET Core och .NET 5/6+. I den här handledningen går vi igenom varje steg—från att importera namnrymder till att skriva en EWKB-fil—så att du kan bevara SRID‑information och integrera GIS‑data i PostgreSQL/PostGIS eller någon annan binärbaserad arbetsflöde utan krångel.

## Snabba svar
- **Vad står WKB för?** Well‑Known Binary, en kompakt binär representation av geometriska objekt.  
- **Vilken WKB-variant lagrar SRID?** `ExtendedPostGis` (EWKB) varianten bäddar in SRID direkt i den binära representationen.  
- **Behöver jag en licens?** En tillfällig eller full Aspose.GIS‑licens krävs för produktionsdistributioner.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, och .NET 5/6+.  
- **Hur lång tid tar implementeringen?** Vanligtvis under 10 minuter för ett grundexempel.

## Vad är en Linestring-geometri?
En linestring-geometri är en enkel form bestående av en ordnad lista med punkter som är förbundna med raka linjesegment. Det är den föredragna representationen för linjära funktioner såsom vägar, rörledningar eller flodförlopp i rumsliga databaser.

## Varför ange en WKB-variant?
Att använda rätt WKB-variant garanterar att kritisk metadata—särskilt Spatial Reference System Identifier (SRID)—följer med din geometri. `ExtendedPostGis` (EWKB)-varianten lagrar SRID i den binära nyttolasten, vilket möjliggör sömlös round‑tripping med PostGIS, Oracle Spatial eller något system som förväntar sig SRID‑medvetna binärer.

## Förutsättningar
Innan du börjar, se till att du har följande:

### Installera Aspose.GIS för .NET
1. Ladda ner Aspose.GIS: Besök [download link](https://releases.aspose.com/gis/net/) för att hämta det senaste paketet.  
2. Lägg till NuGet‑paketet i ditt projekt (t.ex. `Install-Package Aspose.GIS`).  

### Bekantskap med C#‑programmering
- Grundläggande förståelse för C#‑syntax och projektstruktur.  
- Förmåga att köra ett .NET‑konsol‑ eller klassbiblioteksprojekt.

## Importera namnrymder
`Aspose.GIS`‑namnrymden ger dig åtkomst till alla geometrirelaterade klasser.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Dessa namnrymder tillhandahåller den grundläggande GIS‑funktionaliteten, inklusive skapande av geometrier, transformation och binär serialisering.

## Hur skapar man linestring-geometri?
För att skapa en linestring, instansiera ett `Linestring`‑objekt med en ordnad lista av koordinatpar, sätt dess SRID om det behövs, och serialisera sedan till önskad WKB-variant. Processen involverar tre steg: bygga geometrin, välja `ExtendedPostGis`‑varianten för att behålla SRID, och skriva den resulterande byte‑arrayen till en fil.

### Steg 1: Skapa ett geometriskt objekt
`Geometry`‑klassen är Aspose.GIS:s bastyp som representerar alla rumsliga objekt i minnet. Linestring representerar en serie av sammankopplade punkter som bildar en linjär geometri.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
I detta steg instansierar vi ett `Linestring` med en samling av koordinatpar som modellerar ett enkelt vägssegment.

### Steg 2: Generera WKB-representation
`WkbVariant.ExtendedPostGis` är enum‑värdet som instruerar Aspose.GIS att inkludera SRID i den utgående binära representationen.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Här anropar vi `AsBinary`‑metoden, med EWKB‑varianten som argument, vilket returnerar en `byte[]` som innehåller den fullständiga binära representationen.

### Steg 3: Skriva till fil
`File.WriteAllBytes` skriver den binära arrayen till disk.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Den resulterande filen (`EWkbFile.ewkb`) kan importeras direkt till en PostGIS‑tabell med hjälp av funktionen `ST_GeomFromEWKB`.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|--------|----------|
| **Tom fil** | `Path.Combine` pekar på en icke‑existerande katalog. | Se till att mål katalogen finns eller skapa den med `Directory.CreateDirectory`. |
| **Fel SRID** | Att använda standardvärdet `WkbVariant.Standard` tar bort SRID. | Använd alltid `WkbVariant.ExtendedPostGis` när SRID‑bevarande krävs. |
| **Licensundantag** | Kör utan en giltig licens i produktion. | Applicera en tillfällig eller full licens innan du kör koden i en produktionsmiljö. |

## Vanliga frågor
**Q: Kan jag använda EWKB-filen med PostGIS?**  
A: Ja, `ExtendedPostGis`‑varianten producerar EWKB som inkluderar SRID, vilket PostGIS läser direkt via `ST_GeomFromEWKB`.  

**Q: Är det möjligt att läsa en WKB-fil tillbaka till ett geometriskt objekt?**  
A: Absolut. Använd `Geometry.FromBinary(byteArray)` för att rekonstruera geometrin från dess binära form.  

**Q: Stöder biblioteket andra geometri‑typer som polygoner?**  
A: Ja, Aspose.GIS hanterar punkter, linestrings, polygoner, multipolygoner och många fler rumsliga typer.  

**Q: Hur specificerar jag ett annat SRID när jag skapar geometrin?**  
A: Sätt `SRID`‑egenskapen på geometrin innan du anropar `AsBinary`, t.ex. `linestring.SRID = 4326;`.  

**Q: Kommer den här koden att fungera på .NET Core?**  
A: Ja, samma API fungerar över .NET Framework, .NET Core och .NET 5/6 utan modifiering.  

---

**Senast uppdaterad:** 2026-06-10  
**Testat med:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Översätta geometri till WKB-format med Aspose.GIS för .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Ange WKT-variant vid översättning med Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Skapa MultiLineString-geometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}