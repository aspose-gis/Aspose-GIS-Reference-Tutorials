---
title: Assign Spatial Reference & Set WKT Variant using Aspose.GIS
linktitle: Specify WKT Variant on Translation
second_title: Aspose.GIS .NET API
description: Learn how to assign spatial reference and set decimal precision when creating point C# with Aspose.GIS for .NET in your .NET applications.
weight: 19
url: /net/geometry-processing/specify-wkt-variant-on-translation/
date: 2026-04-09
keywords:
- assign spatial reference
- set decimal precision
- create point c#
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Assign Spatial Reference & Set WKT Variant using Aspose.GIS

## Introduction
In this tutorial you’ll learn how to **assign spatial reference** to a geometry and control the exact WKT output format with Aspose.GIS for .NET. Whether you need to **create point C#** objects for mapping, analytics, or data exchange, being able to choose the right WKT variant and numeric precision makes your spatial data interoperable and easy to read. Let’s walk through the process step by step.

## Quick Answers
- **What does “assign spatial reference” mean?** It binds a geometry to a specific coordinate system such as WGS‑84.  
- **Which WKT variants are supported?** Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.  
- **How can I control decimal precision?** Use the `NumericFormat` options like `General`, `RoundTrip`, or `Flat`.  
- **Do I need a license?** A free trial is available; a commercial license is required for production.  
- **What .NET versions are compatible?** .NET Framework 4.0+ and .NET Core/5/6+.

## What is “assign spatial reference”?
Assigning a spatial reference (or spatial reference system, SRS) tells GIS software how to interpret the coordinate values of a geometry. Without an SRS, a point’s latitude‑longitude numbers have no real-world meaning.

## Why control the WKT variant and numeric format?
Different GIS tools expect slightly different WKT syntaxes. Selecting the proper variant ensures seamless data exchange, while setting decimal precision prevents rounding errors or overly long numbers that clutter logs and files.

## Prerequisites
1. Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).  
2. A .NET development environment (Visual Studio, VS Code, or Rider).  
3. Basic familiarity with C# and the .NET framework.

## Import Namespaces
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

## Step 1: Create a Point Object (create point C#)
We start by constructing a `Point` with latitude, longitude, and an optional measure (M) value:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Step 2: Assign Spatial Reference System (SRS)
Now we **assign spatial reference** to the point. Here we use the widely‑supported WGS‑84 system (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Step 3: Specify the Desired WKT Variant
Choose the WKT variant that matches your downstream application:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Step 4: Set Decimal Precision for the WKT Output
Control how many digits appear in the final string using `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Common Pitfalls & Tips
- **Pitfall:** Forgetting to set the SRS before calling `AsText` can result in missing SRID information.  
- **Tip:** Use `NumericFormat.RoundTrip` when you need lossless round‑tripping of coordinates.  
- **Tip:** The `Iso` variant is the most portable; choose `ExtendedPostGis` only when you need SRID embedded.

## Conclusion
You now know how to **assign spatial reference**, choose the appropriate WKT variant, and **set decimal precision** when you **create point C#** objects with Aspose.GIS. These controls give you the flexibility to meet the exact requirements of any GIS workflow, from simple visualisation to high‑precision spatial analysis.

## Frequently Asked Questions

**Q:** Is Aspose.GIS compatible with all versions of .NET?  
**A:** Yes, Aspose.GIS supports .NET Framework 4.0 and higher, as well as .NET Core/5/6.

**Q:** Can I use Aspose.GIS for commercial projects?  
**A:** Absolutely. A commercial license is required for production use, but a free trial is available for evaluation.

**Q:** Does Aspose.GIS support other spatial data formats?  
**A:** Yes, it works with ESRI Shapefile, GeoJSON, KML, and many more formats.

**Q:** Where can I download a free trial?  
**A:** You can download a free trial version of Aspose.GIS from [here](https://releases.aspose.com/).

**Q:** How do I get help if I run into issues?  
**A:** Post your questions on the Aspose.GIS community [forum](https://forum.aspose.com/c/gis/33) where both Aspose staff and community members can assist.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}