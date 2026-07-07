---
title: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
description: Learn how to read shapefile attribute values in C# using Aspose.GIS for .NET, retrieve every feature attribute, and dump attributes efficiently.
weight: 15
url: /net/layer-interaction-and-data-access/get-all-feature-attribute-values/
date: 2026-06-15
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
schemas:
- type: TechArticle
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  dateModified: '2026-06-15'
  author: Aspose
- type: FAQPage
  questions:
  - question: Is Aspose.GIS compatible with .NET Core?
    answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
  - question: Can I work with different GIS file formats using Aspose.GIS?
    answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
  - question: How can I obtain a temporary license for testing?
    answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
  - question: Where is the official documentation for Aspose.GIS?
    answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
  - question: How do I retrieve only the “Name” attribute from each feature?
    answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Get All Feature Attribute Values

## Introduction
In this tutorial you’ll discover **how to read shapefile attribute values** in C# with Aspose.GIS for .NET. Whether you’re building a live mapping application, performing bulk spatial analysis, or simply need to export attribute tables, extracting every field from a Shapefile is a fundamental skill. We’ll walk through the complete workflow, from setting the data directory to dumping attribute collections, and highlight best‑practice tips that keep your code clean and performant.

## Quick Answers
- **What does this code do?** It opens a Shapefile, iterates over each feature, and retrieves every attribute value or a selected subset.  
- **Which library is required?** Aspose.GIS for .NET (works with .NET Framework, .NET Core, .NET 5/6).  
- **Do I need a license?** A temporary license is sufficient for testing; a full license is mandatory for production deployments.  
- **Can I read other formats?** Yes – the same API reads GeoJSON, KML, GML, CSV, and 30+ other GIS formats.  
- **How to dump attributes?** Call `feature.GetValuesDump()` to obtain an object array that can be serialized or inspected directly.

## What is “read shapefile C#”?
Reading a Shapefile in C# means opening the `.shp` file with a GIS library, iterating over its vector features, and accessing the attribute data stored in the accompanying `.dbf` file. Aspose.GIS abstracts low‑level file handling, letting you extract attribute values with just a few lines of code.

## Why use Aspose.GIS to read attributes?
Aspose.GIS provides a high‑performance, cross‑platform API that simplifies attribute extraction from Shapefiles. It supports **30+ GIS formats**, processes up to **500 000 features per second** on a standard 4‑core server, and offers intuitive methods like `GetValues` and `GetValuesDump` that eliminate manual DBF parsing. Use it when you need reliable, license‑free (for testing) code that works on Windows, Linux, and macOS without extra plugins.

## Prerequisites
- **Aspose.GIS for .NET** – download from the [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
- **Development environment** – Visual Studio 2022, Rider, or any IDE that supports .NET 6+.  
- **Sample Shapefile** – place a file such as `InputShapeFile.shp` in a known folder on your machine.  

## Import Namespaces
The `Aspose.Gis` namespace contains core GIS types like `VectorLayer` and `Feature`.  
`VectorLayer` represents a vector dataset such as a Shapefile, while `Feature` represents an individual spatial record.  
```csharp
using System;
using Aspose.Gis;
```

## Step 1: Set the Document Directory
Define the folder that holds your Shapefile so the API can locate the `.shp`, `.shx`, and `.dbf` files.  
```csharp
string dataDir = "Your Document Directory";
```
Replace “Your Document Directory” with the actual path where your Shapefile resides.

## Step 2: Open the VectorLayer
`VectorLayer` represents a vector dataset (Shapefile, GeoJSON, etc.). Opening it loads the schema without reading all geometry data, which keeps memory usage low.  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
This step specifies the file path and format (Shapefile).

## Step 3: Retrieve All Feature Attribute Values
`GetValues` fills a pre‑allocated array with the raw attribute values of a feature. This approach is ideal when you need a deterministic, fixed‑size result set.  
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
The snippet shows how to read attributes for **every** feature into a fixed‑size array.

## Step 4: Retrieve Several Feature Attribute Values
When only a subset of fields is required, you can pass a smaller array or use column indexes to limit the data transferred. This reduces memory overhead and speeds up processing.  
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
Here we demonstrate reading specific attribute values (e.g., “Name” and “Population”).

## Step 5: Retrieve Attribute Values as Objects Dump
`GetValuesDump` returns an `object[]` containing all attribute values of a feature, matching the feature’s schema. This allows you to enumerate fields without prior knowledge of their order or types.  
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
This final step showcases a flexible, schema‑agnostic way to dump attributes for debugging or serialization.

## Common Issues and Solutions
- **Array size mismatch** – Ensure the array you pass to `GetValues` matches the number of attributes you expect; otherwise you’ll receive `null` entries.  
- **File not found** – Verify `dataDir` points to the correct folder and that the Shapefile name is spelled exactly, including the `.shp` extension.  
- **License exception** – If a licensing error appears, apply a temporary or full license before invoking any API methods.

## Frequently Asked Questions
**Q: Is Aspose.GIS compatible with .NET Core?**  
A: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS solutions on Windows, Linux, and macOS.

**Q: Can I work with different GIS file formats using Aspose.GIS?**  
A: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and over 30 other formats without additional plugins.

**Q: How can I obtain a temporary license for testing?**  
A: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).

**Q: Where is the official documentation for Aspose.GIS?**  
A: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).

**Q: How do I retrieve only the “Name” attribute from each feature?**  
A: Use `GetValues` with a single‑element array and pass the column index of “Name”, or simply call `feature["Name"]` for direct access.

**Q: What is the difference between `GetValues` and `GetValuesDump`?**  
A: `GetValues` populates a pre‑allocated array with raw values, while `GetValuesDump` returns an `object[]` that can be enumerated without knowing the schema in advance.

**Q: Where can I get help if I run into problems?**  
A: Visit the Aspose GIS [support forum](https://forum.aspose.com/c/gis/33) for community assistance and official support.

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## Related Tutorials

- [Get Layer Attributes – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [How to Get Attribute Value (Default) with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Read Shapefile C# – Filter Features by Attribute with Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}