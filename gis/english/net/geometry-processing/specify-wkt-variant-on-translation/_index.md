---
title: Convert Geometry to WKT Variant Options using Aspose.GIS
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
description: Learn how to convert geometry to WKT with variant options, set numeric format and adjust decimal precision using Aspose.GIS for .NET.
weight: 19
url: /net/geometry-processing/specify-wkt-variant-on-translation/
date: 2025-12-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convert Geometry to WKT Variant Options using Aspose.GIS

## Introduction
In modern .NET applications, **converting geometry to WKT** is a common step when you need to exchange spatial data with other systems or store it in a text‑based format. Aspose.GIS for .NET makes this conversion effortless while giving you full control over the WKT variant, numeric format, and decimal precision. In this tutorial you’ll learn how to convert geometry to WKT, choose the right variant, and fine‑tune the output to meet your project’s exact requirements.

## Quick Answers
- **What does “convert geometry to WKT” mean?** It transforms geometric objects (points, lines, polygons) into the Well‑Known Text representation.  
- **Which WKT variants are supported?** `Iso`, `SimpleFeatureAccessOutdated`, and `ExtendedPostGis`.  
- **How can I control decimal precision?** Use the `NumericFormat` options such as `General`, `RoundTrip`, or `Flat`.  
- **Do I need a license for production?** Yes, a commercial license is required for non‑trial use.  
- **What .NET versions are compatible?** .NET Framework 4.0+ and .NET 5/6/7.

## What is “convert geometry to WKT”?
Converting geometry to WKT produces a human‑readable string that describes spatial objects. This format is widely accepted by GIS tools, databases, and web services, making it ideal for data interchange.

## Why use Aspose.GIS for this conversion?
- **Precision control** – Choose how many decimal places are emitted.  
- **Variant flexibility** – Match the exact WKT dialect required by your downstream system.  
- **No external dependencies** – Pure .NET library, no native binaries.

## Prerequisites
Before we begin, make sure you have:

1. **Aspose.GIS for .NET** – Download and install it from the [download page](https://releases.aspose.com/gis/net/).  
2. **Development Environment** – Any recent version of Visual Studio or VS Code with .NET SDK.  
3. **Basic C# knowledge** – Familiarity with classes, objects, and the .NET framework.

## Import Namespaces
First, bring the required namespaces into scope:

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

## Step 1: Create a Point Object
Create a `Point` that you will later **convert geometry to WKT**. The point includes latitude, longitude, and an optional measure (M) value:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Step 2: Set Spatial Reference System (SRS)
Assign a spatial reference system so the WKT output knows which coordinate system to reference. Here we use the common WGS84 system:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Step 3: Specify WKT Variant
Choose the appropriate WKT variant when you **convert geometry to WKT**. Each variant formats the output slightly differently:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Step 4: Control Numeric Format (Set Numeric Format & Adjust Decimal Precision)
Fine‑tune the numeric representation of coordinates. The `NumericFormat` class lets you **set numeric format** and **adjust decimal precision** to suit your needs:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Common Issues & Tips
- **Missing M value** – If you don’t need a measure, omit the `M` property; the ISO variant will drop it automatically.  
- **Unexpected precision** – Double‑check that you’re using the correct `NumericFormat`; `General` preserves full double precision, while `Flat` rounds to the specified number of decimal places.  
- **SRID not displayed** – Only the `ExtendedPostGis` variant prefixes the output with `SRID=`. Choose this variant when your target system expects an SRID.

## Conclusion
By following these steps you now know how to **convert geometry to WKT**, select the right variant, and precisely control the numeric output. This gives you the flexibility to integrate Aspose.GIS with any GIS workflow, database, or web service that consumes WKT.

## FAQ's
### Is Aspose.GIS compatible with all versions of .NET?
Yes, Aspose.GIS supports .NET Framework 4.0 and higher.  

### Can I use Aspose.GIS for commercial projects?
Yes, Aspose.GIS can be used for both personal and commercial projects.  

### Does Aspose.GIS provide support for other spatial data formats?
Yes, Aspose.GIS supports a wide range of spatial data formats, including ESRI Shapefile, GeoJSON, and KML.  

### Is there a free trial available for Aspose.GIS?
Yes, you can download a free trial version of Aspose.GIS from [here](https://releases.aspose.com/).  

### Where can I get help or support for Aspose.GIS?
You can post your queries or seek assistance from the Aspose.GIS community at the [forum](https://forum.aspose.com/c/gis/33).

## Frequently Asked Questions
**Q: How do I export a Geometry collection to a single WKT string?**  
A: Iterate over each geometry in the collection and concatenate their `AsText` results, optionally separating them with commas or newlines.

**Q: Can I change the SRID without altering the coordinates?**  
A: Yes, set the `SpatialReferenceSystem` property to the desired SRID; the coordinate values remain unchanged.

**Q: What happens if I use an unsupported WKT variant?**  
A: Aspose.GIS will throw an `ArgumentException`. Always validate the variant against `WktVariant` enum values.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}