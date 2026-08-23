---
date: 2026-08-03
description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
  to a linestring, and perform a point on line check using the covers method.
images:
- /net/geometry-analysis/check-geometry-covers-another/og-image.png
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Create linestring c# – Check geometry covers another
og_description: Create linestring c# and verify point on line using Aspose.GIS covers
  method. Learn precise geometry checks for .NET applications. (150‑160 chars)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Create linestring c# – Check geometry covers another (50‑60 chars)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Create linestring c# – Check geometry covers another
url: /net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Check geometry covers another

## Introduction
In this tutorial you’ll learn **how to create linestring c#** using Aspose.GIS for .NET, add points to a linestring, and perform a reliable **point on line check** with the `Covers` and `CoveredBy` methods. Whether you’re building a mapping tool, performing spatial analytics, or simply need to verify geometric relationships, mastering these operations will give your application the precision it needs.

## Quick answers
- **What does “create linestring c#” mean?** It means instantiating a `LineString` geometry object and populating it with coordinate points.  
- **Which method checks if a point lies on a line?** Use the `Covers` method on the `LineString` or `CoveredBy` on the `Point`.  
- **Do I need a license to run the sample?** A temporary license works for evaluation; a full license is required for production.  
- **Can this be used with .NET Core?** Yes, Aspose.GIS supports .NET Framework and .NET Core.  
- **How many points can I add to a linestring?** There is no hard limit; you can add as many points as needed for your spatial analysis.

## What is create linestring c#?
A `LineString` is a geometric shape consisting of an ordered list of points connected by straight line segments. In C# you create it by instantiating the `LineString` class from the `Aspose.Gis.Geometries` namespace and then **add points to linestring** using the `AddPoint` method. This object serves as the foundation for any linear spatial analysis, such as route mapping or network tracing.

## Why use Aspose.GIS for a point on line check?
`Covers` is a spatial predicate method that returns true when the first geometry completely contains the second geometry.  
Aspose.GIS provides a deterministic, high‑precision implementation of spatial predicates. It supports 50+ input and output GIS formats, can handle multi‑hundred‑kilometer line networks without loading the entire dataset into memory, and runs on .NET Framework, .NET Core, and .NET 5/6+. Using its `Covers` method guarantees that floating‑point rounding errors are accounted for, delivering reliable point‑on‑line results even in demanding enterprise scenarios.

## Prerequisites
Before diving into using Aspose.GIS for .NET, ensure that you have the following prerequisites set up:

### 1. Install Visual Studio
Ensure you have Visual Studio installed on your system. Aspose.GIS for .NET seamlessly integrates with Visual Studio, providing a smooth development experience.

### 2. Obtain Aspose.GIS for .NET
Download the Aspose.GIS for .NET library from the [website](https://releases.aspose.com/gis/net/). You can either download the library directly or use a package manager like NuGet to install it into your project.

### 3. Familiarity with .NET Framework
Basic knowledge of the .NET framework and C# programming language is essential to effectively utilize Aspose.GIS for .NET.

### 4. Access to documentation and support
Refer to the [documentation](https://reference.aspose.com/gis/net/) for detailed information on Aspose.GIS APIs and functionalities. In case you encounter any issues or have questions, utilize the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for assistance.

### 5. Optional: temporary license
If you're exploring Aspose.GIS for .NET, you can obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/) to evaluate the library's features.

## Import namespaces
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

## How to create linestring c# – step‑by‑step guide
Load your project, import the required namespaces, and then follow the five concise steps below. In just a few lines of code you will have a `LineString` object, a `Point` object, and two boolean checks that tell you whether the line covers the point and whether the point is covered by the line.

### Step 1: create a linestring object
The `LineString` class represents a sequence of points connected by straight line segments in a two‑dimensional plane.  
```csharp
var line = new LineString();
```
Here, we instantiate a new `LineString` object, which represents a sequence of connected line segments in a two‑dimensional space.

### Step 2: add points to linestring
`AddPoint` appends a coordinate pair to the end of the `LineString` collection, preserving the order of insertion.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
We **add points to linestring** using the `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming a simple diagonal line segment.

### Step 3: create a point object
The `Point` class models a single location in a two‑dimensional coordinate system.  
```csharp
var point = new Point(0, 0);
```
Instantiate a `Point` object representing a single point in a two‑dimensional space. Here, we create a point at coordinates (0, 0).

### Step 4: perform a point on line check – does the line cover the point?
`Covers` determines whether the first geometry completely contains the second geometry, returning true only when every point of the second geometry lies inside the first.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Use the `Covers` method to check if the line covers the point. In this case, it returns `True` because the point (0, 0) lies exactly on the line.

### Step 5: verify the reverse relationship – is the point covered by the line?
`CoveredBy` is the inverse of `Covers`; it returns true when the invoking geometry is entirely inside the target geometry.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Similarly, use the `CoveredBy` method to check if the point is covered by the line. Since the point (0, 0) lies on the line, it also returns `True`.

## Common issues and solutions
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| `line.Covers(point)` returns `False` even though the point looks on the line | The point coordinates are not exactly the same due to floating‑point precision. | Use `Math.Round` on coordinates or employ a tolerance‑based check with `line.Distance(point) < epsilon`. |
| Missing `using Aspose.Gis.Geometries;` | Namespace not imported, causing compile errors. | Ensure the import statement is present (see the **Import namespaces** section). |
| License exception at runtime | No valid license loaded for production. | Load a temporary or full license using `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Frequently asked questions

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
By following the steps above, you now know how to **create linestring c#**, **add points to linestring**, and perform a reliable **point on line check** using the `Covers` and `CoveredBy` methods. This capability enhances the spatial analysis features of your software and opens the door to more advanced GIS operations such as route validation, network topology checks, and proximity queries.

---

**Last Updated:** 2026-08-03  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Learn How to Create LineString Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [How to Add Point to LineString and Convert Geometry to Editable Format with Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – Check Geometry Contains Another](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}