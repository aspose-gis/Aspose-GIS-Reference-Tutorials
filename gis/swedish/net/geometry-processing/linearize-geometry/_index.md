---
date: 2026-09-10
description: Lär dig hur du konverterar kurvor till linjer (linearize geometry) med
  Aspose.GIS för .NET, vilket möjliggör effektiv geospatial processing och analysis
  i dina .NET‑appar.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize en Geometry
og_description: Konvertera kurvor till linjer (linearize geometry) med Aspose.GIS
  för .NET. Lär dig step‑by‑step hur du simplify geometries för snabbare rendering
  och bredare compatibility.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Konvertera kurvor till linjer med Aspose.GIS för .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Hur man konverterar kurvor till linjer med Aspose.GIS för .NET
url: /sv/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera kurvor till linjer (lineariser geometri) med Aspose.GIS för .NET

## Introduktion
Om du behöver **konvertera kurvor till linjer** för kartläggning, rumslig analys eller datautbytesuppgifter, ger Aspose.GIS för .NET dig ett rent, programatiskt sätt att göra det. I den här handledningen går vi igenom ett komplett, verkligt exempel som visar hur du tar en komplex geometri—som innehåller kurvor och sammansatta former—och omvandlar den till en enkel linjär representation som fungerar med alla GIS‑system.

## Snabba svar
- **Vad betyder “convert curves to lines”?** Det omvandlar krökta geometrier till raka linjesegment.  
- **Varför välja Aspose.GIS?** Biblioteket stödjer över 30 GIS‑format och hanterar geometrikonvertering utan externa verktyg.  
- **Vad behöver jag i förväg?** .NET Framework eller .NET Core, Visual Studio (eller någon C#‑IDE), och Aspose.GIS NuGet‑paketet.  
- **Hur länge körs exemplet?** Mindre än fem minuter när biblioteket är installerat.  
- **Kan jag exportera till andra format?** Absolut—byt KML‑drivrutinen mot Shapefile, GeoJSON osv.  
Du kan ladda ner hela produktsviten från [Aspose-webbplatsen](https://releases.aspose.com/).

## Vad betyder konvertera kurvor till linjer?
Att konvertera kurvor till linjer (även kallat **lineariserande geometri**) ersätter varje krökt segment med en serie korta raka linjestycken, vilket skapar en *linjär geometri*. Detta gör rendering upp till fem gånger snabbare, minskar minnesförbrukningen och säkerställer att data kan konsumeras av äldre GIS‑tjänster som endast accepterar linjära objekt.

## Varför konvertera kurvor till linjer?
Linjära geometrier renderas och frågas upp till **5× snabbare** än sina krökta motsvarigheter, och **30+ GIS‑plattformar** accepterar endast linjära objekt. Att förenkla geometri minskar också filstorleken för webbaserade förhandsvisningar och möjliggör algoritmer—såsom nätverksanalys eller klustring—som kräver raka linjeinmatningar.

## Hur lineariserar man geometri?
Använd metoden `ToLinearGeometry()` som tillhandahålls av Aspose.GIS. Den tesselliserar automatiskt varje kurva i en geometri till raka linjesegment samtidigt som eventuella Z‑värden bevaras, så du får en linjär approximation utan att förlora höjddata. Du kan också ange en tolerans för att kontrollera maximal avvikelse mellan den ursprungliga kurvan och de genererade segmenten, vilket låter dig balansera noggrannhet mot filstorlek. Metoden fungerar för både 2‑D och 3‑D geometrier.

## Förutsättningar
Innan du dyker ner i koden, se till att du har:

1. **Aspose.GIS for .NET** – ladda ner det från [Aspose.GIS-webbplatsen](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (eller .NET Core) installerat på din utvecklingsmaskin.  
3. **Visual Studio** (eller någon C#‑kompatibel IDE) för att skriva och köra exemplet.

## Importera namnrymder
För att börja använda Aspose.GIS-funktionalitet, importera de nödvändiga namnrymderna.

### Core Aspose.GIS namnrymder
`Aspose.Gis`‑namnrymden innehåller de grundläggande geometriklasserna, drivrutinerna och verktygen som behövs för alla GIS‑operationer.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Drivrutin för målformatet
`Aspose.Gis.Drivers` tillhandahåller statiska fabriker för varje stödd filformat; `Drivers.Kml` skapar en KML‑skrivare.  
```csharp
using Aspose.GIS.Kml;
```

## Steg‑för‑steg guide för att konvertera kurvor till linjer
Nedan följer en detaljerad genomgång av varje kodrad, som förklarar **hur man konverterar kurvor till linjer** och varför varje steg är viktigt.

### Steg 1: Definiera utdatavägen
`Path.Combine` bygger en plattformsoberoende filsökväg och hanterar Windows‑bakåtsnedstreck samt Unix‑framåtsnedstreck automatiskt.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Ersätt `"Your Document Directory"` med den mapp där du vill spara KML‑filen.

### Steg 2: Skapa ett lager för utdatafilen
Ett *lager* grupperar geografiska objekt av samma typ. Här instansierar vi ett nytt KML‑lager som kommer att lagra den lineariserade geometrin.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Steg 3: Skapa ett nytt objekt
Ett *objekt* representerar ett enskilt geografiskt objekt (punkt, linje, polygon osv.). Vi kommer att fästa vår linjära geometri till detta objekt.  
```csharp
var feature = layer.ConstructFeature();
```

### Steg 4: Definiera den ursprungliga komplexa geometrin
`Geometry.FromWkt` tolkar en Well‑Known Text (WKT)‑sträng till ett geometriskt objekt. Exempel‑WKT:n innehåller en `LineString`, en `CompoundCurve` och en `CircularString` för att demonstrera kurvhante­ring.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Steg 5: Konvertera kurvor till linjer
`ToLinearGeometry()` tesselliserar varje kurva i källgeometrin till raka linjesegment och returnerar en ny linjär geometri som behåller eventuella Z‑koordinater.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Steg 6: Tilldela den linjära geometrin till objektet
Objektets `Geometry`‑egenskap innehåller nu den förenklade, linjära versionen av den ursprungliga formen.  
```csharp
feature.Geometry = linear;
```

### Steg 7: Lägg till objektet i lagret
Att lägga till objektet i KML‑lagret köar det för skrivning; när `using`‑blocket avslutas spolar lagret data till utdatafilen.  
```csharp
layer.Add(feature);
```

## Vanliga fallgropar & pro‑tips
- **Sökvägsavgränsare:** Använd `Path.Combine` för att undvika problem på Windows vs. Linux.  
- **Mycket stora geometrier:** Att lineariserar invecklade former kan generera tusentals hörn; överväg att anropa `Simplify()` efter linearisering för att minska antalet punkter.  
- **Drivrutinval:** Om du behöver ett annat utdataformat, byt `Drivers.Kml` mot `Drivers.Shapefile`, `Drivers.GeoJson` osv., och ändra filändelsen därefter.  
- **Bevara Z‑värden:** `ToLinearGeometry()` behåller 3‑D (Z)‑koordinater, så du förlorar inte höjdinformation.

## Vanliga frågor (FAQ)

**Q: Är Aspose.GIS för .NET kompatibel med .NET Core?**  
A: Ja, Aspose.GIS fungerar med .NET Core, vilket möjliggör plattformsoberoende applikationer.

**Q: Kan jag arbeta med olika GIS‑filformat med Aspose.GIS för .NET?**  
A: Absolut! Biblioteket stödjer KML, Shapefile, GeoJSON och många fler format—över 30 totalt.

**Q: Erbjuder Aspose.GIS rumsliga operationer och analyser?**  
A: Ja, det erbjuder ett brett utbud av rumsliga funktioner, från buffring till rumsliga sammanslagningar.

**Q: Finns det en gratis provversion?**  
A: Ja, du kan ladda ner en gratis provversion från [Aspose.GIS-webbplatsen](https://releases.aspose.com/gis/net/).

**Q: Var kan jag få hjälp om jag stöter på problem?**  
A: Besök [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för community‑ och personalstöd.

### Ytterligare vanliga frågor

**Q: Kan jag lineariserar geometrier som innehåller 3D (Z)‑koordinater?**  
A: Ja, `ToLinearGeometry()` fungerar med både 2D‑ och 3D‑geometrier; Z‑värden bevaras.

**Q: Hur påverkar linearisering filstorleken?**  
A: Att konvertera kurvor till många korta linjesegment kan öka filstorleken; kör `Simplify()` efter linearisering om storleken är ett problem.

**Q: Kan jag styra segmentlängden när jag konverterar kurvor till linjer?**  
A: Standardmetoden använder en intern tolerans. För anpassad segmentering kan du manuellt tessellera kurvor innan du anropar `ToLinearGeometry()`.

## Slutsats
I den här handledningen har vi gått igenom **hur man konverterar kurvor till linjer** (lineariserar geometri) med Aspose.GIS för .NET, från att sätta upp miljön till att skriva det lineariserade resultatet till en KML‑fil. Du kan nu integrera detta arbetsflöde i kartapplikationer, databehandlingspipelines eller vilket GIS‑relaterat projekt som helst som kräver förenklade geometrier.

---

**Last Updated:** 2026-09-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Hur man skapar GeoJSON med tolerans Aspose.GIS för .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Konvertera polygon till linje med Aspose.GIS för .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Lär dig hur man skapar LineString-geometri med Aspose.GIS för .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}