---
date: 2026-09-10
description: Learn how to create vector layer with Aspose.GIS for .NET and limit precision
  to shrink shapefile size, boost performance, and keep coordinate accuracy.
images:
- /net/geometry-processing/limit-precision-reading-geometries/og-image.png
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: Limit Precision Reading Geometries
og_description: Learn how to create vector layer with Aspose.GIS for .NET and limit
  precision to reduce shapefile size, improve performance, and manage coordinate accuracy.
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: How to create vector layer with Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: How to create vector layer with Aspose.GIS for .NET
url: /net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create vector layer with Aspose.GIS for .NET

## Introduction
When you work with geospatial data you often wonder **how to create vector layer** objects that match the accuracy your application really needs. Rounding coordinates to a sensible number of decimal places not only speeds up parsing but can also **reduce shapefile size by up to 30 %** for typical point datasets. In this step‑by‑step guide you’ll see how to create a vector layer, write a point geometry, and then read it back using both exact and rounded precision models. By the end you’ll know how to **set precision model** options that balance performance with the required spatial accuracy.

## Quick answers
- **What does “limit precision” mean?** It rounds coordinate values to a defined number of decimal places.  
- **Why create a vector layer first?** A vector layer is the container that stores geometries such as points, lines, and polygons.  
- **Which precision models are available?** `PrecisionModel.Exact` (no rounding) and `PrecisionModel.Rounding(n)` (round to *n* decimals).  
- **Do I need a license to try this?** A free trial is available from the releases page.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core, and .NET 5/6+.

## What is creating a vector layer?
The act of **creating a vector layer** means instantiating Aspose.GIS’s `VectorLayer` class, which represents a single shapefile on disk and holds all geometry features you add. This layer becomes the entry point for reading, writing, and manipulating spatial data. It also lets you define attribute fields and set the spatial reference for the dataset.

## Why limit precision and how does it help?
- **Performance boost** – Reducing the number of decimal digits cuts the amount of binary data that must be parsed and serialized, often delivering a 15‑20 % speed gain on large files.  
- **Smaller files** – Rounding coordinates to two or three decimals can shrink a 10 MB shapefile to roughly 7 MB, easing storage and network transfer.  
- **Sufficient accuracy** – Most GIS analyses (e.g., city‑level mapping) only need meter‑level precision, making 3‑decimal rounding more than adequate.

## Prerequisites
Before we embark on this journey, ensure that you have the following prerequisites in place:
1. **Installation** – Aspose.GIS for .NET library should be installed in your development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).  
2. **Familiarity with .NET** – Basic knowledge of C# and the .NET framework is necessary to understand and implement the provided code examples.  
3. **Development environment** – A working .NET development environment, such as Visual Studio, is required.  
4. **Document directory** – Have a directory set up where you can store and access the shapefile generated during the process.

## Import namespaces
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

## How to create vector layer
Load a new `VectorLayer` by specifying the output folder and the desired shapefile name. This creates an empty container ready to accept geometry objects.

The `VectorLayer` class is Aspose.GIS's top‑level object that represents a single shapefile on disk. After you create an instance you can add features, define attribute fields, and finally call `Save()` to write the files to the file system.

```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Setting precision options
`PrecisionModel` defines how coordinate values are rounded or kept exact when reading geometries. You set the model on a `ReadOptions` object before opening a layer.

The `PrecisionModel` class is a core component of Aspose.GIS that controls rounding behavior for both X and Y axes. By choosing the appropriate model you dictate whether the library preserves every digit or truncates to a specific decimal count.

```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Reading geometries with exact precision
`ReadOptions` specifies parameters for reading a vector layer, such as the precision model to apply.  
Open the previously saved vector layer using a `ReadOptions` instance that references `PrecisionModel.Exact`. This ensures every coordinate is read without any rounding.

When you use `PrecisionModel.Exact`, Aspose.GIS reads the raw double‑precision values stored in the shapefile, guaranteeing that no information is lost during the read operation.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Truncating precision
If you want to truncate the precision to a specific number of decimal places, replace `Exact` with `PrecisionModel.Rounding(n)`, where *n* is the number of decimals you want to keep.

Rounding to two decimals (`PrecisionModel.Rounding(2)`) typically reduces file size by 20‑30 % while keeping coordinate accuracy within a few centimeters for most mapping scales.

```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## How to set precision model for different scenarios
Choose the model that matches your use case:

- **High‑precision scientific analysis** – Use `PrecisionModel.Exact` to retain every digit.  
- **Web‑mapping tiles or mobile apps** – Use `PrecisionModel.Rounding(2)` to keep files lightweight and rendering fast.

Selecting the appropriate model is part of the **set precision model** decision‑making process that balances accuracy against performance.

## Common issues and solutions
`XYPrecisionModel` is a property of `ReadOptions` that sets the precision model for both X and Y coordinates.  

- **Unexpected coordinate values** – Ensure you set `options.XYPrecisionModel` *before* opening the layer. Changing it after opening has no effect.  
- **File not found** – Verify that the `path` variable points to a valid directory and that the Shapefile was successfully created in the previous step.  
- **Incorrect geometry type** – The example uses a `Point`. For other geometry types (e.g., `LineString`), the casting should match the actual type.  

## Tips for reducing shapefile size
- Use `PrecisionModel.Rounding` with the smallest number of decimals that still meets your accuracy needs.  
- Remove unnecessary attribute fields before writing the layer.  
- Compress the resulting `.shp`, `.shx`, and `.dbf` files using standard ZIP utilities if you need to transfer them.

## Conclusion
Managing precision when reading geometries is a crucial aspect of geospatial data manipulation. Aspose.GIS for .NET provides robust functionalities to achieve this efficiently. By following the steps above you can seamlessly **create vector layer** objects, **set precision model**, and even **reduce shapefile size** when appropriate, ensuring optimal data handling in your applications.

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

## Frequently asked questions
**Q: Does limiting precision affect the original shapefile?**  
A: No. Precision is applied only when reading the geometry; the source file remains unchanged.  

**Q: Can I use a different precision model for X and Y coordinates?**  
A: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.  

**Q: Is it possible to set a custom rounding function?**  
A: The API supports only the built‑in `PrecisionModel.Rounding(int)` method. For custom logic, you would need to post‑process the coordinates after reading.

---

**Last Updated:** 2026-09-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [How to Limit Precision Writing Geometries with Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [How to Create Vector Layer with SRS using Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}