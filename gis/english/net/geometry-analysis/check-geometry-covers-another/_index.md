---
title: Create LineString C# – Check Geometry Covers Another
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
description: Learn how to create LineString in C# using Aspose.GIS for .NET, add points to a LineString, and check if a geometry covers another.
weight: 15
url: /net/geometry-analysis/check-geometry-covers-another/
date: 2025-12-06
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Check Geometry Covers Another

## Introduction
Aspose.GIS for .NET is a powerful library that provides developers with tools to efficiently work with geographical data within their .NET applications. Whether you're building a mapping application, analyzing spatial data, or integrating geographical features into your software, Aspose.GIS offers a comprehensive set of functionalities to streamline your development process. In this tutorial you’ll learn **how to create LineString in C#**, add points to the line, and perform a **point on line check** using the `Covers` and `CoveredBy` methods.

## Quick Answers
- **What does “create LineString in C#” mean?** It means instantiating a `LineString` geometry object and populating it with coordinate points.  
- **Which method checks if a point lies on a line?** Use the `Covers` method on the `LineString` or `CoveredBy` on the `Point`.  
- **Do I need a license to run the sample?** A temporary license works for evaluation; a full license is required for production.  
- **Can this be used with .NET Core?** Yes, Aspose.GIS supports .NET Framework and .NET Core.  
- **How many points can I add to a LineString?** There is no hard limit; you can add as many points as needed for your spatial analysis.

## What is **create LineString C#**?
A `LineString` is a geometric shape consisting of an ordered list of points connected by straight line segments. In C# you create it by instantiating the `LineString` class from the `Aspose.Gis.Geometries` namespace and then **add points to the LineString** using the `AddPoint` method.

## Why use Aspose.GIS for a point on line check?
- **Precision** – Handles floating‑point calculations and spatial predicates accurately.  
- **Cross‑platform** – Works with .NET Framework, .NET Core, and .NET 5/6+.  
- **Rich API** – Provides a full suite of spatial relationship methods (`Covers`, `CoveredBy`, `Intersects`, etc.).  

## Prerequisites
Before diving into using Aspose.GIS for .NET, ensure that you have the following prerequisites set up:

### 1. Install Visual Studio
Ensure you have Visual Studio installed on your system. Aspose.GIS for .NET seamlessly integrates with Visual Studio, providing a smooth development experience.

### 2. Obtain Aspose.GIS for .NET
Download the Aspose.GIS for .NET library from the [website](https://releases.aspose.com/gis/net/). You can either download the library directly or use a package manager like NuGet to install it into your project.

### 3. Familiarity with .NET Framework
Basic knowledge of the .NET framework and C# programming language is essential to effectively utilize Aspose.GIS for .NET.

### 4. Access to Documentation and Support
Refer to the [documentation](https://reference.aspose.com/gis/net/) for detailed information on Aspose.GIS APIs and functionalities. In case you encounter any issues or have questions, utilize the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for assistance.

### 5. Optional: Temporary License
If you're exploring Aspose.GIS for .NET, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/) to evaluate the library's features.

## Import Namespaces
Before using Aspose.GIS for .NET in your project, you need to import the necessary namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Now, let's break down the example provided into multiple steps to understand how to **check if one geometry covers another** using Aspose.GIS for .NET.

## How to **create LineString C#** – Step‑by‑Step Guide

### Step 1: Create a LineString Object
```csharp
var line = new LineString();
```
Here, we instantiate a new `LineString` object, which represents a sequence of connected line segments in a two‑dimensional space.

### Step 2: **Add Points to LineString**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
We **add points to the LineString** using the `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming a simple diagonal line segment.

### Step 3: Create a Point Object
```csharp
var point = new Point(0, 0);
```
Instantiate a `Point` object representing a single point in a two‑dimensional space. Here, we create a point at coordinates (0, 0).

### Step 4: Perform a **point on line check** – Does the line cover the point?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Use the `Covers` method to check if the line covers the point. In this case, it returns `True` because the point (0, 0) lies exactly on the line.

### Step 5: Verify the reverse relationship – Is the point covered by the line?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Similarly, use the `CoveredBy` method to check if the point is covered by the line. Since the point (0, 0) lies on the line, it also returns `True`.

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `line.Covers(point)` returns `False` even though the point looks on the line | The point coordinates are not exactly the same due to floating‑point precision. | Use `Math.Round` on coordinates or employ a tolerance‑based check with `line.Distance(point) < epsilon`. |
| Missing `using Aspose.Gis.Geometries;` | Namespace not imported, causing compile errors. | Ensure the import statement is present (see the **Import Namespaces** section). |
| License exception at runtime | No valid license loaded for production. | Load a temporary or full license using `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Frequently Asked Questions

**Q: Can I use Aspose.GIS for .NET in my commercial projects?**  
A: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial projects after obtaining the appropriate license.

**Q: Is Aspose.GIS for .NET compatible with .NET Core?**  
A: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET Core environments.

**Q: Does Aspose.GIS for .NET support various GIS formats?**  
A: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including Shapefile, GeoJSON, KML, and more.

**Q: Can I contribute to the development of Aspose.GIS for .NET?**  
A: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external contributions are not accepted. However, you can provide feedback and suggestions to improve the library.

**Q: How often are updates released for Aspose.GIS for .NET?**  
A: Updates for Aspose.GIS for .NET are released regularly to introduce new features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/) for the latest releases.

## Conclusion
In conclusion, Aspose.GIS for .NET provides powerful tools for working with geographical data in .NET applications. By following the steps outlined above, you can efficiently **create LineString in C#**, **add points linestring**, and perform a **point on line check** to determine whether one geometry covers another. This capability enhances the spatial analysis features of your software and opens the door to more advanced GIS operations.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-06  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose