---
title: Read Shapefile C# – Get All Feature Attribute Values
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
description: Learn how to read shapefile C# using Aspose.GIS for .NET, retrieve all feature attribute values, and dump attributes efficiently.
weight: 15
url: /net/layer-interaction-and-data-access/get-all-feature-attribute-values/
date: 2026-01-05
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Get All Feature Attribute Values

## Introduction
Welcome to the world of geospatial development with Aspose.GIS for .NET! In this tutorial you’ll learn **how to read shapefile C#** and retrieve every attribute value from its features. Whether you’re building a mapping app or processing spatial data in batch, mastering attribute extraction is essential. Let’s dive in and see the code in action.

## Quick Answers
- **What does this code do?** It opens a Shapefile and reads all, several, or dumped attribute values from each feature.  
- **Which library is required?** Aspose.GIS for .NET (compatible with .NET Framework and .NET Core).  
- **Do I need a license?** A temporary license works for testing; a full license is required for production.  
- **Can I read other formats?** Yes – the same API supports GeoJSON, KML, and many more.  
- **How to dump attributes?** Use `feature.GetValuesDump()` to obtain a flexible object array.

## What is “read shapefile C#”?
Reading a Shapefile in C# means opening the .shp file with a GIS library, iterating over its vector features, and accessing the attribute data stored in the accompanying .dbf file. Aspose.GIS abstracts the low‑level file handling, letting you focus on the attribute values you need.

## Why use Aspose.GIS to read attributes?
- **Simple API** – intuitive methods like `GetValues` and `GetValuesDump`.  
- **Cross‑platform** – works on Windows, Linux, and macOS with .NET Core.  
- **Rich format support** – handle Shapefile, GeoJSON, GML, and more without additional plugins.  
- **Performance‑optimized** – fast iteration over large datasets.

## Prerequisites
Before we embark on this exciting journey, ensure you have the following prerequisites in place:
- Aspose.GIS for .NET: Download and install the library from the [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Development Environment: Set up a .NET development environment, such as Visual Studio.
- Shapefile: Have a sample Shapefile (e.g., "InputShapeFile.shp") ready in your document directory.

## Import Namespaces
In your C# code, begin by importing the necessary namespaces to leverage Aspose.GIS functionalities:
```csharp
using System;
using Aspose.Gis;
```

## Step 1: Set the Document Directory
```csharp
string dataDir = "Your Document Directory";
```
Replace "Your Document Directory" with the actual path where your Shapefile is located.

## Step 2: Open the VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
This step involves opening the Shapefile using Aspose.GIS, specifying the file path and format (in this case, Shapefile).

## Step 3: Retrieve All Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
The snippet shows **how to read attributes** for every feature by loading them into a fixed‑size array.

## Step 4: Retrieve Several Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Here we demonstrate **how to read specific attribute values** when you only need a subset of fields.

## Step 5: Retrieve Attribute Values as Objects Dump
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
This final step showcases **how to dump attributes** using `GetValuesDump()`, which returns a flexible collection you can inspect or serialize.

## Common Issues and Solutions
- **Array size mismatch** – Ensure the array you pass to `GetValues` matches the number of attributes you expect; otherwise you’ll get `null` entries.  
- **File not found** – Verify `dataDir` points to the correct folder and that the Shapefile name is spelled exactly.  
- **License exception** – If you see a licensing error, apply a temporary or full license before calling any API methods.

## Frequently Asked Questions
### Is Aspose.GIS compatible with .NET Core?
Yes, Aspose.GIS is fully compatible with .NET Core, allowing you to build cross‑platform applications.

### Can I work with different GIS file formats using Aspose.GIS?
Absolutely! Aspose.GIS supports various formats, including Shapefile, GeoJSON, and more.

### Is there a community forum for Aspose.GIS support?
Yes, you can find assistance and engage with the Aspose.GIS community on the [support forum](https://forum.aspose.com/c/gis/33).

### How can I obtain a temporary license for Aspose.GIS?
You can acquire a temporary license for testing purposes [here](https://purchase.aspose.com/temporary-license/).

### Where can I find detailed documentation for Aspose.GIS?
The comprehensive documentation is available [here](https://reference.aspose.com/gis/net/).

### How do I retrieve only the “Name” attribute from each feature?
Use `GetValues` with an array sized to one element and pass the index of the “Name” field, or call `feature["Name"]` directly.

### What is the difference between `GetValues` and `GetValuesDump`?
`GetValues` fills a pre‑allocated array with raw values, while `GetValuesDump` returns an object array that can be enumerated without knowing the schema ahead of time.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

---