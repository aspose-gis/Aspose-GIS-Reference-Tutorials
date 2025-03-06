---
title: Create Polygon with Hole Geometry using Aspose.GIS
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
description: Learn how to create polygon with hole geometry using Aspose.GIS for .NET. Step-by-step tutorial with code examples.
weight: 13
url: /net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Polygon with Hole Geometry using Aspose.GIS

## Introduction
In this tutorial, we'll walk through the process of creating a polygon with a hole geometry using Aspose.GIS for .NET. Aspose.GIS is a powerful library that enables developers to work with geospatial data in their .NET applications. 
## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. Aspose.GIS for .NET Library: You can download it from [here](https://releases.aspose.com/gis/net/).
2. Development Environment: Ensure you have a development environment set up with Visual Studio or any other .NET IDE installed.
## Import Namespaces
Firstly, you need to import the necessary namespaces to work with Aspose.GIS functionalities. Here's how to do it:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Now, let's proceed to create a polygon with a hole geometry using Aspose.GIS for .NET.
## Step 1: Create Polygon Object
```csharp
Polygon polygon = new Polygon();
```
## Step 2: Define Exterior Ring
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Step 3: Define Interior Ring (Hole)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Step 4: Assign Exterior Ring and Add Interior Ring to Polygon
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Conclusion
Congratulations! You have successfully learned how to create a polygon with a hole geometry using Aspose.GIS for .NET. This knowledge will be beneficial for various geospatial applications where such geometries are essential.
## FAQ's
### 1. What is Aspose.GIS?
Aspose.GIS is a .NET library that enables developers to work with geospatial data, allowing them to create, read, and manipulate various geospatial file formats.
### 2. Can I use Aspose.GIS for commercial projects?
Yes, you can use Aspose.GIS for both personal and commercial projects by purchasing a license. Visit [here](https://purchase.aspose.com/buy) for more details.
### 3. Is there a free trial available for Aspose.GIS?
Yes, you can avail of a free trial of Aspose.GIS from [here](https://releases.aspose.com/).
### 4. Where can I find support for Aspose.GIS?
You can find support for Aspose.GIS on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).
### 5. How can I obtain a temporary license for Aspose.GIS?
You can obtain a temporary license for Aspose.GIS from [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
