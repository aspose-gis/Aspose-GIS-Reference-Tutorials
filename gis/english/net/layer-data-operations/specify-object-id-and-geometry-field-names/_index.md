---
title: Specify Object ID and Geometry Field Names
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
description: Explore GIS magic with Aspose.GIS for .NET! Manage geospatial data effortlessly. Download now and unleash the power of spatial intelligence.
weight: 20
url: /net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Specify Object ID and Geometry Field Names

## Introduction
Embarking on a journey into the realm of Geographic Information Systems (GIS) using Aspose.GIS for .NET opens up a world of possibilities for developers and enthusiasts alike. This powerful library empowers you to handle geospatial data effortlessly. In this tutorial, we'll guide you through the process of specifying Object ID and Geometry field names, laying the foundation for your GIS endeavors.
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
## Step 1: Specify Object ID and Geometry Field Names
In this step, you'll learn how to set up the Object ID and Geometry field names for your GIS data. This is crucial for efficient data management.
## Step 1.1: Set Document Directory
Start by defining the path to your document directory:
```csharp
string dataDir = "Your Document Directory";
```
## Step 1.2: Create a GeoDatabase and Define Options
Create a GeoDatabase with specified Object ID and Geometry field names:
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
## Step 1.3: Create and Add a Layer
Create a layer within the GeoDatabase and add a feature with a specific geometry:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```
## Step 1.4: Open and Retrieve Data from the Layer
Open the layer and retrieve data from it based on the specified Object ID:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```
## Conclusion
Congratulations! You've successfully navigated through the process of specifying Object ID and Geometry field names using Aspose.GIS for .NET. This lays a solid foundation for your GIS projects, enabling you to manage geospatial data with ease.
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

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
