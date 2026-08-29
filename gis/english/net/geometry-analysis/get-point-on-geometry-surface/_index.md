---
date: 2026-08-13
description: Learn how to check point inside polygon using Aspose.GIS for .NET, create
  polygon geometry, and get point on surface in C#. Step‑by‑step guide with full code
  example.
images:
- /net/geometry-analysis/get-point-on-geometry-surface/og-image.png
keywords:
- check point inside polygon
- how to test polygon
- Aspose.GIS geometry
- .NET spatial analysis
lastmod: 2026-08-13
linktitle: Check point inside polygon and get point on surface
og_description: Learn how to check point inside polygon and get point on surface using
  Aspise.GIS for .NET. Detailed C# example and best practices for spatial analysis.
og_image_alt: Screenshot of Aspose.GIS code checking point inside polygon in C#
og_title: Check point inside polygon – Aspose.GIS .NET guide
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to check point inside polygon using Aspose.GIS for .NET,
    create polygon geometry, and get point on surface in C#. Step‑by‑step guide with
    full code example.
  headline: Check point inside polygon and get point on surface
  type: TechArticle
- description: Learn how to check point inside polygon using Aspose.GIS for .NET,
    create polygon geometry, and get point on surface in C#. Step‑by‑step guide with
    full code example.
  name: Check point inside polygon and get point on surface
  steps:
  - name: create polygon geometry in C#
    text: First, we need to **create a polygon** geometry. We define the exterior
      ring of the polygon by specifying its vertices.
  - name: get point on surface
    text: The `GetPointOnSurface()` method returns a single interior point guaranteed
      to lie inside the polygon’s area. Next, we retrieve a point on the surface of
      the polygon using this method. This is the **get point on surface** step.
  - name: check point inside polygon
    text: The `SpatiallyContains()` method evaluates whether a geometry completely
      contains another geometry, returning true or false. We can verify whether the
      retrieved point lies inside the polygon using this method. This demonstrates
      **retrieving point on polygon** and then checking it.
  type: HowTo
- questions:
  - answer: It verifies whether a given coordinate lies within the boundaries of a
      polygon geometry.
    question: What does “check point inside polygon” mean?
  - answer: '`GetPointOnSurface()` returns a point guaranteed to be inside the polygon.'
    question: Which method returns a point on a polygon’s interior?
  - answer: A free trial works for evaluation; a full license is required for production.
    question: Do I need a license to run the example?
  - answer: .NET Framework, .NET Core, and .NET Standard are all compatible.
    question: Which .NET versions are supported?
  - answer: About 5‑10 minutes to copy, compile, and run.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- check point inside polygon
- Aspose.GIS
- .NET geometry
- C# spatial operations
title: Check point inside polygon and get point on surface
url: /net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Check point inside polygon and get point on surface

## Introduction
In this tutorial you'll learn **how to check point inside polygon** with Aspose.GIS for .NET and also see how to **get point on surface** of a geometry. We'll walk through creating a polygon geometry in C#, retrieving a point that lies on the polygon’s surface, and verifying that the point truly resides inside the polygon. By the end, you’ll have a ready‑to‑use snippet you can drop into any .NET geospatial application.

## Quick Answers
- **What does “check point inside polygon” mean?** It verifies whether a given coordinate lies within the boundaries of a polygon geometry.  
- **Which method returns a point on a polygon’s interior?** `GetPointOnSurface()` returns a point guaranteed to be inside the polygon.  
- **Do I need a license to run the example?** A free trial works for evaluation; a full license is required for production.  
- **Which .NET versions are supported?** .NET Framework, .NET Core, and .NET Standard are all compatible.  
- **How long does the implementation take?** About 5‑10 minutes to copy, compile, and run.

## What is “check point inside polygon”?
Checking a point inside a polygon determines whether a specific coordinate lies within the closed area defined by the polygon’s vertices. The operation returns true when the point is fully enclosed and false when it lies outside or on the boundary. This fundamental spatial test powers geofencing, location‑based analytics, and map‑driven validation scenarios.

## Why use Aspose.GIS for this task?
Aspose.GIS offers a fully managed .NET API that processes polygon operations up to 200 MB in memory‑efficient mode, supports over 50 coordinate reference systems, and runs on .NET Framework, .NET Core, and .NET Standard without native dependencies.  
`GetPointOnSurface()` returns a point guaranteed to lie inside the geometry’s interior.  
`SpatiallyContains()` determines whether one geometry completely contains another.  
The library’s chainable methods—such as `SpatiallyContains()` and `GetPointOnSurface()`—provide deterministic results and eliminate the need for external GIS engines.

## Prerequisites
Before we begin, make sure you have the following:

### Environment setup
1. Install Aspose.GIS for .NET: Download and install the Aspose.GIS for .NET library from the **Aspose.GIS for .NET download page**([here](https://releases.aspose.com/gis/net/)).  
2. Set up your development environment: Use Visual Studio, Rider, or any .NET‑compatible IDE you prefer.  
3. Basic knowledge of C#: You should be comfortable with classes, methods, and simple console‑app projects.  
4. Access to documentation: Keep the **Aspose.GIS documentation**([documentation](https://reference.aspose.com/gis/net/)) handy for reference throughout the tutorial.

## Import namespaces
Before we delve into the implementation, let's start by importing the necessary namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑step guide

### Step 1: create polygon geometry in C#
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

### Step 2: get point on surface
The `GetPointOnSurface()` method returns a single interior point guaranteed to lie inside the polygon’s area. Next, we retrieve a point on the surface of the polygon using this method. This is the **get point on surface** step.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

### Step 3: check point inside polygon
The `SpatiallyContains()` method evaluates whether a geometry completely contains another geometry, returning true or false. We can verify whether the retrieved point lies inside the polygon using this method. This demonstrates **retrieving point on polygon** and then checking it.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## How to test polygon containment in C#
You test polygon containment by creating the polygon geometry, calling `GetPointOnSurface()` to obtain an interior point, and then using `SpatiallyContains()` to verify the point is inside. This two‑step pattern works for any valid polygon and scales to large datasets when combined with lazy loading.

## Common issues and solutions
- **Empty polygon** – Ensure the exterior ring has at least three distinct vertices; otherwise `GetPointOnSurface()` may return an undefined point.  
- **Clockwise vs. counter‑clockwise** – The orientation of the ring does not affect the containment check, but keeping a consistent winding order helps with other spatial operations.  
- **Coordinate system** – The example uses a simple Cartesian plane; when working with real‑world coordinates, make sure the CRS (coordinate reference system) is correctly defined.

## Frequently asked questions

### FAQ's
#### Is Aspose.GIS compatible with other .NET frameworks?
Yes, Aspose.GIS supports various .NET frameworks, including .NET Framework, .NET Core, and .NET Standard.

#### Can I try Aspose.GIS before purchasing?
Yes, you can download a free trial of Aspose.GIS from the **Aspose.GIS free trial download page**([here](https://releases.aspose.com/)).

#### How can I get support for Aspose.GIS?
You can visit the **Aspose.GIS forum**([here](https://forum.aspose.com/c/gis/33)) to seek assistance and interact with other users and developers.

#### Does Aspose.GIS offer temporary licenses?
Yes, you can obtain temporary licenses for Aspose.GIS from the **temporary license page**([here](https://purchase.aspose.com/temporary-license/)).

#### Where can I purchase Aspose.GIS?
You can buy Aspose.GIS from the **Aspose.GIS purchase page**([here](https://purchase.aspose.com/buy)).

### Additional Q&A

**Q:** What is the best way to handle large polygon datasets?  
**A:** Load geometries lazily and reuse a single `GeometryFactory` instance to reduce memory overhead.

**Q:** Can I retrieve multiple points on the surface?  
**A:** `GetPointOnSurface()` returns a single interior point. To generate multiple interior points, you can use a random point generator within the polygon’s bounding box and test each with `SpatiallyContains()`.

**Q:** Is it possible to export the polygon to a shapefile after creation?  
**A:** Yes, Aspose.GIS provides `FeatureSet` and `ShapefileWriter` classes to write geometries to Shapefile format.

## Conclusion
In this tutorial, we've learned how to **check point inside polygon** using Aspose.GIS for .NET, obtain a **point on surface**, and verify its containment. With Aspose.GIS, handling geospatial data becomes efficient and straightforward, empowering you to build robust geospatial applications that scale from simple maps to enterprise‑grade spatial analytics.

---

**Last Updated:** 2026-08-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [How to Create Polygon Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [point inside polygon c# – Check Geometry Contains Another](/gis/net/geometry-analysis/check-geometry-contains-another/)
- [How to Compute Centroid of a Geometry with Aspose.GIS for .NET](/gis/net/geometry-analysis/get-geometry-centroid/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}