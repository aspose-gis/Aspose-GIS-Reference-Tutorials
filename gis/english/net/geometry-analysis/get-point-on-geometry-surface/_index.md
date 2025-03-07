---
title: Get Point on Geometry Surface
linktitle: Get Point on Geometry Surface
second_title: Aspose.GIS .NET API
description: Learn how to work with geospatial data efficiently using Aspose.GIS for .NET. Step-by-step guide and FAQs included.
weight: 25
url: /net/geometry-analysis/get-point-on-geometry-surface/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Get Point on Geometry Surface

## Introduction
In this tutorial, we will explore how to use Aspose.GIS for .NET to work with geometries and retrieve points on their surfaces. Aspose.GIS is a powerful library that provides various functionalities for geospatial data processing, manipulation, and visualization in .NET applications.
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
## Step 1: Create a Polygon
First, we need to create a polygon geometry. We define the exterior ring of the polygon by specifying its vertices.
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
## Step 2: Get Point on Surface
Next, we retrieve a point on the surface of the polygon using the `GetPointOnSurface()` method.
```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```
## Step 3: Verify Point Inside Polygon
We can verify whether the retrieved point lies inside the polygon using the `SpatiallyContains()` method.
```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Conclusion
In this tutorial, we've learned how to use Aspose.GIS for .NET to obtain a point on the surface of a polygon geometry and verify its containment within the polygon. With Aspose.GIS, handling geospatial data becomes efficient and straightforward, empowering developers to build robust geospatial applications.
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

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
