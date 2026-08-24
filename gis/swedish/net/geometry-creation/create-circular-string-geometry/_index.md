---
date: 2026-08-24
description: Lär dig hur du skapar vector layer .NET och lägger till circular string
  geometry med Aspose.GIS – ett snabbt, produktionsklart sätt att bygga GIS-applikationer.
keywords:
- create vector layer .net
- circular string geometry
- Aspose.GIS .NET
- GIS vector layer
- C# geometry
lastmod: 2026-08-24
linktitle: Skapa Circular String Geometry
og_description: Lär dig hur du skapar vector layer .NET och lägger till circular string
  geometry med Aspose.GIS – ett snabbt, produktionsklart sätt att bygga GIS-applikationer.
og_image_alt: Tutorial showing how to create a vector layer and circular string geometry
  in Aspose.GIS for .NET
og_title: Skapa vector layer .NET med circular string geometry
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create vector layer .NET and add circular string geometry
    with Aspose.GIS – a fast, production‑ready way to build GIS applications.
  headline: Create vector layer .NET with circular string geometry
  type: TechArticle
- description: Learn how to create vector layer .NET and add circular string geometry
    with Aspose.GIS – a fast, production‑ready way to build GIS applications.
  name: Create vector layer .NET with circular string geometry
  steps:
  - name: Define the output file path
    text: Set the location where the Shapefile will be written. Use an absolute or
      relative path that your application can write to. Replace `"Your Document Directory"`
      with the actual folder path on your system.
  - name: Create vector layer
    text: '`VectorLayer.Create` opens (or creates) a new vector layer backed by the
      specified driver. This is the core of the **create vector layer .NET** operation.'
  - name: Construct a new feature
    text: A feature represents a single spatial record inside the layer. The `Feature`
      class holds attribute data and a geometry object.
  - name: Build the circular string geometry
    text: '`CircularString` is the class that models an arc‑based line. You add points
      with `AddPoint(x, y)`; the first and last points should be identical for a closed
      shape.'
  - name: Assign geometry and add the feature to the layer
    text: Link the geometry to the feature and store it in the layer. When the `using`
      block ends, the layer is automatically flushed to the Shapefile on disk. When
      the `using` block ends, the layer is automatically flushed to the Shapefile
      on disk.
  type: HowTo
- questions:
  - answer: It creates a new container (layer) that can hold spatial features like
      points, lines, or polygons.
    question: What does “create vector layer” mean?
  - answer: '`CircularString` from `Aspose.Gis.Geometries`.'
    question: Which class represents a circular string?
  - answer: Yes – use `Drivers.Shapefile` when creating the layer.
    question: Can I save the layer as a Shapefile?
  - answer: A temporary license works for evaluation; a full license is required for
      production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create vector layer
- circular string
- Aspose.GIS
- .NET GIS
- C# geometry
title: Skapa vector layer .NET med circular string geometry
url: /sv/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager .NET med cirkulär stränggeometri

## Introduktion
Om du bygger en GIS‑applikation på .NET‑plattformen är första steget ofta **to create vector layer .NET**‑objekt som lagrar dina rumsliga funktioner. Aspose.GIS for .NET gör denna process enkel och låter dig berika dessa lager med avancerade geometrier såsom cirkulära strängar. I den här handledningen kommer du att lära dig exakt hur du **create vector layer**, **add circular string**‑geometri och sparar resultatet som en Shapefile — allt med ren, produktionsklar C#‑kod.

## Snabba svar
- **Vad betyder “create vector layer”?** Det skapar en ny behållare (lager) som kan hålla rumsliga funktioner som punkter, linjer eller polygoner.  
- **Vilken klass representerar en circular string?** `CircularString` från `Aspose.Gis.Geometries`.  
- **Kan jag spara lagret som en Shapefile?** Ja – använd `Drivers.Shapefile` när du skapar lagret.  
- **Behöver jag en licens för utveckling?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är “create vector layer”?
Ett vektorlager är en logisk gruppering av vektorfunktioner — punkter, linjer eller polygoner — som lagras tillsammans i en enda datakälla. Det fungerar som en behållare som låter dig hantera, fråga och bestå rumsliga poster effektivt. I Aspose.GIS skapar du ett genom att anropa `VectorLayer.Create` med målfilens sökväg och en drivrutin såsom Shapefile.

## Varför lägga till en circular string?
Circular strings låter dig modellera släta bågar med mycket färre hörn än en traditionell polylinje. **De är idealiska för att representera kurviga vägar, flodböjar eller någon funktion där en sann kurva krävs utan att öka filstorleken.** Att använda en circular string minskar antalet lagrade punkter med upp till 80 % jämfört med en tät line‑string‑approximation, vilket förbättrar både lagringseffektivitet och renderingsprestanda i de flesta GIS‑visare.

## Förutsättningar
- **.NET Framework eller .NET Core** installerat på din maskin.  
- **Aspose.GIS for .NET**‑biblioteket – ladda ner det från den officiella webbplatsen **[download Aspose.GIS for .NET](https://releases.aspose.com/gis/net/)**.  
- En IDE såsom **Visual Studio** eller **JetBrains Rider**.  
- Grundläggande kunskap om **C#**‑programmering.

## Importera namnrymder
Lägg till de nödvändiga namnrymderna i din C#‑fil:

`Aspose.Gis`‑namnrymden innehåller de grundläggande GIS‑typerna, medan `Aspose.Gis.Geometries` tillhandahåller geometriklasser såsom `CircularString`. Att importera dem gör API‑et tillgängligt i hela filen.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg‑för‑steg‑guide

### Steg 1: Definiera sökvägen för utdatafilen
Ange platsen där Shapefile‑filen ska skrivas. Använd en absolut eller relativ sökväg som din applikation kan skriva till.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Ersätt `"Your Document Directory"` med den faktiska mappens sökväg på ditt system.

### Steg 2: Skapa vektorlager
`VectorLayer.Create` öppnar (eller skapar) ett nytt vektorlager som stöds av den angivna drivrutinen. Detta är kärnan i **create vector layer .NET**‑operationen.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Steg 3: Konstruera ett nytt objekt
Ett objekt representerar en enskild rumslig post i lagret. `Feature`‑klassen innehåller attributdata och ett geometriskt objekt.

```csharp
    var feature = layer.ConstructFeature();
```

### Steg 4: Bygg circular string‑geometrin
`CircularString` är klassen som modellerar en bågbaserad linje. Du lägger till punkter med `AddPoint(x, y)`; den första och sista punkten bör vara identiska för en sluten form.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Steg 5: Tilldela geometri och lägg till objektet i lagret
Koppla geometrin till objektet och lagra det i lagret. När `using`‑blocket avslutas skrivs lagret automatiskt till Shapefile‑filen på disken.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

När `using`‑blocket avslutas skrivs lagret automatiskt till Shapefile‑filen på disken.

## Vanliga problem & lösningar
| Issue | Solution |
|-------|----------|
| **Ogiltig filsökväg** | Se till att katalogen finns och att du har skrivbehörighet. |
| **CircularString visas som en rak linje** | Verifiera att punkterna läggs till i rätt ordning; den första och sista punkten bör vara identiska för en sluten form. |
| **Licensundantag** | Använd en tillfällig licens under utveckling eller köp en full licens för produktionsbruk. |
| **Prestandaförsämring på stora dataset** | Aspose.GIS strömmar data, så du kan säkert bearbeta filer med 500 + objekt utan att ladda hela datasetet i minnet. |

## Vanliga frågor

### Är Aspose.GIS for .NET kompatibel med alla versioner av .NET Framework?
Ja, Aspose.GIS for .NET är designat för att fungera med ett brett spektrum av .NET‑versioner, från Framework 4.5 upp till de senaste .NET 8‑utgåvorna.

### Kan jag integrera Aspose.GIS for .NET med andra GIS‑bibliotek?
Absolut! Du kan läsa data med andra bibliotek, manipulera dem med Aspose.GIS och sedan skriva tillbaka dem, tack vare dess flexibla API.

### Stöder Aspose.GIS for .NET visualisering av rumsliga data?
Ja, biblioteket innehåller renderingsverktyg som låter dig generera kartor och visuella representationer av dina geometrier.

### Finns det ett community‑forum där jag kan söka hjälp med Aspose.GIS for .NET?
Ja, du kan besöka Aspose.GIS‑forumet **[Aspose GIS forum](https://forum.aspose.com/c/gis/33)** för att ställa frågor och dela erfarenheter.

### Kan jag få en tillfällig licens för att utvärdera Aspose.GIS for .NET?
Självklart! En tillfällig utvärderingslicens finns tillgänglig **[temporary license page](https://purchase.aspose.com/temporary-license/)**.

### Hur lägger jag till mer komplexa geometrier (t.ex. MultiLineString) i samma lager?
Skapa det lämpliga geometriska objektet (t.ex. `MultiLineString`), fyll det med enskilda `LineString`‑objekt, tilldela det till `feature.Geometry` och lägg till objektet precis som vi gjorde med circular string.

## FAQ (snabbreferens)

**Q:** Hur skapar jag **create vector layer** programmässigt?  
**A:** Anropa `VectorLayer.Create(path, Drivers.Shapefile)` (eller en annan drivrutin) inom ett `using`‑block.

**Q:** Vilken metod lägger till punkter i en circular string?  
**A:** Använd `circularString.AddPoint(x, y)` för varje koordinat.

**Q:** Kan jag lagra flera geometrier i samma lager?  
**A:** Ja, konstruera ett nytt objekt för varje geometri och lägg till det med `layer.Add(feature)`.

**Q:** Vad ska jag göra om Shapefile‑filen inte skapas?  
**A:** Verifiera att utmatningskatalogen finns, att du har skrivbehörighet och att drivrutinen (`Drivers.Shapefile`) är korrekt refererad.

**Q:** Krävs en licens för utvärderingsversionen?  
**A:** En tillfällig licens räcker för utveckling och testning; en full licens behövs för produktionsdistributioner.

## Slutsats
Genom att följa dessa steg vet du nu hur du **create vector layer**‑objekt och berikar dem med en **circular string**‑geometri med hjälp av Aspose.GIS for .NET. Denna grund låter dig bygga rikare GIS‑lösningar — oavsett om du kartlägger transportnät, visualiserar miljödata eller utvecklar anpassade verktyg för rumslig analys. Nästa steg är att utforska andra geometrityper såsom `MultiPolygon` eller experimentera med rumslig indexering för att förbättra frågeprestanda.

---

**Senast uppdaterad:** 2026-08-24  
**Testad med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar vektorlager med SRS med Aspose.GIS för .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Skapa vektorlager och kurvpolygon med Aspose.GIS](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Lär dig hur man skapar LineString‑geometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}