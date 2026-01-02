---
title: Add point feature and specify Object ID and Geometry Field Names
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
description: Learn how to add point feature while setting field names and reading object id using Aspose.GIS for .NET. Step‑by‑step guide for developers.
weight: 20
url: /net/layer-data-operations/specify-object-id-and-geometry-field-names/
date: 2026-01-02
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add point feature and specify Object ID and Geometry Field Names

## Introduction
Embarking on a journey into the realm of Geographic Information Systems (GIS) using Aspose.GIS for .NET opens up a world of possibilities for developers and enthusiasts alike. In this tutorial, **you’ll learn how to add point feature** while also **setting field names** and **reading object id** values, giving you full control over your spatial data.

## Quick Answers
- **What is the primary purpose of this guide?** To show how to add a point feature and configure Object ID and Geometry field names.  
- **Which library is used?** Aspose.GIS for .NET.  
- **Do I need a license?** A free trial is available; a license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Can I read the Object ID after insertion?** Yes – the tutorial demonstrates how to read object id from the layer.

## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Aspose.GIS for .NET: Download and install the library from [here](https://releases.aspose.com/gis/net/).
- Document Directory: Set up a directory for your documents to store the geodatabases.
- .NET Environment: Make sure you have a working .NET environment.

## Import Namespaces
To kick things off, you need to import the necessary namespaces into your project. These namespaces provide the essential classes and methods for interacting with Aspose.GIS for .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Step 1: Add point feature and specify Object ID and Geometry Field Names
In this step, you'll learn how to set up the Object ID and Geometry field names for your GIS data. This is crucial for efficient data management and for being able to **read object id** later.

### Step 1.1: Set Document Directory
Start by defining the path to your document directory:

```csharp
string dataDir = "Your Document Directory";
```

### Step 1.2: Create a GeoDatabase and Define Options
Create a GeoDatabase with the desired **set field names** for Object ID and Geometry:

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

### Step 1.3: Create and Add a Layer
Create a layer within the GeoDatabase and add a feature that represents a point geometry:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Step 1.4: Open and Retrieve Data from the Layer
Open the layer and retrieve the feature you just added. This demonstrates how to **read object id** from the dataset:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Why set custom field names?
Customizing the Object ID and Geometry field names gives you flexibility when integrating with existing databases or when adhering to naming conventions required by downstream applications. It also makes the data more self‑descriptive, which simplifies maintenance and collaboration.

## Common pitfalls and troubleshooting
- **Missing directory** – Ensure `dataDir` points to an existing folder; otherwise, `Dataset.Create` will throw an exception.
- **Field name conflicts** – If a field with the same name already exists in the geodatabase, the creation will fail. Choose unique names.
- **Spatial reference mismatch** – Always match the spatial reference system (e.g., WGS84) with the data you intend to store.

## Conclusion
Congratulations! You've successfully learned how to **add point feature**, **set field names**, and **read object id** using Aspose.GIS for .NET. This foundation empowers you to build robust GIS applications and manage spatial data with confidence.

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET in my web applications?
A: Yes, Aspose.GIS for .NET is suitable for both desktop and web applications, providing versatile geospatial capabilities.

### Q: Is there a trial version available before purchasing?
A: Yes, you can explore the features of Aspose.GIS for .NET with a free trial available [here](https://releases.aspose.com/).

### Q: How can I obtain a temporary license for Aspose.GIS for .NET?
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/) for evaluation purposes.

### Q: What spatial reference systems does Aspose.GIS for .NET support?
A: Aspose.GIS for .NET supports various spatial reference systems, providing flexibility for different geographic datasets.

### Q: Where can I seek help or discuss Aspose.GIS-related queries?
A: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for support and discussions.

## Additional Frequently Asked Questions

**Q: Can I change the Object ID field after the layer is created?**  
A: No. The field name is defined when the layer is created; you must recreate the layer with a new `FileGdbOptions` object to change it.

**Q: How do I retrieve other attribute values besides the Object ID?**  
A: Use `feature.GetValue<T>("FieldName")` where `FieldName` is the name of the attribute you want to read.

**Q: Is it possible to add multiple point features in one batch?**  
A: Yes. Loop over your data, construct a feature for each point, set its geometry, and call `layer.Add(feature)` inside the same `using` block.

**Q: Does Aspose.GIS support other geometry types?**  
A: Absolutely. You can work with `LineString`, `Polygon`, `MultiPoint`, and more by creating the appropriate geometry objects.

**Q: What happens if I try to read an Object ID that doesn’t exist?**  
A: Accessing an out‑of‑range index (e.g., `layer[10]` when only one feature exists) will throw an `IndexOutOfRangeException`. Always check `layer.Count` first.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}