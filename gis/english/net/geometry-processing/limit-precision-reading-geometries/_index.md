---
title: Create Vector Layer, Limit Precision with Aspose.GIS for .NET
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
description: Learn how to create vector layer and limit precision when reading geometries using Aspose.GIS for .NET. Step‑by‑step guide for optimal geospatial data handling.
weight: 12
url: /net/geometry-processing/limit-precision-reading-geometries/
date: 2026-04-03
keywords:
- create vector layer
- reduce shapefile size
- set precision model
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Vector Layer, Limit Precision with Aspose.GIS for .NET

## Introduction
When working with geospatial data, you often need to **create vector layer** objects and decide how many decimal places of coordinate detail you really need. Limiting precision not only speeds up processing but can also **reduce shapefile size**, making storage and transfer more efficient. In this tutorial we’ll walk through creating a vector layer, writing a simple point geometry, and then reading it back using both exact and rounded precision models. By the end you’ll understand how to **set precision model** options that fit your application’s accuracy requirements.

## Quick Answers
- **What does “limit precision” mean?** It rounds coordinate values to a defined number of decimal places.  
- **Why create a vector layer first?** A vector layer is the container that stores geometries such as points, lines, and polygons.  
- **Which precision models are available?** `PrecisionModel.Exact` (no rounding) and `PrecisionModel.Rounding(n)` (round to *n* decimals).  
- **Do I need a license to try this?** A free trial is available from the releases page.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core, and .NET 5/6+.

## Why limit precision and how does it help?
- **Performance boost** – Fewer digits mean less data to parse and serialize.  
- **Smaller files** – Rounding coordinates can noticeably shrink a shapefile, especially for large datasets.  
- **Sufficient accuracy** – Many GIS analyses don’t require sub‑millimeter precision, so rounding to 2‑3 decimals is often enough.

## Prerequisites
Before we embark on this journey, ensure that you have the following prerequisites in place:
1. **Installation** – Aspose.GIS for .NET library should be installed in your development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).
2. **Familiarity with .NET** – Basic knowledge of C# and the .NET framework is necessary to understand and implement the provided code examples.
3. **Development Environment** – A working .NET development environment, such as Visual Studio, is required.
4. **Document Directory** – Have a directory set up where you can store and access the shapefile generated during the process.

## Import Namespaces
Before we begin implementing the functionality to limit precision when reading geometries, let's ensure we import the necessary namespaces:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to Create Vector Layer
The first step is to **create vector layer** that will hold our geometry. This layer will be saved as a Shapefile so we can later reopen it with different precision settings.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Setting Precision Options
Next, we need to define options for reading geometries, specifying the desired precision model. We can start with exact precision:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Reading Geometries with Exact Precision
Now, let's open the vector layer with the specified options to read geometries with exact precision:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Truncating Precision
If we want to truncate the precision to a specific number of decimal places, we can adjust the precision model accordingly:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## How to Set Precision Model for Different Scenarios
You might wonder when to use `Exact` versus `Rounding`. Here are two common scenarios:

| Scenario | Recommended Model | Reason |
|----------|-------------------|--------|
| High‑precision scientific analysis | `PrecisionModel.Exact` | No loss of coordinate detail |
| Web‑mapping tiles or mobile apps | `PrecisionModel.Rounding(2)` | Reduces file size and speeds up rendering |

Choosing the right model is part of the **set precision model** decision‑making process that balances accuracy against performance.

## Common Issues and Solutions
- **Unexpected coordinate values** – Ensure you set `options.XYPrecisionModel` *before* opening the layer. Changing it after opening has no effect.  
- **File not found** – Verify that the `path` variable points to a valid directory and that the Shapefile was successfully created in the previous step.  
- **Incorrect geometry type** – The example uses a `Point`. For other geometry types (e.g., `LineString`), the casting should match the actual type.  

## Tips for Reducing Shapefile Size
- Use `PrecisionModel.Rounding` with the smallest number of decimals that still meets your accuracy needs.  
- Remove unnecessary attribute fields before writing the layer.  
- Compress the resulting `.shp`, `.shx`, and `.dbf` files using standard ZIP utilities if you need to transfer them.

## Conclusion
In conclusion, managing precision when reading geometries is a crucial aspect of geospatial data manipulation. Aspose.GIS for .NET provides robust functionalities to achieve this efficiently. By following the steps above you can seamlessly **create vector layer** objects, **set precision model**, and even **reduce shapefile size** when appropriate, ensuring optimal data handling in your applications.

## FAQ's
### Can I use Aspose.GIS for .NET with other .NET frameworks like .NET Core or .NET Standard?
Yes, Aspose.GIS for .NET is compatible with various .NET frameworks, including .NET Core and .NET Standard.  
### Is there a trial version available for Aspose.GIS for .NET?
Yes, you can obtain a free trial version from the [releases page](https://releases.aspose.com/).  
### Where can I find comprehensive documentation for Aspose.GIS for .NET?
You can refer to the [documentation](https://reference.aspose.com/gis/net/) for detailed information and examples.  
### How can I obtain temporary licenses for Aspose.GIS for .NET?
Temporary licenses can be acquired from the [purchase page](https://purchase.aspose.com/temporary-license/) for Aspose.GIS.  
### Where can I seek assistance or support for Aspose.GIS for .NET?
You can visit the Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) for any queries, discussions, or support needs.

## Frequently Asked Questions
**Q: Does limiting precision affect the original shapefile?**  
A: No. Precision is applied only when reading the geometry; the source file remains unchanged.  

**Q: Can I use a different precision model for X and Y coordinates?**  
A: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.  

**Q: Is it possible to set a custom rounding function?**  
A: The API supports only the built‑in `PrecisionModel.Rounding(int)` method. For custom logic, you would need to post‑process the coordinates after reading.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}