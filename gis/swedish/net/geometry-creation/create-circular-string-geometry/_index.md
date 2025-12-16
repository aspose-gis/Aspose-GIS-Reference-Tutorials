---
date: 2025-12-12
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

## Introduction
Om du bygger en GIS‑applikation på .NET‑plattformen är första steget ofta **att skapa vektorlager**‑objekt som lagrar dina rumsliga funktioner. Aspose.GIS för .NET gör denna process enkel och låter dig berika dessa lager med avancerade geometrier såsom cirkulära strängar. I den här handledningen kommer du att lära dig exakt hur du skapar ett vektorlager, lägger till en cirkulär stränggeometri och sparar resultatet som en Shapefile – allt med ren, produktionsklar C#‑kod.

## Quick Answers
- **Vad betyder “create vector layer”?** Det skapar en ny behållare (lager) som kan hålla rumsliga funktioner som punkter, linjer eller polygoner.  
- **Vilken klass representerar en cirkulär sträng?** `CircularString` från `Aspose.Gis.Geometries`.  
- **Kan jag spara lagret som en Shapefile?** Ja – använd `Drivers.Shapefile` när du skapar lagret.  
- **Behöver jag en licens för utveckling?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create vector layer”?
Ett vektorlager är en logisk gruppering av vektorfunktioner (punkter, linjer, polygoner) som lagras i en enda datakälla. I Aspose.GIS instansierar du ett lager genom att anropa `VectorLayer.Create`, ange målfilens sökväg och önskad drivrutin (t.ex. Shapefile). När lagret finns kan du lägga till funktioner, tilldela geometrier och utföra rumsliga operationer.

## Why add a circular string?
Cirkulära strängar är en typ av **linjär geometri** som approximerar bågar med en sekvens av punkter. De är användbara för att representera böjda vägar, flodsvängar eller någon funktion där en jämn kurva krävs utan att behöva många små linjesegment.

## Prerequisites
Innan du börjar, se till att du har:

- **.NET Framework eller .NET Core** installerat på din maskin.  
- **Aspose.GIS för .NET**‑biblioteket – ladda ner det från den officiella webbplatsen **[here](https://releases.aspose.com/gis/net/)**.  
- En IDE såsom **Visual Studio** eller **JetBrains Rider**.  
- Grundläggande kunskap om **C#**‑programmering.

## Import Namespaces
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

## Step‑by‑Step Guide

### Step 1: Define the output file path
Set the location where the Shapefile will be written.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Replace `"Your Document Directory"` with the actual folder path on your system.

### Step 2: **Create vector layer**
Open a `VectorLayer` using the `Create` method. This is the core of the **create vector layer** operation.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Step 3: Construct a new feature
A feature represents a single spatial record inside the layer.

```csharp
    var feature = layer.ConstructFeature();
```

### Step 4: Build the circular string geometry
Add the points that define the curved shape. The sequence of points creates an arc that starts and ends at the same location, forming a closed circular string.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Step 5: Assign geometry and add the feature to the layer
Link the geometry to the feature and store it in the layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

When the `using` block ends, the layer is automatically flushed to the Shapefile on disk.

## Common Issues & Solutions
| Problem | Lösning |
|-------|----------|
| **Filväg ogiltig** | Se till att katalogen finns och att du har skrivbehörighet. |
| **CircularString visas som en rak linje** | Verifiera att punkterna läggs till i rätt ordning; den första och sista punkten bör vara identiska för en sluten form. |
| **Licensundantag** | Använd en tillfällig licens under utveckling eller köp en full licens för produktionsbruk. |

## Frequently Asked Questions

### Är Aspose.GIS för .NET kompatibel med alla versioner av .NET Framework?
Ja, Aspose.GIS för .NET är designad för att fungera med ett brett spektrum av .NET‑versioner, från Framework 4.5 upp till de senaste .NET 8‑utgåvorna.

### Kan jag integrera Aspose.GIS för .NET med andra GIS‑bibliotek?
Absolut! Du kan läsa data med andra bibliotek, manipulera dem med Aspose.GIS och sedan skriva tillbaka dem, tack vare dess flexibla API.

### Stöder Aspose.GIS för .NET visualisering av rumsliga data?
Ja, biblioteket innehåller renderingsverktyg som låter dig generera kartor och visuella representationer av dina geometrier.

### Finns det ett community‑forum där jag kan få hjälp med Aspose.GIS för .NET?
Ja, du kan besöka Aspose.GIS‑forumet **[here](https://forum.aspose.com/c/gis/33)** för att ställa frågor och dela erfarenheter.

### Kan jag få en tillfällig licens för att utvärdera Aspose.GIS för .NET?
Självklart! En tillfällig utvärderingslicens finns tillgänglig **[here](https://purchase.aspose.com/temporary-license/)**.

### Hur lägger jag till mer komplexa geometrier (t.ex. MultiLineString) i samma lager?
Skapa det lämpliga geometriska objektet (t.ex. `MultiLineString`), fyll det med enskilda `LineString`‑objekt, tilldela det till `feature.Geometry` och lägg till funktionen precis som vi gjorde med den cirkulära strängen.

## Conclusion
Genom att följa dessa steg vet du nu hur du **skapar vektorlager**‑objekt och berikar dem med en cirkulär stränggeometri med hjälp av Aspose.GIS för .NET. Denna grund låter dig bygga rikare GIS‑lösningar – oavsett om du kartlägger transportnät, visualiserar miljödata eller utvecklar anpassade verktyg för rumslig analys.

---

**Last Updated:** 2025-12-12  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}