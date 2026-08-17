---
date: 2026-05-31
description: Lär dig hur du skapar GeoJSON, konfigurerar GeoJSON-alternativ och lägger
  till ett objekt i ett lager med Aspose.GIS för .NET. Följ den här steg‑för‑steg‑guiden.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Ställ in linjäriseringstolerans
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Hur man skapar GeoJSON med tolerans i Aspose.GIS för .NET
url: /sv/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar GeoJSON med tolerans Aspose.GIS för .NET

## Introduktion
If you want to **learn how to create GeoJSON** files, control curve precision, and export the result as a ready‑to‑use document, Aspose.GIS for .NET makes it straightforward. In this tutorial you’ll discover how to configure GeoJSON options, set the linearization tolerance, and **add feature to layer** objects while keeping the code clean and production‑ready.

## Snabba svar
- **Vad betyder “create vector layer”?** Det skapar ett nytt GIS‑vektordataset (t.ex. en GeoJSON‑fil) som kan lagra geometrier och attribut.  
- **Hur ställer jag in lineariseringstolerans?** Ställ in egenskapen `LinearizationTolerance` på en `GeoJsonOptions`‑instans innan du skapar lagret.  
- **Kan jag exportera en GeoJSON‑fil direkt?** Ja—använd `VectorLayer.Create` med drivrutinen `Drivers.GeoJson` och de konfigurerade alternativen.  
- **Behöver jag en licens?** En giltig Aspose.GIS‑licens låser upp alla funktioner; en tillfällig utvärderingsnyckel fungerar för testning.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är “create vector layer”?
Creating a vector layer means initializing a new GIS container (such as a GeoJSON file) that can hold points, lines, polygons, and associated attribute data. This layer becomes the target for any geometry you construct and any attributes you attach.

## Varför konfigurera GeoJSON‑alternativ?
Configuring GeoJSON options—especially the **linearization tolerance**—ensures that curved geometries (e.g., `CircularString`) are approximated with a precision that meets your application's accuracy requirements. Proper configuration reduces file size while preserving visual fidelity, which is critical when the GeoJSON is consumed by web maps or spatial analytics tools.

## Förutsättningar
Before we start, make sure you have:

1. **Visual Studio** (any recent version).  
2. **Aspose.GIS license** (or a temporary evaluation key).  
3. **Aspose.GIS for .NET** library referenced in your project.  
4. Basic familiarity with **C#**.

## Importera namnrymder
First, import the required namespaces so the compiler knows where to find the GIS classes:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Steg‑för‑steg guide

### Steg 1: Konfigurera GeoJSON‑alternativ (hur man ställer in tolerans)
`GeoJsonOptions` specifies the serialization settings used when writing GeoJSON files.  
`GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including linearization tolerance, coordinate precision, and other output settings.  
We’ll create a `GeoJsonOptions` object and tell Aspose.GIS how close the linearized geometry must be to the original curve.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Steg 2: Definiera utdatavägen (hur man exporterar GeoJSON)
Specify the full file path where the resulting GeoJSON will be saved. Ensure the folder exists and the application has write permissions.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Steg 3: **Create Vector Layer** med de konfigurerade alternativen
The `VectorLayer` class represents a GIS container that can read and write spatial data.  
`Drivers.GeoJson` is the driver identifier for writing GeoJSON format files.  
Using `VectorLayer.Create` together with the `Drivers.GeoJson` driver and the previously configured `GeoJsonOptions` creates a new GeoJSON file ready for feature insertion.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Steg 4: Konstruera en geometri (t.ex. en cirkulär sträng)
`CircularString` is a curved line geometry that Aspose.GIS can linearize based on the tolerance you set. You can replace this with any valid WKT representation such as `POINT`, `LINESTRING`, or `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Steg 5: **Add Feature to Layer** och spara
`Feature` is the object that couples a geometry with attribute data. After creating a `Feature` instance, assign the geometry, optionally add attribute values, and call `layer.Add(feature)` to persist it. When the `using` block ends, the layer is automatically written to the file defined in `path`.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

When the `using` block ends, the layer is automatically written to the file defined in `path`, giving you a ready‑to‑use GeoJSON file.

## Vanliga problem & tips
- **Felaktig sökväg** – Verify the directory exists and you have write permissions.  
- **Tolerans för låg** – Setting `LinearizationTolerance` to a very small value can increase file size dramatically; a tolerance of 0.001 usually balances precision and size.  
- **Licensfel** – If you see licensing warnings, ensure the license file is loaded before any Aspose.GIS calls.  
- **Prestanda‑anmärkning** – Aspose.GIS supports processing of files up to 2 GB without loading the entire document into memory, thanks to its streaming architecture.

## Vanliga frågor

**Q: Är Aspose.GIS för .NET kompatibel med andra .NET‑ramverk?**  
A: Ja, den fungerar med .NET Framework 4.5+, .NET Core 3.1+, och .NET 5/6/7.

**Q: Kan jag använda Aspose.GIS i kommersiella projekt?**  
A: Absolut. En kommersiell licens tar bort alla utvärderingsrestriktioner och ger full teknisk support.

**Q: Stöder Aspose.GIS andra GIS‑format förutom GeoJSON?**  
A: Ja, den stödjer över 30 format—inklusive Shapefile, KML, GML och CSV—vilket möjliggör sömlös konvertering mellan dem.

**Q: Finns det en provversion tillgänglig?**  
A: Du kan ladda ner en gratis 30‑dagars provversion från Aspose‑webbplatsen; den inkluderar alla funktioner.

**Q: Var kan jag få support?**  
A: Använd Aspose‑forum, den dedikerade supportportalen, eller länken “Contact Support” i produktens instrumentpanel.

## Slutsats
By following these steps you now know **how to create GeoJSON**, configure the linearization tolerance, and **add feature to layer** for seamless GeoJSON export. Explore additional geometry types, attribute handling, and bulk‑processing scenarios to fully leverage Aspose.GIS in your .NET GIS projects.

---

**Senast uppdaterad:** 2026-05-31  
**Testat med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man konverterar GeoJSON – Aspose.GIS för .NET](/gis/net/geo-data-conversion/)
- [Skapa vektorlagring, begränsa precision med Aspose.GIS för .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Skapa vektorlagring i File GDB – Aspose.GIS .NET-handledning](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}