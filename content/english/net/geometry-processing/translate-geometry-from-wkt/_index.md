---
title: Translate Geometry from WKT using Aspose.GIS in .NET
linktitle: Translate Geometry from WKT
second_title: Aspose.GIS .NET API
description: Learn how to translate geometry from Well-Known Text using Aspose.GIS for .NET. A step-by-step tutorial for seamless integration.
type: docs
weight: 21
url: /net/geometry-processing/translate-geometry-from-wkt/
---
## Introduction
In this tutorial, we will delve into the process of translating geometry from Well-Known Text (WKT) using Aspose.GIS for .NET. Aspose.GIS is a powerful .NET API that allows developers to work with geospatial data effortlessly. Whether you're a seasoned developer or just starting with geospatial programming, this tutorial will guide you through the process step by step.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Aspose.GIS for .NET API: You can download it from [here](https://releases.aspose.com/gis/net/).
2. Basic understanding of C# programming language.

## Import Namespaces
First, let's import the necessary namespaces into our C# project:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Step 1: Create a LineString from WKT
The first step is to create a LineString object from the Well-Known Text representation:
```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```
## Step 2: Count the Points in LineString
Next, let's count the number of points in the LineString:
```csharp
Console.WriteLine(line.Count); // Output: 3
```

## Conclusion
In this tutorial, we explored how to translate geometry from Well-Known Text using Aspose.GIS for .NET. By following these simple steps, you can seamlessly integrate geospatial data processing into your .NET applications.
## FAQ's
### Can I use Aspose.GIS for .NET in my commercial projects?
Yes, you can. Aspose.GIS for .NET is licensed per developer, allowing you to use it in commercial projects without any restrictions.
### Does Aspose.GIS for .NET support other geometric formats besides WKT?
Yes, Aspose.GIS for .NET supports various geometric formats, including WKB, GeoJSON, and Shapefile.
### Is there a free trial available for Aspose.GIS for .NET?
Yes, you can get a free trial from [here](https://releases.aspose.com/).
### Where can I find documentation for Aspose.GIS for .NET?
You can find the documentation [here](https://reference.aspose.com/gis/net/).
### How can I get support for Aspose.GIS for .NET?
You can get support from the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33).
