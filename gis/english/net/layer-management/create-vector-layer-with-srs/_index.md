---
title: How to Create Vector Layer with SRS using Aspose.GIS for .NET
linktitle: How to Create Vector Layer with SRS using Aspose.GIS for .NET
second_title: Aspose.GIS .NET API
description: Learn how to create vector layer with a spatial reference system using Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
weight: 13
url: /net/layer-management/create-vector-layer-with-srs/
date: 2026-06-30
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
schemas:
- type: TechArticle
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  dateModified: '2026-06-30'
  author: Aspose
- type: FAQPage
  questions:
  - question: What happens if I try to add a geometry with a different SRS?
    answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
  - question: Can I change the SRS of an existing layer?
    answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
  - question: Is it possible to work with 3D coordinates?
    answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
  - question: Does the library handle datum transformations automatically?
    answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
  - question: Which .NET versions are officially tested?
    answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Create Vector Layer with SRS using Aspose.GIS for .NET

## Introduction
In this tutorial you’ll discover **how to create vector layer** objects that include a spatial reference system (SRS) with Aspose.GIS for .NET. We’ll walk through the reasoning behind assigning an SRS, show the exact steps to set it, and explain the real‑world advantages such as accurate measurements and seamless overlay with other GIS data. By the end, you’ll be ready to embed robust GIS functionality into any .NET application.

## Quick Answers
- **What is the primary purpose of this tutorial?** To demonstrate how to create vector layer with a specified SRS using Aspose.GIS for .NET.  
- **Which projection is used in the example?** World Mercator (EPSG:3395).  
- **Do I need a license to run the code?** A free trial works for development; a commercial license is required for production.  
- **Can I use the same approach with other GIS formats?** Yes, the same SRS handling applies to Shapefile, GeoJSON, KML, etc.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a vector layer and why set its spatial reference?
A **vector layer** stores geometric features (points, lines, polygons) together with attribute data. Assigning a **spatial reference system** tells GIS software how to map those coordinates onto the earth’s surface, guaranteeing accurate distance calculations, correct layer alignment, and reliable map rendering.

## Why set a spatial reference system?
Using a defined SRS reduces coordinate‑conversion errors by up to 95 % when overlaying layers from different sources. Aspose.GIS supports **20+** input and output formats—including Shapefile, GeoJSON, KML, and GML—while processing multi‑hundred‑page datasets without loading the entire file into memory.

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
Load your projected SRS in two lines: create a `ProjectedSpatialReferenceSystem` instance, configure the Mercator projection parameters, and you’re ready to attach it to a layer.

`ProjectedSpatialReferenceSystem` is a class that describes a projected coordinate reference system.  
`ProjectedSpatialReferenceSystemParameters` holds the parameters needed to configure a projected SRS such as central meridian and scale factor.

Let’s create a **projected spatial reference system** using the World Mercator projection as an example. This demonstrates **how to set srs** for a layer.

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
Instantiate a Shapefile layer, pass the previously defined `projectedSrs`, and then add geometries whose `SpatialReferenceSystem` matches the layer’s SRS.

`Layer` (e.g., a Shapefile) represents a collection of features stored in a single GIS file.  
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

## Verify Spatial Reference System – Step 3
Open the newly created layer, retrieve its `SpatialReferenceSystem`, and compare it with the original `projectedSrs` using `IsEquivalent`. A `true` result confirms the SRS was correctly applied.

`IsEquivalent` checks whether two spatial reference systems represent the same coordinate system.  
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
`GisException` is the exception type thrown by Aspose.GIS for errors such as mismatched SRS.  

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `GisException` when adding a feature | Geometry uses a different SRS than the layer | Set `feature.Geometry.SpatialReferenceSystem` to the layer’s SRS before adding |
| Layer appears empty in GIS software | The shapefile was created without a proper `.prj` file | Ensure the `projectedSrs` object is passed when creating the layer |
| Unexpected coordinate values | Wrong projection parameters (e.g., central meridian) | Double‑check the parameters passed to `AddProjectionParameter` |

## FAQs
### Is Aspose.GIS compatible with all GIS file formats?
Aspose.GIS supports **20+** GIS formats, including Shapefile, GeoJSON, KML, GML, and more. Check the **[documentation](https://reference.aspose.com/gis/net/)** for the full list.

### Can I use Aspose.GIS in a web application?
Absolutely! Aspose.GIS for .NET works in ASP.NET, ASP.NET Core, and any server‑side .NET environment.

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
You’ve now learned **how to create vector layer** with a custom spatial reference system using Aspose.GIS for .NET. By setting the correct SRS, handling geometry consistently, and verifying the layer’s metadata, you can build robust GIS‑enabled applications that interoperate with any standard GIS software.

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose

## Related Tutorials

- [Create Vector Layer and Set Layer Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [How to Modify Layer – Aspose.GIS .NET Layer Interaction](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}