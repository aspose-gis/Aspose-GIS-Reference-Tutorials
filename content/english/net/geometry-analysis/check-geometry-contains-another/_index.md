---
title: Check Geometry Contains Another
linktitle: Check Geometry Contains Another
second_title: Aspose.GIS .NET API
description: Explore Aspose.GIS for .NET a robust library for seamless geospatial data integration in your .NET applications.
type: docs
weight: 14
url: /net/geometry-analysis/check-geometry-contains-another/
---
## Introduction
Aspose.GIS for .NET is a powerful library that enables developers to work with geospatial data seamlessly within their .NET applications. Whether you're building a mapping application, performing geospatial analysis, or integrating location-based features into your software, Aspose.GIS simplifies the process by providing intuitive APIs and robust functionality.
## Prerequisites
Before diving into using Aspose.GIS for .NET, ensure you have the following prerequisites:
### 1. .NET Development Environment Setup
Ensure you have a working .NET development environment set up on your machine. This includes having the .NET SDK installed and configured properly.
### 2. Aspose.GIS Installation
Install Aspose.GIS for .NET by downloading the library from the release page [here](https://releases.aspose.com/gis/net/). Follow the installation instructions provided in the documentation [here](https://reference.aspose.com/gis/net/) to integrate Aspose.GIS into your project.
### 3. Basic Understanding of C#
Familiarize yourself with the C# programming language as Aspose.GIS for .NET is primarily used with C#.

## Import Namespaces
In your C# project, import the necessary namespaces to utilize Aspose.GIS functionalities:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Define Geometry Objects
First, define the geometry objects using Aspose.GIS classes:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## Step 2: Check Spatial Containment
Next, check if one geometry contains another:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // False
```
## Step 3: Define Another Geometry
Define another geometry object:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Step 4: Check Spatial Containment Again
Check if the newly defined geometry is contained within the first geometry:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // True
```
## Step 5: Equivalent Functionality
Understand that `a.SpatiallyContains(b)` is equivalent to `b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // True
```

## Conclusion
In conclusion, Aspose.GIS for .NET provides powerful tools for handling geospatial data in .NET applications. By following this guide and utilizing the provided example, you can efficiently perform spatial containment checks and leverage other geospatial functionalities within your projects.
## FAQ's
### Q1: Is Aspose.GIS compatible with .NET Core?
A: Yes, Aspose.GIS fully supports .NET Core, allowing you to develop geospatial applications across different platforms.
### Q2: Can I perform geospatial analysis using Aspose.GIS?
A: Absolutely, Aspose.GIS offers various functionalities for geospatial analysis, including spatial queries, distance calculations, and geometry manipulations.
### Q3: How frequently are updates released for Aspose.GIS?
A: Aspose.GIS regularly releases updates to improve performance, add new features, and address any reported issues. You can stay updated by visiting the release page.
### Q4: Is there a community forum for Aspose.GIS users?
A: Yes, you can join the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33) to connect with other users, ask questions, and share your experiences.
### Q5: Can I try Aspose.GIS before purchasing?
A: Certainly, you can explore Aspose.GIS by downloading the free trial from [here](https://releases.aspose.com/).
