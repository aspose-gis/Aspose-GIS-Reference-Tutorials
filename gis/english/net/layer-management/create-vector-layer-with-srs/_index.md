---
title: Create Vector Layer with SRS
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
description: Explore Aspose.GIS for .NET to create vector layer with a spatial reference system. Learn how to set SRS, create layer, and manage GIS data. Download now!
weight: 13
url: /net/layer-management/create-vector-layer-with-srs/
date: 2026-01-15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Vector Layer with SRS

## Introduction
Aspose.GIS for .NET is a powerful library that enables developers to **create vector layer** objects and work with geographic information system (GIS) data seamlessly in .NET applications. In this tutorial, we’ll walk through how to create a vector layer with a spatial reference system (SRS), why you’d want to set spatial reference, and what benefits this brings to real‑world projects. By the end of this guide, you’ll be able to integrate GIS capabilities into your .NET solutions with confidence.

## Quick Answers
- **What is the primary purpose of this tutorial?** To show how to create vector layer with a specified SRS using Aspose.GIS for .NET.  
- **Which projection is used in the example?** World Mercator (EPSG:3395).  
- **Do I need a license to run the code?** A free trial works for development; a commercial license is required for production.  
- **Can I use the same approach with other GIS formats?** Yes, the same SRS handling applies to Shapefile, GeoJSON, KML, etc.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a vector layer and why set its spatial reference?
A **vector layer** stores geometric features (points, lines, polygons) together with attribute data. Assigning a **spatial reference** (SRS) tells GIS software how to interpret those coordinates on the earth’s surface. Setting the correct SRS ensures accurate measurements, proper overlay with other layers, and reliable map visualizations.

## Prerequisites
Before we dive in, make sure you have:

- Basic knowledge of C# and .NET development.  
- Aspose.GIS for .NET library installed. You can download it **[here](https://releases.aspose.com/gis/net/)**.  
- A development environment (Visual Studio, VS Code, or any C# IDE).  

## Import Namespaces
Ensure you have the necessary namespaces imported at the top of your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to set spatial reference (SRS) – Step 1
Let's create a **projected spatial reference system** using the World Mercator projection as an example. This demonstrates **how to set srs** for a layer.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## How to create layer – Step 2
Now we’ll **create a vector layer** (a Shapefile) and add features that use the SRS we just defined. This part answers **how to create layer** with Aspose.GIS.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Pro tip:** Always verify that the geometry’s `SpatialReferenceSystem` matches the layer’s SRS before adding it. Mismatched SRS values raise a `GisException`, as shown above.

## Verify Spatial Reference System – Step 3
Finally, open the layer and confirm that the SRS was correctly applied.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

If the `IsEquivalent` call returns `true`, you’ve successfully **create vector layer** with the desired spatial reference.

## Common Issues & Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `GisException` when adding a feature | Geometry uses a different SRS than the layer | Set `feature.Geometry.SpatialReferenceSystem` to the layer’s SRS before adding |
| Layer appears empty in GIS software | The shapefile was created without a proper `.prj` file | Ensure the `projectedSrs` object is passed when creating the layer |
| Unexpected coordinate values | Wrong projection parameters (e.g., central meridian) | Double‑check the parameters passed to `AddProjectionParameter` |

## FAQs
### Is Aspose.GIS compatible with all GIS file formats?
Aspose.GIS supports various GIS formats, including Shapefile, GeoJSON, KML, and more. Check the **[documentation](https://reference.aspose.com/gis/net/)** for the complete list.

### Can I use Aspose.GIS in a web application?
Absolutely! Aspose.GIS for .NET is versatile and can be used in web applications, desktop applications, and even mobile apps.

### Where can I get support for Aspose.GIS?
You can find a helpful community at the **[Aspose.GIS forum](https://forum.aspose.com/c/gis/33)** for any queries or issues you may encounter.

### Is there a free trial available?
Yes, you can explore the features of Aspose.GIS by obtaining a free trial **[here](https://releases.aspose.com/)**.

### How can I purchase a license for Aspose.GIS?
To purchase a license, visit the **[purchase page](https://purchase.aspose.com/buy)**.

## Frequently Asked Questions (Additional)

**Q: What happens if I try to add a geometry with a different SRS?**  
A: Aspose.GIS throws a `GisException`. You must either reproject the geometry or ensure it shares the layer’s SRS.

**Q: Can I change the SRS of an existing layer?**  
A: Yes, you can create a new layer with the desired SRS and copy features over, reprojecting them as needed.

**Q: Is it possible to work with 3D coordinates?**  
A: Aspose.GIS supports Z‑coordinates; just use geometry constructors that accept a Z value.

**Q: Does the library handle datum transformations automatically?**  
A: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs the necessary datum shift.

**Q: Which .NET versions are officially tested?**  
A: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.

## Conclusion
You’ve now learned how to **create vector layer** with a custom spatial reference system using Aspose.GIS for .NET. By setting the correct SRS, handling geometry consistently, and verifying the layer’s metadata, you can build robust GIS-enabled applications that interoperate with any standard GIS software.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}