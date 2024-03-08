---
title: Check Geometries for Equality
linktitle: Check Geometries for Equality
second_title: Aspose.GIS .NET API
description: Learn how to use Aspose.GIS for .NET to check geometries for equality in your .NET applications with this comprehensive tutorial.
type: docs
weight: 10
url: /net/geometry-analysis/check-geometries-for-equality/
---
## Introduction
Aspose.GIS for .NET is a powerful library that enables developers to work with geospatial data efficiently in their .NET applications. Whether you're building mapping applications, spatial analysis tools, or integrating geospatial functionality into existing software, Aspose.GIS provides the tools you need to get the job done.
## Prerequisites
Before diving into using Aspose.GIS for .NET, ensure you have the following prerequisites in place:
### .NET Framework Installed
Ensure you have the .NET Framework installed on your system. You can download it from the Microsoft website.
### Aspose.GIS for .NET Library
Download and install the Aspose.GIS for .NET library from the [download page](https://releases.aspose.com/gis/net/). Follow the installation instructions provided in the documentation.
### Development Environment
Set up your preferred development environment, such as Visual Studio, for .NET development.

## Import Namespaces
In your .NET application, import the necessary namespaces to use Aspose.GIS functionality:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Define Geometries
First, define the geometries you want to compare. In this example, we have two geometries: `geometry1` and `geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Step 2: Check Geometries for Equality
Now, check whether the geometries are spatially equal using the `SpatiallyEquals` method provided by Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```
This will print `True` to the console since `geometry1` and `geometry2` are spatially equal.
## Step 3: Modify Geometry
Next, let's modify `geometry2` by adding a new point.
```csharp
geometry2.AddPoint(3, 3);
```
## Step 4: Recheck Equality
Now, recheck the equality of the geometries after the modification.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```
This time, the output will be `False` since the geometries are no longer spatially equal due to the modification made to `geometry2`.

## Conclusion
In conclusion, Aspose.GIS for .NET provides powerful tools for working with geospatial data in .NET applications. By following this step-by-step guide, you can easily check geometries for equality using Aspose.GIS methods.
## FAQ's
### Can I use Aspose.GIS for .NET with other .NET frameworks?
Yes, Aspose.GIS for .NET is compatible with various .NET frameworks, including .NET Core and .NET Standard.
### Is there a free trial available for Aspose.GIS for .NET?
Yes, you can download a free trial from the [releases page](https://releases.aspose.com/).
### Where can I find documentation for Aspose.GIS for .NET?
You can find detailed documentation on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
### How can I get support for Aspose.GIS for .NET?
You can get support from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
### Can I purchase a temporary license for Aspose.GIS for .NET?
Yes, you can purchase a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/).
