---
date: 2026-04-06
description: Lär dig hur du konverterar kurvor till linjer och linjäriserar geometri
  med Aspose.GIS för .NET, vilket möjliggör snabb geospatial bearbetning och analys
  i dina .NET‑applikationer.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Linearisa en geometri
second_title: Aspose.GIS .NET API
title: Konvertera kurvor till linjer med Aspose.GIS för .NET
url: /sv/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera kurvor till linjer med Aspose.GIS för .NET

## Introduktion
If you need to **convert curves to lines** for mapping, spatial analysis, or data‑exchange tasks, Aspose.GIS for .NET gives you a clean, programmatic way to do it. In this tutorial we’ll walk through a complete, real‑world example that shows you how to take a complex geometry—containing curves and compound shapes—and turn it into a simple linear representation that works with any GIS system.

## Snabba svar
- **Vad betyder linjärisering av en geometri?** Converting curves and complex shapes into straight‑line segments.  
- **Varför använda Aspose.GIS?** It supports dozens of GIS formats and handles geometry conversion without external tools.  
- **Förutsättningar?** .NET Framework or .NET Core, Visual Studio, and the Aspose.GIS library.  
- **Hur lång tid tar exemplet?** Under five minutes to run once the library is installed.  
- **Kan jag spara till andra format?** Yes—replace the KML driver with Shapefile, GeoJSON, etc.

## Vad är linjärisering av geometri?
Linearizing geometry means breaking down any curved or composite shape into a series of straight‑line segments (a “linear geometry”). This simplifies rendering, analysis, and interoperability with tools that only understand lines and points.

## Varför konvertera kurvor till linjer?
- **Prestanda:** Linear geometries are faster to render and query.  
- **Kompatibilitet:** Many GIS platforms (e.g., older map services) only accept linear features.  
- **Förenkling:** Useful for creating thumbnails, quick previews, or feeding data into algorithms that require linear input.

## Förutsättningar
Before diving into the code, make sure you have:

1. **Aspose.GIS for .NET** – download it from the [Aspose.GIS webbplats](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (or .NET Core) installed on your development machine.  
3. **Visual Studio** (or any C#‑compatible IDE) for writing and executing the sample.

## Importera namnrymder
To start using Aspose.GIS functionality, import the required namespaces.

### Steg 1: Importera Aspose.GIS Core-namnrymderna
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Steg 2: Importera drivrutinen för ditt målformat
For this example we’ll write the result to a KML file:
```csharp
using Aspose.GIS.Kml;
```

## Hur man konverterar kurvor till linjer – Steg‑för‑steg‑guide
Below is a detailed walk‑through of each line of code, explaining **how to convert curves to lines** and why each step matters.

### Steg 1: Definiera utdatavägen
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Replace `"Your Document Directory"` with the folder where you want the KML file saved.

### Steg 2: Skapa ett lager för utdatafilen
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
A *layer* is a container for geographic features. Here we create a new KML layer that will hold our linearized geometry.

### Steg 3: Skapa ett nytt objekt
```csharp
var feature = layer.ConstructFeature();
```
A *feature* represents a single geographic object (point, line, polygon, etc.). We’ll attach our linear geometry to this feature.

### Steg 4: Definiera den ursprungliga komplexa geometrin
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
We create a geometry from a Well‑Known Text (WKT) string. This example includes a `LineString`, a `CompoundCurve`, and a `CircularString`—perfect for demonstrating the conversion of curves to lines.

### Steg 5: Linjärisera geometrin
```csharp
var linear = geometry.ToLinearGeometry();
```
The `ToLinearGeometry()` method converts all curves into straight‑line segments, producing a *linear* version of the original geometry.

### Steg 6: Tilldela den linjära geometrin till objektet
```csharp
feature.Geometry = linear;
```
Now the feature holds the simplified, linear geometry.

### Steg 7: Lägg till objektet i lagret
```csharp
layer.Add(feature);
```
Finally, we add the feature to the KML layer, which writes the linear geometry to the output file when the `using` block ends.

## Vanliga fallgropar och tips
- **Sökvägsavgränsare:** Use `Path.Combine` for cross‑platform path building.  
- **Stora geometrier:** Linearizing very complex shapes can produce many vertices; consider using `Simplify()` after linearization if you need fewer points.  
- **Drivrutinval:** If you need a different output format, swap `Drivers.Kml` with `Drivers.Shapefile`, `Drivers.GeoJson`, etc., and adjust the file extension accordingly.

## Vanliga frågor (förbättrad)

**Q: Är Aspose.GIS för .NET kompatibel med .NET Core?**  
A: Yes, Aspose.GIS for .NET works with .NET Core, allowing you to build cross‑platform applications.

**Q: Kan jag arbeta med olika GIS-filformat med Aspose.GIS för .NET?**  
A: Absolutely! Aspose.GIS supports KML, Shapefile, GeoJSON, and many other formats.

**Q: Erbjuder Aspose.GIS stöd för rumsliga operationer och analyser?**  
A: Yes, it provides a wide range of spatial operations and analysis capabilities to handle complex geospatial tasks.

**Q: Finns en gratis provversion av Aspose.GIS för .NET?**  
A: Yes, you can download a free trial from the [Aspose website](https://releases.aspose.com/).

**Q: Var kan jag hitta hjälp och support för Aspose.GIS?**  
A: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for assistance from the community and Aspose support staff.

**Ytterligare frågor och svar**

**Q: Kan jag linjärisera geometrier som innehåller 3D (Z)-koordinater?**  
A: Yes, `ToLinearGeometry()` works with both 2D and 3D geometries; the Z values are preserved in the resulting line segments.

**Q: Hur påverkar linjärisering storleken på utdatafilen?**  
A: Converting curves to many short line segments can increase file size. Use `Simplify()` after linearization if file size is a concern.

**Q: Är det möjligt att kontrollera segmentlängden vid linjärisering?**  
A: The default method uses an internal tolerance. For custom segmentation, you can manually tessellate curves before calling `ToLinearGeometry()`.

## Slutsats
In this tutorial we covered **how to convert curves to lines** using Aspose.GIS for .NET, from setting up the environment to writing the linearized result to a KML file. You can now integrate this workflow into mapping applications, data‑processing pipelines, or any GIS‑related project that requires simplified geometries.

---

**Senast uppdaterad:** 2026-04-06  
**Testat med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}