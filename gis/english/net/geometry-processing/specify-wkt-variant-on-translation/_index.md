---
date: 2026-09-15
description: Learn how to assign coordinate system, set the WKT variant and control
  decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
images:
- /net/geometry-processing/specify-wkt-variant-on-translation/og-image.png
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Specify WKT Variant on Translation
og_description: Learn how to assign coordinate system, set the WKT variant and control
  decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Assign coordinate system, set WKT variant using Aspose.GIS
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
title: Assign coordinate system, set WKT variant using Aspose.GIS
url: /net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Assign coordinate system, set WKT variant using Aspose.GIS

## Introduction
In this tutorial you’ll learn how to **assign coordinate system**, choose the right WKT variant, and control decimal precision when you **create point geometry** in C# with Aspose.GIS for .NET. Whether you are building a mapping service, performing spatial analytics, or exchanging data between GIS platforms, these settings guarantee that your output is both interoperable and easy to read. Let’s walk through the process step by step.

## Quick answers
- **What does “assign coordinate system” mean?** It binds a geometry to a specific coordinate reference system such as WGS‑84.  
- **Which WKT variants are supported?** Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.  
- **How can I control decimal precision?** Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).  
- **Do I need a license for Aspose.GIS?** A free trial is available; a commercial license is required for production use.  
- **What .NET versions are compatible?** .NET Framework 4.0+ and .NET Core/5/6+.

## What is “assign coordinate system”?
Assigning a spatial reference (or spatial reference system, SRS) tells GIS software how to interpret the coordinate values of a geometry, linking the numbers to a real‑world coordinate system such as WGS‑84. Without an SRS, a point’s latitude‑longitude numbers have no real‑world meaning.

## Why control the WKT variant and numeric format?
Over 30 GIS tools expect specific WKT syntaxes, so selecting the proper variant prevents import errors. Setting numeric format reduces rounding noise and keeps the output concise, which is especially important when logs or files are parsed programmatically.

## Prerequisites
1. Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).  
2. A .NET development environment (Visual Studio, VS Code, or Rider).  
3. Basic familiarity with C# and the .NET framework.

## Import namespaces
Before using any Aspose.GIS classes, import the required namespaces:

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

## How to assign coordinate system to a point?
Load a `Point` instance, then attach a spatial reference system (SRS) using the `SpatialReference` class. This two‑step pattern ensures the geometry carries its coordinate system metadata when exported, allowing downstream tools to correctly interpret the coordinates. The `Point` class represents a single location defined by X (longitude) and Y (latitude) coordinates.

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Step 2: assign spatial reference system (SRS)
Now we **assign spatial reference** to the point. `SpatialReference` represents a coordinate reference system identified by an SRID. Here we use the widely‑supported WGS‑84 system (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Step 3: specify the desired WKT variant
Choose the WKT variant that matches your downstream application:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## How to set decimal precision for WKT output?
Control how many digits appear in the final string using the `NumericFormat` enum, which defines formatting rules such as `General`, `RoundTrip`, or `Flat`. Selecting `RoundTrip` preserves full coordinate fidelity for round‑tripping scenarios, while `General` provides a concise representation suitable for most visualisation tasks. The `NumericFormat` enum controls how coordinate numbers are formatted in the WKT output.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Common pitfalls & tips
- **Pitfall:** Forgetting to set the SRS before calling `AsText` can result in missing SRID information.  
- **Tip:** Use `NumericFormat.RoundTrip` when you need lossless round‑tripping of coordinates.  
- **Tip:** The `Iso` variant is the most portable; choose `ExtendedPostGis` only when you need SRID embedded.

## Conclusion
You now know how to **assign coordinate system**, choose the appropriate WKT variant, and **set decimal precision** when you **create point geometry** with Aspose.GIS. These controls give you the flexibility to meet the exact requirements of any GIS workflow, from simple visualisation to high‑precision spatial analysis.

## Frequently asked questions

**Q:** Is Aspose.GIS compatible with all versions of .NET?  
**A:** Yes, Aspose.GIS supports .NET Framework 4.0 and higher, as well as .NET Core/5/6.

**Q:** Can I use Aspose.GIS for commercial projects?  
**A:** Absolutely. A commercial license is required for production use, but a free trial is available for evaluation.

**Q:** Does Aspose.GIS support other spatial data formats?  
**A:** Yes, it works with 30+ formats, including ESRI Shapefile, GeoJSON, KML, CSV, and many more.

**Q:** Where can I download a free trial?  
**A:** You can download a free trial version of Aspose.GIS from the [Aspose.GIS free trial download page](https://releases.aspose.com/).

**Q:** How do I get help if I run into issues?  
**A:** Post your questions on the Aspose.GIS community [forum](https://forum.aspose.com/c/gis/33) where both Aspose staff and community members can assist.

---

**Last Updated:** 2026-09-15  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## Related Tutorials

- [Create a Vector Layer and Set Its Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [How to Translate Geometry to WKT with Aspose.GIS for .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [How to Limit Precision Writing Geometries with Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}