---
title: Create Vector Layer with SRS
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
description: Explore Aspose.GIS for .NET - your key to seamless GIS integration. Create vector layers effortlessly with specified spatial reference systems. Download now!
weight: 13
url: /net/layer-management/create-vector-layer-with-srs/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Vector Layer with SRS

## Introduction
Aspose.GIS for .NET is a powerful library that enables developers to work with geographic information system (GIS) data seamlessly in .NET applications. In this tutorial, we'll focus on creating a vector layer with a spatial reference system (SRS). By the end of this guide, you'll be able to effortlessly integrate GIS capabilities into your .NET projects.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Basic knowledge of C# and .NET development.
- Aspose.GIS for .NET library installed. You can download it [here](https://releases.aspose.com/gis/net/).
- A development environment set up and ready.
## Import Namespaces
Ensure you have the necessary namespaces imported at the beginning of your C# file:
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
## Step 1: Set Up the Projected Spatial Reference System
Let's create a projected spatial reference system (SRS) using the World Mercator projection as an example. Follow these steps:
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
## Step 2: Create a Vector Layer and Add Features
Now, let's create a shapefile and add features with the specified SRS:
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
## Step 3: Verify Spatial Reference System
Finally, let's open the layer and verify its spatial reference system:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```
By following these steps, you've successfully created a vector layer with a specified spatial reference system using Aspose.GIS for .NET.
## Conclusion
Integrating GIS functionality into your .NET applications has never been easier, thanks to Aspose.GIS. With the ability to effortlessly create vector layers and manage spatial reference systems, you can enhance your projects with powerful geospatial capabilities.
## FAQs
### Is Aspose.GIS compatible with all GIS file formats?
Aspose.GIS supports various GIS formats, including Shapefile, GeoJSON, KML, and more. Check the [documentation](https://reference.aspose.com/gis/net/) for the complete list.
### Can I use Aspose.GIS in a web application?
Absolutely! Aspose.GIS for .NET is versatile and can be used in web applications, desktop applications, and even mobile apps.
### Where can I get support for Aspose.GIS?
You can find a helpful community at the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for any queries or issues you may encounter.
### Is there a free trial available?
Yes, you can explore the features of Aspose.GIS by obtaining a free trial [here](https://releases.aspose.com/).
### How can I purchase a license for Aspose.GIS?
To purchase a license, visit the [purchase page](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
