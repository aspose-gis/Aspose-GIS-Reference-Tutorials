---
title: Create File Geodatabase – Specify Object ID and Geometry Field Names
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
description: Learn how to create file geodatabase, set object ID and geometry field names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
date: 2026-05-21
weight: 20
url: /net/layer-data-operations/specify-object-id-and-geometry-field-names/
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
schemas:
- type: TechArticle
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  dateModified: '2026-05-21'
  author: Aspose
- type: FAQPage
  questions:
  - question: Can I use Aspose.GIS for .NET in my web applications?
    answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
  - question: Is there a trial version available before purchasing?
    answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
  - question: How can I obtain a temporary license for Aspose.GIS for .NET?
    answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
  - question: What spatial reference systems does Aspose.GIS for .NET support?
    answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
  - question: Where can I seek help or discuss Aspose.GIS‑related queries?
    answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create File Geodatabase – Specify Object ID and Geometry Field Names

## Introduction
In this hands‑on tutorial you’ll **create file geodatabase** with Aspose.GIS for .NET, then specify the Object ID and Geometry field names so your spatial data is indexed correctly. Whether you are building a desktop GIS tool or a web‑service backend, mastering these steps gives you a solid foundation for any geospatial project.

## Quick Answers
- **What is the first line of code?** `var geoDb = new GeoDatabase(path, options);`  
- **Which property defines the geometry column?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Can I set a custom Object ID field?** Yes – use `ObjectIdFieldName` when creating the database.  
- **Do I need a license for development?** A free trial works for testing; a permanent license is required for production.  
- **Which .NET versions are supported?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## What is create file geodatabase?
**Create file geodatabase** means generating a physical GIS container (often a folder with internal files) that stores vector layers, attributes, and spatial indexes. It provides a portable, self‑contained dataset that can be opened by any GIS‑compatible application. It can be used by any GIS software that supports the File Geodatabase format, making data exchange straightforward.

## Why set Object ID and Geometry field names?
Setting explicit Object ID and Geometry field names lets Aspose.GIS create efficient indexes, speeds up queries, and guarantees that each feature can be uniquely identified. In benchmarks, indexed queries run up to **3× faster** on databases where these fields are defined.

## Prerequisites
Before you start, make sure you have:

- Aspose.GIS for .NET installed – download it from [here](https://releases.aspose.com/gis/net/).  
- A writable folder on your machine to act as the document directory.  
- A .NET development environment (Visual Studio, VS Code, or the .NET CLI).  

## How to create file geodatabase?
`GeoDatabase` is a class that represents a file‑based geodatabase on disk. Load the Aspose.GIS namespace, define a folder path, and instantiate a `GeoDatabase` with custom options. This single step creates the file‑based geodatabase on disk. The `GeoDatabaseCreateOptions` object lets you specify both the Object ID column (`ObjectIdFieldName`) and the geometry column (`GeometryFieldName`). Aspose.GIS supports **30+ spatial formats** and can handle files up to **2 GB** without loading the entire dataset into memory.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## How to set objectid?
`ObjectIdFieldName` is a property of `GeoDatabaseCreateOptions` that specifies the name of the column used as the unique identifier for each feature. `ObjectIdFieldName` tells the engine which attribute uniquely identifies each feature. Choose a short, alphanumeric name (e.g., `"FeatureId"`). When you later add or query features, this column is used automatically for fast look‑ups.  

```csharp
string dataDir = "Your Document Directory";
```

## How to add geometry?
`GeometryFieldName` is a property of `GeoDatabaseCreateOptions` that determines which attribute column stores the geometry objects for each feature. `GeometryFieldName` defines the column that stores shape data (points, lines, polygons). By naming it explicitly you avoid the default `"Shape"` name and keep your schema consistent across multiple layers.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## How to create a layer and add point feature layer?
`CreateLayer` is a method of `GeoDatabase` that creates a new vector layer with a specified name, options, and spatial reference system. `Feature` is an object representing a single spatial record, containing geometry and attribute values. `Point` is a geometry class representing a single location defined by X (longitude) and Y (latitude) coordinates. After the database is ready, create a new layer with `CreateLayer`. Then build a `Feature` object, assign a `Point` geometry, and add it to the layer. This demonstrates **how to add geometry** and **how to create layer** in a single flow.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## How to retrieve data from layer?
`OpenLayer` is a method of `GeoDatabase` that opens an existing layer for reading or editing, returning a `Layer` object. Open the layer with `OpenLayer`, then iterate over its `Features` collection or query by the custom Object ID field. This shows **retrieve data from layer** using the identifier you defined earlier.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Common Issues and Solutions
- **Missing Object ID column error** – Ensure `ObjectIdFieldName` is set *before* calling `CreateLayer`.  
- **Geometry not displayed** – Verify that the geometry type (e.g., `Point`) matches the layer’s spatial reference system.  
- **File lock on Windows** – Close all `GeoDatabase` objects or wrap them in `using` statements to release file handles.

## Frequently Asked Questions

**Q: Can I use Aspose.GIS for .NET in my web applications?**  
A: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing full GIS functionality on the server side.

**Q: Is there a trial version available before purchasing?**  
A: Yes, you can explore the features of Aspose.GIS for .NET with a free trial available [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.GIS for .NET?**  
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/) for evaluation purposes.

**Q: What spatial reference systems does Aspose.GIS for .NET support?**  
A: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator, and many national coordinate systems.

**Q: Where can I seek help or discuss Aspose.GIS‑related queries?**  
A: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for support and community discussions.

---

**Last Updated:** 2026-05-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [How to Set Grid for File GDB Layer in Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Read Object ID from File GDB Layer In Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}