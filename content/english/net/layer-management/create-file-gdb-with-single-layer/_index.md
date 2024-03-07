---
title: Create File GDB with Single Layer
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
description: Unlock the potential of geospatial data management in .NET with Aspose.GIS. Learn how to create File Geodatabases and layers step-by-step. Download now!
type: docs
weight: 11
url: /net/layer-management/create-file-gdb-with-single-layer/
---
## Introduction
Are you ready to elevate your geospatial applications with robust file geodatabases and layers? Look no further than Aspose.GIS for .NET. In this tutorial, we'll walk you through the process of creating a File Geodatabase (GDB) with a single layer using Aspose.GIS for .NET. Harness the power of spatial data management and visualization in your .NET applications effortlessly.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
1. Aspose.GIS for .NET: Make sure you have the Aspose.GIS library installed. You can download it from the [official Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
2. Development Environment: Set up a working .NET development environment on your machine.
3. Document Directory: Choose or create a directory on your system where you'll store your geospatial data files.
## Import Namespaces
To get started, you need to import the necessary namespaces in your .NET project. These namespaces will provide access to the Aspose.GIS functionalities. Add the following lines at the beginning of your code file:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Step 1: Set Up Your Document Directory
```csharp
string dataDir = "Your Document Directory";
```
Replace "Your Document Directory" with the path to the directory where you want to store your geospatial data files.
## Step 2: Create a File Geodatabase with a Single Layer
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
This code snippet creates a File Geodatabase with a single layer and adds a line feature to it.
## Step 3: Open the File Geodatabase and Retrieve Layer Information
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
In this step, we open the created File Geodatabase, retrieve the layer named "layer," and print the count of features in the layer.
## Conclusion
Congratulations! You've successfully created a File Geodatabase with a single layer using Aspose.GIS for .NET. Explore the vast capabilities of spatial data management in your applications with ease.
## Frequently Asked Questions
### Can I use Aspose.GIS for .NET in my existing .NET projects?
Yes, Aspose.GIS for .NET can be seamlessly integrated into your existing .NET projects.
### Is there a trial version available for Aspose.GIS for .NET?
Yes, you can explore the features of Aspose.GIS for .NET by downloading the [free trial version](https://releases.aspose.com/).
### Where can I find detailed documentation for Aspose.GIS for .NET?
Refer to the [official documentation](https://reference.aspose.com/gis/net/) for comprehensive information on Aspose.GIS for .NET.
### How can I get support for Aspose.GIS for .NET?
Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community support and assistance.
### Are temporary licenses available for Aspose.GIS for .NET?
Yes, you can obtain a [temporary license](https://purchase.aspose.com/temporary-license/) for Aspose.GIS for .NET.
