---
date: 2026-02-15
description: Lär dig hur du skapar ett vektorlager och lägger till cirkulär stränggeometri
  med Aspose.GIS för .NET – ett snabbt sätt att bygga GIS-applikationer.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Skapa vektorlager och cirkulär sträng i Aspose.GIS för .NET
url: /sv/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vektorlager och cirkulär stränggeometri med Aspose.GIS för .NET

## Introduktion
Om du bygger en GIS‑applikation på .NET‑plattformen är första steget ofta **to create vector layer**‑objekt som lagrar dina rumsliga funktioner. Aspose.GIS för .NET gör processen enkel och låter dig berika dessa lager med avancerade geometrier såsom cirkulära strängar. I den här handledningen kommer du att lära dig exakt hur du **create vector layer**, **add circular string**‑geometri och sparar resultatet som en Shapefile – allt med ren, produktionsklar C#‑kod.

## Snabba svar
- **Vad betyder “create vector layer”?** Skapar en ny behållare (lager) som kan hålla rumsliga funktioner som punkter, linjer eller polygoner.  
- **Vilken klass representerar en circular string?** `CircularString` från `Aspose.Gis.Geometries`.  
- **Kan jag spara lagret som en Shapefile?** Ja – använd `Drivers.Shapefile` när du skapar lagret.  
- **Behöver jag en licens för utveckling?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är “create vector layer”?
Ett vektorlager är en logisk gruppering av vektorfunktioner (punkter, linjer, polygoner) som lagras i en enda datakälla. I Aspose.GIS instansierar du ett lager genom att anropa `VectorLayer.Create` och ange målfilens sökväg samt önskad drivrutin (t.ex. Shapefile). När lagret finns kan du lägga till funktioner, tilldela geometrier och utföra rumsliga operationer.

## Varför lägga till en circular string?
Circular strings är en typ av **linear geometry** som approximerar bågar med en sekvens av punkter. De är användbara för att representera krökta vägar, flodböjar eller någon funktion där en jämn kurva krävs utan att behöva många små linjesegment.

## Förutsättningar
- **.NET Framework eller .NET Core** installerat på din maskin.  
- **Aspose.GIS for .NET**‑biblioteket – ladda ner det från den officiella webbplatsen **[here](https://releases.aspose.com/gis/net/)**.  
- En IDE såsom **Visual Studio** eller **JetBrains Rider**.  
- Grundläggande kunskap om **C#**‑programmering.

## Importera namnrymder
Add the required namespaces to your C# file:

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
Set the location where the Shapefile will be written.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Ersätt `"Your Document Directory"` med den faktiska mappens sökväg på ditt system.

### Steg 2: **Create vector layer**
Open a `VectorLayer` using the `Create` method. This is the core of the **create vector layer** operation.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Steg 3: Skapa ett nytt feature
A feature represents a single spatial record inside the layer.

```csharp
    var feature = layer.ConstructFeature();
```

### Steg 4: Bygg circular string‑geometrin
Add the points that define the curved shape. The sequence of points creates an arc that starts and ends at the same location, forming a closed circular string.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Steg 5: Tilldela geometri och lägg till feature i lagret
Link the geometry to the feature and store it in the layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

När `using`‑blocket avslutas skrivs lagret automatiskt till Shapefile‑filen på disken.

## Vanliga problem & lösningar

| Problem | Lösning |
|-------|----------|
| **Filväg ogiltig** | Se till att katalogen finns och att du har skrivbehörighet. |
| **CircularString visas som en rak linje** | Verifiera att punkterna läggs till i rätt ordning; den första och sista punkten bör vara identiska för en sluten form. |
| **Licensundantag** | Använd en tillfällig licens under utveckling eller köp en full licens för produktionsanvändning. |

## Vanliga frågor

### Är Aspose.GIS för .NET kompatibel med alla versioner av .NET Framework?
Ja, Aspose.GIS för .NET är utformad för att fungera med ett brett spektrum av .NET‑versioner, från Framework 4.5 upp till de senaste .NET 8‑utgåvorna.

### Kan jag integrera Aspose.GIS för .NET med andra GIS‑bibliotek?
Absolut! Du kan läsa data med andra bibliotek, manipulera dem med Aspose.GIS och sedan skriva tillbaka dem, tack vare dess flexibla API.

### Stöder Aspose.GIS för .NET visualisering av rumsliga data?
Ja, biblioteket inkluderar renderingsverktyg som låter dig generera kartor och visuella representationer av dina geometrier.

### Finns det ett community‑forum där jag kan få hjälp med Aspose.GIS för .NET?
Ja, du kan besöka Aspose.GIS‑forumet **[here](https://forum.aspose.com/c/gis/33)** för att ställa frågor och dela erfarenheter.

### Kan jag få en tillfällig licens för att utvärdera Aspose.GIS för .NET?
Självklart! En tillfällig utvärderingslicens finns tillgänglig **[here](https://purchase.aspose.com/temporary-license/)**.

### Hur lägger jag till mer komplexa geometrier (t.ex. MultiLineString) i samma lager?
Skapa lämpligt geometriskt objekt (t.ex. `MultiLineString`), fyll det med enskilda `LineString`‑objekt, tilldela det till `feature.Geometry` och lägg till feature på samma sätt som vi gjorde med circular string.

## FAQ (Snabbreferens)

**Q:** Hur skapar jag **create vector layer** programatiskt?  
**A:** Anropa `VectorLayer.Create(path, Drivers.Shapefile)` (eller en annan drivrutin) inom ett `using`‑block.

**Q:** Vilken metod lägger till punkter i en circular string?  
**A:** Använd `circularString.AddPoint(x, y)` för varje koordinat.

**Q:** Kan jag lagra flera geometrier i samma lager?  
**A:** Ja, skapa ett nytt feature för varje geometri och lägg till det med `layer.Add(feature)`.

**Q:** Vad ska jag göra om Shapefile‑filen inte skapas?  
**A:** Kontrollera att utmatningskatalogen finns, att du har skrivbehörighet och att drivrutinen (`Drivers.Shapefile`) är korrekt refererad.

**Q:** Krävs en licens för utvärderingsversionen?  
**A:** En tillfällig licens räcker för utveckling och testning; en full licens behövs för produktionsdistribution.

## Slutsats
Genom att följa dessa steg vet du nu hur du **create vector layer**‑objekt och berikar dem med en **circular string**‑geometri med Aspose.GIS för .NET. Detta grundläggande kunskapsblock låter dig bygga rikare GIS‑lösningar – oavsett om du kartlägger transportnät, visualiserar miljödata eller utvecklar anpassade verktyg för rumslig analys.

**Senast uppdaterad:** 2026-02-15  
**Testad med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}