---
title: Check Point Inside Polygon and Get Point on Surface
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
description: Learn how to check point inside polygon using Aspose.GIS for .NET. Step‑by‑step guide to get point on surface, create polygon C#, and retrieve point on polygon.
weight: 25
url: /net/geometry-analysis/get-point-on-geometry-surface/
date: 2025-12-09
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Check Point Inside Polygon and Get Point on Surface

## Introduction
In this tutorial you'll learn **how to check point inside polygon** with Aspose.GIS for .NET and also see how to **get point on surface** of a geometry. We'll walk through creating a polygon in C#, retrieving a point that lies on the polygon’s surface, and verifying that the point truly resides inside the polygon. By the end, you’ll have a ready‑to‑use snippet you can drop into any .NET geospatial application.

## Quick Answers
- **What does “check point inside polygon” mean?** It verifies whether a given coordinate lies within the boundaries of a polygon geometry.  
- **Which method returns a point on a polygon’s interior?** `GetPointOnSurface()` returns a point guaranteed to be inside the polygon.  
- **Do I need a license to run the example?** A free trial works for evaluation; a full license is required for production.  
- **Which .NET versions are supported?** .NET Framework, .NET Core, and .NET Standard are all compatible.  
- **How long does the implementation take?** About 5‑10 minutes to copy, compile, and run.

## Prerequisites
Before we begin, make sure you have the following:

### Environment Setup
1. Install Aspose.GIS for .NET: Download and install the Aspose.GIS for .NET library from [here](https://releases.aspose.com/gis/net/).  
2. Set Up Your Development Environment: Ensure you have a working development environment for .NET programming. If not, you can set up Visual Studio or any other .NET development environment of your choice.  
3. Basic Knowledge of C#: Familiarize yourself with C# programming language basics if you're not already acquainted.  
4. Access to Documentation: Keep the [documentation](https://reference.aspose.com/gis/net/) handy for reference throughout the tutorial.

## Import Namespaces
Before we delve into the implementation, let's start by importing the necessary namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Now that we have set up our environment and imported the required namespaces, let's break down the example into multiple steps to understand it better.

## How to Create Polygon C#  
First, we need to **create a polygon** geometry. We define the exterior ring of the polygon by specifying its vertices.

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

## How to Get Point on Surface  
Next, we retrieve a point on the surface of the polygon using the `GetPointOnSurface()` method. This is the **get point on surface** step.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## How to Check Point Inside Polygon  
We can verify whether the retrieved point lies inside the polygon using the `SpatiallyContains()` method. This demonstrates **retrieving point on polygon** and then checking it.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Common Issues and Solutions
- **Empty polygon** – Ensure the exterior ring has at least three distinct vertices; otherwise `GetPointOnSurface()` may return an undefined point.  
- **Clockwise vs. Counter‑clockwise** – The orientation of the ring does not affect the containment check, but keeping a consistent winding order helps with other spatial operations.  
- **Coordinate System** – The example uses a simple Cartesian plane; when working with real‑world coordinates, make sure the CRS (coordinate reference system) is correctly defined.

## Conclusion
In this tutorial, we've learned how to **check point inside polygon** using Aspose.GIS for .NET, obtain a **point on surface**, and verify its containment. With Aspose.GIS, handling geospatial data becomes efficient and straightforward, empowering developers to build robust geospatial applications.

## FAQ's
### Is Aspose.GIS compatible with other .NET frameworks?
Yes, Aspose.GIS supports various .NET frameworks, including .NET Framework, .NET Core, and .NET Standard.

### Can I try Aspose.GIS before purchasing?
Yes, you can download a free trial of Aspose.GIS from [here](https://releases.aspose.com/).

### How can I get support for Aspose.GIS?
You can visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) to seek assistance and interact with other users and developers.

### Does Aspose.GIS offer temporary licenses?
Yes, you can obtain temporary licenses for Aspose.GIS from [here](https://purchase.aspose.com/temporary-license/).

### Where can I purchase Aspose.GIS?
You can buy Aspose.GIS from the purchase page [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** What is the best way to handle large polygon datasets?  
**A:** Load geometries lazily and reuse a single `GeometryFactory` instance to reduce memory overhead.

**Q:** Can I retrieve multiple points on the surface?  
**A:** `GetPointOnSurface()` returns a single interior point. To generate multiple interior points, you can use a random point generator within the polygon’s bounding box and test each with `SpatiallyContains()`.

**Q:** Is it possible to export the polygon to a shapefile after creation?  
**A:** Yes, Aspose.GIS provides `FeatureSet` and `ShapefileWriter` classes to write geometries to Shapefile format.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---